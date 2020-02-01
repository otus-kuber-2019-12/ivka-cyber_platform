# Custom Resource Definition

Создано определение [mysqls.otus.homework](./deploy/crd.yaml) и ресурс [mysql-instance](./deploy/cr.yml)

Создан [ServiceAccount](./deploy/service-account.yml) и [назначена](./deploy/ClusterRoleBinding.yml) ему роль [mysql-operator](./delpoy/role.yml), которой все разрешено.

Рассмотрен пример создания собственного [оператора](./build/mysql-operator.py) на Python, для обработки объектов типа MySQL.
Оператор генерирует манифесты с помощью [шаблонов](./build/templates), и умеет:
- при создании: создать PV + PVC для базы и бекапов и запусть восстановление
- при удалении: все удалить


## Полезные сылки:

- Официальная документация [CRD](https://kubernetes.io/docs/tasks/access-kubernetes-api/custom-resources/custom-resource-definitions/)
- Статья на [Хабре](https://habr.com/ru/company/flant/blog/459320/) как создавать контроллеры.
- Официальная документация [Kopf](https://pypi.org/project/kopf/)
