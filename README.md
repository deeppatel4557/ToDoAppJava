

## Description of the app

This application is a replica of the [JavaGuides Todo App](https://www.javaguides.net/2019/10/build-todo-app-using-jsp-servlet-jdbc-and-mysql.html), which was built using JSP, Servlet, JDBC, and MySQL. However, the original app had a bug where the session was not being revalidated after the user pressed the logout button. Additionally, if the user pressed the back button after logging out, they were still able to access the features of the app. 

To address this issue, I have fixed the bug and added a session management feature to the app. This involves revalidating the username and password once the user presses the logout button, as well as preventing the user from using the back button once they are logged out.

## Technical details

The app is built using JSP, Servlet, JDBC, and MySQL. The session management feature is implemented using the HttpSession interface provided by the Servlet API. 

When the user logs in, their credentials are validated against the user information stored in the MySQL database. Once the user is authenticated, a session is created and stored in the server. The session contains information about the user, such as their username and password.

When the user logs out, the session is invalidated, and the user is redirected to the login page. Before invalidating the session, the app checks whether the session is still valid by revalidating the user's credentials. This ensures that even if the user tries to access the app after logging out, they will be redirected to the login page.

To prevent the user from using the back button once they are logged out, the app uses the response headers to set the cache-control and pragma directives. These directives instruct the browser not to cache the pages and to revalidate the page with the server on every request. This ensures that the user cannot access the pages once they are logged out, even if they try to use the back button.
