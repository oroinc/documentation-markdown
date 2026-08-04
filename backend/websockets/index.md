<!-- meta: description = Websockets functionality and notification settings documentation for the backend developers -->

<a id="dev-guide-system-websockets"></a>

<a id="dev-guide-system-websockets-architecture"></a>

# WebSocket Notifications

**WebSockets** is a full-duplex communication protocol for real-time messaging between a server and clients through persistent connections.

WebSockets provide real-time notifications about server events or changes, so clients no longer need to repeatedly ask the server for new information. For example:

* Someone changes a document that another user is editing. A notification that someone is working on the document, or that the document has been modified, is immensely helpful.
* Real-time charts of stock prices or currency exchange rates on financial portals. This type of data must be accurate and timely for portal visitors, and refreshing the page manually can be exhausting.
* Real-time instant messaging on a website. Users must receive messages without refreshing the chat page.

In Oro applications, WebSocket communications use <a href="https://wamp-proto.org/" target="_blank">Web Application Message Protocol (WAMP)</a>, a WebSocket subprotocol for organizing communication between program components in applications with a loosely coupled architecture.

The main two parts of WAMP protocol are <a href="https://en.wikipedia.org/wiki/Remote_procedure_call" target="_blank">Remote Procedure Call</a> (RPC) mechanism and <a href="https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern" target="_blank">PubSub</a> messaging pattern.

**RPC** mechanism allows calling a function from a different code remotely via a WebSocket.

**PubSub** messaging pattern means that when publishers publish messages to topics (or “channels”), the broker distributes them to the clients subscribed to those topics.

The **WAMP** protocol therefore relies on a **WebSocket server** that acts as the message broker, and it lets application components **register topics** for messages, **publish messages** to topics, and **subscribe to topic** messages.

In Oro applications, <a href="https://github.com/oroinc/platform/tree/master/src/Oro/Bundle/SyncBundle/" target="_blank">OroSyncBundle</a> provides all WebSocket-related functionality. Because OroSyncBundle is
part of OroPlatform, the base for all Oro applications, the WebSocket functionality exists in every Oro
application.

#### NOTE
WebSocket functionality exists only in the Oro application admin UI which guarantees authentication of all clients who subscribe to the topic messages.

## Getting Started

You need to [Setup and Configure](configuration/index.md#dev-guide-system-websockets-setup-configuration) websocket functionality before you can use it in Oro applications.

Out-of-the-box, OroSyncBundle uses WebSocket connection for two purposes:

* [Content outdated notifications](recipes/content-outdating-notifications.md#dev-cookbook-system-websockets-content-outdating-notifications) — To provide flash notifications for the user informing about outdated content, if several users try to edit the same entity record simultaneously.
* [Maintenance mode notifications](recipes/maintenance-mode.md#dev-cookbook-system-websockets-maintenance-mode) — To send flash notifications to all application site visitors once a developer turns on the system maintenance mode by a console’s CLI tool.

To start using websocket messages for your custom functionality, refer to the following articles:

* [Create Your Own Topic for Publishing and Subscribing](recipes/create-topic-and-handler.md#dev-cookbook-system-websockets-create-topic-and-handler)
* [Publish Messages to Existing Topics](recipes/publish-to-topic.md#dev-cookbook-system-websockets-publish-to-topic)

<!-- Frontend -->
