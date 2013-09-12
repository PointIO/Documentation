Documentation
=============

To do in the code:
- switch apikey to appId in /auth
- Why is /auth a post? Shouldn't it be a get as it contains a password?
- Hide passwords!

To do with core.json:
- /accessrules/create
  - couldn't manage to create an accessrule, no Error returned to help me. 
- /folders/files/edit
  - "ERROR - The parameter userId to function createEditToken is required but was not passed in."
- /folders/files/upload
  - stil don't get what's suppose to go in the filecontents.
- /folders/{folderid}/getauthorizedembed
- /storagesites/create
  - trying to get a box or dropbox token

To do with hub.json:
- check respons class of /auth in every .json
- check HUBID returned by /hubs/list
- in /hubs/create 
  - description param is required. Couldn't it be empty string by default?
  - session key parameter (present in the Taffy) is not used, Authorization is as always. sessionkey param should be removed from prodN
  - hideusers param should be numeric [0,1] or boolean instead of String.
- in /hubs/list
  - returned roomid is used as hubId for the other call. Change the name of the returned roomid in hubId in prod?
- in /hubs/{hubId}/auth
  - Returns a different session key than /auth. Both can be used to activate hubs calls.
  - Will not work with a user not belonging to the hub (which is good)!
  - When trying to use a not registered user sessionKey to use a call return ERROR = 0, the hub still exists but has been altered. Will open a JIRA.
  - Exemple of the above: 
      1/ julien.gaye creates a hub. 
      2/ jgaye gets his standard sessionKey from /auth. 
      3/ jgaye use this sessionkey, and the hubid to activate /hubs/{hubsId}/delete. 
      4/return ERROR=0, the hub is still present in julien.gaye list, but has 0 users registered and julien.gaye can't access it anymore (return: you're not registered to this hub).
- in /hubs/{hubId}/folders/list
  - verify from where the parameter comes from. folderid = room id or access rule id?
  - returns ERROR - getFileSharePermissions: Invalid shared folder, or you do not have access privileges.
- in /hubs/{hubId}/shares/add
  - Not sure of the params descriptions and use. especially DefaultRole, ShowFilter, HideFilters.
  - Is DefaultRole having any effect? I was able to download and preview from the console with a defaultRole = azhfaomfhazmo.
- in /hubs/{hubId}/users/add
  - call returns   "MESSAGE": "ERROR - Error adding share to hub: email-smtp.us-east-1.amazonaws.com railo.runtime.exp.NativeException:501 Syntax: HELO <hostname>\n:0",
  - but the user is added.
- in /hubs/{hubId}/users/list
  - hideusers is boolean but was string in /hubs/create. See the comment on /hubs/create.
  - call returns   "MESSAGE": "ERROR - key [ROOMID] doesn't exist in argument scope. existing keys are [hubId, hideusers]"
- in /hubs/{hubId}/users/remove
  - can't test because can't get userid from /users/list


