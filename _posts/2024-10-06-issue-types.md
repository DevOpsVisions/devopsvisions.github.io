---
layout: post
title:  "GitHub Issue Types (Public Preview)"
date:   2024-10-06 07:00:05 +0100
author: Rehab Ragab     
categories: [Blogging, Post]
tags: [github, issues] 
---

Issues are the way to plan, discuss and track your work inside GitHub. GitHub introduced a significant evolution of Issues, one of the most exciting being the new `Issue Types` feature.

Issue Types enables you to classify and manage different types of issues across all repositories in your organization.

> Issue Types are currently available in an opt-in beta for organizations. To add your organization to the waiting list, sign up here [Join the GitHub Issues Waitlist](https://github.com/features/issues/signup)
{: .prompt-tip }

In this blog post, we will Learn more about Issue Types and how to manage them in your organization.

As an organization admin, you can customize the Issue Types for the organization by adding, editing, disabling, or deleting them.

## Adding an Issue Type

1. Click **Settings** within your organization
2. In the "Code, planning and automation" section, select **Planning**, then click **Issue Types**
3. On the right-hand side, click **Create new type**
4. Under "Type name", add the name of the new Issue Type
5. Under "Description", add a description for the new type
6. Under "Color", select the color you would like
7. If you would like to prevent this new type from being assigned to issues created in public repositories, click **Private repositories only**
8. Click Create

   ![Create New Type](/assets/img/issue-types/1-create-new-type.png)

   ![Create New Type](/assets/img/issue-types/2-create-new.png)

## Making changes to Issue Types (Edit, Disable, Delete)

### Editing an Issue Type

You can edit Issue Type, by changing it's name, description, color, or restricting its use in public repositories.

1. Click the tree dots (...) of the Issue Type, you would like to edit
2. In the menu, click **Edit**
3. Edit name, description, color, or public repository visibility
4. Click **Save**
5. If you want to discard any changes, click **Revert changes**

   ![Type Options](/assets/img/issue-types/3-type-options.png)

   ![Revert Changes](/assets/img/issue-types/4-edit-save-revert.png)

### Disabling an Issue Type

If an Issue Type is no longer relevant, you can disable it. Once you disabled, it will no longer be available to use across your organization. If you re-enable it in the future, it will be preserved on existing issues of this type unless a different type has been added.

1. Click the tree dots (...) of the Issue Type, you would like to disable
2. In the menu, click **Disable**
3. Confirm by clicking **Disable** in the prompt

   ![Disable](/assets/img/issue-types/5-disable.png)

### Deleting an Issue Type

If an Issue Type is completely obsolete, you can permanently delete it. Once you delete it, it will be removed from all issues across the organization.

1. Click the tree dots (...) of the Issue Type, you would like to delete
2. In the menu, click **Delete**
3. Confirm by clicking **Delete** in the prompt

   ![Delete](/assets/img/issue-types/6-delete.png)

> Once you delete the Issue Type, it can't be restored
{: .prompt-danger }

## Adding a Type to an Issue

When creating a new issue, you can easily assign an Issue Type:

1. In the `Type` dropdown menu, select the appropriate Issue Type.

   ![Issue by Type](/assets/img/issue-types/7-create-issue-by-type.png)

   ![Multi Issues](/assets/img/issue-types/8-multi-issues-with-types.png)

> You can use the new **Create more** button to quickly create multiple issues without being redirected to the issue details page. This feature keeps you on the issue creation page, enabling you to efficiently add multiple issues back-to-back.
{: .prompt-tip }

## Changing Issue Type

To change the Issue Type for a single issue:

1. Open the issue, click on the `Type` dropdown menu, and select the new Issue Type you'd like to assign.

   ![Change Type](/assets/img/issue-types/9-change-single-issue-type.png)

You can also change the Issue Type for multiple issues at once:

1. Select the issues, then from the `Issue Type` dropdown, and select the new Issue Type you'd like to assign.

   ![Change Type](/assets/img/issue-types/10-change-multi-issue-type.png)

## Filtering Issues by Type

You can filter issues by their type to quickly find and manage relevant issues. In the issues view, use the `Issue Type` field to apply this filter.

1. From the filter bar, type `type`, then select the desired Issue Type.
2. Alternatively, use the `Types` dropdown menu to select the type you would like to filter by.
  
   ![Filter by Type](/assets/img/issue-types/11-filter-by-type.png)


## Creating custom views in your project

You can customize your project views by using the new `Type` field to filter, slice, or group issues based on their type.

### Group by Type

1. From your view, select **Group by:**
2. Select **Type**

   ![Group by Type](/assets/img/issue-types/12-group-by-type.png)

   ![Group by Type](/assets/img/issue-types/13-group-by-view.png)

### Slice by Type

1. From your view, select **Slice by:**
2. Select **Type**

   ![Slice by Type](/assets/img/issue-types/14-slice-by.png)

   ![Slice by Type](/assets/img/issue-types/15-slice-by-view.png)

## Auto-add to project workflow

You can set up a workflow that automatically adds issues to your project based on their type:

1. Within your project, click the three dots (...)
2. Click on **Workflows**
   
   ![Automation Workflow](/assets/img/issue-types/16-automation-workflow.png)

1. On the left, under the list of default workflows, click **Auto-add to project**.
2. Click **Edit**
   
   ![Auto Add to Project](/assets/img/issue-types/17-auto-add.png)

1. Inside the filter input, type `Type`, then select the Issue Type you would like to filter by. You can filter by `Has type`, `No Type`, `Exclude Type`, or select a specific type.

   ![Type Filter](/assets/img/issue-types/18-auto-add-type-filter.png)

2. Click **Save and turn on workflow**

   ![Auto Add to Project](/assets/img/issue-types/19-auto-add-save.png)

   ![Auto Add to Project](/assets/img/issue-types/20-auto-add-test.gif)

> **Example:** If your filter is set to `is:issue type:"Bug"`, this means whenever you create a new issue of type **Bug** in your selected repository, that issue will automatically be added to your project.
{: .prompt-tip }

## Conclusion

The introduction of Issue Types in GitHub marks a significant improvement in how teams can classify, manage, and track their work. 

If you're interested in trying out Issue Types for your organization, you can [sign up](https://github.com/features/issues/signup) for the public preview.

You can watch the following video that walks you through all the steps explained in this post.

[![Public Session](/assets/img/issue-types/21-session.png)](https://www.linkedin.com/events/7234094335183536128)






