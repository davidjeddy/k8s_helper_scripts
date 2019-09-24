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
        "uid": "5801a249-747d-45d8-9959-0d97479e0f80",
        "resourceVersion": "234",
        "creationTimestamp": "2019-06-03T12:00:00Z",
        "deletionTimestamp": "2019-06-03T12:05:00Z"
    },
    "spec": {
        "finalizers": [
            "vendor/product"  <--- remove me
        ]
    },
    "status": {
        "phase": "Terminating"
    }
}
```

- Save and exit.
- Wait 15 to 30 seconds for the namespace deletion to complete.
