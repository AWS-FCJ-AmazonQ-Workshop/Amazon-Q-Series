---
title: "Replatforming with Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 3.5.2. </b> "
---

Suppose you have an existing ASP.NET 8 Web API running on a Windows-based container. You want to replatform it to run on Linux for better portability and cost efficiency.

##### Example: Dockerfile Migration

**Step 1:** Create a new file called `Dockerfile` in VSCode and paste in your existing Windows-based Dockerfile:

```dockerfile
FROM mcr.microsoft.com/dotnet/aspnet:8.0-windowsservercore-ltsc2022 AS base
WORKDIR /app
EXPOSE 6268

ENV ASPNETCORE_URLS=http://+:6268

FROM mcr.microsoft.com/dotnet/sdk:8.0-windowsservercore-ltsc2022 AS build
ARG BUILD_CONFIGURATION=Release
WORKDIR /src
# ...rest of your Dockerfile
```

**Step 2:** Use Amazon Q Developer to suggest changes for running on Linux (e.g., update base images, environment variables, and file paths).

**Step 3:** Review and test the new Dockerfile to ensure your app runs correctly on Linux.

![alt text](/images/3-sdlc/3.5-maintain/3.5.2-replatforming/image.png?width=40pc)

#### Best Practices
- Always test replatformed applications in a staging environment
- Update documentation to reflect new platform requirements
- Monitor for platform-specific issues after migration