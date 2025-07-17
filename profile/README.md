 # BizMonX

**W I P**

A xymon fork for mainly non-systems monitoring. C -> [Zig](https://ziglang.org)

## Introduction

This is a rebranded fork of [Xymon](https://xymon.sourceforge.io/). Goal is to move away from some of the things that have grown obsolete, whilst
keeping the parts that are still very much relevant today.


## First, a few things about Xymon
### the good

- lightweight
- extremely flexible and pluggable
- fast
- extensible
- status inheritance and propagation across the configuration tree
- written in C
- ...

### the not so good
- frontend style and design
- management of the hosts and groups
- authentication and authorization
- db backend and rrd charts
- ...

## To do, the plan

Just the start, but here are the goals:

-> gradually rewrite using zig

1. move build to zig
2. rewrite frontend! 
3. rewrite clients
4. rewrite endpoints (HTTP/2 gRPC vs REST)
5. rewrite database (duckdb, tigerbeetle, ...?)
6. rewrite charts
7. manage hosts.cfg or replace
8. ...
9. n. rewrite while maybe reusing bits?


+ already added temporary http(s) gateway (golang), to be replaced with zig (zap)

## Doing
- write frontend using [Zap](https://github.com/zigzap/zap)
- migrate Xymon build to zig and push all monkey patching from dockerfile/startup script to build
- write endpoint for: 
    - download hosts.cfg
    - upload hosts.cfg
    - restart xymon
 This will serve to make this project usable while refactoring.

## Done
- dockerize xymon build
- http(s) gateway (status + data, others are pending) -> to be replaced with zig (zap)
- cleanup frontend with css, no code changes yet
- debian and ubi (redhat) versions
- rebranding with monkey patching (temporary step)
- polished icons (temporary)


## Why Zig, not Go/Rust?
Zig works extremely well with C and allows for gradual migration.



