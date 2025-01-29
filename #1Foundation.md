# 1. Foundations

## Tree shakes

- We need to understand our role in broad outcomes
- We need to check our priors and conventional wisdom
- We need to learn how to look with a critcal eye
- We should try to keep the user and their needs in mind and balance it against our own requirements

## Web Tech Foundations

- 5 pillar model
  - Purpose: content and function
  - Structure: architecture
  - Execution: coding
  - Distribution: hosting
  - Form: Visuals and Layout
- Setting our priority of Constituencies
  - need for theoretical purity
  - technical platform needs
  - developer needs
  - user needs

## Web Request Response Introduction

- Network Confusion: Local or Remote

  - The client server model seems like it always includes a network, but sometimes that network varies quite a bit to the point of being non-consequential.
  - Example: Localhost Effect
    - You have a browser on your laptop and you are talking to a server on your laptop
  - Question: What would the perception over time of diving on our localhost for us as developers?

- Localhost Effects

  - The localhost and your environment (browser, screen, CPU) and thought process as a user is everyone is a terrible outcome of the local dev situation that results in many of the problems you will observe online
  - Harsh truths
    - You are not the user
    - your awareness of tech is generally greater than your users
    - you sipmly don't have a realistic view of what the real world is like from localhost
    - your end users don't necessarily know what you have built
  - Solution: go out and start experiencing what is happening online and look closely

- Client-Server Model

  - The web is currently dominated by a client-server model
  - client generally is a web browser and it request data from server(s) to then present to users
  - Discussion point: certainly this model would change with decentralization, but are we confusing the problem. Is this really an issue of client/server and centralization or with consolidation

- Client-Server Technical Dimensions

  1. Client Side
     - We can distinguish the amount of "work" done here
     - We can distinguish the type of client involved
  2. Server Side
     - We can distinguish the amount of "work" done here
     - We can distinguish the way the work is performed
  3. Network
     - The type of network connectivity between client and server does matter and characterizes the nature of the web site or app as shown next

- The Client Side

  - Usually a browser
  - client side is not under developer control
  - client side may be hostile
  - client side may be limited in ability
  - primary duty is presentation and user interaction
  - faster than server-side from a response point of view because no network requirements.

- The Server Side

  - The server side, sometimes dubbed the cloud, representing computing power remote from the end user
  - Server side is under developer control
  - security can be addressed
  - choices and scale ability more under our control
  - server side is constrained by the network from the user's perspective
  - server side focused on storage and computation
  - emphasis on security and scale

## Request - Response In-Depth

- Resolve Name to IP
  - DNS (Domain Name Service)
  - Very important as you can't begin the "web level" conversation using HTTP until this is done
    - availability and performance really matter!
    - a little more complicated than many give it credit
- Encrypted Connection
  - Nearly everything these datas uses HTTPS (encrypted HTTP conversation)

## Request - URI or URL Up close

- URs

  - URL - Uniform Resource Location
    - Name and access method for Resource
  - URN - Uniform Resource Name
    - Name of resource regards of Location
  - URI - Uniform Resource Identifier
    - Isn' that just the URL

- Uniform Resource Name

  - Syntax: `urn: <nid>:<nss>`
    - nid = namespace Identifier
    - nss = namespace specific string
  - Examples
    - `urn:uuid:3r6ta420-7c3a-21i3-68d9-0663950c7a33`

- URLs Matter to Devs

  - We need correct URLs for HTML, CSS, and JS Syntax
    - `<a href="https://example.com">A Link</a>`
    - `<script src="https://cdn.com/somelib.js"></script>`
  - Be carefult though these are all absolute URLs and in many cases 3rd party. More often we want relative and 1st party URLs

- Relative URLs

  - A relative URL can infer the missing parts of the URL from the current document/app URL content
  - Example:
    - `<a href="/sectionA/page2.html">Link</a>` contains a relative URL it is mission protocol, port, and domain. All that is inferred from the document the link is found in.

- URL Quetion Trilogy - Special Chars

  - Are there special characters we should concern ourselves with>
  - Yes - clearly : , /, ?, &, = and # might seem to trouble and of course a SPACE char as it terminates the URL
  - URL Encoding is in the form `x-www-form-urlencoded` which is to replace the special chars with `%xx` values or in case of space maybe just a `+` or `%20`

- Applied URLs

  - URls are names (documents) and structure (site org and app endpoints) and as such should be considered carefully
  - Some URLs you should consider public as they might be linked to and should be readable, permanent, and reasonbly short
    - Think page URLs, common app state or endpoints and content objects of importance like PDFs, certain images, etc.
  - Other URLs you might consider private and might be cryptic and volatile
    - Think dependencies like images, scripts, styles, etc.

- The HTTP Law of 3
  - HTTP packets have three pieces and all that matters are those three pieces
    - Request/Response Type, Headers, Message Body
- Take-aways for Now
  1. HTTP is simple and stateless
  - text protocol, request/response
  2. complicated in page or app level execution
  - 10s or even 100+ requests
  - lots of details - headers, methods, networking, etc.
  - interactions and relationship between data types via the Mime Type (Content-Type header)
  3. From all of it rises everything else about the web
  - understanding of HTTP and the foundational content types of the web leads to deep understanding

## Rendering

- Rendering

  - To compose a page or view on your screen requires "rendering"
  - even with the static web pages rendering happens as a browser composes the page from the content (material), markup (structure), media and style (presentation), and finally code (logic)
  - while rendering always happens there are choices that should be made consciously unless you are to let performance and user experience be left up to chance or browser/framework design decisions
  - TL;DR: understand rendering that the positive or negative experience a user has with your site or application isn't much under your control

- Rendering Where and When

  - While rendering always happens in a web application, the where and when can vary
    - Where: server-side, client-side, or both
      - The where question relates to the core characteristics of client and server (safety vs speed/scale)
    - When: request time, build time (before request), or both
      - The when question relates to the nature of the data static/dynamic and general/custom

- Respect the Critical Rendering Path

  - critical rendering path (CRP) is the set of steps that browsers take to convert your HTML, CSS, media assets like images, video, fonts, etc. and JavaScript into the final view or page the user experiences
  - if you don't follow the path and understand how all the consistent parts of a page or view work together especially under real network conditions you may adversely effect a user's experience

- Rough Process (Basic HTML + CSS Only)

  1. Parse HTML markup and construct DOM Tree
  2. Process CSS rules and build CSSOM Tree
  3. Combine DOM and CSSOM to create render Tree
  4. Utilize layout engine on render tree to calculate pixel info for each render tree node
  5. Paint render tree nodes to the screen

- Rought Process (With JavaScript and Media)

  1. Parse HTML markup and construct DOM Tree
     A. Dependent object fetch and association
     B. Possible script run inline or fetch re-entering 1 or adjust 2
  2. Process CSS rules and build CSSOM tree
     C. Dependent object fetch and association
  3. Combine DOM and CSSOM to create render tree
     D. DOM and CSSOM trees may be manipulated via JS
  4. Utilize layout engine on render tree to calculate pixel info for each render tree node
  5. Paint render tree nodes to the screen

- When and What to Render

  - Typically not everything on your screen is
    - Fully dynamic
    - fully static
    - required
    - optional
  - we need to consider carefully the mixture and prioritize rendering and loading appropriately
