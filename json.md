# ressources

 - https://realpython.com/python-json/
 - https://en.wikipedia.org/wiki/JSON
 - https://docs.python.org/3/library/json.html
 - https://docs.python.org/3/library/json.html#basic-usage
 

# Conversion tables

[The tables](https://docs.python.org/3/library/json.html#py-to-json-table) are not symetric so serialize-deserialize is not always a null operation.

From Python to JSON : 

|      Python    |  JSON  |
|----------------|--------|
|dict 	         | object |
|list, tuple 	 | array  |
|str 	         | string |
|int, long, float| number |
|True 	         | true   |
|False 	         | false  |
|None 	         | null   |

From JSON to Python : 

|    JSON        | Python |
|----------------|--------|
| object 	     | dict   |
| array 	     | list   |
| string 	     | str    |
| number (int)   | int    |
| number (real)  | float  |
| true           | True   |
| false 	     | False  |
| null 	         | None   |


# Base example 

## dump 
```python
import json
data = {
    "president": {
        "name": "Zaphod Beeblebrox",
        "species": "Betelgeusian"
    }
}
# write into a json file
with open("data_file.json", "w") as write_file:
    json.dump(data, write_file)
# or into a python str
json_string = json.dumps(data)
```

## load
```python
# load from file
with open("data_file.json", "r") as read_file:
    data = json.load(read_file)
# load from json python string
json_string = """
{
    "researcher": {
        "name": "Ford Prefect",
        "species": "Betelgeusian",
        "relatives": [
            {
                "name": "Zaphod Beeblebrox",
                "species": "Betelgeusian"
            }
        ]
    }
}
"""
data = json.loads(json_string)
```

## serialize custom objects

 - encode using `default` arg : `json.dumps(9 + 5j, default=encode_complex)`
 - encode using `cls` arg : `json.dumps(2 + 5j, cls=ComplexEncoder)`
 - decode using `object_hook` : `json.loads(data, object_hook=decode_complex)`


### encode using the default arg

For non-json-serializable objects : 

```python
z = 3 + 8j
print(type(z))
#raise Exception : json.dumps(z)
# create an encoding function
def encode_complex(z):
    if isinstance(z, complex):
        return ("__complex__", z.real, z.imag)
    else:
        type_name = z.__class__.__name__
        raise TypeError(f"Object of type '{type_name}' is not JSON serializable")
# then use the default arg of dump
json.dumps(9 + 5j, default=encode_complex)
```

### encode using the cls arg

Subclassing from JSONEncoder

```python
class ComplexEncoder(json.JSONEncoder):
    def default(self, z):
        if isinstance(z, complex):
            return ("__complex__", z.real, z.imag)
        else:
            return super().default(z)
# using the cls arg
json.dumps(2 + 5j, cls=ComplexEncoder)
# or an instance of encoder
encoder = ComplexEncoder()
encoder.encode(3 + 6j)
```

### decode

In a json : 
```json
{
    "__complex__": true,
    "real": 42,
    "imag": 36
}
```

then create a decoding function

```python
def decode_complex(dct):
    if "__complex__" in dct:
        return complex(dct["real"], dct["imag"])
    return dct

with open("complex_data.json") as complex_data:
    data = complex_data.read()
    z = json.loads(data, object_hook=decode_complex)
```


# common args

 - indentation : `json.dumps(data, indent=4)`
 - separators : `separators=(", ", ": ")` by default, `(",", ":")`
 - default function encoder : `json.dumps(9 + 5j, default=encode_complex)`
 - class encoder : `json.dumps(2 + 5j, cls=ComplexEncoder)`
 - object_hook decoder : `json.loads(data, object_hook=decode_complex)`
 - sort keys : `sort_keys=True`
 - parse float : `json.loads('1.1', parse_float=decimal.Decimal)`