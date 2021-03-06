****
# День 2 <a name="day2"></a>


## Сбор фитнес и медицинских данных с помощью мобильных приложений <a name="31"></a>

В нашем хакатоне мы не имеем возможности использовать дорогостоящее медицинское оборудование, поэтому мы будет прототипировать систему на основе фитнес данных, полученных с помощью Ваших смартфонов.
В этой части нашего конкурса Вам предстоит разработать мобильное приложение, позволяющее собирать данные и передавать их в разрбатывемую систему через вычислительный хаб Raspberry Pi.

Вы можете использовать один из двух вариантов:

* Разработка в ОС Android.
* Разработка в IOS.

Подсистема сбора данных будет работать следующим образом. На смартфоне должны быть установлены приложения Google Fit и Apple Health, которые позволяют собирать различные фитнес-данные: активность, пройденный путь, количество шагов, пульс. Ондако при наличии специального оборудования и сенсоров, подключаемых к смарфону или передаваемых по беспроводным интерфейсам, эти приложения позволяют фиксировать и анализировать любые медицинские данные, а также передавать их по специальным API другим приложениям. Стоит отметить, что в настоящее время проекты динамично развиваются, поэтому не всегда представляется возможным быстро прототипировать проект из-зи наличия ошибок, отсутствия подробной документации и пр. Поэтому мы поступим другим образом: мы будем использовать накопленную статистику приложений, для чего мы разработаем собственное мобильное приложения, агрегирующее даные медицинского характера. 

## Мобильный телефон с ОС Android <a name="32"></a>

### Установка программного обеспечения для разработки мобильных приложений на OS Android <a name="321"></a>

Если вы решили делать приложение для Android, вам потребуются следующие компоненты:

* AndroidStudio
* Нужный нам SDK для AndroidStudio
* Android телефон
* Google аккаунт
* Приложение Google Fit
* Данные в Google Fit
Теперь рассмотрим подробнее каждый элемент отдельно.

#### Установка Android Studio <a name="3211"></a>

