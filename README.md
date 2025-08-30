# ChangeStreamName
Изменение названия трансляции 

Нужно:
1) Получить access_token (!!!Это ваш личный ключ. Никому его не показывайте!!!)
2) Получить broadcasterId

1) Чтобы получить access_token переходим по ссылке. 
https://id.twitch.tv/oauth2/authorize?client_id=ztdcs2aqnlcvjpaxmu7u19xsa497zn&redirect_uri=http://localhost&response_type=token&scope=channel:manage:broadcast

	После чего вы будете перенаправлены на другой URL(Страница не найдена).
	В этот момент из URL копируем ключ после access_token= до &scope
	URL будет выглядеть так:
http://localhost/#access_token=3w7m8on8yuyqebе1nic3eethd2lxbv&scope=channel%3Amanage%3Abroadcast&token_type=bearer

2) Заходите на ваш канал https://www.twitch.tv/ВАШЕ_ИМЯ
	Нажимаем f12 -> Network(Закладка вверху) -> f5(Обновить страницу) -> 
	-> В поле Name выбираем gql 2q или 3й -> Response(Закладка правее) ->
	-> Ctrl+а в окне поиска пишете ваше имя. Нужно найти что-то вроде 
			"data": {
            		        "user": {
	ТО ВАШ broadcasterId ->"id": "25726788", <- ЭТО ВАШ broadcasterId
                		"displayName": "ВАШЕ_ИМЯ",
                		"self": {

3) Далее открываем через блокнот ChangeStreamName.html
4) На строках 97 и 102 в полях value="accessToken"> поменять на веше значение
5) Сохранить
6) Открыть двойным кликом ChangeStreamName.html(должен открыться браузер)
7) В поле пишем название стрима, нажимаем "Изменить"
8) Profit
