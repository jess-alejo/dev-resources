### Managing Users

Add a user with home directory

```bash
useradd -m john
```

<br>

Change user's default shell

```bash
usermod -s bin/bash john
```

Add user to a group

```bash
usermod -G developers john
```

<br>

Delete a user

```bash
userdel john
```
