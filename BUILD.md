# Getting started

## Fork the repository

<p align="center">
  <img src="https://github.com/user-attachments/assets/82327bc5-331e-49af-8b5c-717f563b67d4" width="400" style="border-radius: 8px;">
</p>

## Clone the repository

```bash
# specify github username
USERNAME="your_github_username_here"
git clone git@github.com:${USERNAME}/serenedb.git
cd serenedb
git remote add upstream git@github.com:serenedb/serenedb.git
git submodule update --init --recursive
```

## Build

Use cmake with preset 'lldb' to build it in debug. Additional build presets are defined in `CMakePresets.json` file.

```
# from the root of the repository
cmake --preset lldb
cd build/
ninja
```

## Launch 

Now you can launch serenedb:

```
# from the root of the repository
./build/bin/serened ./build_dir --server.endpoint='pgsql+tcp://0.0.0.0:7777'
```

It's possible to connect it via psql: `psql -h localhost -p 7777 -U postgres`


## Test 

Commands in this section are supposed to be executed from the root of the repository.

### Sql-logic tests

The tests requires SereneDB to be running

Launch all the tests
```bash
./tests/sqllogic/run.sh --single-port 7777 --debug true`
```

Also it's possible to specify a filter

```bash
./tests/sqllogic/run.sh --single-port 7777 --test 'tests/sqllogic/any/pg/simple/*.test' --debug true
```

### C++ unit tests:

```bash
./build/bin/iresearch-tests "--gtest_filter=*PhraseFilterTestCase*"
```


