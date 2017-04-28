# PostgreSQL Sails/Waterline Adapter with PrepQuery
sails-postgresql v0.12.2 with prepQuery

prepQuery is used for performance optimization. x2 faster then raw query. millions times faster then sails adapter. Doh....
For personal usage.

### example,
```javascript
      User.prepQuery({
        text: `select * from users where id = $1`,
        type: ['int'],
        values: [clientSession.uid]
      },
      (err, result) => {
        if (err) {return cb(err)}
        if (!result.rowCount) {return cb(null, [])}
        return cb(null, result.rows)
      })

```

## Install

Install is through NPM.

```bash
$ npm install sails-postgresql-prepquery
```

## Credits

To learn more visit the project on GitHub at [sails-postgresql](https://github.com/balderdashy/sails-postgresql).
