# Service Account

## 1. Authentication
> Dangj

## 2. Authorization
RBAC: Role Base Access Control
ABAC: Attribute Based Access Control
Node: Authorization
WebHook Mode

## 2.1 RBAC
RBAC uses rbac.authorization.k8s.io API Group that allow admin auto
Enable RBAC: start apiserver: `-- authorization-mobel=RBAC`

RBAC khai báo 4 `top-level` types.

### Role and ClusterRole

A role contains:
- Rules: Đại diện cho một tập quyền
- Permission:

- Role with a namespace => Role
- Role with cluster-wide => ClusterRole

Một `Role` chỉ có thể được sử dụng để gán quyền truy cập tới resources trong một `single namespace`.

Một `ClusterRole` có thể được sử dụng để gán quyền truy cập tương tự như `Role` nhưng ở phạm vi của Cluster (rộng hơn role):
- Clustered-scoped resources (nodes, ..)
- Non-resources endpoints: (/helthz)
- Namespaced resources (ex: Pods)

# role binding
- A `role binding` cấp tập hợn các `permissions` được định nghĩa trong một `role` tới một `user` hoặc một tập các `users`
- Hold a list of subjects (users, groups, account)
- Tham chiếu đến `role` được cấp

### 2. 1 Auth Mechanism
kube-apiserver xác thực nhờ 2 cơ chế là: Static Password File và Static Token File
