Documentation
=============

To do in the code:
- switch apikey to appId in /auth
- Why is /auth a post? Shouldn't it be a get as it contains a password?
- Hide passwords!

To do with core.json:
- /accessrules/create
  - couldn't manage to create an accessrule, no Error returned to help me. 
- /links/list
  - what are the two parmas in the Taffy for? Removing them from the doc for now.
- /links/{linkid}/details
  - what is the ipadddress param in the Taffy for? Removing it from the doc for now.
  - Not giving details, no message returned.
- Other links call to add ? delete, update?
- /folders/files/edit
  - "ERROR - The parameter userId to function createEditToken is required but was not passed in."
- /folders/files/upload
  - stil don't get what's suppose to go in the filecontents.
- /folders/{folderid}/getauthorizedembed
- /storagesites/create
  - trying to get a box or dropbox token


To do with hub.json:
- in /hubs/list
  - returned roomid is used as hubId for the other call. Change the name of the returned roomid in hubId in prod?
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