Переходим на сайт [https://developer.android.com/studio/](https://developer.android.com/studio/)

Скачиваем и устанавливаем `Android Studio` на компьютер (желательно исопльзовать ОС Linux). В ходе установки загружаем все предлагаемые модули.


#### Установка версии SDK <a name="3212"></a>

Определяем версию ОС Вашего телефона.

![Определение версии ОС Android](assets/image4-56.png)
**Распиновка Raspberry**

Запускаем студию и переходим в настройки. 

![Установка Android Studio](assets/SDK.png)
**Установка Android Studio**

Далее необходимо скачать нужный SDK из соответствующего раздела меню.

![Выбор версии ОС](assets/Android-SDK-24.4.1-Latest-Version-Download.png)
**Выбор версии ОС**

#### Android телефон, Google аккаунт, Приложение Google Fit <a name="3213"></a>


Вам необходимо создать аккаунт для вашего проекта. Зайти в него на телефоне и установить приложение `Google Fit` с помощью `Google Play Market`.

Далее запустите приложение и войдите под созданным аккаунтом. Теперь вам можно начать собирать данные, например, начав ходить по аудитории.  Проверьте, что данные корректно фиксируются в приложении `GoogleFit`.

![Приложение Google Fit](assets/GoogleFit.png)
**Приложение Google Fit**

### Сборка и запуск тестового приложения Android <a name="322"></a>


Данные о пульсе можно брать из приложения Accurate Heart Rate Monitor

![](assets/Android_html_14f3eb2f8656de30.png)

После установки приложения заходим в настройки и устанавливаем флаг интеграции с Google Fit

![](assets/Android_html_ea1277131a4ca99b.png)

Далее измеряем пульс. Вскоре эти данные должны появиться в облаке Google.

Для получения данных о сне устанавливаем Runtastic Sleep Better

![](assets/Android_html_5e94403be6fa9409.png)

Интеграция автоматическая

Для получения данных о питании устанавливаем myfitnesspal

![](assets/Android_html_3379c061e26f43b.png)


Скачайте тестовый проект MyApplication. Для этого скачайте [git репозиторий](https://github.com/alexbmstu/2018.git)

Вам понадобится архив в папке `./scr`. Распакуйте архив MyApplication4-2.zip.

Открываем папку с проектом в андройд студии.

![](assets/Android_html_8bcd05d31e182942.png)

Синхронизируем Gradle

![](assets/Android_html_1d748bdfffa9b2c0.png)

Нужна эта иконка

![](assets/Android_html_c98922279a04202f.png)

Далее подключаем телефон шнурок к компу

На телефоне открываем настройки и ищем страницу информации о ОС (о телефоне)

Много раз нажимаем на версию прошивки, пока не увидим сообщение о том что стали разработчиком

![](assets/Android_html_c6fce88d8df6496c.gif)

Далее где-то в настройках у вас появится пункт «Для разработчиков»

![](assets/Android_html_36c8dbf4b65f72cf.gif)

Открываем этот пункт, включаем режим разработчика и включаем все что связано с отладкой по USB

![](assets/Android_html_36a60ff32714ad68.gif) ![](assets/Android_html_9ef7d8303dc304cd.gif)

Далее идем в настройки проекта

![](assets/Android_html_46738d97691ddd88.png)

Устанавливаем минимальную версию SDK не ниже чем версия на вашем телефоне

![](assets/Android_html_b154999772502f4f.png)

Пробуем запустить приложение

![](assets/Android_html_a076265319378453.png)

В окне выбора устройств выбираем свой телефон

![](assets/Android_html_b42aea9b179417a9.png)

Далее необходимо настроить консоль разработчика

Идем на сайт

[https://console.developers.google.com](https://console.developers.google.com/)

В окне выбора проектов создаем новый

![](assets/Android_html_b9419a7dd5c11d8e.png)

Вводим имя проекта и сохраняем

В окне выбора проектов выбираем созданный проект

![](assets/Android_html_208dccb66d9c7037.png)

![](assets/Android_html_561c1afc02a2744e.png)

Жмем включить Api и Сервисы

В поиске вводим Fit и выбираем Fitness Api.

![](assets/Android_html_d835e4401ccaded6.png)

На странице Api жмем включить

Теперь нужно создать учетные данные

![](assets/Android_html_4228554e8cda4eb7.png)

или так

![](assets/Android_html_6cc240583ff1ac57.png)

На странице учетных данных жмем создать

![](assets/Android_html_36f7d18055e40435.png)

Заполняем первую форму

![](assets/Android_html_a4ca26a14681e8f5.png)

Жмем выбор типа учетных данных

Открываем окно Gradle

![](assets/Android_html_f079c6322684ab37.png)

Открываем Signing Report

![](assets/Android_html_f66a3f1cf94e57a1.png)

Дважды кликаем на него

В консоли нам напишет

![](assets/Android_html_f867acd3beeb5659.png)

Нас интересует этот блок

![](assets/Android_html_4c1ae61136bdf6d1.png)

Копируем SHA1 ключ

A7:fvdnvldfvnldfnvkldnvlkdnfvndfklvndlfnvkdfnvlkdnklfnvld

Открываем файл манифеста

![](assets/Android_html_193a41c49336dd86.png)

Ищем название пакета

package="com.example.alexdark.myapplication4"

![](assets/Android_html_5fb18a465ab137a4.png)

Жмем создать идентификатор клиента

Далее заполняем форму

![](assets/Android_html_e1576d155732e85.png)

Скачиваем ClientID

![](assets/Android_html_5e05523ea8ee76c6.png)

Это  строка  вида

чтоТоТамСекретное.apps.googleusercontent.com

Открываем файл констант

![](assets/Android_html_e88f7068271090a.png)

Меняем строчку

`<string name="server_client_id">-- </string>`

Вставляем свой ключ

Теперь еще раз запускаем приложение на устройстве и наслаждаемся его работой.

При запуске ждем когда произойдет подключение к серваку

Когда это произойдет жмем кнопку GetData

Важный код описан комментариями

  
Данные которые можно запрашивать из GoogleFit приведены тут

[https://developers.google.com/android/reference/com/google/android/gms/fitness/data/DataType](https://developers.google.com/android/reference/com/google/android/gms/fitness/data/DataType)

Чтобы получить доступ к ряду значений необходимо при создании клиента запрашивать дополнительные разрешения
```

mGoogleApiClient = new GoogleApiClient.Builder(this)
.addApi(Fitness._HISTORY_API_)
.addScope(new Scope(Scopes._FITNESS_ACTIVITY_READ_WRITE_))
.addScope(new Scope(Scopes._FITNESS_BODY_READ_WRITE_))
.addScope(new Scope(Scopes._FITNESS_NUTRITION_READ_))
.addConnectionCallbacks(this)
.enableAutoManage(this, 0, this)
.build();
```
Подробно об этом написано тут

https://developers.google.com/android/reference/com/google/android/gms/common/Scopes

Если вы хотите анализировать активность то расшифровка типов приведена тут

[https://developers.google.com/fit/rest/v1/reference/activity-types](https://developers.google.com/fit/rest/v1/reference/activity-types)

Если вам нужно получать из облака данные которых там нет, можно попробовать записать их туда самим. Google Fit позволяет записывать данные в облако. Тут очевидного ответа а как нет. Можно выделить лишь общий принцип

1.  Создаем дата сорс

2.  Создаем дата сет из сорса

3.  Создаем измерение

4.  Заполняем измерение данными

5.  Кладем измерение в дата сет

6.  Отправляем дата сет

Основные сложности будут с шагом 4\. Каждый дата поинт для разных типов данных имеет свою специфику заполнения. Это вам придется гуглить. В проекте есть пример для создания активити. Это самый простой пример. Желательно конечно, чтобы вы нашли мобильное приложение, которое интегрируется с фитом.

### Получение и обработка данных на nodejs сервере Raspberry Pi  <a name="331"></a>

Для того, чтобы протестировать получение данных вычислительным хабом RaspberryPi, необходимо поменять код приложения сервера nodejs. Для этого добавьте в код `index.js` в папке `./routes` следующий код:

```js 

router.post('/data', function (req, res) {
    console.log(req);
    res.send();
});

router.post('/step', function (req, res) {
    res.send();
    console.log('********')
    console.log('steps')
    console.log(req.body['start'])
    console.log(req.body['value'])

});

router.post('/pulse', function (req, res) {
    res.send();
    console.log('********')
    console.log('pulse')
    console.log(req.body['start'])
    console.log(req.body['value'])

});

router.post('/activity', function (req, res) {
    res.send();
    console.log('********')
    console.log('activity')
    console.log(req.body['start'])
    console.log(req.body['activity'])
    console.log(req.body['duration'])
    console.log(req.body['segments'])
});

router.post('/nutrition', function (req, res) {
    res.send();
    console.log('********')
    console.log('nutrition')
    console.log(req.body['start']);
    console.log(req.body['mealType']);
    console.log(req.body['calcium']);
    console.log(req.body['calories']);
    console.log(req.body['carbsTotal']);
    console.log(req.body['cholesterol']);
    console.log(req.body['dietaryFiber']);
    console.log(req.body['fatMonounsaturated']);
    console.log(req.body['fatPolyunsaturated']);
    console.log(req.body['fatSaturated']);
    console.log(req.body['fatTotal']);
    console.log(req.body['fatTrans']);
    console.log(req.body['iron']);
    console.log(req.body['potassium']);
    console.log(req.body['protein']);
    console.log(req.body['sodium']);
    console.log(req.body['sugar']);
    console.log(req.body['vitamin_c']);
});

```

!!! В случае возникновения проблем на сервере с парсингом POST запросов от мобильного телефона (например, возникает ошибка в запросе `router.post('/step', function (req, res) `) замените код на следующий (и аналогично для других POST запросов):

```js

app.post('/step', function (req, res) {
let body = '';
req.on('data', (data) => {
body += data;
}).on('end', () => {
const dataObj = JSON.parse(body);
console.log(dataObj);
// формат: {name: Nick, age: 19}
const start = dataObj.start;
const value = dataObj.value;
res.status(200);
res.end(JSON.stringify(dataObj));
});
});

```


Проверьте, что в логах запущенного nodejs появляются сообщения с данными от нашего приложения.

## Мобильный телефон с iOS <a name="33"></a>

### Установка программного обеспечения для разработки мобильных приложений на iOS <a name="331"></a>

Для того, чтобы разрабатывать мобильные приложения для `iOS` необходим компьютер старше 2013 года с операционной системой `maсOS Mojave`. На компьютер необходимо установить IDE для разработки `iOS` приложений – Xcode.

Xcode (версия 10) можно скачать в магазине App Store на компьютере с macOS Mojave :

![](assets/iOS_html_2d196317aa6bb516.png)

После установки, IDE отобразится в меню приложений:

![](assets/iOS_html_95debbd82af313ff.png)

Прежде чем писать приложения под `iOS` и отправлять их на сервер, необходимо их подготовить и собрать при помощи `iPhone`.

Любые параметры, связанные со здоровьем в `iPhone`, как правило передаются в системное приложение `Health`, которое выглядит так:

![](assets/iOS_html_c06e4f2a185a5031.png)

Подробное описание можно найти на сайте: [https://www.apple.com/ru/ios/health/](https://www.apple.com/ru/ios/health/)

Во время работы с нашим примером мы будем собирать следующие данные: пульс, медитацию, сон и отдых (в приложении называется осознанность), шаги, калории и другие параметры питания.

Чтобы собирать данные о пульсе необходимо:

1) Установить приложение

![](assets/iOS_html_b818428146844971.jpg)

2) Зайти в приложение Cardiio

![](assets/iOS_html_582217324c415d5c.jpg)

3) Зайти в настройки и проскроллить до секции `Apple Health`, после чего включить интеграцию с `Health`

![](assets/iOS_html_a66391c66f8a8299.jpg)

4) После измерения пульса, данные можно будет увидеть в `Health`

![](assets/iOS_html_2f275c92138b7eca.jpg)

Чтобы собирать данные с шагомера и пройденного расстояния не нужно ставить никаких дополнительных приложений, все данные уже находятся в `Health`:

![](assets/iOS_html_4b6eb75e2df605fe.jpg)

Чтобы собирать данные о питании необходимо проделать следующие шаги:

1) Установить приложение `FatSecret`

![](assets/iOS_html_61a282a276905974.jpg)

2) Зайти в настройки приложения и включить интеграцию с `Health`

