Documentation
=============

To do in the code:
- switch apikey to appId in /auth

To do with hub.json:
- check respons class of /auth in every .json
- check HUBID returned by /hubs/list
- in /hubs/create 
  - Description is required. Couldn't it be empty string by default?
  - session key parameter (present in the Taffy) is not used, Authorization is as always. Should be removed from the Taffy.
  - hideusers param Should be numeric [0,1] instead of String.
- in /hubs/list
  - returned roomid is used as hubId for the other call. Change the name of the returned roomid in hubId in prod?
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

