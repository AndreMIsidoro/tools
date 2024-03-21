# gdb

## Overview

GDB is a source-level debugger, capable of breaking programs at any specific line, displaying variable values, and determining where errors occurred. Currently, gdb supports C, C++, D, Objective-C, Fortran, Java, OpenCL C, Pascal, assembly, Modula-2, Go, and Ada. A must-have for any serious programmer.

## Usage

	gdb -q <elf_executable>

## commands

Disassemble a function

	disassemble <function_name>

Put a break point in a function

	break <function_name>

Send input to the program

	run $(python -c 'print <input>')

