<a id="dev-translation"></a>

# Content and User Interface Translation

There are three ways to translate content displayed in the Oro applications to a user. You can use:

* [Standard Symfony Translator]()
* [Translatable Doctrine Extension]()
* [LocalizedFallbackValue Entity from OroLocaleBundle]()

This topic explains when to use the three approaches and provides implementation examples.

## Standard Symfony Translator

| Pros                                                                                            | Cons                                                               |
|-------------------------------------------------------------------------------------------------|--------------------------------------------------------------------|
| Does not require additional implementation and can be used in Symfony framework out-of-the-box. | Cannot be applied to translate dynamic content in the application. |

The application you are developing is highly likely to contain some static content that is independent of any dynamic
application data, is always displayed in the same place, and never changes. Examples of such content are labels of field
forms, static text in the interface, flash messages, etc. Keep in mind that this translation approach is used only for static
content that does not impact any entity (entity field values).

To translate labels, use the Translation component, one of the main Symfony framework components.

Oro application adds the translation functionality on top of Symfony’s standard approach, which enables modification of
translations via UI.

To use this approach, add the translation file to the bundle: **Resources/translations/messages.en.yml**

```php
oro:
   translation:
       some_field:
           label: Localized value
```

Use the Symfony translator to translate a label in the twig template:
**Resources/views/Form/form.html.twig**

```php
{{ ‘oro.translation.some_field.label’|trans }}
```

or in the php code:

```php
namespace Oro\Bundle\AcmeBundle\Controller;

use Symfony\Contracts\Translation\TranslatorInterface;

class AcmeController
{
    private $translator;
    public function __constructor(TranslatorInterface $translator)
    {
        $this->translator = $translator;
    }

    public function viewAction(): array
    {
        return [
            'label' => $this->translator->trans('oro.translation.some_field.label')
        ];
    }
}
```

More information on how to use it is available in <a href="https://symfony.com/doc/5.4/translation.html" target="_blank">Symfony Documentation</a>.

## Translatable Doctrine Extension

| Pros                                                                                                                                                            | Cons                                                                                                                                                                                                                                           |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| * Dynamic content in the application can be easily translated.<br/>  \* The translatable fields have a value related to the actual language of the application. | > * The user must switch the current language to the required language in the system configuration to fill the fields with the required values.<br/>> * Translatable fields can have values only for some languages but not for Localizations. |

Dynamic content is another type of content used in Oro applications. What is displayed in the UI is based on data loaded from fixtures into the database and entered by users in the UI. As a rule, this data is based on dictionaries used in certain entities.

Examples of such data are the Country and Region fields used in the Address entity. The application has dictionaries for each of these entities with all available translations for all translatable fields of these entities (into all available languages). For instance, these fields must consider the language selected for the interface when users must be able to filter and sort data by Country and Region in a grid with addresses. In this case, use <a href="https://github.com/doctrine-extensions/DoctrineExtensions/blob/main/doc/translatable.md" target="_blank">Gedmo/Translatable</a>. Such fields are displayed in the UI in the selected language. All requests to the database will change for the translations grid to retrieve data based on the current locale.

Below is an example of an entity that must work with `Gedmo/Translatable` for the `name` field of this entity.

```php
namespace Oro\Bundle\AcmeBundle\Entity;

use Doctrine\ORM\Mapping as ORM;
use Gedmo\Mapping\Annotation as Gedmo;
use Gedmo\Translatable\Translatable;

/**
 * @ORM\Table("oro_acme_country")
 * @ORM\Entity()
 * @Gedmo\TranslationEntity(class="Oro\Bundle\AcmeBundle\Entity\CountryTranslation")
 */
class Country implements Translatable
{
    /**
     * @var string
     *
     * @ORM\Column(name="name", type="string", length=255)
     * @Gedmo\Translatable
     */
    private $name;

    /**
     * @var string
     *
     * @Gedmo\Locale
     */
    private $locale;

    /**
     * @param string $name
     */
    public function setName(string $name)
    {
        $this->name = $name;
    }

    /**
     * @return string
     */
    public function getName()
    {
        return $this->name;
    }

    public function setLocale(string $locale)
    {
        $this->locale = $locale;
    }

    /**
     * @return string
     */
    public function getLocale()
    {
        return $this->locale;
    }
}
```

