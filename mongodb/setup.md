# mongodb using homebrew

#### 1. Tell homebrew where mongodb's installation recipe lives

```bash
brew tap mongodb/brew
```

homebrew calls an installation recipe a `formula`, and repositores which contain such formula's are called `taps`

Hence, this command adds mongodb's offical formula repository to homebrew

#### 2. Mark the source as trusted

```bash
brew trust mongodb/brew
```

#### 3. Install a specific mongodb version family

```bash
brew install mongodb-community@8.0
```

- `mongodb-community` &rarr; mongodb's community edition

- `@8.0` &rarr; release family, homebrew choses the available patch release within the family

This installs the server executable i.e. `mongod`, along with the interactive client, `mongosh` and supporting tools

#### _Attention Homies!_

- `mongod` &rarr; _the database server process_, owns the stored data and answers connection

- `mongosh` &rarr; the client we use _to connect_ to that server

On _Apple Silicon Mac_, homebrew's installation also creates this default locations

| Path                            | Purpose                |
| ------------------------------- | ---------------------- |
| `/opt/homebrew/etc/mongod.conf` | Server configuration   |
| `/opt/homebrew/var/mongodb`     | Default database files |
| `/opt/homebrew/var/log/mongodb` | Default logs           |

#### 4. Verify the installation

```bash
command -v mongod mongosh
```

These establish that whether your shell can locate the executables such that they can run

> opt/homebrew/bin/mongod </br>
> opt/homebrew/bin/mongosh

If you see this in your shell, yay :)

#### 5. Check version (optional)

```bash
mongod --version
mongosh --version
```
