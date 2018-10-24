## Classes

<dl>
<dt><a href="#VolaError">VolaError</a> ⇐ <code>Error</code></dt>
<dd><p>You did something wrong, or vola did, not sure</p>
</dd>
<dt><a href="#VolaPrivilegeError">VolaPrivilegeError</a> ⇐ <code><a href="#VolaError">VolaError</a></code></dt>
<dd><p>pls leave</p>
</dd>
<dt><a href="#File">File</a></dt>
<dd><p>Your friendly neighborhood file</p>
</dd>
<dt><a href="#Message">Message</a></dt>
<dd><p>Somebody said something!</p>
</dd>
<dt><a href="#Room">Room</a></dt>
<dd><p>Yay, we vola</p>
</dd>
</dl>

<a name="VolaError"></a>

## VolaError ⇐ <code>Error</code>
You did something wrong, or vola did, not sure

**Kind**: global class  
**Extends**: <code>Error</code>  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| volaSaysNo | <code>boolean</code> | If defined and true, this is a VolaError |

<a name="VolaPrivilegeError"></a>

## VolaPrivilegeError ⇐ [<code>VolaError</code>](#VolaError)
pls leave

**Kind**: global class  
**Extends**: [<code>VolaError</code>](#VolaError)  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| volaSaysPlsLeave | <code>boolean</code> | If defined and true, this is a VolaPrivilegeError |

<a name="File"></a>

## File
Your friendly neighborhood file

**Kind**: global class  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| id | <code>string</code> | ID |
| name | <code>string</code> | Name |
| type | <code>string</code> | Type |
| size | <code>number</code> | Size in bytes |
| expires | <code>Date</code> | Point when the files goes dodo |
| uploaded | <code>Date</code> | When?! |
| uploader | <code>string</code> | Who?! |
| tags | <code>object</code> | Other stuffs vola told us |
| url | <code>string</code> | File URL |
| expired | <code>boolean</code> | Still there? |
| validFor | <code>number</code> | Seconds till dodo |
| thumb | <code>string</code> | Image or video thumbnail url |


* [File](#File)
    * [.infos([force])](#File+infos) ⇒ <code>Promise.&lt;Object&gt;</code>
    * [.getAsset(type)](#File+getAsset) ⇒ <code>string</code>
    * [.delete()](#File+delete)
    * [.fetch()](#File+fetch) ⇒ <code>Promise.&lt;Request&gt;</code>
    * [.timeout(minutes)](#File+timeout)
    * [.ban([options])](#File+ban)
    * [.unban([options])](#File+unban)
    * [.blacklist([options])](#File+blacklist)
    * [.whitelist()](#File+whitelist)

<a name="File+infos"></a>

### file.infos([force]) ⇒ <code>Promise.&lt;Object&gt;</code>
Get extended file information, such as checksums

**Kind**: instance method of [<code>File</code>](#File)  
**Returns**: <code>Promise.&lt;Object&gt;</code> - The information you are looking for  

| Param | Type | Description |
| --- | --- | --- |
| [force] | <code>boolean</code> | Force (re-)getting the info |

<a name="File+getAsset"></a>

### file.getAsset(type) ⇒ <code>string</code>
Get a specific asset such as the video_thumb

**Kind**: instance method of [<code>File</code>](#File)  
**Returns**: <code>string</code> - URL of the asset  

| Param | Type | Description |
| --- | --- | --- |
| type | <code>string</code> | Asset type |

<a name="File+delete"></a>

### file.delete()
Files goes byebye

**Kind**: instance method of [<code>File</code>](#File)  
<a name="File+fetch"></a>

### file.fetch() ⇒ <code>Promise.&lt;Request&gt;</code>
Fetch this file

**Kind**: instance method of [<code>File</code>](#File)  
<a name="File+timeout"></a>

### file.timeout(minutes)
Timeout the uploader of this file, does not delete it tho

**Kind**: instance method of [<code>File</code>](#File)  

| Param | Type |
| --- | --- |
| minutes | <code>number</code> | 

<a name="File+ban"></a>

### file.ban([options])
Ban user who uploaded this file

**Kind**: instance method of [<code>File</code>](#File)  

| Param | Type | Description |
| --- | --- | --- |
| [options] | <code>Object</code> | Blacklist options |

<a name="File+unban"></a>

### file.unban([options])
Unban user who uploaded this file

**Kind**: instance method of [<code>File</code>](#File)  

| Param | Type | Description |
| --- | --- | --- |
| [options] | <code>Object</code> | Whitelist options |

<a name="File+blacklist"></a>

### file.blacklist([options])
Blacklist this file

**Kind**: instance method of [<code>File</code>](#File)  

| Param | Type | Description |
| --- | --- | --- |
| [options] | <code>Object</code> | Blacklist options |

<a name="File+whitelist"></a>

### file.whitelist()
Whitelist this file

**Kind**: instance method of [<code>File</code>](#File)  
<a name="Message"></a>

## Message
Somebody said something!

**Kind**: global class  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| nick | <code>string</code> | Nickname |
| self | <code>bool</code> | Is this message from muh? |
| rooms | <code>Array.&lt;string&gt;</code> | Linked room ids |
| files | <code>Array.&lt;string&gt;</code> | Linked file ids |
| urls | <code>Array.&lt;string&gt;</code> | Links |
| message | <code>string</code> | That's what she said! |
| owner | <code>bool</code> | Said by the owner |
| pro | <code>bool</code> | Said by a pro |
| donor | <code>bool</code> | Said by a donor |
| user | <code>bool</code> | Said by a logged in user |
| user | <code>staff</code> | Said by a (((trusted))) user |
| user | <code>admin</code> | Said by a mod |


* [Message](#Message)
    * [.system](#Message+system) ⇒ <code>boolean</code>
    * [.purple](#Message+purple) ⇒ <code>boolean</code>
    * [.white](#Message+white) ⇒ <code>boolean</code>
    * [.green](#Message+green) ⇒ <code>boolean</code>
    * [.timeout(minutes)](#Message+timeout)
    * [.ban(options)](#Message+ban)
    * [.unban(options)](#Message+unban)

<a name="Message+system"></a>

### message.system ⇒ <code>boolean</code>
Said by the system

**Kind**: instance property of [<code>Message</code>](#Message)  
<a name="Message+purple"></a>

### message.purple ⇒ <code>boolean</code>
Said by a purple

**Kind**: instance property of [<code>Message</code>](#Message)  
<a name="Message+white"></a>

### message.white ⇒ <code>boolean</code>
Said by a white

**Kind**: instance property of [<code>Message</code>](#Message)  
<a name="Message+green"></a>

### message.green ⇒ <code>boolean</code>
Said by a green

**Kind**: instance property of [<code>Message</code>](#Message)  
<a name="Message+timeout"></a>

### message.timeout(minutes)
Timeout whoever said this

**Kind**: instance method of [<code>Message</code>](#Message)  

| Param | Type | Description |
| --- | --- | --- |
| minutes | <code>number</code> | Duration |

<a name="Message+ban"></a>

### message.ban(options)
Ban whoever said this

**Kind**: instance method of [<code>Message</code>](#Message)  

| Param | Type |
| --- | --- |
| options | <code>object</code> | 

<a name="Message+unban"></a>

### message.unban(options)
Unban whoever said this

**Kind**: instance method of [<code>Message</code>](#Message)  

| Param | Type |
| --- | --- |
| options | <code>object</code> | 

<a name="Room"></a>

## Room
Yay, we vola

**Kind**: global class  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| admin | <code>boolean</code> | Wew, a mod! |
| adult | <code>boolean</code> | Room is an adult room |
| connected | <code>boolean</code> | This thing on? |
| disabled | <code>boolean</code> | Room is nuked |
| owner | <code>boolean</code> | Your room m8 |
| staff | <code>boolean</code> | (((Trusted))) you are |
| files | [<code>Array.&lt;File&gt;</code>](#File) | Current set of files in here |
| alias | <code>string</code> | Room alias (custom name) |
| id | <code>string</code> | Room id |
| motd | <code>string</code> | MOTD |
| name | <code>string</code> | Room name |
| nick | <code>string</code> | Connected user name |
| url | <code>string</code> | Full URL of this room |


* [Room](#Room)
    * [new Room(id, [nick], [options])](#new_Room_new)
    * [.login(password)](#Room+login)
    * [.connect()](#Room+connect)
    * [.run()](#Room+run) ⇒ <code>Promise.&lt;reason&gt;</code>
    * [.close()](#Room+close)
    * [.chat(msg, [options])](#Room+chat)
    * [.getFile(id)](#Room+getFile) ⇒ [<code>File</code>](#File)
    * [.waitFile(id, [timeout])](#Room+waitFile) ⇒ [<code>File</code>](#File)
    * [.deleteFiles(ids)](#Room+deleteFiles)
    * [.whitelistFiles(ids)](#Room+whitelistFiles)
    * [.blacklistFiles(ids, [options])](#Room+blacklistFiles)
    * [.ban(spec, [options])](#Room+ban)
    * [.unban(spec, [options])](#Room+unban)
    * [.uploadFile(options)](#Room+uploadFile) ⇒ <code>Object</code>
    * ["open"](#Room+event_open)
    * ["subscribed"](#Room+event_subscribed)
    * ["chat"](#Room+event_chat)
    * ["file"](#Room+event_file)
    * ["received_files"](#Room+event_received_files)
    * ["file"](#Room+event_file)
    * ["users"](#Room+event_users)
    * ["config"](#Room+event_config)
    * ["misc"](#Room+event_misc)
    * ["error"](#Room+event_error)
    * ["close"](#Room+event_close)

<a name="new_Room_new"></a>

### new Room(id, [nick], [options])
A new room for a new day


| Param | Type | Description |
| --- | --- | --- |
| id | <code>string</code> | Room id (or alias or full url) |
| [nick] | <code>string</code> | Nickname |
| [options] | <code>Object</code> | Room options |
| [options.password] | <code>string</code> | Room password |
| [options.key] | <code>string</code> | Room key (aka session password) |
| [options.other] | [<code>Room</code>](#Room) | Other room (to take login info from) |

<a name="Room+login"></a>

### room.login(password)
So you got a password?

**Kind**: instance method of [<code>Room</code>](#Room)  
**Throws**:

- <code>Error</code> o_O


| Param | Type |
| --- | --- |
| password | <code>string</code> | 

<a name="Room+connect"></a>

### room.connect()
Without this life is boring!

**Kind**: instance method of [<code>Room</code>](#Room)  
<a name="Room+run"></a>

### room.run() ⇒ <code>Promise.&lt;reason&gt;</code>
Run until this room somehow closes.

**Kind**: instance method of [<code>Room</code>](#Room)  
**Returns**: <code>Promise.&lt;reason&gt;</code> - Resolving when the room is closed or rejecting on error  
<a name="Room+close"></a>

### room.close()
LIFE SHOULD BE BORING!

**Kind**: instance method of [<code>Room</code>](#Room)  
<a name="Room+chat"></a>

### room.chat(msg, [options])
Say something profound!

**Kind**: instance method of [<code>Room</code>](#Room)  
**Throws**:

- [<code>VolaError</code>](#VolaError) 


| Param | Type | Description |
| --- | --- | --- |
| msg | <code>string</code> | MUST BE PROFOUND! |
| [options] | <code>object</code> | Such as .me and .admin |

<a name="Room+getFile"></a>

### room.getFile(id) ⇒ [<code>File</code>](#File)
Some specific file you had in mind?

**Kind**: instance method of [<code>Room</code>](#Room)  

| Param | Type |
| --- | --- |
| id | <code>string</code> | 

<a name="Room+waitFile"></a>

### room.waitFile(id, [timeout]) ⇒ [<code>File</code>](#File)
Some specific file you had in mind? But wait for it!

**Kind**: instance method of [<code>Room</code>](#Room)  

| Param | Type |
| --- | --- |
| id | <code>string</code> | 
| [timeout] | <code>number</code> | 

<a name="Room+deleteFiles"></a>

### room.deleteFiles(ids)
Cleaning the flow

**Kind**: instance method of [<code>Room</code>](#Room)  
**Throws**:

- [<code>VolaPrivilegeError</code>](#VolaPrivilegeError) 


| Param | Type |
| --- | --- |
| ids | <code>Array.&lt;string&gt;</code> | 

<a name="Room+whitelistFiles"></a>

### room.whitelistFiles(ids)
Everybody should upload THIS!

**Kind**: instance method of [<code>Room</code>](#Room)  
**Throws**:

- [<code>VolaPrivilegeError</code>](#VolaPrivilegeError) 


| Param | Type |
| --- | --- |
| ids | <code>Array.&lt;string&gt;</code> | 

<a name="Room+blacklistFiles"></a>

### room.blacklistFiles(ids, [options])
Nobody should upload THIS!

**Kind**: instance method of [<code>Room</code>](#Room)  
**Throws{volaprivilegeerror}**:   

| Param | Type |
| --- | --- |
| ids | <code>Array.&lt;string&gt;</code> | 
| [options] | <code>object</code> | 

<a name="Room+ban"></a>

### room.ban(spec, [options])
Ban some moron

**Kind**: instance method of [<code>Room</code>](#Room)  
**Throws**:

- [<code>VolaPrivilegeError</code>](#VolaPrivilegeError) 
- [<code>VolaError</code>](#VolaError) 


| Param | Type |
| --- | --- |
| spec | <code>object</code> | 
| [options] | <code>object</code> | 

<a name="Room+unban"></a>

### room.unban(spec, [options])
Unban some moron

**Kind**: instance method of [<code>Room</code>](#Room)  
**Throws**:

- [<code>VolaPrivilegeError</code>](#VolaPrivilegeError) 
- [<code>VolaError</code>](#VolaError) 


| Param | Type |
| --- | --- |
| spec | <code>Object</code> | 
| [options] | <code>object</code> | 

<a name="Room+uploadFile"></a>

### room.uploadFile(options) ⇒ <code>Object</code>
Uploads a file to this room

**Kind**: instance method of [<code>Room</code>](#Room)  
**Returns**: <code>Object</code> - Upload result, containing the file `.id` and local(!)
   `.checksum` of the file/stream.  

| Param | Type | Description |
| --- | --- | --- |
| options | <code>object</code> | Upload options |
| [options.file] | <code>string</code> | File to upload (stream has preference!) |
| [options.name] | <code>string</code> | Name to upload file with. If not given, it    will be derived from file property. If neither property is given, an    Error is thrown! |
| [options.stream] | <code>Object</code> | A supported stream, buffer or string. If    provided the file property will be ignored (except for deriving a name). |
| [options.progress] | <code>callback</code> | Upload progress callback. |

<a name="Room+event_open"></a>

### "open"
This Room is not ready for shitposting

**Kind**: event emitted by [<code>Room</code>](#Room)  
<a name="Room+event_subscribed"></a>

### "subscribed"
This Room will now receive messages

**Kind**: event emitted by [<code>Room</code>](#Room)  
<a name="Room+event_chat"></a>

### "chat"
Somebody said something, but nobody listened

**Kind**: event emitted by [<code>Room</code>](#Room)  
<a name="Room+event_file"></a>

### "file"
A random file appears

**Kind**: event emitted by [<code>Room</code>](#Room)  
<a name="Room+event_received_files"></a>

### "received_files"
We got a brand new file list of pre-existing files!

**Kind**: event emitted by [<code>Room</code>](#Room)  
<a name="Room+event_file"></a>

### "file"
A random file vanished

**Kind**: event emitted by [<code>Room</code>](#Room)  
<a name="Room+event_users"></a>

### "users"
User count changed

**Kind**: event emitted by [<code>Room</code>](#Room)  
<a name="Room+event_config"></a>

### "config"
Config changed

**Kind**: event emitted by [<code>Room</code>](#Room)  
**Properties**

| Name | Type |
| --- | --- |
| name | <code>string</code> | 
| value | <code>\*</code> | 

<a name="Room+event_misc"></a>

### "misc"
Other stuff also generates events, such as "pro", etc.
Subscribe to their names (not actually misc)

**Kind**: event emitted by [<code>Room</code>](#Room)  
<a name="Room+event_error"></a>

### "error"
This Room is rekt

**Kind**: event emitted by [<code>Room</code>](#Room)  
<a name="Room+event_close"></a>

### "close"
This Room is no mo

**Kind**: event emitted by [<code>Room</code>](#Room)  
