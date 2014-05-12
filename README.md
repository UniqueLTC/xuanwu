# Overview

xuanwu is a GO ORM using code generation approach.

Supporting MongoDB & Mysql.

Definition file is using thrift.

Parser is using https://github.com/wickman/ptsd

`pip install ply`

Template is using cheetah

	sudo su
	export ARCHFLAGS=-Wno-error=unused-command-line-argument-hard-error-in-future
	pip install cheetah

# Usage

	python xuanwu.py thrift_file_path output_folder_path

# Types

Currently only supports:

* bool: A boolean value (true or false), one byte
* i32: A 32-bit signed integer
* string: Encoding agnostic text or binary string

Will support when needed:

* byte: A signed byte
* i16: A 16-bit signed integer
* i64: A 64-bit signed integer
* double: A 64-bit floating point number
* Containers: list/set/map
* Enums

# Convention

* All struct must has the field `1: string ID`
  * xuanwu will map this field to mongo's `_id` specially
* First character of field name must be **upper case**
* Field name ends with ID is the foreign key to another struct
  * `HospitalID` => foreign key to `Hospital` struct

# TBD

How to define index?

Generate crud template?
  * How to update?

Use reflect to support crud?

How to embed groupcache?
