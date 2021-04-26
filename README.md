# project_platform
Repo for OTUS project "Infrastructure platform"

Проект разворачивается с использованием инструмента Argo CD.

disclaimer: К сожалению, не всё удалось реализовать по разным причинам. В дальнейшем планирую проект переработать и реализоваьб всё задуманое.

Итоговый результат доступен по адресу https://hipster-shop.34.68.249.243.xip.io/:
![Снимок экрана от 2021-04-26 20-14-47](https://user-images.githubusercontent.com/26296907/116117611-7a94a300-a6cd-11eb-9695-1bda2aa18d00.png)

1. Процесс деплоя реализован через GitHub Actions.
2. Для разворачивания инфраструктной части используется Terraform Cloud. В директории terraform хранятся файлы для создания кластера k8s в GKE.
3. С использованием Actions kubectl в кластер доставляется ingress
4. Также через kubectl в кластер устанавливается Argo CD, происходит авторизация и создание проекта для деплоя.
![Снимок экрана от 2021-04-26 20-25-57](https://user-images.githubusercontent.com/26296907/116117763-a9ab1480-a6cd-11eb-8aa5-1520d9c4fda2.png)
5. Для мониторинга кластера и приложения в кластере через workflow устанавливается prometheus (kube-prometheus)
![Снимок экрана от 2021-04-26 20-26-53](https://user-images.githubusercontent.com/26296907/116117856-c5161f80-a6cd-11eb-9683-016df67d48d6.png)
6. Для визуализации - Grafana:
![Снимок экрана от 2021-04-26 20-28-15](https://user-images.githubusercontent.com/26296907/116118329-381f9600-a6ce-11eb-8dc6-cd28f1bc3612.png)
![Снимок экрана от 2021-04-26 20-28-41](https://user-images.githubusercontent.com/26296907/116118332-38b82c80-a6ce-11eb-98a3-e4a5f4543e07.png)
![Снимок экрана от 2021-04-26 20-29-36](https://user-images.githubusercontent.com/26296907/116118336-3950c300-a6ce-11eb-8f01-103de80f9383.png)
7. Для сбора логов устанавливается ECK, Filebeat и Kibana
![Снимок экрана от 2021-04-26 20-31-04](https://user-images.githubusercontent.com/26296907/116118461-61402680-a6ce-11eb-8963-e84b9265204c.png)
