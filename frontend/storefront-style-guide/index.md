<!-- meta: description = Instructions on creating and customizing OroPlatform-based application UI using Figma -->

<a id="frontend-storefront-design"></a>

<a id="frontend-storefront-style-guide"></a>

<a id="storefront-style-guide-quick-start"></a>

<a id="frontend-design-customization"></a>

# Storefront Design: Style Guide

OroCommerce 6.1 LTS has introduced brand new Golden Carbon and Refreshing Teal storefront themes that give a modern and fresh look. These themes include a fully editable homepage with configurable content templates and widgets, an improved and retina-optimized slider, product segment widgets and more. The new themes have been designed to improve accessibility and internationalization, making navigation, search, and checkout experiences better, while also ensuring optimal performance.

We understand that every brand has its own unique corporate identity that sets it apart in the market. While OroCommerce offers options to [customize the look and feel of the new themes in the back-office](../../user/back-office/system/theme-configuration/index.md#back-office-theme-configuration), we have compiled this style guide to assist you in customizing the current Golden Carbon theme interface to align it with your corporate identity.

![Storefront designs](img/frontend/storefront-design/Storefront-Style-Guide.png)

## Download Figma Design Files

To help you create your custom Storefront theme design, we compiled two files, the <a href="https://static.oroinc.com/doc/Storefront_Style_Guide-6.1-Public_Files-November_2025.fig" target="_blank">Style Guide</a> and <a href="https://static.oroinc.com/doc/Design_Mockups_6.1-November_2025.fig" target="_blank">Design Mockups</a>. To access these files, you need a <a href="https://www.figma.com/signup" target="_blank">Figma account</a> with a Professional, Organization, or Enterprise plan. This will allow you to connect the library file to your working design files.

#### NOTE
These Figma files use the new <a href="https://github.com/oroinc/storefront-themes/" target="_blank">Golden Carbon theme</a>, which is the recommended and most actively maintained theme for OroCommerce version 6.1.

The *Refreshing Teal* theme is still available in version 6.1 and is pre-installed by default. To sew how *Refreshing Teal* looks on the storefront, please refer to the version 6.0 Figma files: <a href="https://static.oroinc.com/doc/storefront-style-guide-6.0.fig" target="_blank">Style Guide 6.0</a> and <a href="https://static.oroinc.com/doc/design-mockups-6.0.fig" target="_blank">Design Mockups 6.0</a>.

This <a href="https://static.oroinc.com/doc/Storefront_Style_Guide-6.1-Public_Files-November_2025.fig" target="_blank">Style Guide</a> contains:

* **Styles** with instructions on how to use them (colors, shadows and typography). You can change the styles to fit your company identity, publish library updates to your design work Figma file, and these styles will automatically be updated in every instance on every page that uses them.
* **Ready-to-go UI components**, from the simple ones (e.g., <a href="https://github.com/feathericons/feather" target="_blank">Feather Icons</a>, buttons) to the compound ones (e.g., product cards) that are built with auto layouts and according to [the atomic approach](#frontend-design-atomic-approach).

<a href="https://static.oroinc.com/doc/Design_Mockups_6.1-November_2025.fig" target="_blank">Design Mockups</a> encompass all primary screens and page components, allowing for customizable design alterations.

![Color palette in style guide](img/frontend/storefront-design/Colors.png)

### Customize the Library

Once you have downloaded the <a href="https://static.oroinc.com/doc/Storefront_Style_Guide-6.1-Public_Files-November_2025.fig" target="_blank">Style Guide</a> (Storefront Style Guide 6.1) and <a href="https://static.oroinc.com/doc/Design_Mockups_6.1-November_2025.fig" target="_blank">Design Mockups</a> (Design Mockups 6.1) files, you can start customizing and use the provided Figma library:

1. Import the downloaded Figma files into your Figma project.

#### NOTE
Please remember that using a separate library file, which is our suggested approach, is only available if your team in Figma is on Professional, Organization or Enterprise plan.

1. In the newly imported library file (Storefront Style Guide 6.1), open the Assets tab in the left panel and click on the book icon.
2. Find your newly imported library file name and click **Publish**; click Publish again in the window with styles.

![Illustration of the Figma UI with options to Publish the library file](img/frontend/storefront-design/Customize-Library.png)
1. When your library file is successfully published, make sure it does not contain styles or elements from any missing libraries. For this, open the Assets tab in the left panel and click on the book icon again. See if under the *Libraries available in this file* it says *Includes 1 missing library*. If it does, click the chevron right > with the *Choose library* dropdown to select your newly imported library file’s name and click **Swap Library**. The *Swap default styles in instances* option should be checked.
2. Open your newly imported work file (Design Mockups 6.1). In the Assets tab, click on the book icon. Under the *Libraries available in this file* find *Includes 1 missing library* (the source library which your Storefront Style Guide 6.1 file is an exact duplicate of), click the chevron right > with the *Choose library* dropdown to select your newly imported library file’s name and click **Swap Library**. The *Swap default styles in instances* should be checked. Swapping may take some time.
3. While still in your work file, open the Assets tab and click on the book icon again. Make sure your newly imported library is marked as **Added**, and that the file does not use elements or styles from any other libraries.
4. You can now customize the library styles and components.

For the development spec of a certain component, please use the Dev Mode.

### Apply Changes

Once you have finished customizing the style guide and components library, please apply the changes to your work Figma file (the file with the design mockups) where this library has been added:

1. Open the Assets tab in the left panel of this file (library) and click on the book icon.
2. Find the current file (Storefront Style Guide 6.1), click **Publish changes** and then **Publish**.
3. Open your work Figma file. If this library is toggled on in your file, click **Review unpublished changes** (the book icon in the top right corner of the Figma toolbar) and then **Update all**.

![Illustration of the Figma UI with options to Update the file](img/frontend/storefront-design/Apply-Changes.png)

For more in-depth customization of the theme design, such as changing element positions or page layouts, navigate through each page individually in your work file and make the changes there.

<a id="storefront-style-guide-tips-and-tricks"></a>

## Recommended Figma Plugins

We have curated a list of plugins aimed at improving your workflow and productivity within the Figma platform.

* **A11y - Color Contrast Checker** — this plugin checks the color contrast ratio of all visible text in a frame, and it provides feedback on whether it meets WCAG’s AA and/or AAA level compliance. It also provides color sliders that allow users to adjust the colors and understand how the corresponding contrast ratio changes in real-time.
* **Batch Styler** — batch change color styles (hue, saturation, lightness, alpha, hex), typography styles (font family, font weight, line height, letter spacing), batch delete or rename styles.
* **Design System Organizer**  — bulk swap instances and styles between masters with the same name. Copy styles between files. Manage pathnames like “toolbar/nav/back” using a folder-like interface.
* **Style Organizer** — merge and link all color & text styles in the page:
  - overall usage assessment
  - group elements with the same appearance together
  - merge and link to the selected style
  - select all elements with the style
  - make all possible fixes automatically with a single click.
* **Instance Finder** — find all Instances of a Component used in your file.
* **Max Line Length** — a plugin that counts the maximum number of characters across all lines in a text box.
* **Select Layers** — select layers by name, type or any property (hidden/parent/similar, etc.).
* **Iconify** — import Material Design Icons, FontAwesome, Jam Icons, EmojiOne, Twitter Emoji and many other icons (more than 100 icon sets containing over 100,000 icons) to Figma document as vector shapes.
* **Content Reel** — browse or search content to find published collections of text strings, images, and icons.

<a id="frontend-design-atomic-approach"></a>

## Atomic Design Approach

The structure of the OroCommerce UI is based on the Atomic Design approach, which means that all functional elements consist of:

* [Atoms](#principles-atoms) - the smallest elements that cannot be separated and that serve as elementary blocks of the interface (colors, typography, buttons, icons, etc.)
* [Molecules](#principles-molecules) - groups of atoms that form relatively simple functional interface elements (pop-up, button with dropdown, navigation menu)
* [Organisms](#principles-organisms) - groups of molecules that form the relatively complex parts of the interface (header, footer, sidebar)
* [Templates](#principles-templates) - help place components in the layout and demonstrate the content structure underlying the design
* [Pages](#principles-pages) - help apply real content to templates displaying the final interface

![Principle of the atomic design approach](img/frontend/storefront-design/Principles.png)

<a id="principles-atoms"></a>

### Atoms

Atoms are fundamental building blocks of a user interface. They are comprised of basic HTML elements such as buttons, inputs, headers, etc. and cannot be separated without losing their functionality. Each atom has its own unique properties.

For instance, a button atom has properties such as background color, form, title color, size, and font. By modifying these properties, you can alter the overall style of the interface where the atom is utilized.

Atoms provide a foundation for all basic styles. Therefore, they can serve as a valuable reference material while designing and implementing a user interface in OroCommerce.

![Illustration of the atom properties](img/frontend/storefront-design/Atoms.png)

<a id="principles-molecules"></a>

### Molecules

Grouping atoms together forms molecules, which act as functional elements within an interface. For example, an input combined with two buttons becomes a form for editing the title of a shopping list. The input allows for the entry of a name, while the buttons provide options to accept or reject the form.

Utilizing molecules helps ensure the interface remains consistent and intuitive for users.

![Illustration of the molecules properties](img/frontend/storefront-design/Molecules.png)

<a id="principles-organisms"></a>

### Organisms

Organisms are relatively complex components of a user interface. They consist of groups of molecules, atoms, or even other organisms. These organisms form distinct parts of the interface.

Taking the OroCommerce Storefront as an example, the header comprises various molecules and atoms, such as:

- Login links and contact information (atoms)
- Logo (atom)
- Search field (a molecule that includes an input field atom and a search icon)
- Navigation menu (a molecule made up of menu item atoms), etc.

An organism is a self-contained, isolated interface element that can function independently.

![Illustration of the organism properties](img/frontend/storefront-design/Organisms.png)

<a id="principles-templates"></a>

### Templates

Templates are objects that define the layout of a page and provide a basic structure for the content. They show how components interact with each other and how the page should behave. Templates deal with the structure and logic of the page, covering all necessary UX cases where the actual content is not important.

Building on the previous example, the “header” component can be applied to the home page template.

![Illustration of the templates](img/frontend/storefront-design/Templates.png)

<a id="principles-pages"></a>

### Pages

Pages are templates that demonstrate how a user interface with actual content should appear. They represent the final stage of atomic design and showcase the version of the interface that is available to end-users. This is where you can see how all the individual components come together to form an attractive and functional user interface.

![Illustration of the page templates](img/frontend/storefront-design/Pages.png)

<a id="frontend-responsive-approach"></a>

## Responsive Approach

OroCommerce uses responsive web design, an approach that ensures web pages display correctly on various devices and screen sizes. To achieve usability and satisfaction, content, design, and performance must be consistent across all devices.

Breakpoints refer to the points at which the interface adjusts based on the display resolution. To successfully implement the theme design, designers must provide interface designs for the following horizontal resolutions:

* 360px - mobile device
* 768px - tablet
* 1280px - small desktop (optional)
* 1920px - large desktop

![Illustration of the responsive web design approach](img/frontend/storefront-design/Responsive-Approach.png)
<!-- Frontend -->

#### BUSINESS TIP
## Business Tip

How can your manufacturing company prepare for <a href="https://oroinc.com/b2b-ecommerce/blog/digital-transformation-in-manufacturing/" target="_blank">digitalization in manufacturing</a>? In our guide, we share business cases and best practices on succeeding in manufacturing digitization.
