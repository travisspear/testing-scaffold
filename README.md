# Scaffold for Testing, Debugging, and CI of Python Applications

## Project Setup
1. Initiate repo with README and .gitignore
2. Create requirements, Makefile, script, and test_script files

```bash
touch Makefile
touch requirememnts.txt
touch hello.py
touch test_hello.py
```
3. Create and activate a virtual environment (preferably in a hidden folder)

```bash
python -m venv .venv
source ./venv/bin/activate
```

4. Populate Makefile - will vary by project requirements
```Makefile
install: 
    pip install --upgrade pip &&\
        pip install -r requirements.txt

test:
    python -m pytest -vv --cov=hello --cov==hellocli test_hello.py

lint: 
    pylinst --disable=R,C hello.py hellocli.py

all: install lint test
```

## How to Debug
1. Print statements: During development only
2. Testing
3. pdb
```python
def function_name(...):
    # pdb allows you to trace each step executed in a function via console output
    import pdb;pdb.set_trace()
    ...
```