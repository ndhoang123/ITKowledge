# MVC
## MVC request life cycle
- The incoming request from IIS pipeline is handed over to URL Routing module in which looks up the route in Routing table.
- It the route is found in the routing table, **MVC Routehandler** will execute and bring the instance of **MVCHttpHandler**.
- MVC handler begins initializing and executing controller.
- After the controller instance is created, the next major step is to find and execute the corresponding action. A component called **ActionInvoker** finds and executes the action defined in the routing table.
- Before the action method is called, the model binding takes place which maps data from http request to action method parameters.
- After the model binding, action filters are invoked which includes OnActionExecuting filter. This is followed by action execution and Action Executed filter execution and finally preparing Action Result.
## Application life cycle
- MVC Application life cycle contains two application level events that are associated with start and end events of the application.
- The URL Routing handler gets the collection of predefined routes to map from by using Application start event.
- MVC application provide these events in Global.asax which contains all the application level levels.
- In the ASP.Net MVC: Hosted within IIS, ASP.NET apps rely on IIS to instantiate certain objects and call certain methods when a request arrives. ASP.NET creates an instance of the Global.asax file's class, which derives from `HttpApplication`. When the first request is received, before handling the request itself, ASP.NET calls the `Application_Start` method in the Global.asax file's class.
## HttpHandlers
- HttpHandlers are classes that implements IHttpHandler and generate a response to HttpRequest.
- There are two sets of events in the MVC request life cycle that concerns HttpHandlers, [MapRequestHandler and PostMapRequestHandler] and [RequestHandlerExecute and PostRequestHandlerExecute].
- MapRequestHandler and PostMapRequestHandler are the events in the life cycle which determines the HttpRequestHandler responsible for executing the request. Only the selection happens during this time.
- RequestHandlerExecute and PostRequestHandlerExecute are the life cycle events that actually executes the htttp handler determined in the earlier phases of request life cycle.
Reference:
- https://www.tektutorialshub.com/asp-net/routing-in-mvc/#where-do-the-routes-arestored
- https://docs.microsoft.com/en-us/dotnet/architecture/porting-existing-aspnet-apps/app-startup-differences
- https://docs.microsoft.com/en-us/iis/get-started/introduction-to-iis/introduction-to-iis-architecture