## Installation

```sh
brew install cassandra

# Prerequirements: Python
# if no having pip
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python3 get-pip.py
# endif

pip install cql
```

```zsh
# terminal1
cassandra
# terminal2
cqlsh
```

## Basic Commands

```cql
/** Create Keyspace **/
create keyspace first_keyspace with replication = {'class':'SimpleStrategy', 'replication_factor':1};

/** Select Keyspace **/
use first_keyspace;

/** Create Column Family **/
create table first_table (
  name text PRIMARY KEY,
  value text
);

/** Run Select **/
select * from first_table;
-- => 0 rows
```

```cql
/** Insert **/
insert into first_table (name, value) values ('hoge', 'fuga');
insert into first_table (name, value) values ('piyo', 'hage');
select * from first_table;
-- => 2 rows
```

```cql
/** Delete **/
delete from first_table where name = 'hoge';
select * from first_table;
-- => 1 rows
```

```cql
update first_table set value = 'hogera' where name = 'piyo';
select * from first_table;
```
