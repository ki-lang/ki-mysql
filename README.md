
# Mysql client (WIP)

Connect with mysql server and execute queries

## Install

```
ki pkg install github.com/ki-lang/ki-mysql latest mysql
```

## Example

```
@ db = mysql::init("127.0.0.1", "root", "password", "mydb", 3306);
@ con = db.connect() or throw cant_connect;
@ users = con.query("SELECT * FROM users LIMIT 10");
each users as user {
	println(user.get("firstname") or "?");
}
```

## API

```
mysql::init(String host, String username, String password, String database, u16 port) mysql::Client
{mysql::Client}.connect() !mysql::Connection
{mysql::Connection}.run() !
{mysql::Connection}.all() !Array<Map<?String>>
{mysql::Connection}.first() !?Map<?String>
```
