# SWAT+ Editor Design

SWAT+ Editor is a program that allows users to modify SWAT+ inputs easily without having to touch the SWAT+ input text files directly. The editor will import a watershed created in QSWAT+, or allow the user to create a SWAT+ project from scratch. The user may write input files and run the SWAT+ model through the editor.

## Technologies

The following software is used to create and build SWAT+ Editor:

* [Node.js](https://nodejs.org/en/)
* [Electron](https://electron.atom.io/)
* [Vue.js 2.x](https://vuejs.org/)
* [Bootstrap 4](https://getbootstrap.com/)
* [Python 3.x](https://www.python.org/)
* [PyInstaller](http://www.pyinstaller.org/)
* [SQLite](https://www.sqlite.org/)
* [Peewee ORM](http://docs.peewee-orm.com/)

## Database Design

SWAT+ Editor uses a [SQLite](https://www.sqlite.org/) database to hold model input data to allow easy manipulation by the user. The database is structured to closely resemble the SWAT+ ASCII text files in order to keep a clean link between the model and editor. The following conventions are used in the project database:

* The table names will match the text file names, replacing any “.” or “-“ with an underscore “\_”.
* The table column names will match the model’s variable names. All names use lowercase and underscores.
* Any text file with a variable number of repetitive columns will use a related table in the database. For example, many of the connection files contain a variable number of repeated outflow connection columns \(obtyp\_out, obtyno\_out, hytyp\_out, frac\_out\). In the database, we represent these in a separate table, basically transposing a potentially long horizontal file to columns.
* All tables will use a numeric “id” as the primary key, and foreign key relationships will use these integer ids instead of a text name. This will allow for easier modification of these object names by the user and help keep the database size down for large projects.

A separate SQLite database containing common datasets and input metadata will be provided with SWAT+ Editor. \(This is a replacement for the SWAT2012.mdb packaged with SWAT2012 versions of ArcSWAT, QSWAT, and SWATeditor.\)

In addition, reformatted SSURGO and STATSGO soils databases is [available for download](https://bitbucket.org/swatplus/swatplus.editor/downloads/swatplus_soils.sqlite). The structure of the soils database has been split into two tables: a soil table and soil\_layer table.

Similarly, the global weather weather generator database is [available for download](https://bitbucket.org/swatplus/swatplus.editor/downloads/swatplus_wgn.sqlite) in SQLite format. The structure of the wgn database has been split into two tables: a wgn table and wgn\_monthly\_value table.

### Database Access in the Python API

SWAT+ Editor uses the [Peewee ORM](http://docs.peewee-orm.com/) \([object-relational mapping](https://en.wikipedia.org/wiki/Object-relational_mapping)\) to represent and work with the tables in Python. The use of an ORM provides a layer of abstraction and portability in hopes of streamlining future SWAT+ development projects.

Relationships are defined in a [Peewee ORM](http://docs.peewee-orm.com/) python class as a `ForeignKeyField`. In the python class, the field will be named after the object it is referencing. In the database, this name will automatically be appended by the referencing table’s column name, which is usually `id`.

For example, we have two tables representing soils: soils \(`soils_sol`\) and layers \(`soils_sol_layer`\). The layer table has a foreign key to the main soils table, so we know to which soil the layer belongs. In the python class, this field is named `soil`, and in the database it is called `soil_id`.

## Source Code

See the link below for information about accessing and running the source code.

{% page-ref page="../source-code.md" %}

