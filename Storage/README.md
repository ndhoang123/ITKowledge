# Storage in Web
## Cookie, session

1. Session, Cookies:

|Name               | Session      | Cookie |
|--------           | ----------- | ----------- |
|1. Storage| It stores in server      | It stores in browser's client       |
|2. Initialize| It creates in the first request        | It creates by server. And, browser receives in the first respond.|
|3. End| The user terminate|When the time stated in the 'expires' attribute of a cookie occurs.|
|| Timeout|When a browser is closed if a corresponding setting is enabled.|
|| | A cookie with no expiration date specified will expire when the browser is closed.(cookie session)|
- **How the session can reuse the value in last session in order to know all information about website?** -> when the visitor returns, your application could retrieve the cookie and use its information to display the team logo in a banner.
- The handler checks the request for the session cookie. If the request does not include the cookie, the handler generates a new session ID.
- Good Reference: 
    - https://thoughtbot.com/blog/lucky-cookies
    - https://docs.oracle.com/cd/E29542_01/doc.1111/e29634/dev_sessions.htm#WBCSD1268
    - https://docs.microsoft.com/en-us/aspnet/web-api/overview/advanced/http-cookies
    - https://asp.mvc-tutorial.com/vi/479/httpcontext/cookies/
    - [How the session works](https://stackoverflow.com/questions/3804209/what-are-sessions-how-do-they-work?rq=1)