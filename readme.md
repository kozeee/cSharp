# C# Rpg API
Based on this guide: https://www.youtube.com/watch?v=9zJn3a7L1uE&t=7170s

## What is this?
- This is the first project I elected to work on in c# as I felt it would give me a good base understanding of how .NET apis are developed and structured.
- This project contains a few simple endpoints that can be used to create, retrieve, update, and delete an rpg character, otherwise known as a CRUD application.
- The project is currently ephemeral and has no DB connection backing it - each run will default to having the two hard-coded characters created.

## How to use it
- `dotnet watch run` should run the program and open up the swagger api where you can test everything locally.
- Alternatively you can use Postman or any other similar service to make a request. The requests url would be: `locahost:<port>/api/Character/<endpoint>` where `<port>` is the port the application is listening on, and `<endpoint>` is one of the available endpoints.

## Endpoints

### GetAll
- `api/Character/GetAll`
- Get request with no params
- Should retrieve all created characters using the GetAllCharacters DTO (meaning it should exclude the character id)

### Get Character
- Get request to `/api/Character/{id}`
- `id` = the id of the character you wish to retrieve
- finds the first character with the `id` param or returns 404

### Delete Character
- Delete request to `/api/Character/{id}`
- `id` = the id of the character you wish to delete
- deletes the character with the `id` param or returns 404

### Create Character
- Post request to `/api/Character`
- Creates a new character based on the request body
- Autoincrements ID - all other values should be passed or will be set to defaults based on the character model

### Update Character
Put request to `/api/Character/{id}`
- Updates an existing based on the request body
- Currently writes each value meaning any un-passed param will reset to the default value in the character model.

## To Do
- Add persistant storage (i.e itegrate with a database)