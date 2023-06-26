<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/128564204/14.2.3%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/E918)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
<!-- default badges end -->

# ASP.NET Web Forms - How to display progress information about server-side callback processing
<!-- run online -->
**[[Run Online]](https://codecentral.devexpress.com/e918/)**
<!-- run online end -->

This example illustrates how you can inform your users about a server-side process when an operation initiated by a callback request takes too much time.

![](image.png)

In this example, a callback panel sends a request to the server and performs a long server process. 

Another callback panel sends a callback to the server every timer tick. On the server, a callback event handler gets the current operation progress and returns this value to the client.

## How to perform parallel callbacks

This approach does not work if the Session state is used. The Session state blocks parallel execution and forces parallel requests to be executed one after another because the access to the ASP.NET Session state is exclusive per session. 

To avoid this issue, you can [disable the Session](https://learn.microsoft.com/en-US/troubleshoot/developer/webapps/aspnet/development/disable-asp-session-state) state in the following ways:

- At page level, set the `EnableSessionState` property to `False`:

    ```aspx
    <%@ Page Language="C#" AutoEventWireup="true" Inherits="_Default" EnableSessionState="False" CodeFile="Default.aspx.cs" %>
    ```

    You can also set the page `EnableSessionState` property to `ReadOnly`. In this case, the Session state is enabled but not writable.

- At project level, set the `sessionState` mode key to `off` in the **Web.config** file:

    ```aspx
    <system.web>  
        <sessionState mode="Off"></sessionState>  
    </system.web>
    ```

Note that when the Session state is disabled, it is no longer possible to use Session variables. The states below can be used as alternatives:
- Application state that stores variables that can be accessed by all users of an ASP.NET application.
- Profile properties that persist user values in a data store without expiring them.
- ASP.NET caching that stores values in memory available to all ASP.NET applications.
- Cookies.
- Query string that is available from an HTTP request.


## Files to Review

* [Default.aspx](./CS/WebSite/Default.aspx) (VB: [Default.aspx](./VB/WebSite/Default.aspx))
* [Default.aspx.cs](./CS/WebSite/Default.aspx.cs) (VB: [Default.aspx.vb](./VB/WebSite/Default.aspx.vb))

## Documentation 

* [Callbacks](https://docs.devexpress.com/AspNet/402559/common-concepts/callbacks)
* [ASP.NET Session State Overview -- Concurrent Requests and Session State](https://learn.microsoft.com/en-us/previous-versions/ms178581(v=vs.140)?redirectedfrom=MSDN#concurrent-requests-and-session-state)

## More Examples → [Add links to the related examples]

* [How to display progress information about server-side callback processing (MVC)](https://github.com/DevExpress-Examples/how-to-display-progress-information-about-server-side-callback-processing-mvc-e4244)
* [How to track progress of server side processing on the client side (using HttpHandler)](https://github.com/DevExpress-Examples/how-to-track-progress-of-server-side-processing-on-the-client-side-using-httphandler-e4651)
* [How to track progress of server side processing on the client side (using HttpModule)](https://github.com/DevExpress-Examples/how-to-track-progress-of-server-side-processing-on-the-client-side-using-httpmodule-e4656)
* [Progress Bar for ASP.NET Web Forms - How to use the WebMethod attribute to display the progress of a server-side process on the client](https://github.com/DevExpress-Examples/asp-net-web-forms-progress-bar-display-server-process-progress)
