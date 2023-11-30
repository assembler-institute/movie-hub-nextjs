`#react` `#nextjs` `#CI` `#CD` `#vitest` `#movies` `#jenkins` `#frontend` `#typescript` `#react-testing-library` `#assembler-institute-of-technology` `#master-in-software-engineering`

# 🎬 MovieHub: Comprehensive Next.js Development with CI/CD and Testing

## 📝 General Description

MovieHub is an educational project tailored for students keen on exploring Next.js, a cutting-edge JavaScript
development framework. This project revolves around transitioning an existing React.js application to Next.js, enabling
students to engage with the distinct advantages and capabilities of Next.js. These include Server-Side Rendering (SSR),
file-system-based routing, streamlined data fetching, and Static Site Generation (SSG).

As part of this transition, MovieHub will evolve into a comprehensive learning experience, extending beyond basic
development into the realms of Continuous Integration/Continuous Deployment (CI/CD) and advanced testing methodologies.
The project will incorporate the implementation of CI/CD processes using Jenkins, focusing on automating testing and
deployment workflows. This includes setting up a development workflow for automatic testing and deployment upon each
commit to a 'develop' branch, and a production workflow for controlled deployment from 'develop' to 'main' branch,
reflecting real-world software development practices.

The core functionality of the MovieHub application will serve as a practical platform for tracking movies that users
have watched. Each movie will feature essential details such as name, rating, and genre. Users will have the capability
to perform CRUD (Create, Read, Update, Delete) operations on this movie list. This practical application will allow
students to apply their learning in Next.js development, CI/CD processes, and testing in a real-world scenario, making
MovieHub an all-encompassing project for modern web development education.

## 🗄 Data Model

In this project, we will mainly work with three collections or entities: `Users`, `Movies`, and `Genres`. Below, the
structure of each of these entities is detailed.

### 👤 Users

The `Users` collection stores information about the application users. Each user has the following fields:

- `id`: A unique identifier for the user.
- `name`: The user's name.
- `email`: The user's email address.
- `password`: The user's password, securely stored.
- `movies`: A list of movies that the user has added to their list.

### 🎬 Movies

The `Movies` collection stores information about the movies that users have added to their list. Each movie has the
following fields:

- `id`: A unique identifier for the movie.
- `name`: The movie's name.
- `poster_image`: The URL of the movie poster image, stored in Cloudinary.
- `score`: The movie's score, assigned by the user when adding the movie to their list.
- `genre`: The movie's genre, stored as a reference to the corresponding genre document.
- `sinopsis`: A brief description of the movie. **New**

### 🏷️ Genres

The `Genres` collection stores the different movie genres that users can select when adding a movie to their list. Each
genre has the following fields:

- `id`: A unique identifier for the genre.
- `name`: The genre's name.

These are the basic data models that we will use in this project. As you progress in the project, you may find the need
to add more fields or entities to support new functionalities. Remember, the goal is to learn and practice, so feel free
to experiment and make changes as needed.

## 🚀 Project Phases

The MovieHub project will be structured in distinct phases, each concentrating on a specific facet of Next.js
development and modern software practices. As students advance through the course content, they will be enhancing the
application by adding new functionalities and, where required, refactoring the code.

---

### 🛠️ Phase 1: Setup and Initial Structure

### 🎯 Learning Objectives

- Installation and configuration of Next.js
- Understanding the structure of a Next.js project

### 📋 Tasks

1. **Install Next.js**: Use the following command to install Next.js. Make sure you have Node.js and npm installed on
   your system before running this command.

    ```bash
    npx create-next-app@latest
    ```

2. On installation, you'll see the following prompts:

    ```bash
    What is your project named? my-app
    Would you like to use TypeScript? No / Yes
    Would you like to use ESLint? No / Yes
    Would you like to use Tailwind CSS? No / Yes
    Would you like to use `src/` directory? No / Yes
    Would you like to use App Router? (recommended) No / Yes
    Would you like to customize the default import alias? No / Yes
    What import alias would you like configured? @/*
    ```
   **This will create a new directory called `moviehub` with all the necessary file structure for a Next.js project.**

3. Once the installation is complete, navigate to the project folder:

    ```bash
    cd app
    ```

