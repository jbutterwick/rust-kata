# rust-kata
 
# setup
### Install Rust & Cargo
```commandline
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
### Some useful cargo commands
```commandline
cargo build
cargo test
cargo run
cargo check
cargo fmt
```
# Running the tests
First we need to run a postgresql database.
Our docker compose is going to start a postgres server and a pgAdmin

```bash
docker compose up
```
Secondly, we should be able to connect to our local postgree running from docker.
Open any database client (i.e: https://dbeaver.io/) and connect to the database with the following details:

```
host: localhost
port: 5432
database: kata
username: admin
password: pass
```

Alternatively, you may use the provided pgAdmin, navigate to the pgAdmin page http://localhost:5050/ and sign-in with the following credentials:
```
email: admin@admin.com
password: pass
```

Still on the pgAdmin page, create a new server with the following properties and leave the other values as default.
You should be able to connect and see an empty database named `kata`.
```
host: kata-rust-postgres
username: admin
password: pass
```

Finally, run all tests:
```bash
cargo test
```