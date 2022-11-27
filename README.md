# VisualNovel API

## Routes

## GET requests

GET `https://localhost:7063/api/visualnovel/{optional field of ID}`

Returns array of all visual novels, if the ID is specified then it only returns the visual novel with that ID, if the ID does not exist then it returns an error 404 with the message "Error, this visual novel ID does not exist!"

Example Request: 
GET `https://localhost:7063/api/visualnovel/`
```
[
    {
        "visualNovelID": 1,
        "title": "Clannad",
        "languages": "English, Japanese",
        "genre": "Slice-of-life",
        "developer": "Key",
        "character": null
    }
]
```

GET `https://localhost:7063/api/character/{optional field of ID}`
Returns array of all characters, if the ID is specified then it only returns the character with that ID, if the ID does not exist then it returns an error 404 with the message "Error, this character ID does not exist!"
Example Request: 
GET `https://localhost:7063/api/character/`

```
[
    {
        "characterID": 1,
        "characterName": "Nagisa Furukawa",
        "voiceActor": "Mai Nakahara",
        "characterRole": "Main",
        "gender": "Female"
    }
]
```

## POST requests
POST 
Adds a new entry to the visual novel table, provided you enter all the required fields. 

Example Request:
PUT `https://localhost:7063/api/visualnovel/`

```
{
    "title": "Umineko",
    "languages": "English, Japanese",
    "genre": "Mystery",
    "developer": "07th Expansion" 
}
```
Which returns:
```
{
    "visualNovelID": 2,
    "title": "Umineko",
    "languages": "English, Japanese",
    "genre": "Mystery",
    "developer": "07th Expansion",
    "character": null
}
```

Adds a new entry to the character table, provided you enter all the required fields. 
Example Request:
PUT `https://localhost:7063/api/character/`
```
{
    "characterName": "Battler Ushiromiya",
    "voiceActor": "Daisuke Ono",
    "characterRole": "Main",
    "gender": "Male"
}
```
Which returns
```
{
    "characterID": 2,
    "characterName": "Battler Ushiromiya",
    "voiceActor": "Daisuke Ono",
    "characterRole": "Main",
    "gender": "Male"
}
```
## DELETE Requests

Deletes a visual novel based on their ID, if success it should say `Successfully deleted visual novel entry!`, if unsuccessful should say `Error, this visual novel ID does not exist!`

Example Request:
DELETE `https://localhost:7063/api/visualnovel/1`

Deletes a character based on their ID, if success it should say `Successfully deleted character!`, if unsuccessful should say `Error this character ID does not exist!`

Example Request:
DELETE `https://localhost:7063/api/character/1`

## NOTES

Initially I had the foreign key in my character table, which I have moved to my visual novel table as I realized multiple characters would be going to the visual novels and not the other way around. 

Using my SQL script should create a character and visual novel which can be used for testing the first ID. 



