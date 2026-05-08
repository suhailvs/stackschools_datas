# stackschools_datas

### Load data:

```bash
git clone https://github.com/suhailvs/stackschools_datas
cd stackschools_datas
tar xvf sqldump.tar.xz
sudo -u postgres psql -d stackschools < keralaschools.sql
sudo -u postgres psql -d stackschools < colleges.sql
sudo -u postgres psql -d stackschools < schools.sql
sudo -u postgres psql -d stackschools < postalcodes.sql
rm keralaschools.sql schools.sql colleges.sql postalcodes.sql
```

### Dump database:


```
sudo su postgres
pg_dump --data-only -d stackschools -t schools_keralaschool -t schools_staffdesig -t schools_staffdetails > /tmp/keralaschools.sql
pg_dump --data-only -d stackschools -t schools_school > /tmp/schools.sql
pg_dump --data-only -d stackschools -t bachelorsportal_bpcollege > /tmp/colleges.sql
pg_dump --data-only -d stackschools -t postalcodes_postalcode > /tmp/postalcodes.sql
```



