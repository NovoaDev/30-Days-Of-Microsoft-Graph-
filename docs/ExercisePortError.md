# Error auto npx port different from redirect URI port.
In case someone gets the same thing that happens to me 😊. 
In my case **npx http-server** assign a different port than **8080** sometimes **8081**/**8082** depending on the ports it has busy.  This causes it to redirect to another service after getting the token and throwing an error.

## Error scenario
Service up on **8081**  
![DiferentPortNpx](https://github.com/NovoaDev/30-Days-Of-Microsoft-Graph-/blob/main/docs/res/portIssue/DiferentPortNpx.png)

Error when redirecting 
![Error8080](https://github.com/NovoaDev/30-Days-Of-Microsoft-Graph-/blob/main/docs/res/portIssue/Error8080.png)

## My solution
Manually assign a port that is free.
 1. Modify **package.json**. 
![PackageMod](https://github.com/NovoaDev/30-Days-Of-Microsoft-Graph-/blob/main/docs/res/portIssue/PackageMod.png)

 2. Modify redirection **aad.portal.azure** configuration.
![SpaaadappMod](https://github.com/NovoaDev/30-Days-Of-Microsoft-Graph-/blob/main/docs/res/portIssue/SpaaadappMod.png)

3. Modify **redirectUri** in archive auth.js.
![AuthjsMod](https://github.com/NovoaDev/30-Days-Of-Microsoft-Graph-/blob/main/docs/res/portIssue/AuthjsMod.png)

Raise the service again and it worked :P 

![200OK](https://github.com/NovoaDev/30-Days-Of-Microsoft-Graph-/blob/main/docs/res/portIssue/200OK.png)
