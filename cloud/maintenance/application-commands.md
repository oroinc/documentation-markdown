<a id="orocloud-application-commands"></a>

#### IMPORTANT
You are viewing the upcoming documentation for OroCloud, scheduled for release later in 2025. For accurate and up-to-date information, please refer only to the documentation of <a href="https://doc.oroinc.com/cloud/" target="_blank">the latest LTS version</a>.

# Application Commands

## Application Commands

### Run Console

#### NOTE
Any cloud `app:console` command has a default timeout of **1 hour** and a memory limit of **2 GB**. If you need to run a command that exceeds these parameters, please contact our support team.

Run application commands via orocloud-cli app:console, for example:

```none
orocloud-cli app:console oro:user:list
orocloud-cli app:console oro:search:reindex
```

To pass a command that contains arguments or options, wrap the command in quotes.

```none
orocloud-cli app:console "oro:user:list --all"
orocloud-cli app:console 'oro:search:reindex --scheduled Oro\Bundle\UserBundle\Entity\User'
```

Spaces and backslashes must be escaped with  `\`.

```none
orocloud-cli app:console "oro:user:list --roles=Sale\ Manager"
orocloud-cli app:console "oro:user:list --roles='Sale Manager'"
orocloud-cli app:console "oro:user:list --roles=\"Sale Manager\""
orocloud-cli app:console 'oro:user:list --roles=Sale\ Manager'
orocloud-cli app:console 'oro:user:list --roles="Sale Manager"'
orocloud-cli app:console 'oro:search:reindex Oro\Bundle\UserBundle\Entity\User'
orocloud-cli app:console "oro:search:reindex Oro\\Bundle\\UserBundle\\Entity\\User"
orocloud-cli app:console "oro:search:reindex Oro\Bundle\UserBundle\Entity\User"
```

### Schema Update

#### NOTE
Be aware that only those consumers that ran before the orocloud-cli app:schema:update will run afterward.

Sometimes, you may be required to perform schema update operations. To do this, use the orocloud-cli app:schema:update command:

```none
app:schema:update
```

### Application Cache

#### NOTE
Be aware that only those consumers that ran before the upgrade will run afterward.

Sometimes, you may be required to clear the application cache (for example, after applying a patch or changing a configuration).
This can be done with the orocloud-cli app:cache:clear command that rebuilds the application cache. The command is performed without maintenance mode.

```none
orocloud-cli app:cache:clear
```

### Cached Translated Values

[To add translations to the source code](../../backend/translations/translations-add-to-source-code.md#dev-translation-add-to-source-code), run:

```none
orocloud-cli app:translation:update
```

### API Cache

[Warmup API and API doc caches](../../backend/api/commands.md#oroapidoccacheclear-command)

```none
orocloud-cli app:cache:api
```

### Consumer

[To run a consumer for a given queue for two minutes](../../backend/mq/consumer/index.md#dev-cookbook-system-mq-consumer), run:

```none
orocloud-cli app:consumer oro.default
```

### Search Reindex

[To trigger reindexation](../../backend/architecture/tech-stack/search/index.md#search-index-overview), run:

```none
orocloud-cli app:search:reindex
```
