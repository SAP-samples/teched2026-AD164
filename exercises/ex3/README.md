# Exercise 3 - Create an Invoice Verification Agent

In this exercise, you will create an AI agent that reads an invoice from SAP S/4HANA Public Cloud together with the related Purchase Order, Goods Receipt, and Supplier contract. The agent compares these business documents and summarizes the reason for any payment block.

## Exercise 3.1 - Build the Invoice Verification Agent

After completing these steps you will have created the invoice verification agent using Quick Create and provided the business goals required to generate the specification.

1. Click **New** and select **Agent**. In the **Create Agent** dialog, enter the following intent statement in the **Intent Statement** field:
    ```
    Please create an agent. The agent should...Read an invoice from SAP S/4 HANA Public Cloud, related Purchase Order, Goods Receipt and Supplier contract. Compare the invoice with these business documents and summarize the reason if the invoice has any payment block.
    ```
<br>![](images/Step1.png)

2. Check **Quick Create** to skip the clarifying questions and start building the solution directly. Click **Create**.
<br>![](images/Step2.png)

3. Even in Quick Create mode, the Webagent asks for measurable business goals. Enter the following and click **Submit Answer**:
    ```
    Reduce time to identify payment block reasons from 2 hours to 5 minutes
    ```
<br>![](images/Step3.png)

4. The Webagent generates the specification, identifying the required SAP APIs — Supplier Invoice, Purchase Order, Goods Receipt, and Purchasing Info Record. Review the specification and type **execute specification/specification.md** to proceed with the build.
<br>![](images/Step4.png)

## Exercise 3.2 - Review and Deploy the Agent

After completing these steps you will have reviewed the generated solution and deployed the invoice verification agent.

5. The Webagent completes the build. Review the generated solution: **1 AI Agent + 4 MCP Servers** wired together, with 132/132 tests passed and 78% coverage. The agent performs a 3-way match on invoice data from SAP S/4HANA and returns a plain-language explanation of the payment block reason.
<br>![](images/Step5.png)

6. The solution overview shows the agent is ready but not yet deployed. Click **Deploy** to deploy the invoice verification agent.
<br>![](images/Step6.png)

## Summary

You have successfully created and deployed an invoice verification agent in Joule Studio. The agent reads invoice data and related business documents from SAP S/4HANA Public Cloud and summarizes the reason for any payment block.
