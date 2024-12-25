# Lilliepy-query

this is a sub module for the lilliepy framework to be able to query and cache queries effectivly

## dependecies

* request
* time
* threading
* functools

## how to use

### Import: 

step 1:
```bash
pip install lilliepy-query
```

step 2:
```python
from lilliepy import Fetcher
```

### Syntax:
you will be using these 4 lines of code the most:

```python
from lilliepy import Fetcher

req = query.Fetcher("https://jsonplaceholder.typicode.com", refetch_interval=2) # initilizes the Fetcher class, you will now be able to start fetching and caching data, params are listed in the class comment docs
req.fetch("/todos/3") # fetches the data, since the base url is "https://jsonplaceholder.typicode.com", it will fetch from "https://jsonplaceholder.typicode.com/todos/3"
req.refetch("/todos/3") # refetches every interval stated by the Fetcher init, in this case, 2

data, err, load = req.get_state() # 3 vars are declared here: data, for the data from the fetch; error, for containing any error from preforming the fetch; and load, to indicate if the fetch is still loading or not
```