# ICBTask Documentation

## Get started

You only need to:
1. Create an account and generate an **API Key** [here](https://icbtask.com/signup)
2. Download ICBTask official cli [here](https://github.com/icbtask/cli)

You're ready to go !

## Todolist
- You can create as many todolists as you want
Check out ICBTask cli for examples [herel](https://github.com/icbtask/cli)

## Task
- You can create as many tasks as you want
- To keep things simple, a task has two fields: `project` and `description`
Check out ICBTask cli for examples [herel](https://github.com/icbtask/cli)

## Task sharing

## Terminology
- An `address` is a random 52 characters.
- You can generate as many as you want.
- They are not sensitive data, you can share them publicly, that's fine.
- You can attach multiple addresses to a single todolist.

## Rules for sharing tasks
- You can receive tasks only from addresses that you explicitly allow.
- You need to attach an address to a todolist first before you can receive tasks to that address

## Example
### Sharing your task(s) with someone
1. You need to create an address
```
$ icbtask address add
```
2. Attach the address to a todolist
```
$ icbtask attach
```
3. The remote address SHOULD allow you to send it tasks
```
$ icbtask task share --id=<task id> --remote-address=<remote_address>
```

### Receive task(s) from someone
1. You need an address that is attached to a todolist
```
$ icbtask address attach --address=<your address> --todolist-id=<your todolist id>
```
2. allow the remote address to send you tasks
```
$ icbtask address allow --address=<your address> --remote-address=<remote address>
```

## API Documentation
Check the API documentation [here](/api/)
