# Containing Files

1. The LICENSE file:
In most cases, the license for SAP sample projects is `Apache 2.0`.

2. The REUSE.toml file: 
The [Reuse Tool](https://reuse.software/) must be used for your samples project. You can find the REUSE.toml in the project initial. Please replace the parts inside the single angle quotation marks < > by the specific information for your repository.

3. The README.md file (this file):
Please edit this file as it is the primary description file for your project. You can find some placeholder titles for sections below.

# Session AD164 - Generate agentic workflows using SAP-managed n8n in Joule Studio

## Description

This repository contains the material for the SAP TechEd 2026 session called Session AD164 - Generate agentic workflows using SAP-managed n8n in Joule Studio.  

## Overview

This session introduces attendees to building and deploying agentic workflows using SAP-managed n8n in Joule Studio.

The scenario is based on a real-world accounts payable use case: an invoice with a payment block exists in SAP S/4HANA Cloud. An AI agent retrieves the invoice and analyses it in the context of the related purchase order, goods receipt, and supplier contract. The agent's findings are presented to an approver through Joule Chat, enabling a conversational experience to review the details and make an informed decision. When the approver approves the invoice, the payment block is automatically removed in SAP S/4HANA Cloud.

SAP Business AI Platform provides agentic workflow capabilities, and n8n is the SAP agentic workflow orchestration solution included in Joule Studio. It leverages n8n as a modern agentic workflow engine, running on scalable and robust SAP infrastructure with AI-driven development using LLMs and SAP knowledge systems.

![](images/n8n.png)

## Requirements

The requirements to follow the exercises in this repository are:

- SAP Joule Studio
- SAP S/4HANA Public Cloud

## Exercises

- [Exercise 1 - Create an Invoice Approval Workflow](exercises/ex1/)
    - [Exercise 1.1 - Build the Workflow](exercises/ex1#exercise-11-build-the-workflow)
    - [Exercise 1.2 - Deploy and Test the Workflow](exercises/ex1#exercise-12-deploy-and-test-the-workflow)
- [Exercise 2 - Create and Deploy a Custom Agent](exercises/ex2/)
    - [Exercise 2.1 - Build and Deploy the Agent](exercises/ex2#exercise-21-build-and-deploy-the-agent)
    - [Exercise 2.2 - Test the Agent](exercises/ex2#exercise-22-test-the-agent)
- [Exercise 3 - Create an Invoice Verification Agent](exercises/ex3/)
    - [Exercise 3.1 - Build the Invoice Verification Agent](exercises/ex3#exercise-31-build-the-invoice-verification-agent)
    - [Exercise 3.2 - Review and Deploy the Agent](exercises/ex3#exercise-32-review-and-deploy-the-agent)

  
**OR** Link to the Tutorial Navigator for example...

Start the exercises [here](https://developers.sap.com/tutorials/abap-environment-trial-onboarding.html).

**IMPORTANT**

Your repo must contain the .reuse and LICENSES folder and the License section below. DO NOT REMOVE the section or folders/files. Also, remove all unused template assets(images, folders, etc) from the exercises folder. 

## Contributing
Please read the [CONTRIBUTING.md](./CONTRIBUTING.md) to understand the contribution guidelines.

## Code of Conduct
Please read the [SAP Open Source Code of Conduct](https://github.com/SAP-samples/.github/blob/main/CODE_OF_CONDUCT.md).

## How to obtain support

Support for the content in this repository is available during the actual time of the online session for which this content has been designed. Otherwise, you may request support via the [Issues](../../issues) tab.

## License
Copyright (20xx-)20xx SAP SE or an SAP affiliate company and <your-project> contributors. Please see our [LICENSE](LICENSE) for copyright and license information. Detailed information including third-party components and their licensing/copyright information is available [via the REUSE tool](https://api.reuse.software/info/github.com/SAP/<your-project>).
