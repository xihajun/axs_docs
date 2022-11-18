# How-to guides

## Python Packages Installation

### Install Packages

Here is an example of how to install a Python package using `axs`:

```{bash, eval=F}
axs byquery python_package,package_name=numpy
```
This will install the `numpy` package for Python 3.9.

### Get package version

To check the version of a Python package, you can use the `get package_version` command:

```{bash, eval=F}
axs byquery python_package,package_name=numpy , get package_version
```

### Removing package

You can remove a Python package using the `remove` command:

```{bash, eval=F}
axs byquery python_package,package_name=numpy , remove
```


## A Basic Example: Which city are you living?

### Create a basic json file

```{bash, eval=F}
vi city1/data_axs.json
```

We are based on Cambridge, so we have a little bit bias here.

```{bash, eval=F}
{
        "name": "Cambridge",
        "population": 150000
}
```

### Query

If you know the path and what to know the city name and population, `bypath` and `get` could be used here.


```
➜  tmp axs bypath city1 , get name
Cambridge
➜  tmp axs bypath city1 , get population
150000
```

### Living in a different city?
Given this simple json structure with `name` and `population`, any city could be replaced here for a different city.

When you want to change the data in a json file, you can use the `plant` and `save` command.

For example, if you want to change the name and population of a city, you can do this:

```
axs bypath city2 , plant name Oxford population 200000 , save
```

This will create a json file under `city2/data_axs.json`, and change the `name` key to `Oxford` and the `population` key to `200000` in the json file.

Note that ` , ` was used to seperate the commands.


## Run C code: square root

For Compiled Programming Language, `axs byname project_name , run` will generated the complied file

```{bash, eval=F}
axs byname square_root_c , run
```

It will generate `square_root_compiled` folder with a complied file, the rule is defined in the `data_axs.json` file.

```{bash, eval=F}
axs byname square_root_compiled , run --area=81
```

By providing the input parameter, you will be able to get the result `9.0`.

However, a straightforward way would be `byquery compute`.

```{bash, eval=F}
axs byquery compute , square_root , area=81
```

This will compile the `square_root_c` tool and run it with the `area` parameter set to `81`.


## Run Python Code: Q&A

By default, we have a bert model in our example case

```{bash, eval=F}
axs byname bert_demo_torch_py , run --bert_data_context_path=../my_context.txt --bert_data_questions_path=.../my_questions.txt
```

Output

```{bash, eval=F}
Torch execution device: CPU
Loading BERT model 'bert-large-uncased-whole-word-masking-finetuned-squad' from the HuggingFace transformers' hub ...
Vocabulary size: 30522

Context taken from './my_context.txt':
The docker export command does not export the contents of volumes associated with the container. If a volume is mounted on top of an existing directory in the container, docker export will export the contents of the underlying directory, not the contents of the volume.
----------------------------------------------------------------
Questions taken from './my_questions.txt':

Question_1: What does docker export do?
Answer_1: export the contents of the underlying directory , not the contents of the volume
```
