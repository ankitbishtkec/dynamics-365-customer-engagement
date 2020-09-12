---
title: "Map form data to entities with custom Workflows (Dynamics 365 Marketing) | Microsoft Docs"
description: "Learn how to map form data to entities with custom Workflows"
keywords: customer journey
ms.date: 09/09/2020
ms.service: dynamics-365-marketing
ms.custom: 
  - dyn365-marketing
ms.topic: reference
ms.assetid: 57e1c0f7-a12e-49ff-9110-0dcaae176855
author: alfergus
ms.author: alfergus
manager: shellyha
ms.reviewer:
topic-status:
search.audienceType: 
  - admin
  - customizer
  - enduser
search.app: 
  - D365CE
  - D365Mktg
---

# Map form data to entities with custom Workflows

If you have configured a marketing form to collect form submissions without updating contacts or leads, you can create a Workflow to map the form submission data to any entity.
- Learn more about collecting form data without updating contacts or leads: [Create, view, and manage marketing forms](marketing-forms.md#do-not-createupdate-contacts-or-leads)
- Learn more about building workflows: [Use Workflow processes to automate processes that don't require user interaction](https://docs.microsoft.com/dynamics365/customerengagement/on-premises/customize/workflow-processes)

## Creating a Workflow

Create a Workflow to extract the values from a form submission. You can use this data to create a custom entity or to create or update any existing entity.

To create a Workflow:

1. Go to **Process Center** > **Processes** in Dynamics 365 Customer Engagement (on-premises) this path is easiest to access and allows you to use views defined for the Process entity, including any custom views.

    ![Go to the Process center](media/entity-mapping-process-center.png "Go to the Process center")

1. Create new blank process, set the **Category** to **Workflow**, and add the entity that triggers your workflow. In this case, we'll add the Marketing form submission.

    ![Create a Workflow](media/entity-mapping-create-process.png "Create a Workflow")

1. Next, you will start adding steps to your Workflow. You will find flexible options to handle entities under **Add Step** > **Dynamics 365 Marketing**

    For example, you can start with **Extract a submitted value by field** to find a value inside a submission that you would like to store. Add a **Match entity** step to match the marketing form submission to the entity that you want to update. Add a **Json set property** step to be used in the other steps’ JSON properties.

    ![Add steps to your Workflow](media/entity-mapping-add-step.png "Add steps to your Workflow")