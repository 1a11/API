# Dynamic AC (β)
#### API доступно по адресу: http://dynamicac.pythonanywhere.com/send
#### Запрос к API должен содержать в себе следующие данные:

|Поле|Описание|Тип данных|Вид передаваемых данных|
|----|--------|----------|-----------------------|
|APIKey|Твой ключ API|str|API key|
|enc|Используется ли шифрование в запросе|str|yes/no|
|keys|Строка нажатых клавиш|str|ababab|
|time|Продолжительность игры|str|10m/1m/5h|
|dur|Продолжительность нажатия клавиши|float|0.1/0.5/1.5|

###### Пример реализации JSON запроса на Python:

~~~~
def snd():
    values = {'APIKey':send,'enc':'yes','keys':'adswdawdsadaw','time':'10m','dur':'0.1-0.2-0.1-0.2'} # json values
    r = requests.post('http://dynamicac.pythonanywhere.com/send/', json=values)
    return(r.text)
~~~~
