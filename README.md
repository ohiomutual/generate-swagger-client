# generate-swagger-client

GitHub Action used to generate clients based on a Swagger document and publish it as a Maven package in your repo.

## Usage

```yaml
steps:
  - uses: ohiomutual/generate-swagger-client@v1
    with:
      swagger-doc: swagger/swagger.json
      language: java
      group-id: com.example
      artifact-id: my-service-client
      version: 1.0.0
      package-name: myService
    env: GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

### Inputs

| Input             | Description                                | Required | Default       |
| ----------------- | ------------------------------------------ | -------- | ------------- |
| swagger-doc       | Relative path to the swagger document      | YES      | N/A           |
| language          | e.g. ```java```, ```typescript-fetch```    | YES      | N/A           |
| group-id          | Package groupId/owner                      | YES      | N/A           |
| artifact-id       | Package artifact name                      | YES      | N/A           |
| version           | Package version                            | YES      | N/A           |
| package-name      | Java package name (appended to group-id)   | NO       | ```client```  |
| java-date-library | e.g. ```java7```, ```java8```              | NO       | ```java8```   |
| templates         | Relative path to swagger template directory| NO       | N/A           |

_Note: The ```GITHUB_TOKEN``` environment variable is required to publish the package to your repository's Packages_