Also, Gedmo/Translatable requires a dictionary with all translations for the original entity fields:

```php
namespace Oro\Bundle\AcmeBundle\Entity;

use Doctrine\ORM\Mapping as ORM;
use Gedmo\Translatable\Entity\MappedSuperclass\AbstractTranslation;

/**
 * @ORM\Table(name="oro_acme_country_trans")
 * @ORM\Entity()
 */
class CountryTranslation extends AbstractTranslation
{
    /**
     * @var string
     *
     * @ORM\Column(type="string", length=255)
     */
    private $content;
}
```

For the grid to have working translations for entities with Gedmo fields, add the HINT_TRANSLATABLE hint:
**Resources/config/oro/datagrids.yml**

```php
datagrids:
   acme-grid:
       source:
           type: orm
           query:
               ...
           hints:
               - HINT_TRANSLATABLE
```

Below is a simple example of a grid configuration which uses the hint: **Resources/config/oro/datagrids.yml**

```php
datagrids:
   acme-grid:
       source:
           type: orm
           query:
               select:
                   - country.id
                   - country.name
               from:
                   - { table: Oro\Bundle\AcmeBundle\Entity\Country, alias: country }
           hints:
               - HINT_TRANSLATABLE

       columns:
           name:
               label: Country Name

       sorters:
           columns:
               name:
                   data_name: country.name

       filters:
           columns:
               name:
                   type: string
                   data_name: country.name
```

In this case, the values in the name field are displayed in the required language, and filtering and sorting for the values happen in the selected language.

<a id="localizedfallbackvalue-entity-from-orolocalebundle"></a>

## LocalizedFallbackValue Entity from OroLocaleBundle

| Pros                                                                                                                                                                                                                     | Cons                                                                                                                                                                                                   |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| > * The translatable fields can be translated for each Localization available in the application.<br/>> * It is easy to provide values for the Localizations in the entity form without changing the actual UI language. | > * Translated values cannot be used in the datagrids for filtering and sorting out-of-the-box.<br/>> * Additional implementation is required to render translated values for the actual Localization. |

UI language is incorporated into the localization entity. You can have several localizations in the application with the
same interface language. However, data for various localizations may differ.
In addition, if the current localization is assigned a parent localization, then in cases when a field value does not
exist, it is taken from the parent. This allows for setting up a flexible translation tree via the UI.

