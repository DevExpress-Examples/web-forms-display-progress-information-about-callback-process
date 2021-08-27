<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/128564204/14.2.3%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/E918)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
<!-- default badges end -->
<!-- default file list -->
*Files to look at*:

* [Default.aspx](./CS/WebSite/Default.aspx) (VB: [Default.aspx](./VB/WebSite/Default.aspx))
* [Default.aspx.cs](./CS/WebSite/Default.aspx.cs) (VB: [Default.aspx.vb](./VB/WebSite/Default.aspx.vb))
<!-- default file list end -->
# How to display progress information about server-side callback processing
<!-- run online -->
**[[Run Online]](https://codecentral.devexpress.com/e918/)**
<!-- run online end -->


<p>Sometimes a server-side operation, which is initiated via a callback request sent by the ASPxCallback control, may take much time (for instance, when a lot of data is obtained and being processed on the server). This example illustrates how you can inform your users about the server-side processing progress.</p>
<p>Note that this approach does not work if the Session state is used. It blocks parallel execution and forces parallel requests to be executed one after another because the access to ASP.NET Session state is exclusive per session. <br> Refer to the <a href="https://www.devexpress.com/Support/Center/p/KA18599">KA18599: How to perform parallel callbacks to get some information about server-side process</a> KB Article for explanation.</p>
<p><strong>See also:<br> </strong><a href="https://www.devexpress.com/Support/Center/p/E4244">How to display progress information about server-side callback processing (MVC)</a><u></u></p>
<p><u></u><a href="https://www.devexpress.com/Support/Center/p/E4651">How to track progress of server side processing on the client side (using HttpHandler)</a><u><br> </u><a href="https://www.devexpress.com/Support/Center/p/E4656">How to track progress of server side processing on the client side (using HttpModule)</a><br><a href="https://www.devexpress.com/Support/Center/p/T156786">How to track progress of server side processing on the client side (using WebMethods)</a><br><a href="https://www.devexpress.com/Support/Center/p/T518056">ASPxGridView - How to show a lengthy operation's progress and allow canceling such operations</a></p>

<br/>


