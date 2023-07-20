## Postman

[Postman](https://www.postman.com/) is an API platform for building and using APIs. It generally simplifies each step of the API lifecycle and streamlines collaboration between team members.   
From a QA perspective, Postman can help us with, `manual testing` on the backend side, `partial automation` using _JavaScript_, and `volumetric testing`. 

This tour guide will show you how to start with `manual testing`. If you want to review `partial automation` or `volumetric testing`, do not hesitate to review the different repositories. 

### API Concepts 🛫

To run manual testing, it is necessary to have one `collection` or several `endpoints`. 

But first, we need to review some `concepts`.  

*   A `collection` is a group of folders at different levels that will help us to organize our `endpoints`.
*   An `endpoint` is an `HTTP request`.
*   `HTTP` is a protocol for communication between the client and the server.
*   `HTTP request` means to ask the server for something specific.
*   An `HTTP method` is a specific way to communicate with the server. 
    *   List of the `HTTP methods`:
        *   **GET** - ask for information from the client
        *   **POST** - send information to the server
        *   **PUT** - save information 
        *   **PATCH** - modify information
        *   **DELETE** - delete information
        *   Others - **HEAD**, **OPTIONS**, **TRACE**, etc.
*   `HTTP Status code` indicates whether a specific `HTTP request` has been completed.
    *   List of `HTTP Status codes`:
        *   \[100-199\] - Informational responses
        *   \[200-299\] - Successful responses
        *   \[300-399\] - Redirection messages
        *   \[400-499\] - Client error responses
        *   \[500-599\] - Server error responses
*   A `swagger` is a set of open-source software tools for designing, building, documenting, and using the `REST` API.
*   `REST` is a limited standard for architecture.
*   `URL` is an address locator for network resources.

If you do not belong to a company, you can use open-source `collections`.

### Tour guide on Postman 🚀

*   Create an account to use Postman.

> You can use your Google account to log-in

*   Once you are logged in, you can install the application or you can use the web version.

> I recommend using the desktop application

*   Now is the time to explore the Postman interface.
    *   On the top, you have the `hamburger menu`, back and next arrows, `Home`, `Workspaces` dropdown, API Network dropdown, and Explore
        *   Hamburger menu → File, Edit, View, and Help options
        *   Home → Home dashboard of your account. Also, you will see some links and you will be able to explore the most popular APIs.
        *   Workspaces → Will display a list of different workspaces if you have them. If not, there would" be “`My Workspace`” and the option to create more spaces.
            *   My Workspace → is your personal space, usually used for play.
    *   Once you review every general option, you can jump to “My Workspace”.
        *   On the left side, you will see `collections`, `environments`, history, and configurations.
            *   Collections → Is a group of endpoints separated by folders.
            *   Environments → Is a set of variables that are stored as key-value pairs and you can change them according to the paths.
    *   If you are on the collection view, you will see the `collection name` and the distribution of endpoints.
        *   As a new user, you can click on the `+` button:
            *   “New Collection” will be displayed.
            *   You can add requests by clicking on the down arrow and selecting `Add a request` - next to the name. (remember to take into consideration the HTTP Request methods)
                *   By default, the name will be “New Request” and the method `GET` is selected in green. If you want to change the method, click on the down arrow - next to the `GET`.
            *   You need to set an `URL`.
            *   Also, according to the type of endpoint, you should review the `params`, `auth`, `headers`, and `body`. Those elements are important in the request.
                *   The `params` are related to `query parameters`. Usually, those are attached to the end of a URL.
                *   The `auth` is related to access authorization. There are different types and you need to be sure which type is used for each endpoint.
                    *   Most common types → inherit auth from parent, no auth, API Key, Bearer Token, and Basic auth.
                *   A `header` is a part of the data packet that carries metadata or other information necessary for processing the main data. Usually, you don't need to set up something, populated according to the body and the request.
                *   The `body` is where the data should be.
                    *   Most common formats →  none, form-data, and raw.
            *   On the right side, you have the section of the `response`. 
                *   Once you send a request, you will see the information (HTTP status code, body, time of execution, response size, etc.)
    *   If you are on the environment view, you will see the `globals` section and `create an environment.`
        *   If you click on `globals`, a new tab is displayed. Here you can set up a `variable`, `type`, `initial value`, and `current value`.
            *   The `variable` is a data element that can vary according to the `value`.
            *   The `type` of variable is according to the secret or public concept. Some values can be displayed `***` for the security process.
            *   The `initial value` and the `current value` could be the same. The `current value` is the most important, especially when you want to edit new values.
        *   If you click on `Create an Environment`, a new tab is displayed. Here you can set up the name of your environment. Like the global tab, you can add, edit and delete variables according to your preference.

### Checking free API documentation ⭐

For this section, we will review the `catboys` documentation before playing on Postman.

*   Open the link below [_free-api_](https://catboys.com/api)_._
*   Identify the version `<v2.0.0>`
    *   v\[major\].\[minor\].\[patch\]
        *   When we update the `<major>` it means we made a backward compatibility-breaking change, so the API is no longer fully compatible with things that were built relying on it before. 
        *   When we add new endpoints to the API, we should update the `<minor>`version.
        *   When we fix bugs or update the response in the API, we should update the `<patch>` version.
*   Identify the Base URL `<https://api.catboys.com>`
    *   This means that you can set a variable called `base_url` and the different parameters according to the endpoint.
*   Identify how many endpoints are displayed `<7 endpoints>`
*   Identify how many HTTP methods are used on each endpoint `<only use GET method>`
*   Identify the HTTP status code `<as a GET method, the response should be 200>` 
*   Identify the body response `<when you expand the endpoints, you will be able to review the different responses>`

#### Now is time to analyze the first endpoint 🔍

The first endpoint `<ping>` and it's using the `GET` method.

The URL should be a combination of the `base_url` and the specific `route` = `<https://api.catboys.com/ping>`

There is no access authentication required, so you should set it as `No Auth`

There is no-body request, so you should set it as `None`

The HTTP status code should be `200`.

The body response format is `JSON`. - starts and ends with `{}`

```plaintext
{
"catboy_says": "rawr",
"error": "none"
"code": 200
}
```

> ### Try to do the same with the other endpoints to improve your sense of analysis. Think about the response and body structure. Check if it is possible to define the value of keys for JSON formats. Identify happy paths and try to imagine unhappy paths. Being a manual tester means being creative!

### Migrating `catboys` to Postman 🐱

*   Open your Postman application
*   Create a New Collection → `CatBoys`
*   Add a new request → `ping`
*   Create an environment → `demo`
*   Set the base\_url → [`https://api.catboys.com`](https://api.catboys.com)
*   Set the environment → `demo`
*   Set the URL → `{{base_url}}/ping`
*   Set your Auth → `No Auth`
*   Set your Body → `none`
*   Click on `Send` or press `Control + ENTER` on your keyboard.

> ### **Now is your time to migrate all the CatBoys endpoints on Postman!**

### Performing `manual testing` on Postman 🐾

This section will use the `<ping>` endpoint and different `scenarios`. But first, some definitions 

*   **Test Case → defines the steps/actions required to verify the efficacy of a “change”. “How to test?”**
*   **Test Scenario → Defines the actual function/feature/to be tested. "What to test?**
*   **Happy path → testing technique to know how the product works under perfect conditions**
*   **Unhappy path → testing technique to know what happens when things go wrong**

> ### If you are new to Manual Testing, please review the following repo \<manual-testing-begin>.

*   We need to identify the happy path → Usually if the API has documentation, the happy path is displayed on it.
    *   The response for a `GET` method should be `200`. ← happy path HTTP status code response
    *   The body response should be a `JSON` ← happy path body response format
    *   The value `catboy_says` should be a `string` ← happy path JSON value format
    *   The value `catboy_says` should be `“rawr”` ← happy path JSON value 
    *   The value `error` should be `“none”` ← happy path JSON value 
    *   The value `code` should be an `int` ← happy path JSON value format
    *   The value `code` should be 200 ← happy path JSON value 
*   We need to identify the unhappy paths:
    *   **What happens if** the URL was not correct? `<i.e. add a “**s**” at the end>.`
        *   URL = `{{base_url}}/pings`
            *   The HTTP status code should be 404
            *   The value for the `message` should be a `string` 
            *   The value for the `message` should be `“Incorrect endpoint. Please use https://api.catboys.com/endpoints for the full list of endpoints and https://catboys.com/api for our API documentation.”` 
            *   The value `error` should be `“Not found”` 
            *   The value `code` should be an `int` 
            *   The value `code` should be 404 

> ### **Now is your time to review the happy and unhappy paths for the rest of the endpoints you migrated to Postman!**

**If you want to increase your skills, please review the link** [public\_apis](https://github.com/public-apis/public-apis) **to practice with more APIs. Make sure to follow all the steps displayed on this repo.**
