[![Repo Status](http://img.shields.io/travis/Azure/azure-rest-api-specs/master.svg?style=flat-square&label=repo-status)](https://travis-ci.org/Azure/azure-rest-api-specs)

# Azure REST API Specifications

## Code of Conduct
This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Description

This repository is the canonical source for REST API specifications for Microsoft Azure.

## Creating the Swagger Specification for Azure
- This [document](./documentation/creating-swagger.md) will help you understand how AutoRest converts Swagger in to code.
- If you are using **swashbuckle** to generate a swagger spec from your .NET WEB API then please take a look at this [repo]( https://github.com/Azure/swashbuckle-resource-provider).
- Swagger spec for every api-version should be in a separate folder named with the api-version.
  - It is time consuming to review the file line by line for every api-version. When you are creating the swagger spec for the new api-version, please copy the swagger spec from the previous version in to the new api-versioned folder and commit it. After that overwrite it with the changes for the new api-version. This makes it easy for us to review the changes.

## Directory Structure

The structure of the directory should strictly follow these rules:
- The top level folder must be the service name
- The second level must be the API versions
- The third level must be the format of the specification
- The fourth level must be the specifications

The structure should appear like so:
```bash
.
├── arm-authorization
│   └── 2015-01-01
│       └── swagger
│           └── authorization.json
├── arm-compute
│   └── 2015-06-15
│       └── swagger
│           └── service.json
├── arm-features
│   └── 2014-08-01-preview
│       └── swagger
│           └── features.json
├── arm-network
│   └── 2015-05-01-preview
│       └── swagger
│           └── service.json
├── arm-resources
│   └── 2014-04-01-preview
│       └── swagger
│           └── service.json
├── arm-storage
│   └── 2015-05-01-preview
│       └── swagger
│           └── service.json
├── arm-subscriptions
│   └── 2014-04-01-preview
│       └── swagger
│           └── service.json
├── arm-web
├── documentation
└── readme.md
```

At this point, the specifications are expected to be in swagger format

## How to validate your swagger
* [You can use this json schema validator](https://json-schema-validator.herokuapp.com/)
  * In the upper left box, paste the [swagger schema from here](https://github.com/swagger-api/swagger-spec/blob/master/schemas/v2.0/schema.json)
  * In the lower left box, paste your swagger json
  * Upon clicking the validate button, you should either see errors or success.

## Generating Code from Specifications

If you are interested in generating code from these specifications, please check out [AutoRest](https://github.com/azure/autorest). There you will find the code generator as well as instructions on how to use it.

## How to Contribute

Please contribute to services you know and love. The curation of these specifications will ensure that we have great documentation and even better client library support for our Azure Services. If you have any questions, please reach out to the autoresteng dl.

### Submitting changes

Please send a [GitHub Pull Request to Azure REST API Specs](https://github.com/azure/azure-rest-api-specs/pull/new/master) with a clear list of what you've done (read more about [pull requests](http://help.github.com/pull-requests/)). When you send a pull request, we will love you forever if you include additions to the documentation for your given service. We can always use more documentation and beautiful markdown. Please follow make sure all of your commits are atomic (one feature per commit).

Always write a clear log message for your commits. One-line messages are fine for small changes, but bigger changes should look like this:

    $ git commit -m "A brief summary of the commit
    >
    > A paragraph describing what changed and its impact."
    
Please be kind with your pull requests and ensure you keeping them as focused and cohesive as possible. Keep your pull
request free of merge commits, code review fixes and anything that may take away from the essence of your contribution.
Use the git tools you have available to you, such as amend, rebase, etc.
