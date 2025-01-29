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
    - Think page URLs, common app state
