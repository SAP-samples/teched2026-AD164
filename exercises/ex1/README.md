# Exercise 1 - Create an Invoice Approval Workflow

In this exercise, you will use SAP Joule Studio to create an agentic invoice approval workflow powered by SAP-managed n8n. You will describe what you want in plain business language (an *intent*), refine the requirements through a guided Q&A with the AI **Webagent**, generate the workflow specification and solution, and then deploy and test it.

> **New to Joule Studio or n8n? Start here.**
> - **SAP Joule Studio** — SAP's environment for building, deploying, and managing AI-powered automations and agents.
> - **SAP-managed n8n** — a visual, node-based workflow engine hosted and run by SAP. You build a process as a series of connected steps called *nodes*.
> - **Webagent** — the AI assistant that turns your plain-language *intent* into a working solution by asking you a few clarifying questions.
> - **Solution** — the container for your work. It holds one or more **assets** (a workflow, an agent, or an MCP server) and is the unit you deploy. A solution can also be shared, committed to a GitHub repository, and transported to another Joule Studio tenant.
> - **Intent** — a description of the business outcome you want, in everyday language — no technical terms required.
>
> **Throughout this guide, the action you need to perform is shown in bold.** Steps marked *(Review only)* need no action — just look and move on.

## Exercise 1.1 - Build the Workflow

After completing these steps you will have built an invoice approval workflow that validates invoices, routes them to an AP Clerk for approval via SAP Task Center with email and Teams notifications, and returns the outcome.

1. **Log on to SAP Joule Studio** in your browser (preferably Chrome) : 
https://747391938.eu10.sapdas.cloud.sap/new/
with username <br>AD164-0XX  (XX to be replaced with the number as provided)  and the password as shared by your trainers.

2. You arrive on the **Joule Studio home screen**, which opens with the **Joule Chat** interface. *(Review only — get oriented.)*
<br>![](images/Step2.png)

3. In the left navigation, **click Solutions** to open the Solutions area.
<br>![](images/Step3.png)
> A **solution** groups one or more **assets** (a workflow, agent, or MCP server) and is what you ultimately deploy.

4. **Click New** to start creating a solution.
<br>![](images/Step4.png)

5. **Select n8n Workflow** as the type for your new solution.
<br>![](images/Step5.png)
> You're telling Joule Studio to build this solution as a visual n8n workflow (a sequence of connected nodes).

6. The **Create n8n Workflow** dialog opens. **Enter your solution name** (e.g. `AD164-00`, replacing `00` with your user number), **paste the following intent into the Intent Statement field**, and **click Create**:
    ```
    Please create a workflow. The workflow should...Receive Invoice header data as input, do basic validation and submit the invoice for an approval to an AP clerk. AP Clerk receive Mail and Teams notifications. AP Clerk approve or reject the invoice
    ```
<br>![](images/Step6.png)
> Your **intent** is simply the business outcome you want. The Webagent translates it into requirement and specification documents, then builds the solution for you — you don't need to write any technical detail here.
> **The Webagent will ask clarifying questions from this step onwards. The questions may differ slightly from what is shown in the screenshots — provide appropriate answers and continue.**


7. The Webagent asks what **invoice header fields** the workflow should accept as input. **Select "Standard set: Invoice Number, Vendor, Date, Amount, Currency, Company Code"** and **click Submit Answer**.
<br>![](images/Step7.png)

8. The Webagent asks what **validation rules** to apply before routing the invoice to the AP clerk. **Select "Basic: mandatory fields + amount > 0 + valid date"** and **click Submit Answer**.
<br>![](images/Step8.png)

9. The Webagent asks what should happen after the AP clerk approves or rejects the invoice. **Select "Just return the approval/rejection result to the caller (no SAP write-back)"** and **click Submit Answer**.
<br>![](images/Step9.png)

10. The Webagent asks for the main business outcome. **Type `Reduce Invoice approval time`** and **click Submit Answer**.
<br>![](images/Step10.png)

11. The Webagent asks for a measurable target. **Select "From 5 days to 1 day"** and **click Submit Answer**.
<br>![](images/Step11.png)

12. The Webagent presents a **Business Goals & Success Criteria** summary table (Metric: Invoice approval cycle time, Baseline: 5 days, Target: 1 day). **Select "Confirm — proceed"** and **click Submit Answer**.
<br>![](images/Step12.png)

13. The Webagent shows a complete recap of everything captured: workflow design, input fields, validation rules, post-approval action, and business goal. It confirms all required n8n nodes are available (Webhook, SAP Task Center, Outlook, Teams). *(Review only — confirm it matches your intent.)*
<br>![](images/Step13.png)

14. The Webagent presents the **Solution Architecture** and **Product Requirements Document (PRD)** summary — including key milestones (M1: Invoice Received → M5: Result Returned) and scope boundaries. **Select "Confirm — proceed"** and **click Submit Answer** to write the PRD.
<br>![](images/Step14.png)

15. The Webagent saves `product-requirements-document.md` and asks whether to proceed to the **specification phase**, where the PRD is translated into a detailed technical checklist. **Type `Yes`** and **send it**.
<br>![](images/Step15.png)

