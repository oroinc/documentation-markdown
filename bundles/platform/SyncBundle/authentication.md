# Authentication

All connections to socket server are protected with Sync authentication tickets.

Before connecting, the client should receive the connection ticket and pass it as part of the connection URL as a ticket query parameter.

For the frontend clients, the authentication ticket can be received by calling the POST request to oro_sync_ticket route. A response
of this request is a JSON object with the ticket field that contains a one-time authentication ticket.

For backend clients, the authentication ticket can be received by calling the generateTicket method of the <a href="https://github.com/oroinc/platform/blob/master/src/Oro/Bundle/SyncBundle/Authentication/Ticket/TicketProvider.php" target="_blank">oro_sync.authentication.ticket_provider</a> service.

All tickets have the default limited lifetime of 300 seconds.

When authentication is successful, the client is able to subscribe and send new messages to topics.

<!-- Frontend -->
