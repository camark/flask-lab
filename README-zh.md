# Flask-Lab

Flask-Lab 可以直接从数据库创建 Restful API。

Flask-Lab 依赖 flask 和 peewee.

## 快速开始

### 安装

```
pip install flask-lab
```

更好的方式, 使用 `poetry`:

```
poetry add flask-lab
```

这将会安装 `flask_lab` 模块以及一个 `flask-lab` 命令.

### 创建一个演示用的 sqlite 数据库(非必须)

如果你手头没有现成的数据库，只想尝试一下 flask-lab 的话，可以直接创建一个演示数据库, 其中有
user 和 article 两个表供你演示。

```
flask-lab --create-demo
```

这将会创建 `flask_lab_demo.db` 并且带有一些假数据.

### 打开 Flask-lab 服务

```
flask-lab --engine sqlite --database flask_lab_demo.db
```

在浏览器中打开 http://localhost:5000/api/user 或者 http://localhost:5000/api/article 你就可以看到 user 或者 article 的列表.

这将会同时创建 `flask_lab_models.py` 和 `flask_lab_app.py`, 可以从这两个文件开始构建你的应用.

## 文档

```
flask-lab -h

Usage: flask_lab.py [options], flask_lab.py -h for detailed help

Options:
  -h, --help            show this help message and exit
  -H HOST, --host=HOST
  -p PORT, --port=PORT
  -u USER, --user=USER
  -P, --password
  -e ENGINE, --engine=ENGINE
                        Database type, e.g. sqlite, mysql, postgresql or
                        cockroachdb. Default is "postgresql".
  -s SCHEMA, --schema=SCHEMA
  -t TABLES, --tables=TABLES
                        Only generate the specified tables. Multiple table
                        names should be separated by commas.
  -v, --views           Generate model classes for VIEWs in addition to
                        tables.
  -i, --info            Add database information and other metadata to top of
                        the generated file.
  -o, --preserve-order  Model definition column ordering matches source table.
  -I, --ignore-unknown  Ignore fields whose type cannot be determined.
  -L, --legacy-naming   Use legacy table- and column-name generation.
  -m MODEL_FILE, --model-file=MODEL_FILE
                        Model filename to generate
  -a APP_FILE, --app-file=APP_FILE
                        Flask App filename to generate
  -l LISTEN_ADDRESS, --listen-address=LISTEN_ADDRESS
                        Port for flask app to listen on. Format: 0.0.0.0:5000
  -C, --create-demo     Create a demo database with Article and User Model to
                        demo Flask-Lab
  -d DATABASE, --database=DATABASE
                        Database to use
```

详细文档马上就来。。（如果我有时间的话）


## TODO

- filter_x methods
- include and exclude
- date_format
- user, group and permission tables like django-admin
- a react-admin based admin panel like django-admin
- OpenAPI documentation
