<a id="user-guide-processes"></a>

# Configure Processes in the Back-Office

Some actions in the Oro application trigger other actions. This behavior is pre-defined at the background and can be modified in the course of the system integration.
For example, as soon as a new customer has been uploaded to the Oro application, an account and a record are automatically created for it, and if a new campaign has been created in a Dotdigital address book synchronized with a marketing list in Oro, a new email campaign record is automatically created in OroCRM/OroCommerce.

You can view and activate/deactivate the process in the Oro application UI.

## View Processes

To view the processes, navigate to **System > Processes** in the main menu.

The All Processes grid contains the following details:

> * **NAME** — Defines the process available in the system.
> * **RELATED ENTITY** — Entity which records are influenced by the process.
> * **EXECUTION ORDER** — Priority of the process execution. The smaller is the number, the higher is the priority. If several processes have been triggered simultaneously, the processes with a higher priority are executed first.
> * **ENABLED** — If set to *Yes*, the process will be executed.
> * **CREATED AT** — Date and time when the process was added to the system.
![The page of all processes run in the system](user/img/system/processes/all_processes.png)

From the grid, you can <i class="fa fa-eye fa-lg" aria-hidden="true"></i> view, <i class="fa fa-check fa-lg" aria-hidden="true"></i> activate or <i class="fa fa-times fa-lg" aria-hidden="true"></i> deactivate the process by clicking the corresponding icon.

On the process’s details page, you can see the basic process details (as in the grid) and the **Process Triggers**, i.e., in what case and with what delay after the event the process will be executed.

![The details page of a selected processes](user/img/system/processes/processes_details.png)

Here, you can <i class="fa fa-check fa-lg" aria-hidden="true"></i> Activate or <i class="fa fa-times fa-lg" aria-hidden="true"></i> Deactivate the process by clicking the necessary button.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
