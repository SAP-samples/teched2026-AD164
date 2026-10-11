# Exercise 1 - Create an Invoice Approval Workflow

In this exercise, you will use Joule Studio to create an agentic invoice approval workflow powered by SAP-managed n8n. You will define the workflow intent, refine requirements through a guided Q&A with the AI Webagent, generate the workflow specification and solution, and deploy it.

## Exercise 1.1 - Build the Workflow, Deploy and Test

After completing these steps you will have created and deployed an invoice approval workflow that validates invoices, routes them for AP Clerk approval via email and Teams notifications, and logs the outcome.

1. Open your browser and log on to Joule Studio.
<br><img src="images/Step1.png" style="border:1px solid #d0d7de; border-radius:4px;">

2. You are now on the Joule Studio home screen with the Joule Chat interface.
<br><img src="images/Step2.png" style="border:1px solid #d0d7de; border-radius:4px;">

3. In the left navigation, click on **Solutions** to open the Solutions section.
<br><img src="images/Step3.png" style="border:1px solid #d0d7de; border-radius:4px;">

4. Click **New** to create a new solution.
<br><img src="images/Step4.png" style="border:1px solid #d0d7de; border-radius:4px;">

5. Select **n8n Workflow** as the workflow type for your new solution.
<br><img src="images/Step5.png" style="border:1px solid #d0d7de; border-radius:4px;">

6. Copy and paste the intent statement below into the **Intent** field. Optionally provide a **Solution name** using your username. Click **Create**.
    ```
    Please create a workflow. The workflow should...Receive Invoice data as input, do basic validation of each line item of the invoice. Submit the invoice for an approval to a AP clerk for approval. AP Clerk receive Mail and Teams notifications. AP Clerk approve or reject the invoice.
    ```
<br><img src="images/Step6.png" style="border:1px solid #d0d7de; border-radius:4px;">

7. The Webagent will ask a series of questions to refine the workflow requirements. For the first set of questions about trigger, validation, and approver setup, provide the following answers:
    ```
    webhook call. validation of amount, currency, due date. AP Clerk - provide your user email id. AP Clerk approve using Task Center. Post approval the log the outcome and workflow ends
    ```
<br><img src="images/Step7.png" style="border:1px solid #d0d7de; border-radius:4px;">

8. The next question is related to approval task behaviour and success criteria as a business KPI. Enter the following answer and submit:
    ```
    reduce manual processing and ensure 100% invoices are validated
    ```
<br><img src="images/Step8.png" style="border:1px solid #d0d7de; border-radius:4px;">

9. The next question is related to the AP Clerk as approver. Select all applicable options and click **Submit Answer**.
<br><img src="images/Step9.png" style="border:1px solid #d0d7de; border-radius:4px;">

10. Select all remaining options and click **Submit Answer**.
<br><img src="images/Step10.png" style="border:1px solid #d0d7de; border-radius:4px;">

11. Enter your **AP Clerk email ID** — use your own user email address.
<br><img src="images/Step11.png" style="border:1px solid #d0d7de; border-radius:4px;">

12. When asked what happens when the AP Clerk rejects an invoice, choose **Log only - record outcome and end**.
<br><img src="images/Step12.png" style="border:1px solid #d0d7de; border-radius:4px;">

13. Review and confirm the refined intent together with the Key Business Goals.
<br><img src="images/Step13.png" style="border:1px solid #d0d7de; border-radius:4px;">

14. Review and confirm the Business Goals and Success Criteria, then proceed.
<br><img src="images/Step14.png" style="border:1px solid #d0d7de; border-radius:4px;">

15. Click the **Generate Requirements** button to generate the workflow requirements.
<br><img src="images/Step15.png" style="border:1px solid #d0d7de; border-radius:4px;">

16. Review the generated requirements and confirm them.
<br><img src="images/Step16.png" style="border:1px solid #d0d7de; border-radius:4px;">

17. The Webagent has created a requirements document. Read through it carefully and click **Generate Specification**.
<br><img src="images/Step17.png" style="border:1px solid #d0d7de; border-radius:4px;">

18. Read through the generated specification and click **Generate Solution**.
<br><img src="images/Step18.png" style="border:1px solid #d0d7de; border-radius:4px;">

19. Review the generated workflow overview. Click on **Invoice-approval-workflow** to open the n8n workflow editor.
<br><img src="images/Step19.png" style="border:1px solid #d0d7de; border-radius:4px;">
<br><img src="images/Step19_2.png" style="border:1px solid #d0d7de; border-radius:4px;">

20. In the n8n workflow editor, delete the **Outlook** and **MS Teams** notification nodes.
<br><img src="images/Step20.png" style="border:1px solid #d0d7de; border-radius:4px;">

21. This is the final workflow model ready for deployment.
<br><img src="images/Step21.png" style="border:1px solid #d0d7de; border-radius:4px;">

22. Click the **Deploy** action and confirm by clicking the **Deploy** button in the confirmation dialog.
<br><img src="images/Step22.png" style="border:1px solid #d0d7de; border-radius:4px;">

23. A toast message confirms that deployment has started. Click **View deployment history**.
<br><img src="images/Step23.png" style="border:1px solid #d0d7de; border-radius:4px;">

24. Click **View logs** to monitor deployment progress.
<br><img src="images/Step24.png" style="border:1px solid #d0d7de; border-radius:4px;">

25. The log confirms a successful deployment of your invoice approval workflow.
<br><img src="images/Step25.png" style="border:1px solid #d0d7de; border-radius:4px;">

## Summary

You have successfully created and deployed an invoice approval workflow in Joule Studio using SAP-managed n8n. The workflow validates incoming invoices, routes them for approval to an AP Clerk, and logs the outcome.

Continue to - [Exercise 2 - Create and Deploy a Custom Agent](../ex2/README.md)
