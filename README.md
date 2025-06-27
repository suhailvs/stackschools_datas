# stackschools_datas

### Load data:

```
git clone https://github.com/sta-k/stackschools_datas
cd stackschools_datas
tar xvf data_sql.tar.xz
psql -U postgres -d stackschools < keralaschools.sql
psql -U postgres -d stackschools < schools.sql
psql -U postgres -d stackschools < colleges.sql
rm keralaschools.sql schools.sql colleges.sql
```

##### if error:
```
psql: error: connection to server on socket "/var/run/postgresql/.s.PGSQL.5432" failed: FATAL:  Peer authentication failed for user "postgres"
```

change `peer` to `sha`:
```
$ vim /etc/postgresql/*/main/pg_hba.conf

local   all   postgres   scram-sha-256
```

### Dump database:

`pg_dump --data-only -d stackschools -t <table_name> > /tmp/file.sql`

example for keralaschools:
```
sudo su postgres
pg_dump --data-only -d stackschools -t schools_keralaschool -t schools_staffdesig -t schools_staffdetails > /tmp/keralaschools.sql
```



