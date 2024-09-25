Sample for installing Redis in docker
---


# Key Notes

- All certificates should be in PEM format. It seems that Redis cannot parse DER format
- To enable Redis ACL, users should be defined in config/users.acl
- To digest users password (in order to add in users.acl file) use following command:
```
  > echo -n <<<pasword>>> | sha256sum
```
- In order to follow least privilege principle, use following command to create log and data directories (for more info read [Redis Permission](https://stackoverflow.com/questions/55201167/redis-service-fails-with-permission-denied-on-append-file/59607890#59607890)):
```
  > mkdir data
  > mkdir logs
  > sudo chown -R 1001:1001 data
  > sudo chown -R 1001:1001 logs
```