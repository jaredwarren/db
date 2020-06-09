# DB
MySQL Database manager
manages connection to db including ssh connection
supports generic query results (`map[string]interface{}`)


## Usage
### direct connect
```go
	dsn := db.NewDSN(username, password, host, port, path)
	dbc := db.Connect(dsn)
``` 


### ssh connect
```go
	dsn := &db.DSN{
		User: &Userinfo{
			Username: "username",
			Password: "password",
		},
		Host: &Host{
			Host: "host",
			Port: 3306,
		},
        Path: "path",
        SSH: &ssh.Conn {
            Host: "123.123.123.123",
            Port: 22,
            User: "root",
            Key: "~/.ssh/id_rsa",
        }
	}
	dbc := db.Connect(dsn)
``` 