---
layout: post
title:  ".HTTP Documentation File"
date:   2024-12-01 10:35:20 +0330
categories: dotnet documentation http
---

> **Warning! To use .http files, you must have Visual Studio 2022 version 17.6 or later installed with the ASP.NET and web development environment.**

I have always had to rely on tools like Postman/Insomnia or REST Client tools to test the endpoints of API projects that do not have Swagger. Given the state of internet connectivity and the cloud-based features of these applications (especially Postman), I faced time-consuming limitations until I was recently introduced to .http files by one of my colleagues.

These files provide a very simple solution for testing API project endpoints, which I believe share some similarities with curl.

Let's take a look at an example:

First, open the project in Solution Explorer, right-click on the folder where you want to create the file, and select .http from the available options:

![create .http file](../assets/images/thoughts/2024-12-01-dotnet-http-documentation-file/baqxskqlen5g.webp)

To test, we can use the endpoints from the reqres.in website:

 
 `GET https://reqres.in/api/users?page=2`

You can test it using the "Send Request" button above the GET.

![Send Request Button for Calling the Endpoint](../assets/images/thoughts/2024-12-01-dotnet-http-documentation-file/onevrv8uspqx.webp)

The result will be displayed next to the file in this format:

![Result of Calling One of the Endpoints
](../assets/images/thoughts/2024-12-01-dotnet-http-documentation-file/t7y9y1przncu.webp)

![Detailed Result of Calling One of the Endpoints
](../assets/images/thoughts/2024-12-01-dotnet-http-documentation-file/shuxvoicj2g5.webp)

Now, what if we need to add a header?

To add a header, we can use the following method:
 
```
  GET https://reqres.in/api/users?page=2
  Age: 100
```

In the results section, we can verify that our header was sent:

![Checking the Presence of Header in the Request We Sent
](../assets/images/thoughts/2024-12-01-dotnet-http-documentation-file/qzx6qztsjxfi.webp)

To send a body, we can use the following method:

 ```
POST https://reqres.in/api/register
Content-Type: application/json

{
  "email": "eve.holt@reqres.in",
  "password": "pistol"
}
```

Let’s take a look at the POST request along with the inputs.

![POST Request with Inputs
](../assets/images/thoughts/2024-12-01-dotnet-http-documentation-file/dlos3mwyknm6.webp)

Finally, let's review the output together.

![POST Request with Inputs Output
](../assets/images/thoughts/2024-12-01-dotnet-http-documentation-file/zgbws0az6p8y.webp)

## Advantages

- Default installation in Visual Studio 2022
- Ability to save endpoints and related information
- API document sharing in .HTTP format

## Disadvantages

- Lack of history maintenance for called endpoints
- Does not support all features of REST Client (like the Rest Client extension in Visual Studio Code)

## Conclusion
This new feature in Visual Studio 2022 has helped me quickly test endpoints without the need for any additional dependencies, and if necessary, easily share these endpoints with my colleagues by creating this file in the project. However, in certain use cases, its limitations may hinder its usefulness.

I highly recommend studying this feature further.

### Source
[Microsoft Documentation](https://learn.microsoft.com/en-us/aspnet/core/test/http-files)


