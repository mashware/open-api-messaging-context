Little context in behat for validate published messages and http responses according to an AsyncApi and OpenApi specification.

# Installation
```
composer require --dev mashware/open-api-messaging-context
```
# How to use

Configure the context in your `behat.yml`

```yaml
default:
  suites:
    default:
      contexts:
        - PcComponentes\OpenApiMessagingContext\Behat\ResponseValidatorOpenApiContext:
          - '%%kernel.project_dir%%'
```

Check if http responses are documented in your openapi file:
```gherkin
Then the response should be valid according to OpenApi "docs/openapi.yml" with path "/your/openapi/path/"
And the JSON response should be valid according to OpenApi "docs/openapi.yml" schema "MySchema"
```
