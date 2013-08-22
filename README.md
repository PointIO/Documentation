Documentation
=============

To do in the code:
- switch apikey to appId in /auth

To do with hub.json:
- check respons class of /auth in every .json
- check HUBID returned by /hubs/list
- in /hubs/create 
  - Inconsistant sessionkey parameter was named Authorization in every core.json calls, or is it a second param?
  - hideusers param. What is it about?
  - visibleTabs. What is that?
- in /hubs/{hubId}/users/list
  - hideusers is boolean but was string in /hubs/create$
- in /hubs/{hubId}/shares/remove
  - roomShareId, verify how to get it from shares/list
- in /hubs/{hubId}/shares/add
  - verify how to get all the params
- in /hubs/{hubId}/folders/list
  - verify from where the parameter come from. folderid = room id or access rule id?
- in /hubs/{hubs}/details
  - which details?
- in /hubs/{hubId}/auth
  - Returns a session key?

