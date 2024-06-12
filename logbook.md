# Logbook

## Initial Setup

**2024-05-10 10:00 AM:** Presentation Meeting of the final BackOffice version at Sharp.

- Request for the integration project made by Vinícius Gimenes.

**2024-05-15 01:00 PM:** Meeting with Vinícius about Sharp Automations.

- Discussed the integration scope and the need to connect SharpSpring with Move Desk and Uno ERP.
- Highlighted the requirement for real-time updates using webhooks.
- Emphasized the importance of automating customer analysis initiation upon status change in CRM.

**2024-05-15 01:45 PM:** Requirements Analysis - CRM <-> Backoffice with Camila.

- Mapped the customer analysis process and identified key data points needed for integration.
- Discussed the manual steps involved in the current process and opportunities for automation.

### Personal Notes and Analysis

**2024-05-16 09:00 AM:** Personal notes review.

- Analyzed the possibility of using OCR for extracting data from documents.
- Evaluated the current SLA for customer registration and approval, aiming to reduce it from 26 hours to 24 hours.
- Considered integrating solutions with the data pipeline for the company's datalake.

**2024-05-16 11:00 AM:** Drafted initial project structure and modules.

- Outlined core modules: domain, service, API, frontend, and infrastructure.
- Prioritized development tasks based on meeting discussions and personal notes.

**2024-05-17 09:00 AM:** Started project development.

- Set up the N8N automation server using Docker.
- Configured basic workflows and environment settings.
- Set up PostgreSQL database using Docker and configured connection settings.

## Recent Updates

**2024-06-11 02:00 PM:** Integration with Shopify for Lead Generation

- Decided to use the webhook trigger node in N8N instead of the Shopify trigger node for more flexibility.
- Implemented a JavaScript code node to handle the webhook data and create leads and opportunities in SharpSpring.
- Updated the development prompts for Chat GPT 4o to reflect this change.

**2024-06-11 03:30 PM:** Documentation Update

- Created the main documentation for the E-Comm module.
- Explained the integration of the 958 brand's Shopify store with SharpSpring to automate lead generation.
- Documented the two main workflows: new leads per completed checkout and management of store webhooks via the Shopify API.

**2024-06-12 10:00 AM:** Testing and Debugging

- Tested the updated workflow with webhook trigger node for checkout data.
- Debugged issues related to data extraction and API calls to SharpSpring.
- Verified the creation of leads and opportunities in SharpSpring based on the webhook data.

**2024-06-12 01:00 PM:** Final Adjustments and Deployment

- Made final adjustments to the workflow and code nodes based on testing feedback.
- Deployed the updated workflows to the N8N instance running on Docker.
- Updated the project documentation to reflect the final workflow configurations and deployment steps.

### Personal Notes

**2024-06-12 03:00 PM:** Review and Next Steps

- Reviewed the project progress and documentation.
- Planned the next steps for further integrations and automation enhancements.
- Considered potential improvements in data handling and error logging for better workflow monitoring and troubleshooting.
- 