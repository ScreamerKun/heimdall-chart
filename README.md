# heimdall-chart
Этот проект содержит Helm Chart для развертывания Heimdall, который представляет собой приложение для управления и организации веб-сервисов. Chart включает в себя конфигурацию для Deployment, Service и Persistent Volume Claim, что обеспечивает сохранность данных между перезапусками.

#### Конфигурация

Вы можете настроить Chart, отредактировав файл values.yaml. Основные параметры включают:

- replicaCount: количество реплик Deployment.
- image.repository: репозиторий Docker-образа для Heimdall.
- image.tag: тег Docker-образа (по умолчанию "latest").
- service.type: тип Kubernetes Service (например, ClusterIP, NodePort).
- service.port: порт, на котором будет доступен Heimdall.
- persistence.enabled: включение/выключение использования Persistent Volume.
- persistence.size: размер Persistent Volume.

#### Установка

1. Убедитесь, что у вас установлен Helm и настроен доступ к вашему Kubernetes кластеру.
2. Склонируйте репозиторий с Helm Chart.
3. Перейдите в директорию heimdall-chart.
4. Установите Chart с помощью следующей команды:

helm install my-heimdall ./


Это создаст Deployment, Service и Persistent Volume Claim для Heimdall.

#### Обновление

Для обновления развернутого приложения после изменения конфигурации используйте команду:

helm upgrade my-heimdall ./

#### Удаление

Для удаления развернутого приложения и связанных ресурсов выполните:

helm uninstall my-heimdall