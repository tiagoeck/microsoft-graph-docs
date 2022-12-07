---
title: "Various API requests for Azure AD and Entra APIs"
description: "Various API requests for Azure AD and Entra APIs."
author: "FaithOmbongi"
ms.localizationpriority: medium
ms.topic: conceptual
---
<!-- markdownlint-disable MD041-->
<!-- This file is used to manage a collection of examples for different Azure AD and Entra APIs. The snippets in the file are then pulled from IT admin docs (Azure docs) through cross-repo references. 

The example names are prefixed by the name of the IT admin file that references the example.

Do not delete or change any example name without making the required change in the IT admin and avoid broken links.
-->

# Various API requests for Azure AD and Entra APIs

## Example: Create a role assignment between a user and a role definition
<!-- Required by an example in this doc https://learn.microsoft.com/en-us/azure/active-directory/roles/custom-assign-graph  -->

<!-- {
  "blockType": "request",
  "name": "custom-assign-graph-create-roleassignment-all-directory"
}-->
```http
POST https://graph.microsoft.com/v1.0/roleManagement/directory/roleAssignments
Content-type: application/json

{
    "@odata.type": "#microsoft.graph.unifiedRoleAssignment",
    "principalId": "ab2e1023-bddc-4038-9ac1-ad4843e7e539",
    "roleDefinitionId": "194ae4cb-b126-40b2-bd5b-6091b380977d",
    "directoryScopeId": "/"
}
```

## Example: Create a role assignment where the principal or role definition does not exist

<!-- Required by an example in this doc https://learn.microsoft.com/en-us/azure/active-directory/roles/custom-assign-graph  -->

<!-- {
  "blockType": "request",
  "name": "custom-assign-graph-create-404-roleassignment"
}-->
```http
POST https://graph.microsoft.com/v1.0/roleManagement/directory/roleAssignments
Content-type: application/json

{
    "@odata.type": "#microsoft.graph.unifiedRoleAssignment",
    "principalId": "2142743c-a5b3-4983-8486-4532ccba12869",
    "roleDefinitionId": "194ae4cb-b126-40b2-bd5b-6091b380977d",
    "directoryScopeId": "/"
}
```

## Example: Create a role assignment on a single resource scope

<!-- Required by an example in this doc https://learn.microsoft.com/en-us/azure/active-directory/roles/custom-assign-graph  -->

<!-- {
  "blockType": "request",
  "name": "custom-assign-graph-create-404-roleassignment-directoryscope"
}-->
```http
POST https://graph.microsoft.com/v1.0/roleManagement/directory/roleAssignments
Content-type: application/json

{
    "@odata.type": "#microsoft.graph.unifiedRoleAssignment",
    "principalId": "2142743c-a5b3-4983-8486-4532ccba12869",
    "roleDefinitionId": "e9b2b976-1dea-4229-a078-b08abd6c4f84",
    "directoryScopeId": "/13ff0c50-18e7-4071-8b52-a6f08e17c8cc"
}
```

## Example: Create an administrative unit scoped role assignment on a built-in role definition which is not supported

<!-- Required by an example in this doc https://learn.microsoft.com/en-us/azure/active-directory/roles/custom-assign-graph  -->

<!-- {
  "blockType": "request",
  "name": "custom-assign-graph-create-404-roleassignment-auscope"
}-->
```http
POST https://graph.microsoft.com/v1.0/roleManagement/directory/roleAssignments
Content-type: application/json

{
    "@odata.type": "#microsoft.graph.unifiedRoleAssignment",
    "principalId": "ab2e1023-bddc-4038-9ac1-ad4843e7e539",
    "roleDefinitionId": "29232cdf-9323-42fd-ade2-1d097af3e4de",
    "directoryScopeId": "/administrativeUnits/13ff0c50-18e7-4071-8b52-a6f08e17c8cc"
}
```

## Example: Get role assignments for a given principal

<!-- Required by an example in this doc https://learn.microsoft.com/en-us/azure/active-directory/roles/custom-assign-graph  -->

<!-- {
  "blockType": "request",
  "name": "custom-assign-graph-filter-principalid"
}-->
```http
GET https://graph.microsoft.com/v1.0/roleManagement/directory/roleAssignments?$filter=principalId+eq+'<object-id-of-principal>'
```

## Example: Get role assignments for a given role definition

<!-- Required by an example in this doc https://learn.microsoft.com/en-us/azure/active-directory/roles/custom-assign-graph  -->

<!-- {
  "blockType": "request",
  "name": "custom-assign-graph-filter-roledefinitionid"
}-->
```http
GET https://graph.microsoft.com/v1.0/roleManagement/directory/roleAssignments?$filter=roleDefinitionId+eq+'<object-id-or-template-id-of-role-definition>'
```

## Example: Get a role assignment by ID

<!-- Required by an example in this doc https://learn.microsoft.com/en-us/azure/active-directory/roles/custom-assign-graph  -->

<!-- {
  "blockType": "request",
  "name": "custom-assign-graph-get-roleassignment"
}-->
```http
GET https://graph.microsoft.com/v1.0/roleManagement/directory/roleAssignments/lAPpYvVpN0KRkAEhdxReEJC2sEqbR_9Hr48lds9SGHI-1
```

## Example: Get role assignments for a given scope

<!-- Required by an example in this doc https://learn.microsoft.com/en-us/azure/active-directory/roles/custom-assign-graph  -->

<!-- {
  "blockType": "request",
  "name": "custom-assign-graph-get-roleassignment-filter-directoryscope"
}-->
```http
GET https://graph.microsoft.com/v1.0/roleManagement/directory/roleAssignments?$filter=directoryScopeId+eq+'/d23998b1-8853-4c87-b95f-be97d6c6b610'
```

## Example: Delete a role assignment between a user and a role definition

<!-- Required by an example in this doc https://learn.microsoft.com/en-us/azure/active-directory/roles/custom-assign-graph  -->

<!-- {
  "blockType": "request",
  "name": "custom-assign-graph-delete-roleassignment"
}-->
```http
DELETE https://graph.microsoft.com/v1.0/roleManagement/directory/roleAssignments/lAPpYvVpN0KRkAEhdxReEJC2sEqbR_9Hr48lds9SGHI-1
```

## Example: Delete a role assignment between self and Global Administrator role definition

<!-- Required by an example in this doc https://learn.microsoft.com/en-us/azure/active-directory/roles/custom-assign-graph  -->

<!-- {
  "blockType": "request",
  "name": "custom-assign-graph-delete-self-roleassignment"
}-->
```http
DELETE https://graph.microsoft.com/v1.0/roleManagement/directory/roleAssignments/lAPpYvVpN0KRkAEhdxReEJC2sEqbR_9Hr48lds9SGHI-1
```