To implement this approach, use the [LocalizedFallbackValue](../../bundles/platform/LocaleBundle/entities.md#bundle-docs-platform-locale-bundle-localization).

To use `LocalizedFallbackValue` for fields in the entity, make it extendable:

```php
namespace Oro\Bundle\AcmeBundle\Entity;

use Doctrine\ORM\Mapping as ORM;
use Oro\Bundle\AcmeBundle\Model\ExtendAcme;

/**
 * @ORM\Table(name="oro_acme")
 * @ORM\Entity()
 */
class Acme extends ExtendAcme
{
    /**
     * @ORM\ManyToMany(
     *      targetEntity="Oro\Bundle\LocaleBundle\Entity\LocalizedFallbackValue",
     *      cascade={"ALL"},
     *      orphanRemoval=true
     * )
     * @ORM\JoinTable(
     *      name="oro_acme_name",
     *      joinColumns={
     *          @ORM\JoinColumn(name="acme_id", referencedColumnName="id", onDelete="CASCADE")
     *      },
     *      inverseJoinColumns={
     *          @ORM\JoinColumn(name="localized_value_id", referencedColumnName="id", onDelete="CASCADE", unique=true)
     *      }
     * )
     */
    protected $names;
}
```

```php
namespace Oro\Bundle\AcmeBundle\Model;

use Oro\Bundle\LocaleBundle\Entity\Localization;
use Oro\Bundle\LocaleBundle\Entity\LocalizedFallbackValue;

/**
 * @method LocalizedFallbackValue getName(Localization $localization = null)
 * @method LocalizedFallbackValue getDefaultName()
 * @method void setDefaultName(string $value)
 */
class ExtendAcme
{
    public function __construct()
    {
    }
}
```

Enable `Oro\Bundle\LocaleBundle\DependencyInjection\Compiler\DefaultFallbackExtensionPass` for the entity and the field inside the bundle class:

```php
namespace Oro\Bundle\AcmeBundle;

use Oro\Bundle\LocaleBundle\DependencyInjection\Compiler\DefaultFallbackExtensionPass;
use Symfony\Component\DependencyInjection\ContainerBuilder;
use Symfony\Component\HttpKernel\Bundle\Bundle;

class OroAcmeBundle extends Bundle
{
    public function build(ContainerBuilder $container)
    {
        parent::build($container);

        $container->addCompilerPass(new DefaultFallbackExtensionPass([
           'Oro\Bundle\AcmeBundle\Entity\Acme' => [
               'name' => 'names'
           ]
       ]));
    }
}
```

As the result, a proxy class is generated in the application cache: `cache/prod/oro_entities/Extend/Entity/classes.php`.

```php
namespace Extend\Entity;

use Oro\Bundle\LocaleBundle\Entity\Localization;
use Oro\Bundle\LocaleBundle\Entity\LocalizedFallbackValue;

abstract class EX_OroAcmeBundle_Acme extends \Oro\Bundle\LocaleBundle\Model\ExtendFallback implements \Oro\Bundle\EntityExtendBundle\Entity\ExtendEntityInterface
{
  /**
   * @param Localization|null $localization
   * @return LocalizedFallbackValue|null
   */
   public function getName(\Oro\Bundle\LocaleBundle\Entity\Localization $localization = NULL)
   {
       return $this->getFallbackValue($this->names, $localization);
   }
}
```

To be able to provide translations in the UI, use the following example of the form type:

```php
namespace Oro\Bundle\AcmeBundle\Form\Type;

use Oro\Bundle\LocaleBundle\Form\Type\LocalizedFallbackValueCollectionType;
use Symfony\Component\Form\AbstractType;
use Symfony\Component\Form\FormBuilderInterface;

class AcmeType extends AbstractType
{
    /**
     * {@inheritdoc}
     */
    public function buildForm(FormBuilderInterface $builder, array $options)
    {
        $builder->add(
            'names',
            LocalizedFallbackValueCollectionType::class,
            ['label' => 'oro.acme.names.label']
        );
    }
}
```

To retrieve a name for the Localization, it is enough to use the getName() method.

**More Sources on Translations**

*Business User Documentation*

* [Localization and Translation Concept Guide](../../user/concept-guides/localization/index.md#concept-guide-localization-translation)
* [System Localizations and Translations](../../user/back-office/system/localization/index.md#sys-config-sysconfig-general-setup-localization)
  > * [Languages](../../user/back-office/system/localization/languages/index.md#localization-languages)
  > * [Translations](../../user/back-office/system/localization/translations/index.md#localization-translations)
  > * [Localizations](../../user/back-office/system/localization/localizations/index.md#localization-localizations)

*Media Library*

* <a href="https://academy.oroinc.com/media-library/how-to-setup-localization" target="_blank">How to Set up Localization, Translation, and Language</a>

*SlideShare Translation and Localization Slides*

* <a href="https://www.slideshare.net/YevhenShyshkin/data-localization-and-translation" target="_blank">Data Localization and Translation (Slideshare)</a>

<!-- Frontend -->
