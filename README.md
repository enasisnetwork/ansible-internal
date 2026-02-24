# Enasis Network Ansible Internal Collection

> This project has not released its first major version.

> This collection is only a placeholder for the moment.

Ansible content specific for Robert Harris and the Enasis Network.

Check out this collection on
[Ansible Galaxy](https://galaxy.ansible.com/ui/repo/published/enasisnetwork/internal)
for more information.

<a href="https://galaxy.ansible.com/ui/repo/published/enasisnetwork/internal"><img src="https://enasisnetwork.github.io/ansible-internal/badges/galaxy.png"></a><br>
<a href="https://enasisnetwork.github.io/ansible-internal/validate/flake8.txt"><img src="https://enasisnetwork.github.io/ansible-internal/badges/flake8.png"></a><br>
<a href="https://enasisnetwork.github.io/ansible-internal/validate/pylint.txt"><img src="https://enasisnetwork.github.io/ansible-internal/badges/pylint.png"></a><br>
<a href="https://enasisnetwork.github.io/ansible-internal/validate/ruff.txt"><img src="https://enasisnetwork.github.io/ansible-internal/badges/ruff.png"></a><br>
<a href="https://enasisnetwork.github.io/ansible-internal/validate/mypy.txt"><img src="https://enasisnetwork.github.io/ansible-internal/badges/mypy.png"></a><br>
<a href="https://enasisnetwork.github.io/ansible-internal/validate/yamllint.txt"><img src="https://enasisnetwork.github.io/ansible-internal/badges/yamllint.png"></a><br>
<a href="https://enasisnetwork.github.io/ansible-internal/validate/ansblint.txt"><img src="https://enasisnetwork.github.io/ansible-internal/badges/ansblint.png"></a><br>
<a href="https://enasisnetwork.github.io/ansible-internal/validate/pytest.txt"><img src="https://enasisnetwork.github.io/ansible-internal/badges/pytest.png"></a><br>
<a href="https://enasisnetwork.github.io/ansible-internal/validate/coverage.txt"><img src="https://enasisnetwork.github.io/ansible-internal/badges/coverage.png"></a><br>

## Quick start for local development
Start by cloning the repository to your local machine.
```
git clone https://github.com/enasisnetwork/ansible-internal.git
```
Set up the Python virtual environments expected by the Makefile.
```
make -s venv-create
```

### Execute the linters and tests
The comprehensive approach is to use the `check` recipe. This will stop on
any failure that is encountered.
```
make -s check
```
However you can run the linters in a non-blocking mode.
```
make -s linters-pass
```

## Version management
> :warning: Ensure that no changes are pending.

1. Rebuild the environment.
   ```
   make -s check-revenv
   ```

1. Update the [galaxy.yml](galaxy.yml) file.

1. Push to the `main` branch.

1. Create [repository](https://github.com/enasisnetwork/ansible-internal) release.

1. Build the Galaxy package.<br>Be sure no uncommited files in tree.
   ```
   make -s galaxy-build
   ```

1. Upload Galaxy package to Ansible servers.
   ```
   make -s galaxy-upload
   ```
