# ICBTask API Doc

# Host
```
https://api.icbtask.com
```

# Headers
All the requests require the `X-API-KEY` header for authentication.
```
X-API-KEY: <YOUR API KEY HERE>
```
> You can generate one on your account
# Endpoints

## Todolist

#### Create a new todolist
###### Request
```
POST /todolist
{
    "name": <todolist name> (required)
}
```
###### Response
```
204 No content
```

#### Get all todolists
###### Request
```
GET /todolists
```
###### Response
```
{
    "created_at": <created time>,
    "name": <todolist name>,
    "todolist_id": <todolist id>,
}

```

#### Delete a todolist
###### Request
```
DELETE /todolist/<todolist_id>
```
###### Response
```
Code: 204 No content
```

## Address

#### Create a new address
###### Request
```
POST /address
```
###### Response
```
Code: 204 No content
```

#### Get all addresses
###### Request
```
GET /addresses
```
###### Response
```
    [
        {
            "address": <address>,
            "todolist": <attached todolist>,
            "allowed_addresses": [
                {
                    "address": <remote address>,
                    "username": <remote address's username>,
                }
            ]
        }
    ]
```
#### Delete an address
###### Request
```
DELETE /addresss/<address>
```
###### Response
```
Code: 204 No content
```

#### Attach an address to a todolist
###### Request
```
POST /address/todolist/<address>/<todolist_id>
```
###### Response
```
Code: 204 No content
```
#### Detach an address from a todolist
###### Request
```
DELETE /address/todolist/<address>
```
###### Response
```
Code: 204 No content
```

#### Allow a remote address
###### Request
```
POST /address/access/<address>/<remote_address>
```
###### Response
```
Code: 204 No content
```

#### Revoke an address
###### Request
```
DELETE /address/access/<address>/<remote_address>
```
###### Response
```
Code: 204 No content
```
## Task

#### Create a new Task
###### Request
```
POST /task
{
    "todolist_id": <todolist id>, (requied)
    "project": <project>, (required)
    "description": <description> (required)
}
```
###### Response
###### Response
```
Code: 204 No content
```

#### Get all tasks
###### Request
```
GET /tasks
```
###### Response
```
    [
        {
            "created_at": <created time>,
            "description": <task description>,
            "project": <task project>,
            "shared_from": [<username>],
            "shared_with": [<username>],
            "status": <task status>,
            "task_id": <task id>,
            "todolist": <task todolist>
            "updated_at": <updated time>,
        }
    ]

```

#### Update a tasks
###### Request
```
PATCH /task
{
    "task_id": <task id>, (required)
    "description": <description>, (optional)
    "project": <project> (optional)
}
```
###### Response
```
Code: 204 No content
```

#### Complete a task
###### Request
```
PATCH /task
{
    "task_id": <task_id>, (required)
    "status": "COMPLETED"
}
```
###### Response
```
Code: 204 No content
```

#### Delete a task
###### Request
```
DELETE /task/<task_id>
```
###### Response
```
Code: 204 No content
```

#### Share a task
###### Request
```
POST /task/share/<task_id>/<destination_address>
```
###### Response
```
Code: 204 No content
```

#### Unshare a task
###### Request
```
DELETE /task/share/<task_id>/<destination_address>
```
###### Response
```
Code: 204 No content
```
