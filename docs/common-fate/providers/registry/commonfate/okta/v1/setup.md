# Setup
## commonfate/okta@v1
:::info
When setting up a provider for your deployment, we recommend using the [interactive setup workflow](../../../interactive-setup.md) which is available from the Providers tab of your admin dashboard.
:::
## Example granted_deployment.yml
```yaml
version: 2
deployment:
  stackName: example
  account: "12345678912"
  region: ap-southeast-2
  release: v0.11.1
  parameters:
    CognitoDomainPrefix: example
    AdministratorGroupID: granted_administrators
    ProviderConfiguration:
      okta:
        uses: commonfate/okta@v1
        with:
          apiToken: '*****'
          orgUrl: ""

```
## Find the Okta URL
### Configuration Fields
This step will guide you through collecting the values for these fields required to setup your provider.

| Field | Description |
| ----------- | ----------- |
| orgUrl | the Okta organization URL |
Find your okta url, this can be found in the top right dropdown. See more [here](https://developer.okta.com/docs/guides/find-your-domain/main/)

**Make sure that your URL is prefixed with 'https://'**

Use this value for the input **orgUrl**
## Create an API token
### Configuration Fields
This step will guide you through collecting the values for these fields required to setup your provider.

| Field | Description |
| ----------- | ----------- |
| apiToken | the Okta API token |
In the Okta admin portal, in the side bar. Navigate to **Security -> API**
![](https://static.commonfate.io/providers/okta/app.png)

On the API page, go to the **Tokens** tab and create a new API token by pressing **Create Token**

![](https://static.commonfate.io/providers/okta/token.png)

Give the API token a descriptive name, like "common-fate-okta-provider" and click **Create Token**
![](https://static.commonfate.io/providers/okta/token-name.png)

Copy the token and use if for the **apiToken** input.