4. You can now run the following command to start the development server:

    ```bash
    npm run dev
    ```

   **This will start the Next.js development server, and you can view your application in the browser
   at http://localhost:3000.**

### 📂 Familiarize yourself with the directory and file structure generated by Next.js. The important files to consider are:

- **app**: This folder contains the application's routing structure using the App Router. Routes are defined here, and
  routing options are configured. You can find more information about the App Router in Next.js documentation.

- **pages**: This folder contains the application's pages. Each file in this folder represents a route in the
  application. For example, if you have a file called "about.tsx" in this folder, the "/about" route will display the
  content of that file.

- **public**: This folder is used to store static assets that will be served by Next.js, such as images, CSS files, or
  JavaScript files. Files in this folder can be accessed directly from the application's URL root.

- **src**: This folder is optional and is used to store the application's source code. Here you can place your
  components, styles, and any other files related to the application's logic.

### 🔍 Explore the main files related to routing are as follows:

- **layout**: This file defines the application's layout and is used to wrap individual pages. It may contain shared
  components like headers, footers, and navigation bars. It is useful for maintaining a consistent structure throughout
  the application.

- **page**: These files represent the application's individual pages. Each page file corresponds to a specific route in
  the application and defines the content and logic of that particular page. You can use React components and business
  logic in these files to build the page's user interface.

- **loading**: This file is used to display a loading interface while a page is loading or an asynchronous operation is
  being performed. You can customize this file to display a loading indicator or any other visual element you wish to
  show during the loading process.

- **not-found**: This file is used to display an interface when a page is not found. You can customize this file to
  display an error message or any other content you wish to show when a user tries to access a page that does not exist.

- **error**: This file is used to handle general errors in the application. You can customize this file to display
  specific error messages or take additional actions when an error occurs in the application.

- **global-error**: This file is used to handle global errors in the application. You can customize this file to display
  general error messages or take additional actions when an error occurs anywhere in the application.

- **route**: This file represents an API endpoint and is used to define the logic and behavior of a specific route in
  the application. You can use this file to handle HTTP requests, perform database operations, or other tasks related to
  the specific route.

### 📚 Additional Resources

