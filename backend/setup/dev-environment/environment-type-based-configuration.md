<a id="environment-type-based-configuration"></a>

# Environment Type-Based Application Configuration

Use different default configurations based on the environment where the application is deployed:

* <a href="https://doc.oroinc.com/cloud/environments/#production-environment" target="_blank">Production Environment</a>
* <a href="https://doc.oroinc.com/cloud/environments/#development-environment" target="_blank">Development Environment</a>
* <a href="https://doc.oroinc.com/cloud/environments/#testing-environment" target="_blank">Testing Environment</a>
* <a href="https://doc.oroinc.com/cloud/environments/#staging-environment" target="_blank">Staging Environment</a>
* Local Development Machine
* etc.

Deployment type (`deployment_type`) is one of the options in **parameters.yml** file, and it is asked during `composer install`.

> *config/parameters.yml*
> ```text
>    parameters:
>        # ...
>        deployment_type: null
> ```

To start using deployment type, change value `deployment_type: <type>` in *config/parameters.yml* and create a config file in *config/deployment/config_<type>.yml*.

This configuration will have the highest priority.

For example:

> *config/parameters.yml*
> ```text
>        parameters:
>            # ...
>            deployment_type: local
> ```

> *config/deployment/config_local.yml*
> ```text
>        monolog:
>            handlers:
>                # your additional monolog configuration
> ```

#### NOTE
For more details on how to configure the environment type based application in the Cloud environment, please see the <a href="https://doc.oroinc.com/cloud/maintenance/env-vars/" target="_blank">related cloud documentation</a>.

<!-- Frontend -->
