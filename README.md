# Chikenator

url: chikenator.bestzmest.ru
# Для приложения:
1) Регистрация

    uri: /api/register
```
data type: JSON
method: POST
data: 
 {
    "username": String "root",
    "password": String "root"
 }
 ```
 2) **Логин**

    uri: /api/login
```
data type: JSON
method: POST
data: 
 {
    "username": String "root",
    "password": String "root"
 }
 ```
  **В ответ придет токен, его необходимо крепить в заголовок ко всем запросам** 
```   
     header: 
      {
        Authorization: "Bearer " + token
      }
```
3) **Состояние**

    uri: /api/state 
    (все доступные юзеру)
```
data type: JSON
method: GET
```
   Так же можно по айди
   
   uri: /api/state/{id}  
```
data type: JSON
method: GET
```
4) **Настройки**

 **Получение:**
  
    uri: /api/settings
    (все доступные юзеру)
```
data type: JSON
method: GET
```
   Так же можно по айди
   
   uri: /api/settings/{id}  
```
data type: JSON
method: GET
```

**Редактирование:**

```
data type: JSON
method: POST
data: 
{
    "CoopID": 1, 
    "json": "{\"Debug\":\"0\",\n\"Doors\":\n{\"Debug\":\"0\",\"OpenByTime\":true,\"OpenByDaylight\":true,\"OpenTime\":\"05:54:00\",\"CloseTime\":\"11:03:00\",\"TempMore\":19,\"TempLess\":31},\n\"Heating\":\n{\"Debug\":\"0\",\"SwitchOn\":\"23\",\"SwitchOff\":\"23\"},\n\"Light\":\n{\"Debug\":\"0\",\"OpenByTime\":false,\"OpenBySensor\":true,\"OpenFrom\":\"05:00:00\",\"CloseBefore\":\"12:12:00\"},\"\nVent\":\n{\"Debug\":\"0\",\"TimeOn\":\"38\",\"TimeOff\":\"41\",\"TempThreshold\":\" 21\",\"TimeMode\":\" 0\"}}"
}
```

5) **Получить список курятников **

     uri: /api/user/coop 
```
data type: JSON
method: GET
```

6) **Для админа**

  Добавление курятника юзеру:
  
    uri: /api/user/addcoop
    ```
    data type: JSON
    method: POST
    data:
    {
    "CoopID": 2,
    "UserID": 1
    }
    ```
    
   Удаление курятника у юзера
   
   uri: /api/user/coop
       
  
    data type: JSON
    method: DELETE
    data:
    {
    "CoopID": 2,
    "UserID": 1
    }
    
     
   
