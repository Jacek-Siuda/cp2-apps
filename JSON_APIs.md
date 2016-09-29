# Description of JSON APIs available for CosmoPulse2

## /state

Describes important events that have happened on user account (since last check). 
API should not be queries too frequently. Time to next query is provided in response object (_wait_, value in milliseconds).


Object contains array of items like this one:

    {
    	"message": "Liczba nieprzeczytanych wiadomości: 10",
    	"id": "unreadMessageMultiple",
    	"configurable": "true",
    	"type": "unreadMessageMultiple",
    	"url": "/beta/messages/messages.htm"
    }


### Types

* globalMessage - a temporary, important message broadcasted to all users
* unreadMessages - TODO
* logoutWarning - user will be forcibly logged out on given time
* battlesInProgress - notification that user participates in battle(s)
* *ShoutboxMessage - information about last unread message on specific chat room
* userLoginMessage - notification that specific user (for example alliance member, friend) has logged in. 
