## 🎥 imdb-importer

Import imdb open .tsv data to PostgreSQL database and exposes simple REST API to explore data.

### **Usage**

Get list (in alphabetical order) with all actors indicated by **primary_name** value and corresponding titles (titles 'original_title'). Accepts **name** and **page** request arguments.

```http
GET /movies_by_start_year?year=1917&page=1
```

Get list (in alphabetical order) with all titles of movies indicated by **genre** value and corresponding names (actors 'primary_name').
Accepts **genre** and **page** request arguments.

```http
GET /movies_by_genre?genre=Documentary&page=1
```

Get list (in alphabetical order) with all actors indicated by **primary_name** value and corresponding titles (titles 'original_title').
Accepts **name** and **page** request arguments.

```http
GET /movies_by_name?name=Hardy&page=1
```

### **Installation**

Clone repo:

```bash
$ git clone https://github.com/ExtRemoSolutions/imdb-importer.git
```

Create venv in repository root dir (e.g):

```bash
$ virtualenv -p python3 venv
```

Activate venv:

```bash
$ source venv/bin/activate
```

Install binary of psycopg2 (MacOS):

```
pip3 install psycopg2-binary
```

Install requirements:

```bash
$ pip3 install -r requirements.txt
```

Import data to database: (Files to import **name.basics.tsv**, **title.basics.tsv** should be in the same path as **import_tsv.py** script). Supply database credentials in **import_tsv.py**.

```bash
$ python3 import_tsv.py
```

Edit **config.py** in the **/imdb_rest** dir (database credentials)

Run application from the root repo dir (dev server):

```bash
$ python3 run.py
```