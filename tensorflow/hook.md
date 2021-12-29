# implete a tensorflow hook

## learn hook
see tensorflow_core/python/training/session_run_hook.py

```python

class SessionRunArgs(


```
tips:
1. Graph is finallized after function begin(), any Graph-modified is forbided. Further more, Graph modification is not recomended, because at second entry, the graph is unexpected modified.
2. How to fetch tensorvalues 
```python
# overwrite before run and return run args
def before_run(self ,context):
    return SessionRunArgs( tensors) # tensors could be tensor/ tensor_list/tensor_dict

# 2.
def after_run(self,
             run_context,  # pylint: disable=unused-argument
             run_values):
      #  run values is the fetched values of the return value of before_run()
    run_values.results  
```
