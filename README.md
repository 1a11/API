# Dynamic AC (β)
#### API доступно по адресу: http://dynamicac.pythonanywhere.com/send
#### Запрос к API должен содержать в себе следующие данные:

|Поле|Описание|Тип данных|Вид передаваемых данных|
|----|--------|----------|-----------------------|
|APIKey|Твой ключ API|str|API key|
|enc|Используется ли шифрование в запросе|bool|True/False|
|keys|Строка нажатых клавиш|str|ababab|
|time|Продолжительность игры|str|10m/1m/5h|
|dur|Продолжительность нажатия клавиши|float|0.1/0.5/1.5|

###### Пример реализации JSON запроса на Python:

~~~~
def snd():
    values = {'APIKey':send,'enc':True,'keys':'adswdawdsadaw','time':'10m','dur':'0.1-0.2-0.1-0.2'} # json values
    r = requests.post('http://dynamicac.pythonanywhere.com/send/', json=values)
    return(r.text)
~~~~

#### Вы можете использовать массивы элементов в качестве значения списка

|Поле|Описание|Тип данных|Вид передаваемых данных|
|----|--------|----------|-----------------------|
|APIKey|Твой ключ API|str|API key|
|enc|Используется ли шифрование в запросе|bool|True/False|
|gid|Game ID|string dict|'1A1A1A-2B2B2B-3C3C3C'|
|keys|Строка нажатых клавиш|string array|['ababab','ababab']|
|time|Продолжительность игры|string|10m/1m/5h|
|dur|Продолжительность нажатия клавиши|float array|[[1.5,1.3,1.4],[1.5,1.3,1.4]]|


###### Пример реализации JSON запроса со списками на Python:

~~~~
def snd():
    values = {'APIKey':send,'enc':True,'gid':'1A1A1A-2B2B2B-3C3C3C','keys':['ababab','ababab'],'time':'10m','dur':[[1.5,1.3,1.4],[1.5,1.3,1.4]]} # json values
    r = requests.post('http://dynamicac.pythonanywhere.com/send/', json=values)
    return(r.text)
~~~~
# The following text is for RAM team members during the Discord Hackweek event.
There are 2 types of queries that you can perform to the database API. Below are both structured.

Below is an example of a post request and a table of its values. Such a request is needed in order to modify existing entries or create new settings.

|Field|Description|Type of the data|How they should look like|
|----|--------|----------|-----------------------|
|akey|Your API key|str|TEST:TESTKEYID12:SUPERSECRETSTRING|
|channel|Discord channel ID|str|'#abcdef'|
|type|Request type|string|'post'|
|sc|The type of string to be changed. Settings or coefficients|str|'s'|
|emoji|Emoji filter status|str|'y'/'n'|
|copypasta|Copypasta filter status|str|'y'/'n'|
|troll|Troll filter status|str|'y'/'n'|
|insult|Insult filter status|str|'y'/'n'|
|alt|Alt filter status|str|'y'/'n'|

Below is an example of a post request and a table of its values. Such a request is needed in order to modify existing entries or create new coef.

|Field|Description|Type of the data|How they should look like|
|----|--------|----------|-----------------------|
|akey|Your API key|str|TEST:TESTKEYID12:SUPERSECRETSTRING|
|channel|Discord channel ID|str|'#abcdef'|
|type|Request type|string|'post'|
|sc|The type of string to be changed. Settings or coefficients|str|'c'|
|troll|Troll filter status|real|'y'/'n'|
|insult|Insult filter status|real|'y'/'n'|

Below is an example of a post request and a table of its values. Such a query is needed in order to get existing records of coefficients and settings from the database.

|Field|Description|Type of the data|How they should look like|
|----|--------|----------|-----------------------|
|akey|Your API key|str|TEST:TESTKEYID12:SUPERSECRETSTRING|
|channel|Discord channel ID|str|'#abcdef'|
|type|Request type|string|'пуе'|