16. Before writing the specification, the Webagent needs to know who receives the approval task in **SAP Task Center**. **Select "A fixed email address (I'll provide it)"** and **click Submit Answer**. Then **enter your own email address** when prompted.
<br>![](images/Step16.png)
> **Not sure what your email address is?** Click the **avatar icon (your initials)** at the bottom-left of the navigation bar — your email is shown at the top of the profile panel.
<br>![](images/Step16b.png)

17. The specification is ready. The Webagent summarises a **11-node workflow**: Webhook trigger → IF validation → Microsoft Outlook + Teams notifications → SAP Task Center approval → Route decision → Set response → Respond to Webhook. **Type `Yes`** and **send it** to build the workflow now.
<br>![](images/Step17.png)

18. The Webagent builds the workflow and opens it in the **n8n editor**. The Solution Progress panel on the left confirms all phases are complete (Intent Summary ✓, Requirements ✓, Specifications ✓, Solution Artifacts ✓). *(Review only — take a moment to explore the generated workflow.)*
<br>![](images/Step18.png)

19. The workflow contains a **"Notify AP Clerk via Email"** (Outlook) node. This tenant is not connected to a Microsoft 365 tenant, so the node cannot run. **Select the "Notify AP Clerk via Email" node** and **click Delete** (or press the Delete key).
<br>![](images/Step19.png)

20. For the same reason, remove the **"Notify AP Clerk via Teams"** node. **Select it** and **click Delete** (or press the Delete key).
<br>![](images/Step20.png)

21. The Webagent confirms the workflow files have been created (`solution.yaml`, `asset.yaml`, the `.n8n.json` workflow, and the OpenAPI schema). **Type `Deploy`** in the message box and **send it** to deploy the solution.
<br>![](images/Step21.png)

## Exercise 1.2 - Deploy and Test the Workflow

After completing these steps you will have deployed your workflow and run it end to end with sample invoice data.

1. A **"Confirm Deploy Solution"** dialog appears, showing your solution name (e.g. AD164-00) and current quota usage. **Click "Deploy Now"** to confirm.
<br>![](images/Step22.png)

2. The **Manage** tab opens. Deployment completes and the solution status changes to **Running** — version 1.0.0+snapshot.1 is active with the invoice-approval-workflow asset running. *(Review only — confirm the status shows Running.)*
<br>![](images/Step23.png)

3. Under **Try Deployed Solution**, **click "invoice-approval-workflow"** to open the test interface. The Webagent tells you what input the workflow expects: Invoice Number, Invoice Date, Vendor, Amount, Currency, and Company Code.
<br>![](images/Step24.png)

4. **Type `Test Input Data`** in the message box and **send it** to ask the Webagent to generate sample test data.
<br>![](images/Step25.png)

5. The Webagent explains the workflow's input requirements and provides an example **validation failure** payload (sending `amount: 0` returns a `400` response immediately, without reaching the AP clerk). *(Review only — you can try the failure scenario yourself if time permits.)*
<br>![](images/Step26.png)

6. **Enter the following test invoice JSON** in the message box and **send it**:
    ```json
    {
      "invoiceNumber": "INV-2026-00124",
      "vendor": "Test Vendor",
      "invoiceDate": "2026-10-23",
      "amount": 2000,
      "currency": "USD",
      "companyCode": "2000"
    }
    ```
<br>![](images/Step28.png)
> You can use any valid invoice number and any amount greater than 0.

7. The Webagent shows a **summary table** of the invoice data to be submitted (Invoice Number, Vendor, Invoice Date, Amount, Currency, Company Code). Review it, then **type `yes` and send** to confirm and submit to the workflow.
<br>![](images/Step29.png)

8. **Click "Execute Workflow"** to trigger the invoice approval workflow with your test data.
<br>![](images/Step30.png)

9. The Webagent confirms **"Workflow started successfully!"** with a link to the Monitoring section. **Click "Monitoring section"** to view the execution.
<br>![](images/Step31.png)

10. The **Monitoring** dashboard shows **1 total execution** with status **"waiting"** — the workflow has validated the invoice and created an approval task for the AP clerk in SAP Task Center. It is waiting for the approval decision. *(Review only.)*
<br>![](images/Step32.png)

11. **Click the execution row** (e.g. 1646) to open its detail view. The step trace shows: Invoice Approval Submitted (3ms) → Validate Invoice (67ms) → Approve Invoice (3.75s, currently waiting for the AP clerk's decision). *(Review only — observe how each node's execution is tracked.)*
<br>![](images/Step33.png)
> The workflow pauses here until the AP clerk acts in SAP Task Center.

12. The workflow is now waiting for approval. In the left navigation bar, **click the Conversations icon** (speech-bubble icon) to open Joule Chat.
<br>![](images/Step34.png)

13. The **Conversations** panel opens. **Click "+ New"** to start a new conversation with Joule.
<br>![](images/Step35.png)

14. The Joule Chat screen opens. **Type `List my tasks`** and **send it** to see pending approval tasks assigned to you in SAP Task Center.
<br>![](images/Step36.png)

## Summary

You have successfully built, deployed, and tested an invoice approval workflow in Joule Studio using SAP-managed n8n. The workflow validates incoming invoices, creates an approval task for the AP Clerk in SAP Task Center, and waits for their decision — all driven from a plain-language intent.

Continue to - [Exercise 2 - Create and Deploy a Custom Agent](../ex2/README.md)
