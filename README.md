# generate-java-client

GitHub Action used to generate a Java client based on a Swagger document and publish it as a Maven package in your repo.

## Usage

```yaml
steps:
  - uses: ohiomutual/generate-java-client@v1
    with:
      swagger-doc: swagger/swagger.json
      group-id: com.example
      artifact-id: my-service-client
      version: 1.0.0
      package-name: myService
    env: GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

### Inputs

| Input        | Description                                 | Required |
| ------------ | ------------------------------------------- | -------- |
| swagger-doc  | Relative path to the swagger document       | YES      |
| group-id     | Maven groupId value                         | YES      |
| artifact-id  | Maven artifactId value                      | YES      |
| version      | Maven version value                         | YES      |
| package-name | Java package name (appended to group-id)    | YES      |
| templates    | Relative path to swagger template directory | NO       |

_Note: The ```GITHUB_TOKEN``` environment variable is required to publish the package to your repository's Packages_
