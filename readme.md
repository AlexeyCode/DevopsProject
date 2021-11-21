Пререквизиты:
 - Развернуный managed service kubernetes в yandex cloud
 - Установленный ingress по инструкции https://cloud.yandex.ru/docs/managed-kubernetes/solutions/ingress-cert-manager
 - Для запуска CI в github actions необходимо создать секреты в github:
```
DOCKERHUB_USERNAME=dockerhub user
DOCKERHUB_TOKEN=dockerhub password
KUBE_CONFIG=static kube config converted in base64
```

Герерация static kube config для yandex cloud:
1. Получаем kubeconfig и ca.pem по инструкции `https://cloud.yandex.ru/docs/managed-kubernetes/operations/create-static-conf`
2. Конвертируем `ca.pem` в `base64` и сохраняем в файл `cat ca.pem | base64 | tr -d '\n' > cert.txt`
3. Поле `certificate-authority` в kubeconfig меняем на `certificate-authority-data`
4. В значение поля `certificate-authority-data` прописываем данные из файла `cert.txt`
5. Файл `cert.txt` можно удалить
6. Конвертируем kubeconfig в base64 `cat config | base64`
7. Заливаем содержимое файла kubeconfig в секрет `KUBE_CONFIG`