
# Mysql client (WIP)

Connect with mysql server and execute queries

## Install

```
ki pkg install github.com/ki-lang/ki-mysql latest mysql
```

## Example

```
@ db = mysql::init(String host, u16 port);
@ con = db.connect() or throw cant_connect;
@ users = con.query("SELECT * FROM users LIMIT 10");
each users as user {
	println(user.get("firstname") or "?");
}
```

## API

```
mysql::init(String host, u16 port) mysql::Client
{mysql::Client}.connect() !mysql::Connection
{mysql::Connection}.query() !Array<mysql::Result>
```
