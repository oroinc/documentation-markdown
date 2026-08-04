<a id="bundle-docs-platform-action-bundle-glossary"></a>

# Operations (Actions) Glossary

* [Buttons](buttons.md#bundle-docs-platform-action-bundle-buttons) are a user interface component that delivers custom actions for user interaction. Through a specific <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/ActionBundle/Extension/ButtonProviderExtensionInterface.php" target="_blank">ButtonsProviderExtension</a> together with <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/ActionBundle/Button/ButtonInterface.php" target="_blank">Buttons</a> matched by a context, they surface these actions (operations, for example) to the UI in the proper context.
* [Operation](index.md#bundle-docs-platform-action-bundle-operations) are configured user interaction elements (buttons, links or even further: forms, pages) with customized execution logic. One of the main components is ActionBundle. It handles the specific operation logic, how and when a UI element is displayed, the reaction it provides, and how to aggregate the data retrieved from a user (usually through a form) into execution unit values before launching the configured *Actions*.

The operation definition contains the most important information, such as operation related entity classes (‘AcmeBundleDemoBundleEntityMyEntity’), or routes (‘acme_demo_myentity_view’), or datagrids (‘acme-demo-grid’).

The operation can be enabled or disabled. Its other fields hold its name, extended options, and order of displayed buttons. For more options, refer to [Operation Configuration](index.md#bundle-docs-platform-action-bundle-operations).

* [Action Group](action-groups.md#bundle-docs-platform-action-bundle-action-groups) is a set of backend actions that implement complex business logic, grouped together under named configuration nodes. It is another key component in ActionBundle: a named group of actions with entry parameters (required or optional, typed or not) and conditions.

  You can use *Action groups* not only from an operation but also within workflow processes and in any part of the OroPlatform configuration nodes that understand [Actions](actions-conditions.md#bundle-docs-platform-action-bundle-action-component).

A special @run_action_group action runs a group of actions as a single one. (For more information, refer to [\*ActionGroup\* configuration](action-groups.md#bundle-docs-platform-action-bundle-action-groups) and the @run_action_group action.)

* [Condition](actions-conditions.md#bundle-docs-platform-action-bundle-conditions) - defines whether *Operation* or *ActionGroup* is allowed. Conditions use <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Component/ConfigExpression/README.md" target="_blank">ConfigExpression</a> syntax and can be nested within each other.
* [Actions](actions-conditions.md#bundle-docs-platform-action-bundle-action-component) - simple functional blocks (described in Action Component). You can use them in *ActionGroups* or *Operations* to implement the preparation logic before *conditions*, to retrieve rendering data, and to initialize and execute the logic afterward.
  * *Operations* contain the following *actions*: **Preactions** (preactions), the **Form Init** actions (form_init), and **Actions** themselves with the functions of Action Component. The difference is that preactions run before the operation button renders, while the form_init actions run before the form displays. Actions can perform any operations with data in their context (called Action Data) or other entities.
  * **Definition** — part of *Operation* or *ActionGroup* that contains the configuration of the component itself and describes its behavior.
* **Attribute** — an entity that represents a value (mostly in *Operation*) and renders a field value in a step of a form. The attribute knows about its type (string, object, entity, etc.) and additional options. It also contains a name and label as additional parameters.

<!-- Frontend -->