![](assets/iOS_html_ebea3cd28a29ae1c.jpg)

3) Добавить прием пищи в приложение

![](assets/iOS_html_7af205cc846dc391.jpg)

4) После этого вся информации о питании будет доступна в `Health`

![](assets/iOS_html_6b91a9fa11f1d15f.jpg)

Для того чтобы собирать данные о медитации и отдыхе необходимо проделать следующие шаги:

1) Установить приложение `Relax Melodies`

![](assets/iOS_html_3078659d9baa9bab.jpg)

2) Включить в настройках интеграцию с `Health`

![](assets/iOS_html_c488a74b92455944.jpg)

3) Далее после медитации под какую-нибудь бесплатную мелодию данные о медитации отправятся в `Health`

![](assets/iOS_html_141b413dd1351942.jpg)


### Установка и запуск приложения <a name="332"></a>


Скачайте тестовый проект BMSTU2018. Для этого скачайте [git репозиторий](https://github.com/alexbmstu/2018.git)

Вам понадобится архив в папке `./scr`. Распакуйте архив BMSTU2018.zip.

Далее вам необходимо открыть файл с разрешением xcworkspace BMSTU.

Загрузите приложение на девайс.



### Получение и обработка данных на nodejs сервере Raspberry Pi  <a name="333"></a>

Для того, чтобы протестировать получение данных вычислительным хабом RaspberryPi, необходимо поменять код приложения сервера nodejs. Для этого добавьте в код `index.js` в папке `./routes` следующий код:

```js 
router.post('/data', function (req, res) {
    res.send();
    console.log(req.body['parameter']);
    console.log(req.body['value']);
});
```

Проверьте, что в логах запущенного nodejs появляются сообщения с данными от нашего приложения.





