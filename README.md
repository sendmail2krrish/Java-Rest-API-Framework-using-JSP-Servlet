# Java MVC with Routing

## Examples

### Route *(web/WEB-INF/config/route.json)*

```
{
    "routes": [
        {
            "url": "/",
            "type": "get",
            "action": "CmsConroller@home"
        },
        {
            "url": "/about",
            "type": "get",
            "action": "CmsConroller@about"
        },
        {
            "url": "/{page}",
            "type": "get",
            "action": "CmsConroller@page"
        },
        {
            "url": "/{page}/{post}",
            "type": "get",
            "action": "CmsConroller@pageWithPost"
        }
    ]
}
```

### Controller *(controllers.CmsConroller.java)*

```
public class CmsConroller
{
    public void home(
            HttpServletRequest request,
            HttpServletResponse response
    )
            throws IOException
    {
        response.getWriter().println("Home");
    }

    public void about(
            HttpServletRequest request,
            HttpServletResponse response
    )
            throws IOException
    {
        response.getWriter().println("About");
    }

    public void page(
            HttpServletRequest request,
            HttpServletResponse response,
            ArrayList args
    )
            throws IOException
    {
        response.getWriter().println(args.get(0));
    }
    
    public void pageWithPost(
            HttpServletRequest request,
            HttpServletResponse response,
            ArrayList args
    )
            throws IOException
    {
        response.getWriter().println(args.get(0) + " - " + args.get(1));;
    }
}
```

Thnaks, Happy coding :)<br />
Krishna Paul <sendmail2krrish@gmail.com>