
# Retrieval Service

Retrieval service contains :
- database 
- graphQL endpoints 
- RPC connection from the heartbeat

## Compiling & Running
cargo build --features "ch04"
- This will build with the GraphQL to go against the database

cargo build --features "full"
- builds the full final sample

cargo run --features "full" -- --server 0.0.0.0
- runs the full app

cargo run --features "full" -- --server 0.0.0.0 rpc
-- runs the RPC version needd to talk to health bytes

If you receive the error : `ld: library not found for -lpq` its because the postgres library is not installed. You can install it on the mac with:
`brew install postgresql`
or because you have not installed the CLI:
`cargo install diesel_cli --no-default-features --features postgres`

## Ports
- HTTP: 3010
- RPC: 5555

## Database Creation
`export DATABASE_URL=postgres://user:password@localhost:5433/rust-iot-db`
`echo DATABASE_URL=postgres://user:password@localhost:5433/rust-iot-db > .env`

`diesel migration run`
- sets up the database entries

## Retrieval

Adding a Comment
`http PUT localhost:3000/api/comment/add/1311ab7b-ba1a-49e1-824d-2eef906b10c2 comment="This was some great media"'

## Querying

```
# Write your query or mutation here
{
  allMedia {
    media {
      name
      id
      deviceId
    }
  }
}
```
- Queries All Media Data