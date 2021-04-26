# project_platform
Repo for OTUS project "Infrastructure platform"

Проект разворачивается с использованием инструмента Argo CD.
Итоговый результат доступен по адресу https://hipster-shop.34.68.249.243.xip.io/:


1. Процесс деплоя реализован через GitHub Actions.
2. Для разворачивания инфраструктной части используется Terraform Cloud. В директории terraform хранятся файлы для создания кластера k8s в GKE.
3. С использованием Actions kubectl в кластер доставляется ingress
4. Также через kubectl в кластер устанавливается Argo CD, происходит авторизация и создание проекта для деплоя.
5. Для мониторинга кластера через workflow устанавливается prometheus (kube-prometheus), с предустановлеными дашбордами.
6. Для сбора логов устанавливается ECK, Filebeat и Kibana
