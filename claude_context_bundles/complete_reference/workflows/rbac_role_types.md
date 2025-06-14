# RBAC role types

**Source:** https://docs.n8n.io/user-management/rbac/role-types/

---

# RBAC role types

Feature availability

- The Project Editor role is available on Pro Cloud and Self-hosted Enterprise plans.
- The Project Viewer role is only available on Self-hosted Enterprise and Cloud Enterprise plans.

Within projects, there are three user roles: Admin, Editor, and Viewer. These roles control what the user can do in a project. A user can have different roles within different projects.

## Project Admin

A Project Admin role has the highest level of permissions. Project admins can:

- Manage project settings: Change name, delete project.
- Manage project members: Invite members and remove members, change members' roles.
- View, create, update, and delete any workflows, credentials, or executions within a project.

## Project Editor

A Project Editor can view, create, update, and delete any workflows, credentials, or executions within a project.

## Project Viewer

A Project Viewer is effectively a `read-only` role with access to all workflows, credentials, and executions within a project.

Viewers aren't able to manually execute any workflows that exist in a project.

Role types and account types

Role types and [account types](../../account-types/) are different things. Every account has one type. The account can have different role types for different [projects](../projects/).

| Permission | Admin | Editor | Viewer |
| View workflows in the project | ✅ | ✅ | ✅ |
| View credentials in the project | ✅ | ✅ | ✅ |
| View executions | ✅ | ✅ | ✅ |
| Edit credentials and workflows | ✅ | ✅ | ❌ |
| Add workflows and credentials | ✅ | ✅ | ❌ |
| Execute workflows | ✅ | ✅ | ❌ |
| Manage members | ✅ | ❌ | ❌ |
| Modify the project | ✅ | ❌ | ❌ |

[Variables](../../../code/variables/) and [tags](../../../workflows/tags/) aren't affected by RBAC: they're global across the n8n instance.
