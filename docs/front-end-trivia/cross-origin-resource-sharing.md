---
sidebar_position: 2
---

# Cross-Origin Resource Sharing (CORS)

Cross-Origin Resource Sharing (CORS) is a security feature implemented by web browsers that controls how web pages in one domain can request and interact with resources hosted on another domain. The same-origin policy is a security measure that restricts web pages from making requests to a different domain than the one that served the web page. However, there are legitimate scenarios where web applications need to make cross-origin requests, and CORS provides a way to enable such interactions while maintaining security.

## How CORS Works

1. **Origin**: An origin is a combination of a scheme (e.g., HTTP or HTTPS), domain, and port. Two pages have the same origin if all three components match.

2. **Same-Origin Policy (SOP)**: By default, web browsers enforce the same-origin policy, which means that JavaScript running on a web page is only allowed to make requests to the same origin from which the page was served.

3. **Cross-Origin Requests**: When a web page makes a request to a different origin (cross-origin request), the browser sends an HTTP request with an `Origin` header indicating the origin of the requesting page.

4. **CORS Headers**: The server at the target origin must include specific HTTP headers in its response to inform the browser whether the requested resource should be shared with the requesting page. These headers include:
   - **Access-Control-Allow-Origin**: Specifies which origins are allowed to access the resource. It can be a specific origin or a wildcard (`*`) indicating that any origin is allowed.
   - **Access-Control-Allow-Methods**: Specifies the HTTP methods (e.g., GET, POST, PUT) that are allowed when accessing the resource.
   - **Access-Control-Allow-Headers**: Lists the HTTP headers that can be used when making the actual request.

5. **Preflight Requests**: For certain types of requests (e.g., those with non-simple methods or custom headers), the browser may send a preflight request with the HTTP OPTIONS method to check if the server allows the actual request. The server responds to the preflight request with the appropriate CORS headers.

CORS helps prevent malicious websites from making unauthorized requests on behalf of a user and enhances the security of web applications. Web developers need to configure their servers to include the necessary CORS headers to enable cross-origin resource sharing.

## Mock Interview Questions

### CORS Basics
**Can you explain what CORS is in simple terms, and why it's necessary for web development?**
- *Answer*: CORS, or Cross-Origin Resource Sharing, is a security feature implemented by browsers to control how web pages in one domain can request and interact with resources from another domain. It prevents unauthorized cross-origin requests, maintaining the security of web applications.

**What is the Same-Origin Policy, and how does it relate to CORS?**
- *Answer*: The Same-Origin Policy is a browser security feature that restricts web pages from making requests to a different domain than the one that served the web page. CORS is an exception to this policy, allowing controlled access to resources on different domains.

**What are the key CORS headers, and what purposes do they serve?**
- *Answer*: 
  - **Access-Control-Allow-Origin**: Specifies which origins are allowed to access the resource.
  - **Access-Control-Allow-Methods**: Lists the HTTP methods (e.g., GET, POST, PUT) allowed when accessing the resource.
  - **Access-Control-Allow-Headers**: Specifies the allowed HTTP headers for the actual request.

**When and why does a preflight request occur in CORS, and what is its purpose?**
- *Answer*: Preflight requests are sent by the browser before the actual request for certain scenarios, such as requests with non-simple methods or custom headers. The server responds to the preflight request with the necessary CORS headers, allowing the actual request to proceed.

### Real-world Scenarios
**Can you describe a situation where you had to implement CORS in a front-end project, and how did you handle it?**
- *Answer*: Share a specific project experience, discussing the challenges faced and the steps taken to implement CORS. This could include configuring the server to include the required CORS headers and handling preflight requests.

**What steps do you take when encountering CORS-related issues during development?**
- *Answer*: Discuss troubleshooting steps, including checking the browser console for CORS error messages, verifying CORS headers on the server, and potential solutions like configuring the server or using JSONP.

### Advanced Concepts
**How does CORS handle cookies, and what considerations should be taken into account?**
- *Answer*: By default, browsers do not include cookies in cross-origin requests. However, with proper server configuration (setting `Access-Control-Allow-Credentials` to true) and client-side adjustments, cookies can be included in CORS requests.

**What security implications should developers be aware of when implementing CORS?**
- *Answer*: Developers should ensure that their CORS configurations are restrictive, allowing only trusted origins. Allowing any origin (`*`) in production is generally discouraged. Additionally, protecting against Cross-Site Request Forgery (CSRF) attacks is crucial.

