## Getting Started

### Prerequisite Software

- Microsoft Teams 

## App Installation Process

1. **Consent Process**:

   1. Create a user called: [medxplanner1@_____.com](mailto:medxplanner1@_____.com) and make sure `medxplanner1` is all small.
   2. Now hit this end point [https://medxprod-api-consent-service.medx.im](https://medxprod-api-consent-service.medx.im) and sign-in with above credentials.
   2. For admin approval click `Have an admin account? Sign in with that account`.
   3. Sign in with your Admin credentials and accept all the permission.
   4. Sign in again using your medxplanner1 email created earlier.
   
2. **Tab Configuration**:

   1. Use MS Teams browser version to run the application.
   2. Go to the upper tab click `+`, search and add `MedxPlanner` tab to your team.
   3. Create a bucket, if already created then skip.
   4. In the form shown, go to **Dropdown of an existing plan or new plan** and select **New Plan**.
   5. Enable shift, if you use Microsoft Shifts.
   6. **Important:** Click button before saving.

######  Bravo!! tab configuration completed. Get ready to add tasks.

## Add Task using either of the options

**Option 1:** **Postman Overview**

   API Endpoint: [https://medxprod-api-task-service.medx.im/medxtask](https://medxprod-api-task-service.medx.im/medxtask)

   ```
   $ Authorization : Get this from MedxPlanner tab as "API Key",  Example: a55c65d0-d466-480d-9ea9-72b621e0a307
   $ userId: Get this from MedxPlanner tab as "User ID", Example: b8c43f7a-7bc3-4e6f-978b-050e7448a522
   $ routeId: Get this from the MedxPlanner tab as "ID" under route list, for the route which you want to send the task too, Example: 2ebd0508-ef81-4d5f-9f32-07d11a31ee20
   $ tenantId: Click on the ellipsis on the right of Team and click on "Get a link to team", Just Copy your "tenantId". Example: tenantId=5df91xxx-xxxx-xxxx-xxxx-bdc0cba3xxxx
   $ startDateTimestamp example: 2021-01-04 15:12:12Z
   $ hospitalReference: medxtask_a06a7b53-e384-4433-b274-2e4b2712b726
   ```
### Sample Template

   1. Select the request as `POST` and paste the above endpoint.
   2. Under Authorization, select type as `Bearer Token` and paste the above Authorization (`API Key`).
   3. Go to `Body` and select `raw` with text as `JSON`.
   4. Update the content of the below sample bodies with `routeId`, `userId`, `tenantId`.

**Minimal Body content**

```
{
  "routeId": "7fcxxxxx-xxxx-xxxx-xxxx-5d35838xxxxx",
  "userId": "77cxxxxx-xxxx-xxxx-xxxx-5f09858xxxxx",
  "tenantId": "dcdxxxxx-xxxx-xxxx-xxxx-31002a1xxxxx",
  "title": "Task: Add you task title",
  "percentComplete": 0,
  "createdTimestamp": "2021-01-29T21:51:49Z",
  "startDateTimestamp": "2021-01-29T15:10:15Z",
  "dueDate": "2021-11-20T11:47:33.000Z",
  "Notes": "Add some useful notes here"
}

```

**Full Body content**

```
{
  "routeId": "7fcxxxxx-xxxx-xxxx-xxxx-5d35838xxxxx",
  "userId": "77cxxxxx-xxxx-xxxx-xxxx-5f09858xxxxx",
  "tenantId": "dcdxxxxx-xxxx-xxxx-xxxx-31002a1xxxxx",
  "title": "Task: Add you task title",
  "hospitalAssignment": null,
  "percentComplete": 0,
  "createdTimestamp": "2021-01-29T21:51:49Z",
  "startDateTimestamp": "2021-01-29T15:10:15Z",
  "dueDate": "2021-11-20T11:47:33.000Z",
  "Notes": "Add some useful notes here",
  "checklistItems": [
    {
      "title": "itema"
    },
    {
      "title": "itemb"
    }
  ],
  "attachments": [
    {
      "url": "https://www.google.co.in",
      "alias": "name of the file"
    }
  ],
  "comments": "null,",
  "priority": null
}

```

**Option 2:** **Message Extension**
   1. Go to, ellipsis on message conversation, and search for **MedxTasks**.
   2. Add the extension by signing in using the above credentials you created.
   3. You will see 'We didn't find any matches for you' as there is no task added by you yet.
   4. Go to, `+` button on the top-right corner, there you'll see two commands `Add Task` and `Sign Out`.
   5. Add the task using the `Add Task` command, an adaptive card will pop on the screen, fill the details and your task will be created.
   6. Now your added task will be visible on the list.
   7. You can filter the list based on the title and notes.

## To track your task

**Tab Configuration**:

   1. Go to the upper tab click `+`, search and add the `Tasks by Planner and To Do` tab to your team.
   2. Select `Use an existing plan for this team` 
   3. From the dropdown, select the plan which you created during the MedxPlanner configuration and click save.
   4. Here, anyone from the team can see all the task created to the route which you selected.
   5. Also, if you click on the task and can see all the details attached to the task.
