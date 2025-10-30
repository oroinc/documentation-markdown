<a id="user-guide-channels"></a>

<a id="user-guide-channel-guide-type"></a>

<a id="user-guide-channel-guide-entities"></a>

<a id="user-guide-channel-guide-create"></a>

# Configure Channels in the Back-Office

Today, successful businesses usually have more than one sales website. These may be different online stores, business-to-business enterprises, or business-to-customer outlets. Moreover, different customers and sales-related data can be received from various survey-campaigns or memberships in clubs, funds, charity events, etc. Gaining a full understanding of all the information you receive from each of these sources, along with all the individual customer information you collect from various other sources, becomes crucial. With channels, you can do both with minimum effort.

Each channel record represents one source of customer-related data.

Oro Community Edition has two types of channels: Web (built for online stores) and Sales (built for business-to-business activities). Enterprise clients can add more types of channels during system integration.

There is no limit to the number of channel records that can be defined for a single application instance. You can choose what kind of customer-related information to collect from each channel, as described below.

## Create a Channel Record

To create a channel:

1. Navigate to **System > Channels** in the main menu.
2. Click **Create Channel** on the top right.
3. In the **General** section, specify the following channel details:
   * **Name** — A meaningful name used to refer to the channel in the system.
   * **Channel Type** — A type that defines a set of default rules and settings used for the channel.

   #### IMPORTANT
   Extending your Oro application with new channel types is a proven practice, and it can be customized subject to your specific needs and goals.

   The information collected from a channel is represented by the [entities](../entities/index.md#doc-entities) assigned to the channel and their related entities.
4. In the **Entities** section, select the required entity from the list and add it to the channel to collect the necessary data.
5. Click **Add**.

   The customer entity is added to the entity list automatically, subject to the selected channel type:
   * For Sales Channel — Business Customer
   * For Custom Channel — Customer Identity

   Other entities are added to channels of a specific type by default. However, they are optional and can be removed.

   To delete an entity, click <i class="fas fa-trash-alt" aria-hidden="true"></i> **Delete**. The action removes the entity from the channel’s list, but not from the system.
6. Click **Save and Close** to save the channel.

## Manage Channels

From the channels grid, you can <i class="fa fa-eye fa-lg" aria-hidden="true"></i> view, <i class="fa fa-edit fa-lg" aria-hidden="true"></i> edit, or <i class="fas fa-trash-alt" aria-hidden="true"></i> delete the selected channel by hovering over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the item and clicking the required button.

#### CAUTION
Once a channel is deleted, the associated data is removed as well.

![The actions available for channels from the grid](user/img/system/channels/channels_edit.png)

From the channel’s details page, you can edit the channel or view and edit the assigned entities.

#### NOTE
Note that you will receive an error message if you do not have the necessary permissions to edit entities.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
