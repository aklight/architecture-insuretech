# Задание 2. Динамическое масштабирование контейнеров

Требуемые по заданию скриншоты расположены в папке `Task2/screenshots`

---

## 🚀 Запуск кластера Minikube

```powershell
minikube start --driver=docker
```

## 📊 Активация metrics-server

```powershell
minikube addons enable metrics-server
```

## ⚙️ Развертывание приложения

### Применение манифеста развертывания
```powershell
minikube kubectl -- apply -f architecture-insuretech\Task2\scaletestapp-deployment.yaml
```

### Применение манифеста сервиса
```powershell
minikube kubectl -- apply -f architecture-insuretech\Task2\scaletestapp-service.yaml
```

## 📈 Настройка Horizontal Pod Autoscaler (HPA)

### Применение конфигурации HPA
```powershell
minikube kubectl -- apply -f architecture-insuretech\Task2\scaletestapp-hpa.yaml
```

### Проверка статуса HPA
```powershell
minikube kubectl -- get hpa
```

## 🐛 Установка и настройка Locust

### Установка Locust
```powershell
pip install locust
```

### Запуск Locust
```powershell
locust
```

**Доступ к веб-интерфейсу Locust:** http://localhost:8089/

## 📋 Запуск дашборда Minikube

```powershell
minikube dashboard
```

---

## 🔄 Последовательность выполнения

1. **Запуск кластера** → Minikube
2. **Включение мониторинга** → Metrics Server
3. **Развертывание приложения** → Deployment + Service
4. **Настройка автоскейлинга** → HPA
5. **Установка инструмента нагрузки** → Locust
6. **Тестирование и мониторинг** → Dashboard + Locust UI

