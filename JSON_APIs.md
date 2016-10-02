# Description of JSON APIs available for CosmoPulse2

## /state

Describes important events that have happened on user account (since last check). 
API should not be queries too frequently. Time to next query is provided in response object (_wait_, value in milliseconds).


Object contains array of items like these:

    {
        "message": "Uwaga, wkrótce aktualizacja serwera!",
        "id": "1340004504",
        "type": "globalMessage"
    }
 
    {
        "message": "Liczba nieprzeczytanych wiadomości: 3",
        "id": "18718",
        "configurable": "true",
        "type": "unreadMessages",
        "url": "/cosmopulse/messages/messages.htm?showType=USERS"
        "amount": 3,
        "newest": {
                    "sender": "demo",
                    "subject": "Cześć, mam pytanie",
                    "date": 1475404362000,
                    "type": "USERS"
                  }
    }

### Id

Unique identifier of an item. Subsequent messages of given type shall have different ids to distinguish between events they describe.

### Types

* globalMessage - a temporary, important message broadcasted to all users
* unreadMessages - current number of unread messages, with separate entry for amount and details about the newest unread message. Returned only if the most recent unread message is newer than previously reported ones.
* logoutWarning - user will be forcibly logged out on given time
* battlesInProgress - notification that user participates in battle(s)
* \*ShoutboxMessage - information about last unread message on specific chat room
* userLoginMessage - notification that specific user (for example alliance member, friend) has logged in. 
