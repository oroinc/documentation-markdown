<a id="dev-components-system-aware-resolver"></a>

# System Aware Resolver

The <a href="https://github.com/oroinc/platform/blob/4.2/src/Oro/Component/Config/Resolver/SystemAwareResolver.php" target="_blank">SystemAwareResolver</a> class supports the following expressions:

- **%parameter%** - gets a parameter from the DI container
- **$parameter$** - gets a parameter from the context
- **AcmeClass::MY_CONST** - gets a constant
- **AcmeClass::myMethod** - calls the static method without parameters
- **AcmeClass::myMethod()** - calls the static method without parameters
- **AcmeClass::myMethod($param1$, %param2%)** - calls the static method with parameters
- **@service->myMethod** - calls service’s method without parameters
- **@service->myMethod()** - calls service’s method without parameters
- **@service->myMethod($param1$, %param2%)** - calls service’s method with parameters
- **@service** - gets the instance of a service

You can also use parameters inside expressions, for example:

- **%acme.class_name%::myMethod()** - calls the static method without parameters
- **Hello $user_name$**

<!-- Frontend -->
