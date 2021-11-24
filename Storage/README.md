# Storage in Web
## Cookie, session

### Example
- HTTP is stateless. You need a way to store user data between HTTP requests.
- Cookies or URL parameters are both suitable ways to transport data between 2 or more request. However they are not good in case you don't want that data to be readable/editable on client side.
- The solution is to store that data server side, give it an "id", and let the client only know (and pass back at every http request) that id. There you go, sessions implemented.

### Explaination table
|Name               | Session      | Cookie |
|--------           | ----------- | ----------- |
|1. Storage| It stores in server(database, system's disk)      | It stores in browser's client       |
|2. Initialize| It creates in the first request        | It is created by server. And, browser receives in the first respond.|
|3. Ending the lifetime| The user terminate|When the time stated in the 'expires' attribute of a cookie occurs.|
|| Timeout|When a browser is closed if a corresponding setting is enabled.|
|| | A cookie with no expiration date specified will expire when the browser is closed.(cookie session)|

### Some tips
- **How the session can reuse the value in last session in order to know all information about website?** -> when the visitor returns, your application could retrieve the cookie and use its information to display the team logo in a banner.
- The handler checks the request for the session cookie. If the request does not include the cookie, the handler generates a new session ID.
- **Do not store too much data on Server**, it leads to **waste a lot of memory** in **db**. Also, it can cause **the escalation of the traffic** in case **storing** countless data **in user-side**.

### Good Reference: 
- https://thoughtbot.com/blog/lucky-cookies
- https://docs.oracle.com/cd/E29542_01/doc.1111/e29634/dev_sessions.htm#WBCSD1268
- https://docs.microsoft.com/en-us/aspnet/web-api/overview/advanced/http-cookies
- https://asp.mvc-tutorial.com/vi/479/httpcontext/cookies/
- [How the session works](https://stackoverflow.com/questions/3804209/what-are-sessions-how-do-they-work?rq=1) (**Will highly recommend to read if you still get confused why we need the session. Wanna clarify the important of session**)
- [How does web session work with illustration](https://machinesaredigging.com/2013/10/29/how-does-a-web-session-work/) (**must read**)