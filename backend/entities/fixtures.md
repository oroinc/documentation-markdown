<a id="backend-entities-fixtures"></a>

# Fixtures

## Data Fixtures

Symfony loads data using data fixtures, which run every time you execute the doctrine:fixtures:load command.

To avoid loading the same fixture several times, use **oro:migration:data:load**. This command guarantees that each data fixture is loaded only once.

This command supports two types of migration files: main data fixtures and demo data fixtures. During installation, you can choose whether to load demo data.

Place data fixtures for this command in either the Migrations/Data/ORM or Migrations/Data/Demo/ORM directory. Each fixture must implement the `Doctrine\Common\DataFixtures\FixtureInterface` interface.

To change the fixture order, use the standard Doctrine ordering or dependency functionality. For more information about fixture ordering, see the <a href="https://github.com/doctrine/data-fixtures#fixture-ordering" target="_blank">doctrine data fixtures manual</a>.

## Versioned Fixtures

Some fixtures need to run repeatedly. For example, a fixture that uploads country data: normally, each time you add a new list of countries, you must create a new data fixture to upload it. Versioned data fixtures let you avoid this.

To make a fixture versioned, implement <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/MigrationBundle/Fixture/VersionedFixtureInterface.php" target="_blank">VersionedFixtureInterface</a> and the getVersion method that returns a version of the fixture data.

Example:

*src/Acme/Bundle/DemoBundle/Migrations/Data/ORM/LoadFavoritesData.php*
```php
<?php

namespace Acme\Bundle\DemoBundle\Migrations\Data\ORM;

use Acme\Bundle\DemoBundle\Entity\Favorite;
use Doctrine\Common\DataFixtures\AbstractFixture;
use Doctrine\Persistence\ObjectManager;
use Oro\Bundle\MigrationBundle\Fixture\VersionedFixtureInterface;
use Oro\Bundle\OrganizationBundle\Entity\Organization;

/**
 * Load favorites data 1.0.
 */
class LoadFavoritesData extends AbstractFixture implements VersionedFixtureInterface
{
    #[\Override]
    public function getVersion(): string
    {
        return '1.0';
    }

    #[\Override]
    public function load(ObjectManager $manager)
    {
        $organization = $manager->getRepository(Organization::class)->getFirst();

        $newFavorite = new Favorite();
        $newFavorite->setName('First favorite');
        $newFavorite->setValue('First favorite value');
        $newFavorite->setViewCount(14);
        $newFavorite->setOrganization($organization);
        $manager->persist($newFavorite);

        $manager->flush();
    }
}
```

In this example, the fixture will be loaded, and version 1.0 will be saved as its current loaded version.

To load this fixture again, it must return a version greater than 1.0, for example, 1.0.1 or 1.1. The version number must be a PHP-standardized version number string. For more information about PHP-standardized version number strings, see the <a href="http://php.net/manual/en/function.version-compare.php" target="_blank">PHP manual</a>.

If the fixture needs to know the last loaded version, implement <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/MigrationBundle/Fixture/LoadedFixtureVersionAwareInterface.php" target="_blank">LoadedFixtureVersionAwareInterface</a> and the setLoadedVersion method:

*src/Acme/Bundle/DemoBundle/Migrations/Data/ORM/LoadVersionedFavoriteData.php*
```php
<?php

namespace Acme\Bundle\DemoBundle\Migrations\Data\ORM;

use Acme\Bundle\DemoBundle\Entity\Favorite;
use Doctrine\Common\DataFixtures\AbstractFixture;
use Doctrine\Persistence\ObjectManager;
use Oro\Bundle\MigrationBundle\Fixture\LoadedFixtureVersionAwareInterface;
use Oro\Bundle\MigrationBundle\Fixture\VersionedFixtureInterface;
use Oro\Bundle\OrganizationBundle\Entity\Organization;

/**
 * Load versioned favorites data.
 */
class LoadVersionedFavoriteData extends AbstractFixture implements
    VersionedFixtureInterface,
    LoadedFixtureVersionAwareInterface
{
    #[\Override]
    public function getVersion(): string
    {
        return '2.0';
    }

    #[\Override]
    public function setLoadedVersion($version = null): void
    {
    }

    #[\Override]
    public function load(ObjectManager $manager): void
    {
        $newFavorite = new Favorite();
        $newFavorite->setName('Last favorite');
        $newFavorite->setValue('Last favorite value');
        $newFavorite->setViewCount(18);
        $newFavorite->setOrganization($manager->getRepository(Organization::class)->getFirst());
        $manager->persist($newFavorite);
        $manager->flush();
    }
}
```

## Rename Fixtures

When refactoring, you may need to change the fixture namespace or class name.

To prevent the fixture from loading again, it must implement <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/MigrationBundle/Fixture/RenamedFixtureInterface.php" target="_blank">RenamedFixtureInterface</a> and the getPreviousClassNames method, which returns a list of all previous fully specified class names.

Example:

*src/Acme/Bundle/DemoBundle/Migrations/Data/ORM/LoadRenamedFavoritesData.php*
```php
<?php

namespace Acme\Bundle\DemoBundle\Migrations\Data\ORM;

use Acme\Bundle\DemoBundle\Entity\Favorite;
use Doctrine\Common\DataFixtures\AbstractFixture;
use Doctrine\Persistence\ObjectManager;
use Oro\Bundle\MigrationBundle\Fixture\RenamedFixtureInterface;
use Oro\Bundle\OrganizationBundle\Entity\Organization;

/**
 * Load renamed favorites data.
 */
class LoadRenamedFavoritesData extends AbstractFixture implements RenamedFixtureInterface
{
    #[\Override]
    public function load(ObjectManager $manager)
    {
        $organization = $manager->getRepository(Organization::class)->getFirst();

        $newFavorite = new Favorite();
        $newFavorite->setName('Second favorite');
        $newFavorite->setValue('Second favorite value');
        $newFavorite->setViewCount(5);
        $newFavorite->setOrganization($organization);
        $manager->persist($newFavorite);

        $manager->flush();
    }

    #[\Override]
    public function getPreviousClassNames(): array
    {
        return [
            'Acme\Bundle\DemoBundle\Migrations\Data\ORM\LoadFavoritesData'
        ];
    }
}
```

<!-- Frontend -->
