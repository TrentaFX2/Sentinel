
![SentinelLogo-modified](https://github.com/TrentaFX2/Sentinel/assets/112093781/7adfd4e6-e619-45a9-bc34-87f9ddcd64fa)


# Sentinel Admin

Sentinel is an administrative game system that can easily manage your game. We offer a huge load of commands as well as the ability to create plugins for your system and so much more. Sentinel is striving to be the best Admin System out there. Sentinel was created by TrentaFX (@maffy666).
Sentinel has a lot to offer and we currently have over 35 commands that make your game great again. We have a variety of features such as 'Send Later' which allows you to schedule your Personal Messages to someone, advanced grids so your admin frames stay organized. In real time updating so you always know what's going on, ability to create your own plugins, command webhook logging support, and advanced logging systems so you always stay in the know!

_____

# Links

**Discord Server:** https://discord.gg/jVVKmhQWmg 

**Twitter:** https://twitter.com/TrentaFx

_____
# API Docs

### Messages & Hints

```lua
RemoteEvent:FireClient(<Recipient: instance>, <Type: string>, {<Sender: string>, <Description: string>})
```

**Example Usage:**

```lua
RemoteEvent:FireClient(Player, 'Message', {'Server', 'Hey world, this is a message'})
```

-----
### Lists

```lua
RemoteEvent:FireClient(<Recipient: instance>, 'List', {<Title: string>, <Content: table>, <ShowOther: bool>})
```

**Example Usage:**

```lua
local Index = {}

table.insert(Index, {
['Name'] = 'Name Here',
['Description'] = 'Description Here',
['Extra'] = 'Other Info here' --// Remote this line if no other info is to be displayed
})

RemoteEvent:FireClient(Player, 'List', {'Server Admins', Index, true})
```

-----
### Notifications

```lua
RemoteEvent:FireClient(<Recipient: instance>, 'Notif', {<Title: string>, <Description: string>})
```

**Example Usage:**

```lua
RemoteEvent:FireClient(Player, 'Notif', {'Cool Stuff', 'Hey world, this is a notification'})
```

-----
### Personal Message (PM)

```lua
RemoteEvent:FireClient(<Recipient: instance>, 'PersonalMessage', {<Sender: string>, <Description: string>, <CanReply: bool>, <NotifPM: bool>})
```

**Example Usage:**

```lua
RemoteEvent:FireClient(Player, 'PersonalMessage', {'Change Logs', 'Added Drinks & Food' , false, false}) --// This instantly opens the PM without notif and is Read-Only
```

-----
### Get Player Permissions

```lua
Replicated.RemoteFunction:InvokeServer({'GetPerms', <GetPermsFromUserId: number/bool>})
```

**Example Usage:**

```lua
local AdminPerms = Replicated.RemoteFunction:InvokeServer({'GetPerms', false})

print(AdminPerms) -->> OUTPUT: {<AdminLevel: number 0-4>, <AdminName: string>}
```

-----
### Miscellaneous

**Get Requests**

```lua
Replicated.RemoteFunction:InvokeServer({'Get', 'Commands'}) --// Returns table of commands; names & alias
```

```lua
Replicated.RemoteFunction:InvokeServer({'Get', 'Config'}) --// Returns a table of the configuration settings; permissions, configuration, restrictions
```

```lua
Replicated.RemoteFunction:InvokeServer({'Get', 'Logs'}) --// Returns a table of logs; moderator, action & time
```

```lua
Replicated.RemoteFunction:InvokeServer({'Get', 'ChatLogs'}) --// Returns a table of chatlogs; player username, chat string & time
```
