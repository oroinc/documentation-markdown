<a id="orocloud-maintenance-env-vars"></a>

# How to Add/Remove Environment Variables

<a href="https://en.wikipedia.org/wiki/Environment_variable" target="_blank">Environment variable</a> can be configured for application usage, as illustrated below:

```none
---
orocloud_options:
  application:
    env_vars:
      COMPOSER_AUTH:  '{"http-basic":{"example.org":{"username":"username","password":"password"}}'
      COMPOSER_AUTH1: '{"gitlab-oauth":{"gitlab.example.org":"ThisTokenIsNotSoSecretChangeIt"},"gitlab-domains":["gitlab.example.org"]}'
      COMPOSER_AUTH2: '{"gitlab-oauth":{"gitlab.com":"ThisTokenIsNotSoSecretChangeIt"}}'
      COMPOSER_AUTH3: '{"gitlab-token":{"gitlab.example.org":"ThisTokenIsNotSoSecretChangeIt"},"gitlab-domains":["gitlab.example.org"]}'
      COMPOSER_AUTH4: '{"gitlab-token":{"gitlab.com":"ThisTokenIsNotSoSecretChangeIt"}}'
      COMPOSER_AUTH5: '{"github-oauth":{"github.com":"ThisTokenIsNotSoSecretChangeIt"}}'
```

* **env_vars** — the hash where the key is an environment variable name, and the value is the environment variable value.

<a id="cloud-environment-type-based-configuration"></a>

## How to Configure Environment Type Based Application

```none
---
orocloud_options:
  application:
    env_vars:
      'ORO_DEPLOYMENT_TYPE': 'local'
```

* **local** - deployment_type, which will be set to parameters.yml for your deployed application as

```none
deployment_type: local
```

#### NOTE
For more details on the environment type based application configuration, please see the <a href="https://doc.oroinc.com/backend/setup/dev-environment/env-vars/" target="_blank">related documentation in the backend developer guide</a>.

#### WARNING
Environment variables are always string and are not cast automatically to integer, null, or other types. You should never pass an empty environment variable, like ‘ORO_DB_HOST=’ or ‘ORO_DB_HOST=NULL’. Instead, it should never be available (never be set). More information about environment variables is available in the [parameters.yml description](../../backend/setup/dev-environment/parameters-yml.md#installation-parameters-yml-description) section.
