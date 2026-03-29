# Blooket Link Proxying
This is a simple guide on how to use the `blooket.com` domain to proxy static sites (GET requests)
## Basic Format
1. Take any Blooket game-mode host, for example:
   - `https://cafe.blooket.com`
2. Append `/gs/`
3. Make sure your app is plain `http`, not `https`, so no auto https redirs
4. Base64 encode that `http` origin (do not include protocol)
5. Put it after `/gs/`

Example:
- Original app origin:
  - `5.188.124.67:8080`
- Base64:
  - `NS4xODguMTI0LjY3OjgwODA=`
- Final URL:
  - `https://cafe.blooket.com/gs/NS4xODguMTI0LjY3OjgwODA=/`

**make sure you include the forward slash (/) at the end**
## requests
- Your site must be fully static
- The encoded target is expected to be an `http` origin, not `https`
- Do not rely on runtime path guessing from the current URL cus this breaks

## path
If your app is deployed under a Blooket path like:
- `/gs/NS4xODguMTI0LjY3OjkwMDA=/`

then asset URLs must be built against that exact path.

## Compatibility
this ONLY supports GET requests, no WebSocket or POST request will work
