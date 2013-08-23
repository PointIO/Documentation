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
  - hideusers param Should be numeric [0,1] or boolean instead of String.
- in /hubs/list
  - returned roomid is used as hubId for the other call. Change the name of the returned roomid in hubId in prod?
- in /hubs/{hubId}/auth
  - Returns a different session key than /auth. Both can be used to activate hubs calls.
  - Will not work with a user not belonging to the hub (which is good)!
  - When trying to use a not registered user sessionKey (jgaye sessionkey, julien.gaye hub) to use a call (/hubs/{hubsId}/delete) return ERROR = 0, had not affected the hub but julien.gaye is not an active member any more (console displays 0 members in this hub as well). Will open a JIRA.
- in /hubs/{hubId}/folders/list
  - verify from where the parameter come from. folderid = room id or access rule id? TO TEST
- in /hubs/{hubId}/shares/add
  - Not sure of the params descriptions and use. especially DefaultRole, ShowFilter, HideFilters. TO TEST
- in /hubs/{hubId}/users/add
  - call returns   "MESSAGE": "ERROR - Error adding share to hub: email-smtp.us-east-1.amazonaws.com railo.runtime.exp.NativeException:501 Syntax: HELO <hostname>\n:0",
  - but the user is added.
- in /hubs/{hubId}/users/list
  - hideusers is boolean but was string in /hubs/create. See the comment on /hubs/create.
  - call returns   "MESSAGE": "ERROR - key [ROOMID] doesn't exist in argument scope. existing keys are [hubId, hideusers]"
- in /hubs/{hubId}/users/remove
  - can't test because can't get userid from /users/list


