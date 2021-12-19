# Example project using CockaroachDB running in a local instance of Kubernetes
Reference: https://www.cockroachlabs.com/docs/v21.2/orchestrate-a-local-cluster-with-kubernetes

## Userful commands

* Get into a the secure client pod 

```bash
kubectl exec -it cockroachdb-client-secure -- /bin/bash
```

* Execute the sql shell from within the pod
```bash
cockroach sql --certs-dir=/cockroach/cockroach-certs --host=cockroachdb-public
```

* Copy a file inside the secure client
```bash
kubectl cp db.sql cockroachdb-client-secure:/db.sql
```

* Run a sql file
```bash
cockroach sql --certs-dir=/cockroach/cockroach-certs --host=cockroachdb-public --database=%your database% < db.sql.
```

* Check status of non-working pod
```bash
kubectl describe pod %pod-name%
```