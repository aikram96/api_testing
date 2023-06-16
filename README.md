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
*   `HTTP Status code` indicates whether a specific `HTTP request` has been successfully completed.
    *   List of `HTTP Status codes`:
        *   \[100-199\] - Informational responses
        *   \[200-299\] - Successful responses
        *   \[300-399\] - Redirection messages
        *   \[400-499\] - Client error responses
        *   \[500-599\] - Server error responses
*   A `swagger` is a set of open-source software tools for designing, building, documenting, and using the `REST` API.
*   `REST` is a limited standard for architecture.

If you do not belong to a company, you can use open-source `collections`. _For this tour guide, we will use a_ [_free-api_](https://catboys.com/api)_._

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
            *   New Collection name will be displayed
