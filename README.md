# jschema-to-python

Generate Python classes from a JSON schema.

# Usage

```
python -m jschema_to_python [-h] -s SCHEMA_PATH -o OUTPUT_DIRECTORY [-m MODULE_NAME] -r ROOT_CLASS_NAME [-g HINTS_FILE_PATH] [-f] [-v]

Generate source code for a set of Python classes from a JSON schema.

optional arguments:
  -h, --help            show this help message and exit
  -s SCHEMA_PATH, --schema-path SCHEMA_PATH
                        path to the JSON schema file
  -o OUTPUT_DIRECTORY, --output-directory OUTPUT_DIRECTORY
                        directory in which the generated classes will be created
  -m MODULE_NAME, --module-name MODULE_NAME
                        name of the module containing the object model classes
  -r ROOT_CLASS_NAME, --root-class-name ROOT_CLASS_NAME
                        the name of the class at the root of the object model represented by the schema
  -g HINTS_FILE_PATH, --hints-file-path HINTS_FILE_PATH
                        path to a file containing hints that control code generation
  -f, --force           overwrite the output directory if it exists
  -v, --verbose         increase output verbosity (may be specified up to two times)
```

# Improvement from the original
(aside from @macroonroads' changes in his fork)

- Does better with subclasses / definitions ($defs)
- Make better accommodation for arrays (using attrs factories)
- Changed Python type names to match Schema casing
- Put all classes in a single file