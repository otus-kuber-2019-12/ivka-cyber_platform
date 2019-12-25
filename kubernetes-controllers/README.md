# Выполнено ДЗ №2 Kubernetes controllers. ReplicaSet, Deployment, DaemonSet

  - [x] Основное ДЗ. 
Изучить работу контроллеров ReplicaSet, Deployment и DaemonSet.
Сформировать frontend-replicaset.yaml для запуска подов Hipset-Shop frontend.
Понять, почему изменение версии пода не приводит к его перезапуску.
Создать paymentservice-replicaset.yaml для запуска подов Hipster-Shop payment service.

 - [x] Задание со *
Изучить стратегии обновления версий подов.
Понять принципы и механизмы проверки готовности и доступности пода.

 - [x] Задание со **
Заставить запускать DaemonSet Pod on Master node

## В процессе сделано:
 - Сформирован манифест frontend-replicaset.yaml и исследовано влияние изменений на кол-во наблюдаемых подов. Далее он был скопирован и модифицирован в  frontend-daemonset.yaml 
- Создан Deployment манифест paymentservice-deployment.yaml для развертывания подов HipsterShop Payment Service. Изучен механизм обновления версий. Созданы манифесты для [Blue/Green](./paymentservice-deployment-bg.yaml) и [Reverse](./paymentservice-deployment-reverse.yaml) методов.

## Как запустить проект:

## Как проверить работоспособность:

## PR checklist:
 - [x] Выставлен label с номером домашнего задания

Ситуация, при которой после изменения манифеста не обновились поды, возникла из-за того, что ReplicaSet не проверяет конфигурацию запущенных подов. Этот контроллер проверяет только статус и кол-во запущенных подов в соответствии с указанны селектором.
Контроллер, который может корректно обновлять поды при смене версии имиджа, называется Deployment.

Манифест разворачивания Blue/Green деплоймента [paymentservice-deployment-bg.yaml](./paymentservice-deployment-bg.yaml)
