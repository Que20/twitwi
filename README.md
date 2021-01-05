# twitwi

`twitwi` is a command line Twitter client.
With `twitwi` you can scroll over yout feed in your terminal, like, quote and retweet, but also manage your follower and your lists.

## Why ?

So the other day, I was trying to find a tool that would allow me to do one simple thing :
Create a list name "Swift" and put all of my followers that had the mention "Swift" in their bio. Just couldn't find it so I made this project. I was able to just display a list of my followers, grep it to find the Swift persons and then, just add them to the list. A simple usecase.
Also I was willing to play around with Swift+Argment Parser.

## Contribute

Please ^^.

## Available commands

### Login
    twitwi auth --username {username} --password {password}
The first thing you need to do in order to use the Twitter client. The credentials are stored in your ~/.twitwi directory

### Feed
    twitwi feed
Will display your Twitter feed chronologically.
To navigate trought the feed, juste use the arrow keys.
`cmd+l` to like
`cmd+r` to retweet
`cmd+q` to quote
`r` to reply
`q` to quit

    twitwi feed --list {list_name}
Use this command to see a list's feed. 

### Tweet
    twitwi post --message {tweet content} --attachement {lena.jpg}
The post command is used to post a new tweet. The tweet message should be escaped and surrounded by quotes.
    
### Followers
    twitwi followers --self/ --username {username} --format unb --sperator {a separator}
Shows a list of followers. Use --self (-s) to list your own followers, or --username (-u) to show someone's followers.
Use the format param to display info about your followers: bio (b), display name (n) or username (u)

Example :

> `twitwi followers -s -f ub -s ;`

    total: 2
    @someone;Hi, I'm just a someone on twitter
    @aTwitterDude;Hello, world !


### List management
    twitwi list
To show your lists

    twitwi list-create {list_name}
List-create is used to create a new list.

    twitwi list-add --list {list_name} --username {username} 
To add someone to a list

Example :

> `twitwi list-create Super List`

> `twitwi list-add -l Super List -u @someone`

> `twitwi list`

    Super List / 1 member / 0 subscribed
    
> `twitwi feed -l Super List`

    @someone Anyone here ?
    @someone Hi there 👋
