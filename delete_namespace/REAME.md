# Delete Namespace

**Warning: This will orphan any resources assigned to the namespace. Use with caution.**

- Run script w/ the namespace as the first arugment

```sh
./path/to/script/delete_namespace.sh Testing
```

- When vi opens, remove any `finalizers`.

```sh
{
    "kind": "Namespace",
    "apiVersion": "v1",
    "metadata": {
        "name": "testing",
        "selfLink": "/api/v1/namespaces/testing",
        "uid": "33074e57-cb72-11e5-9d3d-28d2444e470d",
        "resourceVersion": "234",
        "creationTimestamp": "2016-02-04T19:05:04Z",
        "deletionTimestamp": "2016-02-04T19:05:54Z"
    },
    "spec": {
        "finalizers": [
            "openshift.io/org"  <--- remove me
        ]
    },
    "status": {
        "phase": "Terminating"
    }
}
```

- Save and exit.
- Wait 15 to 30 seconds for the namespace deletion to complete.
