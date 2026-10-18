# Exercise 3 - Create an Invoice Verification Agent

In this exercise, you will build an **invoice verification agent**. Given an invoice, it reads the related **Purchase Order, Goods Receipt, and Supplier contract** from SAP S/4HANA Public Cloud, compares them, and explains in plain language why an invoice is blocked for payment.

> **New terms for this exercise:**
> - **3-way match** — a standard accounts-payable check that compares the **invoice** against its **purchase order** and **goods receipt** to confirm quantities and prices agree before payment is released. The agent performs this automatically.
> - **Quick Create** — a Webagent mode that skips the detailed clarifying Q&A and builds the solution directly, once you already know what you want.
>
> As before, the **action you perform** is shown in bold, and steps marked *(Review only)* need no action.

## Exercise 3.1 - Build the Invoice Verification Agent

After completing these steps you will have created the invoice verification agent using Quick Create and provided the business goal needed to generate the specification.

1. **Click New and select Agent.** In the **Create Agent** dialog, **enter the following intent in the Intent Statement field:**
    ```
    Please create an agent. The agent should...Read an invoice from SAP S/4 HANA Public Cloud, related Purchase Order, Goods Receipt and Supplier contract. Compare the invoice with these business documents and summarize the reason if the invoice has any payment block.
    ```
<br>![](images/Step1.png)

2. **Check Quick Create**, then **click Create.**
> **Quick Create** tells the Webagent to skip the step-by-step clarifying questions and build the solution directly.
<br>![](images/Step2.png)

3. Even in Quick Create mode, the Webagent asks for one measurable business goal. **Enter the following and click Submit Answer:**
    ```
    Reduce time to identify payment block reasons from 2 hours to 5 minutes
    ```
<br>![](images/Step3.png)

4. The Webagent generates the specification and identifies the SAP APIs it needs — **Supplier Invoice, Purchase Order, Goods Receipt, and Purchasing Info Record**. **Review the specification, then type `execute specification/specification.md`** to start the build.
> Typing this command tells the Webagent to execute the generated specification and assemble the agent and its MCP servers.
<br>![](images/Step4.png)

## Exercise 3.2 - Review and Deploy the Agent

After completing these steps you will have reviewed the generated solution and deployed the invoice verification agent.

5. The Webagent completes the build. **Review the generated solution** — **1 AI Agent + 4 MCP servers** wired together, with 132/132 tests passed and 78% coverage. The agent performs a 3-way match on the SAP S/4HANA data and returns a plain-language explanation of each payment block. *(Review only.)*
<br>![](images/Step5.png)

6. The solution overview shows the agent is built but not yet deployed. **Click Deploy** to deploy the invoice verification agent.
<br>![](images/Step6.png)

## Summary

You have successfully created and deployed an invoice verification agent in Joule Studio. The agent reads invoice data and the related business documents from SAP S/4HANA Public Cloud and summarizes the reason for any payment block.
