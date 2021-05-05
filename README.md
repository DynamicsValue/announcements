# Announcements

We're pleased to announce a new upcoming version of FakeXrmEasy v2.x that targets .net core. 

Use this repository to track important changes that are coming out soon and that will make your migration path easier even before v2 is finally public.

You can also track important updates on [FakeXrmEasy's Twitter page](https://twitter.com/FakeXrmEasy)

## Middleware

We're effectively rewriting FakeXrmeasy in v2. 

Among the nice upcoming features, one is a new middleware that will make the framework fully configurable. In order to make the v2 migration smoother, it'll be a whole lot easier for you if you start moving **TODAY** your XrmFakedContext classes to the constructor of your base test class, like [shown in this repo](https://github.com/DynamicsValue/power-platform-dev-saturday/blob/master/test/WebCdsWithFakeXrmEasy.UnitTests/FakeXrmEasyTestsBase.cs):

```csharp
    public class FakeXrmEasyTestsBase
    {
        protected readonly IOrganizationService _service;
        protected readonly IXrmFakedContext _context;

        public FakeXrmEasyTestsBase()
        {
            _context = XrmFakedContextFactory.New();
            _service = _context.GetOrganizationService();
        }
    }
```

We're looking forward to see what you'll build in v2!
