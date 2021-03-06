# Microsoft Commercial Marketplace - Community Sample Code and SDK for SaaS Applications
![.NET Core](https://github.com/Azure/Microsoft-commercial-marketplace-transactable-SaaS-offer-SDK/workflows/.NET%20Core/badge.svg)


## Introduction

The goal of this project is to provide a reference example with sample code for developers interested publishing transactable, Software as a-Service (SaaS) offers in the Microsoft commercial marketplace.

The sample code uses a .NET-based SDK published as a part of this project. The SDK provides a framework for exercising the commercial marketplace billing system, including the [SaaS Fulfillment API (v2)](https://docs.microsoft.com/azure/marketplace/partner-center-portal/pc-saas-fulfillment-api-v2) and [Marketplace Metering Service API.](https://docs.microsoft.com/azure/marketplace/partner-center-portal/marketplace-metering-service-apis) Leveraging the SDK, the sample code demonstrates how a typical SaaS platform interacts with these APIs in order to provision customers, enable logging, and manage commercial marketplace subscriptions.


## Intended use

The sample code and SDK in this project are for reference purposes only and are meant to complement the existing commercial marketplace documentation by demonstrating common API interactions required for publishing and managing SaaS application offers. The intent of this project is to accelerate the onboarding experience by providing code samples for developers. Although the sample code leverages the SDK, developers are encouraged to work with the SaaS Fulfillment API and Marketplace Metering Service API directly rather than rely on the SDK for production use.


Please note: this is not a Microsoft-supported Azure SDK project. Support for this project is community-based and contributions are welcomed. Details on contributing can be found [below.](https://github.com/Azure/Microsoft-commercial-marketplace-transactable-SaaS-offer-SDK#contributing)


## Commercial marketplace documentation

Before using this sample code and SDK, please review the commercial marketplace documentation resources below to understand the important concepts, account setup, and offer configuration requirements for publishing SaaS SaaS application offers.

- [Commercial marketplace documentation.](https://docs.microsoft.com/azure/marketplace/) Getting started and top articles

- [SaaS applications in the commercial marketplace.](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-new-saas-offer) Overview of the SaaS SaaS application business policies, plus step-by step offer creation and configuration requirements.

- [SaaS fulfillment API (v2).](https://docs.microsoft.com/azure/marketplace/partner-center-portal/pc-saas-fulfillment-api-v2) API details for SaaS SaaS application subscription creation and management.

- [Marketplace metering service API.](https://docs.microsoft.com/azure/marketplace/partner-center-portal/marketplace-metering-service-apis) API details for the Marketplace Metering Service which, when used in conjunction with the SaaS Fulfillment API, enables event-based billing. 

- [SaaS fulfillment API FAQ.](https://docs.microsoft.com/azure/marketplace/partner-center-portal/saas-fulfillment-apis-faq) Frequently-asked questions about the SaaS Fulfillment APIs.


## Sample code and SDK documentation 

The documentation **(docs)** directory contains [installation instructions](./docs/Installation-Instructions.md) to help understand, implement, and deploy the sample code and SDK components. 


## Terminology

- SDK: Software development kit, also referred to as _client library_. This refers to the SDK for the C# language and includes the "Transactable SaaS Client Library".

- Sample Web application. This refers to source code that leverages the SDK and Client Libraries.   


## Projects 

The source **(src)** directory offers the following components, and the installation instructions are in [this document](./docs/Installation-Instructions.md): 


| Project | Description | Directory Name |
| --- | --- | --- |
| **Transactable SaaS Client Library** | Implements the clients for SaaS Fulfillment API (v2), Marketplace Metering Service API, and a webhook helper for handling messages from the commercial marketplace billing system. |SaaS.SDK.Client|
| **Customer Provisioning - Sample web application** | Demonstrates how to register, provision, and activate the commercial marketplace subscription. Implemented using ASP.Net Core 3.1, the sample web application uses the SaaS Client Library and Data Access Library to invoke and persist API interactions and provides an example user interface to demonstrate how a customer would manage their subscriptions and plans. |SaaS.SDK.CustomerProvisioning|
| **Publisher Solution (metered billing)- Sample web application** | Demonstrates how to generate usage events used in metered billing transactions, and how to emit these events to the Marketplace Metering Service API. |SaaS.SDK.PublisherSolution|
| **Client Data Access Library** | Demonstrates how to persist commercial marketplace plans, subscriptions, and related transaction attributes when using the SaaS Fulfillment API (v2) and Marketplace Metering Service API. |SaaS.SDK.Client.DataAccess |
| **[Unit Tests Project](./src/SaaS.SDK.UnitTest)** | Helps validate and test the SDK's codebase. | SaaS.SDK.UnitTest |

The sample code and SDK in this repository run in the Publisher's environment as illustrated below. 

![Usecase](./docs/images/sdk_overview.png)

## Technology and versions

This SDK has been developed using the following technologies and versions: 

- [.NET Core 3.1.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [ASP.NET Core Runtime 3.1.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [Entity Framework](https://docs.microsoft.com/ef/)


## Security
- The sample code and SDK have been scanned for vulnerabilities and use secure configurations. Versions have been reviewed to ensure compatibility with the latest security guidelines.


## Prerequisites

Ensure the following prerequisites are met before getting started:

- An active Azure subscription for development and testing purposes. Create an Azure subscription [here.](https://azure.microsoft.com/free/)
- A Partner Center account enabled for use with the commercial marketplace. Create an account [here.](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-account)
- We recommend using an Integrated Development Environment (IDE):  [Visual Studio Code](https://code.visualstudio.com/),  [Visual Studio 2019](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Community&rel=16#), etc...
- The samples have been implemented using [.NET Core 3.1.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- For data persistence we are using [Azure SQL Database](https://azure.microsoft.com/services/sql-database/) and [Entity Framework](https://docs.microsoft.com/ef/). However, feel free to use any data repository you are comfortable with.  


## Releases

- **February 2020 - v1.0** Current Release. It includes the full implementation of the Fulfillment V2 and metered APIs with web applications that demonstrate customer provisioning and publisher solutions. 


## Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repositories using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## License

This project is released under the [MIT License](LICENSE).
