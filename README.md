# puppy-be

Simple CRUD for puppies.

## Instructions

1.  Run `npm i` or `yarn install`
2.  Run `npm start` or `yarn start`

API will be up & running on `http://localhost:4000`.

## API Documentation

The following endpoints/CRUD operations exist:

1.  `GET /puppies` - Returns a list of all the puppies in the system

    ```
    E.g.:

    Request: GET /puppies
    Response status: 200
    Response body: [
       { "id": 1, "name": "Superman", "type": "Shnitzel", "adopted": false },
       { "id": 2, "name": "Reign", "type": "Rottweiler", "adopted": false }
    ]
    ```

2.  `GET /puppies/:id` - Returns a puppy object or 404 if not found

    ```
    E.g.:

    Request: GET /puppies/1
    Response status: 200  
    Response body: { "id": 1, "name": "Superman", "type": "Shnitzel", "adopted": false }

    Request: GET /puppies/999
    Response status: 404  
    Response body: { "message": "No puppy found." }
    ```

3.  `POST /puppies` - Creates a new puppy object and returns the newly created puppy

    ```
    E.g.:

    Request: POST /puppies
    Request body: { "name": "New Puppy", "type": "Shnitzel", "adopted": false }
    Response status: 200
    Response body: { "id": 3, "name": "New Puppy", "type": "Shnitzel", "adopted": false }
    ```

4.  `PUT /puppies/:id` - Updates a puppy object and returns the newly updated puppy or 404 if not found

    ```
    E.g.:

    Request: PUT /puppies/3
    Request body: { "name": "New Puppy", "type": "Shnitzel", "adopted": true }
    Response status: 200  
    Response body: { "id": 3, "name": "New Puppy", "type": "Shnitzel", "adopted": true }

    Request: PUT /puppies/999
    Request body: { "name": "New Puppy", "type": "Shnitzel", "adopted": true }
    Response status: 404  
    Response body: { "message": "No puppy found." }
    ```

5.  `DELETE /puppies/:id` - Deletes a puppy object and returns 200 or 404 if not found

    ```
    E.g.:

    Request: DELETE /puppies/3
    Response status: 200

    Request: DELETE /puppies/999
    Response status: 404  
    Response body: { "message": "No puppy found." }
    ```

All API endpoints accept and send back JSON format.

## Other considerations

This application uses a JSON file (`data/puppies.json`) as a persistence layer. There is a backup (initial data to be used) in `data/puppies.bk.json`.
