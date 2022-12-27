# ICBTask API Doc

# Host
```
https://api.icbtask.com
```

# Headers
All the requests require the `X-API-KEY` header
```
X-API-KEY: <YOUR API KEY HERE>
```
# Endpoints

## Todolist

#### Create a new todolist
```
POST /todolist
{
    "name": "<todolist name>" (required)
}
```

#### Get all todolists

```
GET /todolists
```

#### Delete a todolist

```
DELETE /todolist/<todolist_id>
```

## Address

#### Create a new address
```
POST /address
```

#### Get all addresses
```
GET /addresses
```
#### Delete an address
```
DELETE /addresss/<address>
```

#### Attach an address to a todolist
```
POST /address/todolist/<address>/<todolist_id>
```
#### Detach an address from a todolist
```
POST /address/todolist/<address>
```

#### Allow a remote address
```
POST /address/access/<address>/<remote_address>
```

#### Revoke an address
```
DELETE /address/access/<address>/<remote_address>
```
## Task

#### Create a new Task
```
POST /task
{
    "todolist_id": <todolist_id>, (requied)
    "project": <project>, (required)
    "description": <description> (required)
}
```

#### Get all tasks
```
GET /tasks
```

#### Update a tasks
```
PATCH /task
{
    "task_id": <task_id>, (required)
    "description": <description>, (optional)
    "project": <project> (optional)
}
```

#### Complete a task
```
PATCH /task
{
    "task_id": <task_id>, (required)
    "status": "COMPLETED"
}
```

#### Delete a task
```
DELETE /task/<task_id>
```

#### Share a task
```
POST /task/share/<task_id>/<destination_address>
```

#### Unshare a task
```
DELETE /task/share/<task_id>/<destination_address>
```
