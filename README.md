# git repos

Easily create git bare repositories on a host.

This role is available on Ansible Galaxy as `vrischmann.gitrepos`.

# Requirements

- Git installed on the host
- The `acl` package will be installed by this role

# Role Variables

| Name                        | Required | Description                                              |
| --------------              | -------- | -----------------------------------                      |
| `git_repositories_root_dir` | yes      | Root directory where the repositories are created.       |
| `git_repositories_user`     | yes      | The user for the repositories permissions.               |
| `git_repositories_group`    | yes      | The group for the repositories permissions.              |
| `git_repositories`          | yes      | The list of repository definitions.                      |

## Repository definition

A repository definition contains only the name at the moment:

```yaml
git_repositories:
- foo
- bar
```

# Example Playbook

```yaml
- hosts: git-server
  roles:
    - role: vrischmann.gitrepos
      vars:
        git_repositories_root_dir: /srv/git
        git_repositories_user: git
        git_repositories_group: git
        git_repositories:
          - myproject
          - another-project
```

# License

MIT
