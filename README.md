# submodule-golf

This Opendaylight project demonstrates a bug in mdsal.binding that produces the following error
message:

```
Failed to find leafref target: ../../main/name in module golf (QNameModule{ns=urn:submodule:golf})
```

The yang modules provide an isolated test case that demonstrates the bug is with a leafref path
inside a union in a submodule.

https://github.com/donaldh/submodule-golf/blob/master/src/main/yang/golf-sub.yang#L15-L21

It's worth noting that there are two problems worth addressing here:

* The underlying bug which is exposed here
* The poor error reporting that does not identify the file location, line number where the error
  was found.