- [Getting Started with Next.js](https://nextjs.org/docs/getting-started)
- [File System Routing](https://nextjs.org/docs/routing/introduction)

---

## 🔄 Phase 2: Migration of React Components to Next.js

### 🎯 Learning Objectives

- Understand how to migrate components and pages from React to Next.js
- Familiarize yourself with Next.js routing system, including dynamic routes

### 📋 Tasks

- **Identify Components and Pages to Migrate**: Make a list of existing components and pages in your React application
  that need to be migrated. This will help you have a systematic approach to migration.

- **Migrate Pages Considering Next.js Routing**: Before migrating individual components, start by migrating the pages of
  your React application. Keep in mind that the folder name will determine the route of the page.

  For example, if you have a `MovieList` page in React, copy the file to the `app/movies` folder and rename it
  as `page.tsx`.

    ```jsx
    // app/movies/page.js
    export default function Movies() {
      return (
        <div>
          <h1>Movies</h1>
          {/* Code to display the list of movies will go here */}
        </div>
      );
    }
    ```

  Now, this page will be available at `http://localhost:3000/movies`.

- **Migrate Individual Components**: Once the pages are in place, start migrating individual components. Create a folder
  called `components` at the root of the project if you don't have one yet. Within this folder, you can organize your
  components into subfolders based on their functionality.

  Copy the component files from your React project to the corresponding folders in your Next.js project. Make sure
  dependencies (like stylesheets or images) are also copied.

- **Optimize for Next.js**:
  Next.js extends the native [fetch Web API](https://developer.mozilla.org/docs/Web/API/Fetch_API) to allow you to
  configure
  the [caching](https://nextjs.org/docs/app/building-your-application/data-fetching/fetching-caching-and-revalidating#caching-data)
  and [revalidating](https://nextjs.org/docs/app/building-your-application/data-fetching/fetching-caching-and-revalidating#revalidating-data)
  behavior for each fetch request on the server. React extends `fetch` to
  automatically [memoize](https://nextjs.org/docs/app/building-your-application/data-fetching/patterns#fetching-data-where-its-needed)
  fetch requests while rendering a React component tree.

    ```tsx
    async function getData() {
      const res = await fetch('https://api.example.com/...')
      // The return value is *not* serialized
      // You can return Date, Map, Set, etc.
     
      if (!res.ok) {
        // This will activate the closest `error.js` Error Boundary
        throw new Error('Failed to fetch data')
      }
     
      return res.json()
    }
     
    export default async function Page() {
      const data = await getData()
     
      return <main></main>
    }
    ```

- **Implement Dynamic Routes**: Next.js offers a straightforward way to handle dynamic routes. If your React application
  had dynamic routes, like for displaying details of a specific movie, you can easily implement this in Next.js.

  To create a dynamic route, name your folder with brackets around the dynamic parameter. For example, for a movie
  details page, you could have a folder named **`[id]`** within a **`movies`** folder in your **`app`** directory.

  **[Example](https://nextjs.org/docs/app/building-your-application/routing/dynamic-routes#example)**

  For example, a movie could include the following route `app/movies/[id]/page.tsx` where `[id]` is the Dynamic Segment
  for movies id.

  `app/movies/[id]/page.tsx`

    ```tsx
    export default function MovieDetails({params}: { params: { id: string } }) {
      return <div>My Movie: {params.id}</div>
    }
    ```

  | Route                    | Example URL | params      |
                        |--------------------------|-------------|-------------|
  | app/movies/[id]/page.tsx | /movies/1   | { id: '1' } |
  | app/movies/[id]/page.tsx | /movies/2   | { id: '2' } |
  | app/movies/[id]/page.tsx | /movies/3   | { id: '3' } |

### 📚 Additional Resources

- [Components in Next.js](https://nextjs.org/docs/app/building-your-application/routing/pages-and-layouts)
- [Data Fetching in Next.js](https://nextjs.org/docs/app/building-your-application/data-fetching/fetching-caching-and-revalidating)
- [Dynamic Routes](https://nextjs.org/docs/app/building-your-application/routing/dynamic-routes)

---

## 📝 Phase 3: Understanding Forms and Mutations

1. **Objective**: Understand how to use forms and data mutations in Next.js using Server Actions.
2. **Tasks**:
    - Use SSR to fetch data.
    - Implement logic to perform CRUD operations on the movie list.

### 🛠️ How Server Actions Work

With Server Actions, you don't need to manually create API endpoints. Instead, you define asynchronous server functions
that can be called directly from your components.

Server Actions can be defined in Server Components or called from Client Components. Defining the action in a Server
Component allows the form to function without JavaScript, providing progressive enhancement.

**Enable Server Actions in your next.config.js file:**

`next.config.js`

```js
module.exports = {
    experimental: {
        serverActions: true,
    },
}
```

**Good to Know [IMPORTANT]:**

- Forms calling Server Actions from Server Components can function without JavaScript.
- Forms calling Server Actions from Client Components will queue submissions if JavaScript isn't loaded yet,
  prioritizing client hydration.
- Server Actions inherit the runtime from the page or layout they are used on.
- Currently, if a route uses a Server Action, it is required to render dynamically.

### 🔄 Revalidating Cached Data

Server Actions integrate deeply with the Next.js caching and revalidation architecture. When a form is submitted, the
Server Action can update cached data and revalidate any cache keys that should change. Rather than being limited to a
single form per route like traditional applications, Server Actions enable having multiple actions per route. Further,
the browser does not need to refresh on form submission. In a single network roundtrip, Next.js can return both the
updated UI and the refreshed data.

### 📚 How to Use Server Actions

Revalidating Data
Server Actions allow you to invalidate the Next.js Cache on demand. You can invalidate an entire route segment
with `revalidatePath`:

**Example:**

```tsx
'use server'

import {revalidatePath} from 'next/cache'

export default async function submit() {
    await submitForm()
    revalidatePath('/')
}
```

As you may have noticed, Next.js offers a very easy way to keep the application's information up to date. Always keep in
mind what type of component you are using (client component/server component) to take full advantage of the benefits
that Next.js offers.

---

## 🔐 Phase 4: Next.js with Auth0 Integration

### 🎯 Learning Objectives

- Understand how to integrate Auth0 into a Next.js application.
- Familiarize yourself with the authentication and authorization flow using Auth0.

### 📝 Tasks

1. **Set Up Auth0**: Create a new application (Regular Web App) in the [Auth0 dashboard](https://manage.auth0.com/) and
   obtain the necessary credentials (Client ID, Client Secret, Domain).

    ```bash
    # .env.local
    AUTH0_SECRET='use [openssl rand -hex 32] to generate a 32 bytes value'
    AUTH0_BASE_URL='YOUR BASE URL'
    AUTH0_ISSUER_BASE_URL='YOUR ISSUER BASE URL'
    AUTH0_CLIENT_ID='YOUR CLIENT ID'
    AUTH0_CLIENT_SECRET='YOUR CLIENT SECRET'
    ```

2. 🔄 **Configure Callback URLs**

   A callback URL is a URL in your application where Auth0 redirects the user after they have authenticated. The
   callback URL for your app must be added to the **Allowed Callback URLs** field in your Application Settings. If this
   field is not set, users will be unable to log in to the application and will get an error.

   ```
    http://localhost:3000/api/auth/callback.
   ```

3. 🚪 **Configure Logout URLs**

   A logout URL is a URL in your application that Auth0 can return to after the user has been logged out of the
   authorization server. This is specified in the returnTo query parameter. The logout URL for your app must be added to
   the **Allowed Logout URLs** field in your Application Settings. If this field is not set, users will be unable to log
   out from the application and will get an error.

    ```
    http://localhost:3000
    ```

4. 💻 **Install Auth0 SDK**

   Install the Auth0 SDK for Next.js.

    ```bash
       npm install @auth0/nextjs-auth0
   ```

5. 🔒 **Implement Authentication Routes**

   Use the SDK to add authentication routes. Create a file at `app/api/auth/[auth0]/route.js`. This is your Route
   Handler
   file with a Dynamic Route Segment.

    ```ts
        // app/api/auth/[auth0]/route.js
    import {handleAuth} from '@auth0/nextjs-auth0';
    
    export const GET = handleAuth({
        login: handleLogin({
            authorizationParams: {
                audience: 'YOUR AUDIENCE', // AUTH0_AUDIENCE
            },
            returnTo: "URL TO REDIRECT AFTER LOGIN" // Ex: "/dashboard", "/home"
        })
    });
      ```

6. 👤 **Add the UserProvider Component**

   On the frontend side, the SDK uses React Context to manage the authentication state of your users. To make that state
   available to all your pages, you need to override the Root Layout component and wrap the `<body>` tag with
   a `UserProvider` in the file `app/layout.jsx`.

7. 🖱️ **Add Login to Your Application**

   Users can now log in to your application by visiting the `/api/auth/login` route provided by the SDK. Add a link that
   points to the login route using an anchor tag. Clicking it redirects your users to the Auth0 Universal Login Page,
   where
   Auth0 can authenticate them. Upon successful authentication, Auth0 will redirect your users back to your application.

    ```tsx
    <a href="/api/auth/login">Login</a>
    ```

8. 🚫 **Add Logout to Your Application**

   Now that you can log in to your Next.js application, you need a way to log out. Add a link that points to
   the `/api/auth/logout` API route. Clicking it redirects your users to your Auth0 logout
   endpoint (https://YOUR_DOMAIN/v2/logout) and then immediately redirects them back to your application.

    ```tsx
    <a href="/api/auth/logout">Logout</a>
    ```

### 👥 **Obtain User Data**

- **Client Components**: The profile information is available through the `user` property exposed by the `useUser()`
  hook.

  ```tsx
  'use client';
  
  import {useUser} from '@auth0/nextjs-auth0/client';
  
  export default function ProfileClient() {
      const {user, error, isLoading} = useUser();
  
      if (isLoading) return <div>Loading...</div>;
      if (error) return <div>{error.message}</div>;
  
      return (
          user && (
              <div>
                  <img src={user.picture} alt={user.name}/>
                  <h2>{user.name}</h2>
                  <p>{user.email}</p>
              </div>
          )
      );
  }
  ```

- **Server Components**: The profile information is available through the `user` property exposed by the `getSession`
  function.

  ```tsx
  import {getSession} from '@auth0/nextjs-auth0';
  
  export default async function ProfileServer() {
      const {user} = await getSession();
  
      return (
          user && (
              <div>
                  <img src={user.picture} alt={user.name}/>
                  <h2>{user.name}</h2>
                  <p>{user.email}</p>
              </div>
          )
      );
  }
  ```

### 🛡️ **Protect Routes**

Learn how to protect routes and components using Auth0 utilities.

At this point, you have implemented the necessary configuration to access the user's token. We can use it in
some `server action`.

```tsx
"use server"
import {revalidatePath} from "next/cache";
import {getAccessToken} from '@auth0/nextjs-auth0';

export const removeUserAccount = async (id: string) => {
    const {accessToken} = await getAccessToken()
    const res = await fetch(`${URL}/v2/api/account/${id}`, {
        method: 'DELETE',
        headers: {
            Authorization: `Bearer ${accessToken}`
        }
    });
    if (res.ok) {
        revalidatePath('/dashboard')
    }
}
```

### 📚 Additional Resources

- [Official Auth0 Documentation for Next.js](https://auth0.com/docs/quickstart/webapp/nextjs)
- [Example of Next.js with Auth0 Integration](https://github.com/auth0/nextjs-auth0)

---

## 🚦 Phase 5: Implementing CI/CD with Jenkins

### 🔄 Introduction to CI/CD

**Learning Objective:** Understand the fundamental concepts of Continuous Integration (CI) and Continuous Deployment (
CD) and their importance in the software development lifecycle.

#### Theoretical Contents

1. **Fundamentals of CI/CD:** Understand the principles of CI/CD, its evolution from traditional development methods,
   and how it contributes to the agility and efficiency of software development.
2. **Benefits of CI/CD:** Explore how implementing CI/CD improves code quality, reduces time to market, and facilitates
   the management of multiple code versions.

#### Installation and Configuration of Jenkins

**Learning Objective:** Learn how to install and configure Jenkins as a key tool for implementing CI/CD.

#### Step 1: Jenkins Installation

Install Jenkins in the development environment following the official guide. Ensure that you meet the prerequisites and
choose the appropriate Jenkins version for your working environment.

#### Step 2: Initial Configuration of Jenkins

Once installed, perform the initial configuration of Jenkins. This includes:

- User and role creation.
- Security and permissions configuration.
- Network and accessibility settings.

#### Step 3: Installation of Essential Plugins

Install the following plugins to enhance Jenkins' functionality and support project needs:

1. **AnsiColor:** Provides support for ANSI colors in console outputs.
2. **Slack Notification Plugin:** Allows sending Jenkins event notifications to a Slack channel.
3. **NodeJS Plugin:** Facilitates running builds and scripts that require Node.js.

#### Step 4: Configuration of the NodeJS Plugin

To configure the NodeJS plugin:

1. Navigate to `Manage Jenkins > Global Tool Configuration`.
2. In the `NodeJS installations` section, add a new NodeJS installation.
3. Define an identifying name for the installation.
4. Select the desired Node.js version from the provided list.
5. Apply and save the changes.

#### Step 5: Configuration of GitHub Credentials

Configure credentials to access GitHub repositories:

1. Go to `Manage Jenkins > Manage Credentials`.
2. In the `Global credentials (unrestricted)` domain, select `Add Credentials`.
3. Choose the credential type `Username with password`.
4. Enter your GitHub username and password.
5. Add an identifying description for the credential.
6. Click `Create` to save the credential.

These steps ensure that Jenkins is correctly configured with the necessary tools and plugins to support the CI/CD
processes of the project. Additionally, integrating GitHub credentials facilitates automation and secure access
management to code repositories.

### ⛗ Definition of CI/CD Workflows

**Learning Objective:** Design and configure CI/CD workflows for development and production environments.

#### Creating a New Workflow (Job)

1. **Getting Started:** Go to `New Item` on the Jenkins dashboard.
2. **Project Type:** Select `Freestyle project`.
3. **Name the Workflow:** Assign a meaningful name to the project and click `OK`.

#### Workflow Configuration

Once the workflow is created, it should be configured according to the following sections:

#### General

- **Description:** Define a clear and concise description for the workflow.
- **Integration with GitHub:** Check the `GitHub project` option and enter the URL of the project's repository,
  e.g., `https://github.com/alejandroaperez1994g/jenkins-workflow/`.

#### Source Code Management

- **Repository Selection:** Choose `Git` as the source code management system.
- **Repository URL:** Enter the repository URL ending in `.git`,
  e.g., `https://github.com/alejandroaperez1994g/jenkins-workflow.git`.
- **Credentials:** Use the previously configured GitHub credentials.
- **Branches to Build:** Specify the branch to work on, e.g., `/develop`.

#### Build Triggers

- **Build Automation:** Check `Poll SCM` and define the schedule in cron format, such as `/5 * * * *` to run every 5
  minutes.

#### Build Environment

- **Environment Settings:**
    - Select `Add timestamps to the Console Output`.
    - Check `Color ANSI Console Output` and leave the `Ansi color map` as `xterm`.
    - Choose `Provide Node & npm bin/ folder to PATH` and specify the previously defined NodeJS installation.

#### Build Steps

In this section, define the specific steps that Jenkins will execute as part of the integration and deployment process.

1. **Add Build Step:** In the `Build Steps` section, select `Add build step`.
2. **Execute Shell Scripts:**
    - **First Step - Dependency Installation:** Add `Execute shell` and write `npm install` to install necessary
      dependencies.
    - **Second Step - Test Execution:** Add another `Execute shell` and write `npm run test` to run project tests.
    - **Third Step - Deployment to Vercel:** Add a third `Execute shell` and use the Vercel command to deploy the
      application. The command should include the Vercel token, project name, and environment variables, for
      example: `vercel --token [vercel token] --yes -n [vercel project name] --build-env [ENVIRONMENT VARIABLE NAME]=[environment variable value]`.

#### Post-build Actions

Finally, configure the actions that will be performed after the project build:

- **Delete Workspace:** In `Post-build Actions`, select `Delete workspace when build is done`. This ensures that the
  workspace is cleaned up after each build, keeping the Jenkins environment tidy and efficient.

The described steps provide a solid and detailed foundation for understanding how Jenkins works in practice. Now, you
are equipped to configure two main workflows:

1. **Development Workflow:** This flow will automatically trigger when a `push` is made to the `develop` branch on
   GitHub. Its primary function is to run automated tests and any other important development operations, such as code
   quality analysis. After successfully passing these tests, the workflow will deploy the application to Vercel in
   development mode. This allows you to see real-time changes and ensure everything works as expected before moving to
   the production phase.
2. **Production Workflow:** Unlike the development flow, this one will be manually triggered. The process involves
   merging the `develop` branch into the `main` branch, ensuring that all features and fixes are ready for release.
   Then, similar to the development workflow, tests and other necessary operations will be performed to confirm that
   everything is in order. Finally, the application will be deployed to Vercel in production mode, meaning your updates
   will be available to the general public.

These two flows provide a comprehensive understanding of how CI/CD practices can be used to improve and automate the
software development and deployment process. With this knowledge, you can configure and tailor your own workflows in
Jenkins to meet the specific needs of your projects.

### 🔔 Integration with Slack for Notifications [EXTRA]

#### Creating an Account and Channel in Slack

1. **Create a Slack Account:** Start by creating a new Slack account if you don't already have one.
2. **Create a Notification Channel:** Once inside Slack, create a new channel to receive Jenkins notifications.
   Right-click on "Channels" and select "Create."
3. **Name the Channel:** Assign an identifying name to the channel that will be specifically used for Jenkins
   notifications.

#### Configuring the Jenkins Integration Application in Slack

1. **Add Jenkins Application to Slack:** Within Slack, click on "Explore Slack," then "Apps."
2. **Search for Jenkins CLI:** In the applications menu, search for "Jenkins CLI."
3. **Add Jenkins CLI to Slack:** Select "Jenkins CLI" and click "Add to Slack."
4. **Choose the Channel:** Choose the channel you created earlier for notifications and click "Add Jenkins CI
   Integration."
5. **Final Configuration:** A window with step-by-step instructions will open to complete the integration setup.

#### Configuring Notifications in Jenkins

1. **Access Workflow (Jobs) Configuration:** Inside Jenkins, go to the configuration of the workflow you want to set up.
2. **Configure Notifications in Post-build Actions:** In the `Post-build Actions` section, add `Slack Notifications`.
3. **Choose Notification Types:** Here, you can configure what types of notifications you want to send. For example, you
   can choose options like `Notify Success`, `Notify Every Failure`, among others, to receive notifications about build
   success or failure in real-time.

With this integration, you will receive real-time notifications in Slack about the status of your workflows (Jobs) in
Jenkins. This makes it easier to track progress and respond quickly to any issues that may arise during the integration
and deployment process.

---

## 🧪 Phase 6: Implementation of Frontend and Backend Testing

**Learning Objective:** Understand the importance of testing in software development for both frontend and backend, and
become familiar with specific testing tools.

### 🖥️ Frontend Testing with Vitest and React Testing Library

**Learning Objective:** Learn to implement unit tests in the frontend using Vitest and React Testing Library.

#### Features to Test

1. **Movie Listing Component:**
    - **List Rendering Test:** Confirm that the component displays a list of movies.
2. **Movie Details Component:**
    - **Details Rendering Test:** Verify that the details of a selected movie, including title, synopsis, and ratings,
      are displayed correctly.
3. **Movie Creation Component:**
    - **User Interface Test:** Ensure that users can create a movie and that it is displayed correctly.

#### Techniques and Methodologies

- **Data Mocking:** Use simulated data to test components without relying on real-time API data.
- **User Event Simulation:** Simulate events such as clicks and text inputs to test component interactivity.
- **State and Prop Validation:** Verify that components correctly handle and render their states and props.

By focusing on these specific tests, you not only ensure that the fundamental aspects of the application work as
expected but also provide a solid foundation upon which you can build and expand your test suite as the project grows
and develops.

### ⚙️ Backend Testing with Jest

**Learning Objective:** Develop skills to write effective unit tests in a backend built with Express, TypeScript,
Prisma, and MongoDB, ensuring server functionality and robustness, and applying effective mocking techniques.

#### Features to Test

1. **Movie Management Functions:**
    - **Test Movie CRUD Operations:** Verify that Create, Read, Update, and Delete (CRUD) operations for movie
      management are performed correctly, making the correct calls to Prisma. Use mocks to simulate these interactions.
    - **Test Movie Metadata:** Ensure that movie metadata (title, director, actors, duration) is sent correctly to
      Prisma. Employ mocks to simulate these operations.

#### Techniques and Methodologies

- **Prisma Mocking:** Use mocks to simulate interactions with the Prisma database, focusing on the logic of functions
  rather than database results.
- **Isolated Testing:** Ensure that tests are unit tests and focus on individual aspects of backend logic without
  depending on the real database or other system components.
- **Call and Argument Validation:** Ensure that functions make the correct calls to Prisma methods with the appropriate
  arguments.

With this focus on unit testing, we emphasize the importance of validating backend logic in an isolated and efficient
manner, which is crucial for ensuring project quality and reliability. These tests will provide a solid foundation for
the ongoing maintenance and scalability of the application.

---

## 📚 Additional Considerations

### 🖥️ Server Components

Server Components allow you to write UI that can be rendered and optionally cached on the server. In Next.js, the
rendering work is further split by route segments to enable streaming and partial rendering. There are three different
server rendering strategies:

- Static Rendering
- Dynamic Rendering
- Streaming

### 🖱️ Client Components

Client Components allow you to write interactive UI that can be rendered on the client at request time. In Next.js,
client rendering is opt-in, meaning you have to explicitly decide what components React should render on the client.

This page will go through how Client Components work, how they're rendered, and when you might use them.

**Benefits of Client Rendering**

- Interactivity: Client Components can use state, effects, and event listeners, meaning they can provide immediate
  feedback to the user and update the UI.
- Browser APIs: Client Components have access to browser APIs, like geolocation or localStorage, allowing you to build
  UI for specific use cases.

### 🔀 [When to Use Server and Client Components?](https://nextjs.org/docs/app/building-your-application/rendering/composition-patterns#when-to-use-server-and-client-components)

Here's a quick summary of the different use cases for Server and Client Components:

| What do you need to do?                                                      | Server Component | Client Component |
|------------------------------------------------------------------------------|------------------|------------------|
| Fetch data                                                                   | ✅                | ❌                |
| Access backend resources (directly)                                          | ✅                | ❌                |
| Keep sensitive information on the server (access tokens, API keys, etc)      | ✅                | ❌                |
| Keep large dependencies on the server / Reduce client-side JavaScript        | ✅                | ❌                |
| Add interactivity and event listeners (onClick(), onChange(), etc)           | ❌                | ✅                |
| Use State and Lifecycle Effects (useState(), useReducer(), useEffect(), etc) | ❌                | ✅                |
| Use browser-only APIs                                                        | ❌                | ✅                |
| Use custom hooks that depend on state, effects, or browser-only APIs         | ❌                | ✅                |
| Use [React Component Reference](https://react.dev/reference/react/Component) | ❌                | ✅                |

---

## 📋 Requirements

To consider the project as completed and suitable for evaluation, students must meet the following minimum requirements:

### 💻 Basic Page Functionality: There must be at least the following pages in the application:

- Login page (/)
- Home page (/movies)
- Details of each movie (/movies/[id])

### 🛠️ CRUD Operations: The application must allow the following CRUD operations for movies:

- Create a new movie
- Read and display details of existing movies
- Update information of existing movies
- Delete movies
- Dynamic Routes: Dynamic routing must be implemented to access the details of each individual movie.

### 📝 Code Quality

- **Project Structure**: The code must be well-organized, with components and pages in their respective folders.
- **Naming**: The naming for variables, functions, and components must be clear and coherent.
- **Optimization**: Optimization practices must be applied, such as good use of **server components**.
- **Routing Conventions**: Next.js routing conventions (**page**, **layout**, **loading**) must be followed.

### 🛠️ CI/CD with Jenkins

- **Jenkins Workflows:** Development and configuration of two workflows in Jenkins:
    - **Development Workflow:** Automation of tests and deployment in the development environment after each push to
      the `develop` branch.
    - **Production Workflow:** Configuration for manual deployment in production, including merging from `develop`
      to `main`, test execution, and final deployment.
- **Integration of Jenkins with Slack [Extra]:** Optional configuration to send Jenkins notifications to a specific
  Slack channel.

### 🧪 Testing

- **Frontend Testing:**
    - Creation of tests for key components such as listing, detailing, and creating movies.
- **Backend Testing:**
    - Creation of tests to check the CRUD of movies.

---

## 🌟 Optional Requirements

### 🎨 Usability and Design

- **User Interface**: The user interface must be intuitive and easy to use.
- **Responsive Design**: The application must be usable on both mobile and desktop devices.

### 📚 Documentation

**README**: There must be a README file that explains how to install the project dependencies, how to run it locally,
and how to deploy it.

### 🔍 User Interface Enhancements

- **Search and Filters**: Implement a search and filter function for movies by genre, rating, etc.
- **Sorting**: Allow users to sort the movie list by different criteria such as rating, date added, etc.

### 🔧 Technical Improvements

- **Enhanced SEO**: Use Next.js features to improve the application's SEO, such as dynamic meta tags.

### 🔗 External Integrations

- **Third-Party API**: Integrate an external [API](https://developer.themoviedb.org/reference/intro/getting-started) to
  get additional details about the movies, like trailers, actors, etc.
- **Notifications**: Implement a real-time notification system, for example, to inform users when new movies are added.

### 🌐 Advanced Features

- **Dark Mode**: Implement a dark mode for the user interface.
- **Internationalization**: Add support for multiple languages in the application.

---

## 📚 Resources

- [Official Next.js Documentation](https://nextjs.org/docs)
- [Official Auth0 Documentation for Next.js integration](https://auth0.com/docs/quickstart/webapp/nextjs/01-login)
- [Official Vercel Documentation](https://www.vercel.com/docs)
- [Official Prisma Documentation](https://www.prisma.io/docs/concepts)
- [Official MongoDB Documentation](https://docs.mongodb.com/)
- [Official Jest Documentation](https://jestjs.io/docs/getting-started)
- [Official React Testing Library Documentation](https://testing-library.com/docs/react-testing-library/intro/)
- [Official Vitest Documentation](https://vitest.dev/guide/)
- [Official Jenkins Documentation](https://www.jenkins.io/doc/)

---


