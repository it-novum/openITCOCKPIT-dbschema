# openITCOCKPIT-dbschema
This repository contains the database documentation of openITCOCKPIT.
By default, openITCOCKPIT supports MySQL or MariaDB as database server.

The database schema is in [DBML](https://www.dbml.org) (Database Markup Language) format.

## Hosted version
The latest database documentation is online available at https://dbdocs.io/community/openITCOCKPIT
This version gets frequently updated by the openITCOCKPIT team.

![dbdocs openITCOCKPIT](images/dbdocs2.png)

## Generate DBML file
The openITCOCKPIT CLI provides a method to generate a fresh version of the currently used database schema as DBML file.
```
oitc Dbml.generate --se
```

## Self-hosted version with Foliant
If preferred you can host your own copy of the documentation using `Foliant`

Download a `.dbml` file from this repository or generate a new one like described above.


```
git clone https://github.com/it-novum/openITCOCKPIT-dbschema.git
cd openITCOCKPIT-dbschema/foliant

cp /opt/openitc/frontend/tmp/cli/database.dbml schema.dbml

# You can also replace slate with mkdocs if preferred
docker-compose run --rm foliant make site --with slate
```

Generate HTML documentation
```
docker run --rm -it -v $(pwd):/usr/src/app -w /usr/src/app foliant/foliant:full make site -w slate
```

More information can be found in the Foliant documentation: https://foliant-docs.github.io/docs/tutorials/db/dbml/

> openITCOCKPIT and it's developers are in no way associated to [dbdiagram](https://dbdiagram.io/), [dbdocs](https://dbdocs.io/) or [Foliant](https://foliant-docs.github.io/docs/) 