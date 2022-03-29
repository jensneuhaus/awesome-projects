[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

# Awesome projects

## Data Science

### `Amundsen`

[![Homepage](https://img.shields.io/badge/Homepage-green)](https://www.amundsen.io/) [![Last commit](https://img.shields.io/github/last-commit/amundsen-io/amundsen)](https://github.com/amundsen-io/amundsen) [![Stars](https://img.shields.io/github/stars/amundsen-io/amundsen)](https://github.com/amundsen-io/amundsen) [![License](https://img.shields.io/github/license/amundsen-io/amundsen)](https://github.com/amundsen-io/amundsen) 
  
Amundsen is like Google search for data. It is improving the productivity of data analysts, data scientists and engineers when interacting with data by indexing data resources (tables, dashboards, streams, etc.) and powering a page-rank style search based on usage patterns. 


## Data handling

### Marshmallow

[![Homepage](https://img.shields.io/badge/Homepage-green)](https://marshmallow.readthedocs.io/) [![PyPi](https://badgen.net/pypi/v/marshmallow)](https://pypi.org/project/marshmallow/) [![Last commit](https://img.shields.io/github/last-commit/marshmallow-code/marshmallow)](https://github.com/marshmallow-code/marshmallow) [![Stars](https://img.shields.io/github/stars/marshmallow-code/marshmallow)](https://github.com/marshmallow-code/marshmallow) [![License](https://img.shields.io/github/license/marshmallow-code/marshmallow)](https://github.com/marshmallow-code/marshmallow) 

A lightweight library for converting complex objects to and from simple Python datatypes**

```
from marshmallow import Schema, fields

class ArtistSchema(Schema):
    name = fields.Str()

class AlbumSchema(Schema):
    title = fields.Str()
    release_date = fields.Date()
    artist = fields.Nested(ArtistSchema())

bowie = dict(name="David Bowie")
album = dict(artist=bowie, title="Hunky Dory", release_date=date(1971, 12, 17))

schema = AlbumSchema()
result = schema.dump(album)
pprint(result, indent=2)
# { 'artist': {'name': 'David Bowie'},
#   'release_date': '1971-12-17',
#   'title': 'Hunky Dory'}
```


## Messaging

### `Huey`

[![Homepage](https://img.shields.io/badge/Homepage-green)](https://huey.readthedocs.io/) [![PyPi](https://badgen.net/pypi/v/marshmallow)](https://pypi.org/project/huey/) [![Last commit](https://img.shields.io/github/last-commit/coleifer/huey)](https://github.com/coleifer/huey) [![Stars](https://img.shields.io/github/stars/coleifer/huey)](https://github.com/coleifer/huey) [![License](https://img.shields.io/github/license/coleifer/huey)](https://github.com/coleifer/huey)

A little task queue

```
from huey import RedisHuey, crontab

huey = RedisHuey('my-app', host='redis.myapp.com')

@huey.task()
def add_numbers(a, b):
    return a + b
```
