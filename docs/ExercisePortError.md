# Error auto npx port different from redirect URI port.
In case someone gets the same thing that happens to me 😊. 
In my case **npx http-server** assign a different port than **8080** sometimes **8081**/**8082** depending on the ports it has busy.  This causes it to redirect to another service after getting the token and throwing an error.

## Error scenario
Service up on **8081** 
<div> <img align='right' src="https://github.com/NovoaDev/30-Days-Of-Microsoft-Graph-/blob/main/docs/res/portIssue/DiferentPortNpx.png" height="" width="300" alt="coding cat"></div>

Error when redirecting
<div> <img align='right' src="https://github.com/NovoaDev/30-Days-Of-Microsoft-Graph-/blob/main/docs/res/portIssue/Error8080.png" height="" width="300" alt="coding cat"></div>

## My solution
 Manually assign a port that is free.

 1. Modify **package.json**. 
<div> <img align='right' src="https://github.com/NovoaDev/30-Days-Of-Microsoft-Graph-/blob/main/docs/res/portIssue/PackageMod.png" height="" width="300" alt="coding cat"></div>

 2. Modify redirection **aad.portal.azure** configuration.
<div> <img align='right' src="https://github.com/NovoaDev/30-Days-Of-Microsoft-Graph-/blob/main/docs/res/portIssue/SpaaadappMod.png" height="" width="300" alt="coding cat"></div>

 3. Modify **redirectUri** in archive auth.js.
<div> <img align='right' src="https://github.com/NovoaDev/30-Days-Of-Microsoft-Graph-/blob/main/docs/res/portIssue/AuthjsMod.png" height="" width="300" alt="coding cat"></div>

Raise the service again and it worked :P 
<div> <img align='right' src="https://github.com/NovoaDev/30-Days-Of-Microsoft-Graph-/blob/main/docs/res/portIssue/200OK.png" height="" width="300" alt="coding cat"></div>