### MicroboxLabs Backend Challenge: Task Management System (Java Quarkus)
This technical test requires you to design and implement a **Task Management System backend** using **Java Quarkus**. The backend will help MicroboxLabs manage tasks by creating, assigning, and tracking the progress of tasks assigned to individual users or groups.

#### **Before You Begin**
Create a private GitHub repository and invite the provided collaborators: `@korutx`, `@odtorres`. Should you have any questions, contact `devtest@microboxlabs.com`.  
**Title of the project**: Backend-Test-(Last Name)

#### **Problem Description**
MicroboxLabs requires a backend solution to manage tasks, assign them to individuals or groups, and track their progress. The system should allow **Admins** to create and assign tasks while **Regular Users** can manage their assigned tasks, marking them as complete and updating their progress.

#### **Core Requirements**
The goal is to create a **Java Quarkus** backend application that provides REST API endpoints for managing tasks, user roles, and tracking task status. The key features are as follows:

### **API Features**
1. **Task Creation and Assignment (Admin Only)**
   - Create an API endpoint (`/api/tasks`) to create a new task. The required fields are:
     - **Title**: The name of the task.
     - **Description**: Details about the task.
     - **Assigned To**: Either a **user** or a **group**.
     - **Due Date**: Date by which the task must be completed.
     - **Priority**: Low, Medium, High.
   - Tasks can be assigned to either a **specific user** or a **group** of users (e.g., "Frontend Team").

2. **View All Tasks (Admin Only)**
   - Create an API endpoint (`/api/tasks/all`) for Admin users to view all tasks.
   - The endpoint should support filtering by **status** (e.g., Pending, In Progress, Completed) and **assignee** (user or group).

3. **View Assigned Tasks (Regular User)**
   - Create an API endpoint (`/api/tasks/assigned`) to allow **Regular Users** to view tasks assigned specifically to them or their group.
   - The response should include **task title**, **description**, **due date**, **priority**, and **status**.

4. **Update Task Status (Regular User)**
   - Create an API endpoint (`/api/tasks/{taskId}/status`) to allow users to **update the status** of a task.
   - Status options include:
     - **Pending**: Task is newly created.
     - **In Progress**: Task is currently being worked on.
     - **Completed**: Task has been finished.

5. **Add Comments to Tasks (Regular User)**
   - Create an API endpoint (`/api/tasks/{taskId}/comments`) to allow users to **add comments** to a task for better communication.

### **Database Requirements**
- Use a lightweight database (e.g., **H2** or **PostgreSQL**) to store tasks.
- Each task should have the following fields:
  - **ID** (auto-generated)
  - **Title**
  - **Description**
  - **Assigned To** (user ID or group ID)
  - **Due Date**
  - **Priority** (Low, Medium, High)
  - **Status** (Pending, In Progress, Completed)
  - **Comments** (list of comments)

### **Authorization**
- Implement **basic authorization** to distinguish between **Admin** users and **Regular** users:
  - **Admin User**: Allowed to create, view, and assign tasks.
  - **Regular User**: Allowed to view assigned tasks, update status, and add comments.

### **Technologies and Tools to Use**
- **Backend Framework**: Quarkus (Java).
- **Database**: H2 or PostgreSQL for storing tasks.
- **RESTful API**: Use **Quarkus RESTEasy** to implement the endpoints.
- **Security**: Implement basic authentication using **Quarkus Security**.

### **Use Cases**
1. **Admin Creates and Assigns a Task**:
   - An **Admin** user calls the `/api/tasks` endpoint to create a new task.
   - The task is then assigned to either an individual user or a group, and stored in the database.

2. **Viewing All Tasks (Admin Only)**:
   - An **Admin** makes a GET request to `/api/tasks/all` to view all tasks.
   - The Admin can filter by **status** or **assignee** to get a better overview.

3. **Viewing Assigned Tasks (Regular User)**:
   - A **Regular User** makes a GET request to `/api/tasks/assigned` to view tasks assigned to them.
   - The user can see details such as **due date**, **priority**, and **status**.

4. **Updating Task Status**:
   - A **Regular User** calls the `/api/tasks/{taskId}/status` endpoint to update the task’s status to **In Progress** or **Completed**.

5. **Adding Comments to a Task**:
   - A **Regular User** makes a POST request to `/api/tasks/{taskId}/comments` to add a comment like "Started working on this task".

#### **Aspects to Be Evaluated**
1. **Functionality**:
   - Does the solution meet all the core requirements?
   - Are users able to create, view, assign, and manage tasks effectively?
2. **Software Design**:
   - Proper use of Quarkus features and logical organization of code.
   - Clean separation between data, business, and presentation layers.
3. **Code Quality**:
   - Readable and maintainable code with meaningful comments.
   - Effective use of modern Java and Quarkus features.
4. **Testing**:
   - **Unit Tests** for creating, updating, and managing tasks.
   - **Integration Tests** for the API endpoints.
5. **Documentation**:
   - Clear instructions on how to set up and run the project.
   - In-line comments for complex parts of the code.

#### **Aspects to Ignore**
- **Deployment**: Focus on local execution and testing rather than deployment.
- **Advanced Security**: Keep authentication simple, as the emphasis is on functionality.

#### **Optional Bonus Points**
- **Swagger Documentation**: Use **Quarkus OpenAPI** to add Swagger documentation for the API.
- **Real-Time Notifications**: Add support for real-time updates using **Server-Sent Events (SSE)** or WebSockets to notify users when a task status changes.

#### **Getting Started**
1. **Fork/Clone** the repository.
2. Set up a **Quarkus** project and configure your chosen database.
3. Implement the required REST API endpoints.
4. Use any tools or resources, including AI (e.g., ChatGPT or GitHub Copilot), to assist you.

This task is designed to evaluate your ability to create a **Java Quarkus backend** for a task management system, focusing on REST API creation, database integration, and effective use of the Quarkus framework.
