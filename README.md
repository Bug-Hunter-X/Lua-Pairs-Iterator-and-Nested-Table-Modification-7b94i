# Lua Pairs Iterator and Nested Table Modification

This repository demonstrates a subtle bug related to Lua's `pairs` iterator and modification of nested tables during iteration.

The `bug.lua` file contains code that recursively iterates through a nested table.  Under certain conditions, this code might skip elements if the table's structure is changed within the loop.

The `bugSolution.lua` file provides a corrected version that avoids this issue.

## Problem

Lua's `pairs` iterator provides no guarantee of iteration order.  Furthermore, if the table being iterated over is modified during iteration, `pairs` might not behave as expected, potentially skipping elements.

## Solution

The solution avoids in-place modification of the table during iteration.  Alternative iteration methods, like explicitly managing indices, can also prevent this issue. 