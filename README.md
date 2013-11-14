Documentation
=============

To do in the code:
- switch apikey to appId in /auth
- Why is /auth a post? Shouldn't it be a get as it contains a password?
- Hide passwords!

To do with core.json:

- /v2/auth
  - ok
- /v2/sessionauth
  - Postman : "MESSAGE": "Session validation failure -- access denied","ERROR": 1
- /v2/folders/files/checkin
  - ok
- /v2/folders/files/checkout
  - ok
- /v2/folders/{folderid}/embed
  - DEPRECATED
- /v2/folders/{folderid}/getauthorizedembed
  - DEPRECATED so removed
- /v2/ping
  - ok on postman
- /v2/permissions/list
  - ok
- /v2/storagetypes/list
  - ok
- /v2/storagetypes/{sitetypeid}/params
  - ok
- /v2/storagesites/create
  - trying to get a box or dropbox token
- /v2/storagesites/{siteId}/details
  - ok
- /v2/storagesites/testconnection
  - siteArgument = {"USERNAME":"tpanagos","DOMAIN":"SPH","DEFAULTCHROOT":"/","HOSTURL":"http://pointio.sharepoint99.com","PASSWORD":"$hare12"}
  - Add an exemple for all calls using struct stuff.
- /v2/storagesites/list
- /v2/storagesites/{siteId}/delete
- /v2/storagesites/{siteId}/update
- /v2/accessrules/{sitetypeid}/params
- /v2/accessrules/{accesruleid}/info
- /v2/accessrules/create
  - couldn't manage to create an accessrule, no Error returned to help me.
- /v2/accessrules/{accessruleid}/delete
- /v2/accessrules/list
- /v2/folders/create
- /v2/folders/info
- /v2/folders/delete
- /v2/folders/list
- /v2/folders/files/upload
  - stil don't get what's suppose to go in the filecontents.
- /v2/folders/files/uploadastext
- /v2/folders/files/download
- /v2/folders/files/copy
- /v2/folders/files/delete
- /v2/folders/files/edit
  - "ERROR - The parameter userId to function createEditToken is required but was not passed in."
- /v2/folders/files/move
- /v2/folders/files/rename
- /v2/folders/files/revisions/list
- /v2/folders/files/revisions/create
- /v2/folders/files/revisions/download
- /v2/folders/files/revisions/restore
- /v2/folders/files/preview
- /v2/folders/files/previewswf
- /v2/folders/isempty
- /v2/folders/files/precache
- /v2/folders/files/history
- /v2/folders/files/comments/create
- /v2/folders/files/comments/list
- /v2/folders/files/comments/delete
- /v2/folders/files/info
- /v2/links/create
- /v2/links/{linkid}/details
  - what is the ipadddress param in the Taffy for? Removing it from the doc for now.
  - Not giving details, no message returned.
- /v2/links/{linkid}/update
- /v2/links/{linkid}/delete
- /v2/links/list
  - what are the two parmas in the Taffy for? Removing them from the doc for now.
- /v2/folders/files/sign
- /v2/signatures/validate
- /v2/signatures/list
- /v2/signatures/revoke


To do with hub.json:
- in /hubs/list
  - returned roomid is used as hubId for the other call. Change the name of the returned roomid in hubId in prod?
- in /hubs/{hubId}/folders/files/upload
  - stil don't get what's suppose to go in the filecontents.
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
  - hideusers is boolean but is numeric in /hubs/create. Change default to false in description!
  - call returns   "MESSAGE": "ERROR - key [ROOMID] doesn't exist in argument scope. existing keys are [hubId, hideusers]"
- in /hubs/{hubId}/users/remove
  - can't test because can't get userid from /users/list


