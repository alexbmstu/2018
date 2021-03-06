# День 5 <a name="day5"></a>

## Облачная платформа *IBM Cloud* <a name="61"></a>

***IBM Cloud*** — это открытое облачная система типа PaaS
(*Platform-as-a-Service*) на базе проекта с открытым исходным кодом Cloud Foundry. Эта платформа предназначена для разработки и хостинга приложений, а также упрощения задач по управлению инфраструктурой. Она позволяет быстро создавать и развертывать приложения, а также управлять ими.

***IBM Cloud*** обеспечивает следующие возможности:

-   быстрое и инкрементное составление приложений из сервисов;
-   непрерывное внесение изменений в приложения и обеспечение постоянной доступности;
-   поддержка высокоспециализированных моделей программирования и сервисов для конкретных рабочих нагрузок;
-   встраивание высокой степени управляемости в сервисы и приложения;
-   оптимизация и эластичная адаптация к рабочей нагрузке.


![Каталог компонентов IBM Cloud](assets/intro04.jpg)
**Каталог компонентов IBM Cloud**


Платформа *IBM Cloud* достигает этих целей посредством абстрагирования и скрытия большинства сложностей, традиционно сопутствующих хостингу приложений в облаке и управлению ими в облачной среде. *IBM Cloud* может быть использована разработчиками для создания и применения самых разных приложений, включая веб-приложения, мобильные приложения, приложения для работы с большими данными, приложения для разумных устройств и т.д. *IBM Cloud* поддерживает разработку на популярных языках программирования и средах разработки. Java-технологии, средства создания серверных частей для мобильных приложений, мониторинг приложений, технологии с открытым исходным кодом и т. д. — все эти возможности
доступны в облаке как сервисы.

Каталог *IBM Cloud* содержит большую часть из того, что необходимо для быстрого начала работы, большое количество шаблонов, заранее сконфигурированны наборов сервисов, сред исполнения и примеров кода, готовых к использованию:

-   сред исполнения, в том числе: Liberty for Java, Node.js, Ruby on Rails;
-   веб-сервисов и сервисов приложений, в том числе: Data/Session Cache,  ElasticMQ, Decision, SSO, Log Analysis, Redis, RabbitMQ, Twilio;
-   мобильных сервисов, в том числе: push-уведомлений, Cloud Code,     Mobile Application Management, Mobile Quality Assurance;
-   сервисов управления данными, в том числе: MongoDB, реляционной базы данных от IBM, JSON-базы данных от IBM, MySQL, PostgreSQL, MobileData, Mobile Sync, BLU Data Warehouse, MapReduce;
-   сервисов мониторинга и анализа;
-   сервисов DevOps Services (прежнее название: JazzHub).
-   проприетарные сервисы IBM, включая аналитическую систему SPSS и другие. 
-   когнитивные сервисы IBM Watson.


****
## Краткое описание концепций *IBM Cloud* <a name="62"></a>


В терминологии *IBM Cloud* приложение (*application*) — это созданный вами артефакт, т. е. весь программный код (исходный код или исполняемые двоичные файлы), который необходимо запустить или на который необходимо сослаться в процессе исполнения. Мобильные приложения выполняются за пределами среды *IBM Cloud* и используют сервисы *IBM Cloud*, представленные приложениями. В случае веб-приложений приложение — это код, загруженный на платформу *IBM Cloud* с целью хостинга. Кроме того, платформа *IBM Cloud* способна осуществлять хостинг программного кода приложения, который вы хотите выполнять на внутреннем сервере в среде на базе контейнера.

На рисунке показаны принципы взаимодействия *IBM Cloud* с клинтскими приложениями.


![Принципы взаимодействия *IBM Cloud* с клинтскими приложениями](assets/intro05.jpg)
**Принципы взаимодействия *IBM Cloud* с клинтскими приложениями**


***Сервис (service)*** — это код, работающий на платформе *IBM Cloud* и предлагающий некоторую функциональность, которую могут использовать приложения. Это может быть готовый сервис, используемый непосредственно — например, push-уведомления для мобильных приложений или эластичное кэширование для веб-приложения. Вы также можете создавать собственные сервисы в диапазоне от простых служебных функций до сложной
бизнес-логики.

***Организация (organization) и пространство (space)*** — это организационные единицы инфраструктуры, способные хранить и отслеживать ресурсы приложения. Организация содержит домены (domain), пространства и пользователей. Пространство содержит приложения и сервисы. По умолчанию используется три пространства: Development (разработка), Production (производство) и Staging (подготовка). Для приложений, которым требуется среда типа PaaS, предоставляются buildpack-пакеты, каждый из которых представляет собой набор скриптов для подготовки кода к исполнению на целевой PaaS-платформе. Buildpack-пакеты, которые включают необходимую вашим приложениям среду исполнения и могут также содержать специализированные инфраструктуры, упрощают развертывание приложения в облаке по сравнению с самостоятельной установкой и конфигурированием среды исполнения.

Использование сервисов в *IBM Cloud* включает три этапа:
1.  Сообщите платформе *IBM Cloud*, что вам требуется новый экземпляр сервиса и какое конкретное приложение будет использовать этот новый экземпляр.
2.  *IBM Cloud* автоматически инициализирует новый экземпляр этого сервиса и свяжет его с приложением.
3.  Приложение взаимодействует с сервисом.

***Пакеты сервисов (Service bundles)*** — это коллекции API-интерфейсов, используемых в конкретных областях. Например, пакет Mobile Services включает сервисы MobileData, Cloud Code, Push и Mobile Application Management. Доступные сервисы и среды исполнения представлены в каталоге IBM Cloud. Кроме того, вы можете зарегистрировать собственные сервисы.

****
## Развертывание и управление приложением <a name="63"></a>

Чтобы развернуть свое приложение, необходимо загрузить его в среду *IBM Cloud* и указать, сколько экземпляров этого приложения должно исполняться, а затем сконфигурировать *IBM Cloud*, введя необходимую информацию для поддержки этого приложения.

В случае мобильного приложения среда *IBM Cloud* содержит артефакт, который представляет серверную часть мобильного приложения — набор сервисов, который использует приложение для взаимодействия с сервером. *IBM Cloud* поддерживает серверные компоненты мобильного приложения, взаимодействующие с сервисами PushWorks, Cloud Code и Mobile Data, непосредственно из пользовательского интерфейса *IBM Cloud*.

В случае веб-приложения необходимо предоставить в *IBM Cloud* соответствующую информацию о среде исполнения и среде разработки, чтобы платформа смогла сформировать надлежащую инфраструктуру для исполнения этого приложения.

При развертывании приложений и управлении ими можно использовать инструмент командной строки cf, веб-интерфейс *IBM Cloud* или сервисы DevOps Services.

Браузерные и мобильные клиенты — а также другие приложения, развернутые на платформе *IBM Cloud* и выполняющиеся за ее пределами — взаимодействуют с приложениями, работающими на платформе *IBM Cloud*, через API-интерфейсы типа REST/HTTP. Каждый клиентский запрос маршрутизируется к одному из экземпляров приложения или составляющих его сервисов. Среды исполнения приложений в *IBM Cloud* изолированы друг от друга даже тогда, когда они находятся на одной и той же физической машине.

В ходе управления приложениями можно запускать, останавливать, перезапускать экземпляры приложения (или, в случае веб-приложения, изменять их количество), а также изменять объем памяти, используемый приложением. Ключевая конструктивная особенность *IBM Cloud* — отличные показатели при хостинге масштабируемых приложений и артефактов приложений. На данный момент эта платформа не масштабирует приложение автоматически в соответствии с нагрузкой, поэтому этим процессом необходимо управлять самостоятельно посредством создания или удаления экземпляров при изменении рабочей нагрузки. По этой причине ваши приложения должны сохранять все персистентные данные за пределами приложения в одном из сервисов хранения данных, предоставляемых платформой *IBM Cloud*. При повторном развертывании приложения после обновления используется тот же процесс, что и при начальном развертывании. *IBM Cloud* останавливает все исполняющиеся экземпляры и переводит новые экземпляры в рабочее состояние автоматически.

****
## Сервисы DevOps Services для *IBM Cloud* <a name="64"></a>

При использовании DevOps Services требуется лишь несколько простых шагов для организации взаимодействия с другими специалистами с целью планирования, отслеживания и создания программного обеспечения в облаке. Вы можете воспользоваться встроенным в браузер редактором программного кода, который DevOps Services предоставляет для разработки приложений, или использовать DevOps Services с Eclipse, с VisualStudio или с инструментом командной строки Git для написания кода приложения и развертывания его на платформе IBM Cloud.

При работе с пользовательским интерфейсом, который помогает разработчику быстро добавлять сведения "кто", "что" и "когда" для своего рабочего проекта, требуется потратить всего несколько минут на задание дат, документирование первого сценария применения, назначение одной-двух задач и переход непосредственно к написанию программного кода.

DevOps Services включает встроенные средства управления исходным кодом — Jazz SCM и хостинговый Git. Каждый проект получает свой собственный репозиторий DevOps Services и рабочее пространство, в котором участники этого проекта могут регистрироваться свои изменения, ассоциировать изменения программного кода и просматривать историю недавних изменений. Кроме того, вы можете создать проект DevOps Services и указать на свой репозиторий GitHub.

Вы также можете с легкостью связать элементы работы с изменениями кода в GitHub. Кроме того, для написания кода в Git вы можете использовать имеющиеся у вас инструменты.

Типичными сценариями использования ресурса DevOps Services являются:

-   Создание приложения для анализа данных социальных сетей с использованием Node.js, Node-RED, Express, sentiment и ntwitter.
-   Создание приложения для создания интерактивных опросов в реальном     времени с использованием Node.js, Node-RED, Express, AngularJS и MongoDB.
-   Построение сервисов уведомления с использованием Node.js, Node-RED и MongoDB.
-   Создание приложений для управления аппаратными устройствами c использованием Node-RED и IoT компонент.


****
## Блокчейн технологии <a name="65"></a>


Смарт-контракт – это запрограммированная бизнес-логика и правила взаимодействия с данными, которые размещены в распределенном реестре (ledger). Реестр содержит цепочку блоков транзакций, которые совершили участники сети. Каждый последующий блок хранит хэш предыдущего блока, за счет чего обеспечивается невозможность изменения части информации. Процесс согласования корректности блока и добавления его в распределенный реестр называется консенсусом. Различные блокчейн-платформы имеют различные механизмы консенсуса: proof of work (PoW), proof of stake (PoS), byzantine fault tolerance (BFT) и прочие.

## Решение Hyperledger Fabric <a name="66"></a>

`Hyperledger` — это консорциум в рамках проекта `Linux Foundation`. `Hyperledger Fabric (HLF)` — реализация технологии блокчейн с контролируемым доступом (permissioned) для построения широкого спектра решений. Участники, взаимодействующие через `Hyperledger Fabric` определяются на этапе проектирования сети и могут иметь различные роли. Наиболее понятными сценариями для таких сетей являются цепочки поставок, в которых участвует множество независимых компаний. С технической точки зрения каждый участник имеет развернутый участок сети у себя в организации (или в облачной инфраструктуре), но не имеет доступа к участкам сети, развернутым в других компаниях. Начиная с версии 1.0 HLF специфична наличием Ordering Service, который является распределенным между участниками кластером и отвечает за очередность транзакций в формирующемся блоке. По сконфигурированным параметрам он собирает транзакции в сети и формирует блок. В случае отказа Ordering Service транзакции в сети перестанут регистрироваться, но сами данные останутся неизменными.

****
## Развертывание сети Blockchain с использованием API-интерфейсов Kubernetes на IBM Cloud <a name="66"></a>


Сеть Hyperledger Fabric можно развернуть несколькими способами:

* [Самостоятельно развернуть сеть нодов HLF из Docker образов](http://hyperledger-fabric.readthedocs.io/en/release-1.0/build_network.html)

* Использовать [Blockchain как услугу](https://console.bluemix.net/catalog/services/blockchain), размещенную в [IBM Cloud](https://console.bluemix.net/). `IBM Cloud` предоставляет доступ к HLF Blockchain как услугу для пользователей Starter и Enterprise Membership Plan (студенческий и преподавательский доступ МГТУ).

* Использовать сеть Hyperledger Fabric под управлением [Kubernetes](https://console.bluemix.net/containers-kubernetes/catalog/cluster), разворачиваемый через [службу IBM Cloud Container](https://console.bluemix.net/containers-kubernetes/catalog/cluster)

В этом примере мы будем использовать третий вариант: развернем и настроим сеть нодов  `Hyperledger Fabric` с использованием Kubernetes кластера в IBM Cloud Container Service.

Хостинг сети `Hyperledger Fabric` в `IBM Cloud` предоставляет много преимуществ:

- хостинг тестового решения будет выполнен на стороннем ресурсе;
- с одной системой смогу работать одновременно несколько пользователей
- решение может быть клонировано, сохранено на локальные машины и повторно развернуто на более продуктивной системе, в том числе на `IBM CLoud Private`. Обратите внимание, что настройка сети blockchain на Kubernetes удобна для демонстрационных сценариев, но для производства рекомендуется использовать `Blockchain` как услугу, размещенную на `IBM Cloud`.

****
## Использование Kubernetes в IBM Cloud <a name="67"></a>

[IBM Cloud Container](https://console.bluemix.net/containers-kubernetes/catalog/cluster) позволяет создать бесплатный кластер с двумя процессорами, 4 ГБ оперативной памяти и одним рабочим узлом. Это позволяет вам познакомиться и проверить возможности `Kubernetes`. Для реализации продуктивной работы такому решению не хватает некоторых возможностей, таких как использование файлового хранилища NFS и др..

Чтобы настроить кластер для максимальной доступности и емкости, IBM Cloud позволяет создать полностью настраиваемый, готовый к тестированию кластер под названием `_standard cluster_`. `_Standard cluster_` позволяют использовать различные конфигурации. Например, имеется возможность объединить два кластера, которые работают в разных регионах IBM Cloud, каждый из которых содержит несколько рабочих узлов. См. [https://console.bluemix.net/docs/containers/cs_planning.html#cs_planning_cluster_config](https://console.bluemix.net/docs/containers/cs_planning.html#cs_planning_cluster_config), чтобы познакомиться с другими вариантами построения высокодоступных конфигураций кластера.

Далее мы будем рассматривать шаблон `_free cluster_`, предоставляемый `IBM Cloud`. Этот шаблон предоставляет вам сценарии для автоматизации процесса настройки сети `Hyperledger Fabric` с использованием API-интерфейса `Kubernetes` в `IBM Cloud`.

****
## Развертывание blockchain решения <a name="68"></a>

  ![](assets/architecture.png)

После регистрации в IBM Cloud вы получите доступ в графический интерфейс управления вашей инфраструктурой. Далее необходимо в левом верхнем углу нажать на кнопку меню и выбрать `Containers`. Нам понадобится развернуть новый `Kubernetes Service`. Выбрав слева в меню пункт `Cluster`, вы увидите интерфейс создания кластера kubernetes и выбор региона, в котором кластер будет развернут. Вы можете создать бесплатный кластер в каждом регионе.

После нажатия кнопки `Create` следует выбрать тип кластера `Free` (_free cluster_) и придумать ему название. Создание кластера займет некоторое время.

Войдите в `IBM Cloud CLI` и выполните инициализацию плагина `IBM Cloud Container Service`.

Для этого установите плагин для bx для работы с kubernetes в IBM Cloud:

`bx plugin install container-service -r Bluemix`

Авторизуйтесь в IBM Cloud:

`bx login -a https://api.eu-gb.bluemix.net`

Укажите регион, где вы создали Ваш кластер (обычно, UK-south):

`bx cs region-set uk-south`

Запросить конфигурацию для вашего кластера, где mycluster — название, которые Вы ввели в графическом интерфейсе IBM Cloud;

`bx cs cluster-config mycluster`

Далее выполните команду, которую вы увидите в результате выполнения предыдущего шага. Она укажет утилите `kubectl`, где находятся ключи доступа к вашему кластеру (путь к конфигурационному файлу может меняться):

`export KUBECONFIG=/path/mycluster/kube-config-mil01-mycluster.yml`

Вы также должны узнать public IP вашего kubernetes worker узла:

`bx cs workers mycluster`

Проверьте, что `kubectl` настроен на `IBM CLoud`:

```
kubectl version  --short
Client Version: v1.9.2
Server Version: v1.8.6-4+9c2a4c1ed1ee7e

kubectl get pods
NAME                          READY     STATUS    RESTARTS   AGE
mycluster-54958d8d9-t5gc2     1/1       Running   0          40d

```

Теперь вы готовы к тому, чтобы начать использовать ваш `kubernetes`-кластер для любых целей. Кластер является бесплатным, в его функционале есть некоторые ограничения, которые нам не помешают развернуть свою блокчейн-сеть

 
## Развертывание сети Hyperledger в Kubernetes <a name="611"></a>

Этот шаблон предоставляет сценарий, который автоматически создает сеть Hyperledger Fabric, состоящую из четырех организаций, каждая из которых поддерживает один одноранговый узел. Кроме того, скрипт создает канал с именем «channel1», соединяет все узлы с каналом «channel1», устанавливает цепочку кодов на всех одноранговых узлах и создает цепочку цепочек на канале. Шаблон также помогает управлять выполнением транзакций по развернутому цепочному коду.

Клонируйте сценарии конфигурации Kubernetes в домашний каталог вашего компьютера:

`git clone https://github.com/IBM/blockchain-network-on-kubernetes.git`

Перейдите в каталог c исходными кодами проекта:

  ```
  cd blockchain-network-on-kubernetes
  ls
  ```

В каталоге находятся файлы:

* `configFiles`  - файлы конфигурации Kubernetes

* `artifacts` - файлы конфигурации сети

* `*.sh` - скрипты для развертывания и удаления сети
  
Если есть какие-либо изменения в топологии сети, необходимо соответствующим образом изменить файлы конфигурации (.yaml-файлы). Файлы конфигурации находятся в каталоге `artifacts` и` configFiles`. Например, если вы решите увеличить / уменьшить емкость хранилища, вам необходимо изменить параметры хранилища в файле`createVolume.yaml`.

## Запуск сценария для развертывания сети узлов <a name="613"></a>

После того, как вы получили файлы конфигурации, вы можете развернуть свою сеть. Выполните сценарий для развертывания blockchain сети.

  ```
  $ chmod + x setup_blockchainNetwork.sh
  $ ./setup_blockchainNetwork.sh
  ```

## Удалить сеть <a name="614"></a>

Если необходимо, вы можете удалить сеть с помощью скрипта `deleteNetwork.sh`. Этот скрипт удалит все ваши контейнеры, задания, deployments и т.д. из вашего кластера `Kubernetes`.

  ```
  $ chmod + x deleteNetwork.sh
  $ ./deleteNetwork.sh
  ```

## Протестируйте развернутую сеть <a name="615"></a>

После успешного выполнения скрипта `setup_blockchainNetwork.sh`, проверьте состояние контейнеров.

```
kubectl get pods
NAME                                    READY     STATUS    RESTARTS   AGE
blockchain-ca-7848c48d64-2cxr5          1/1       Running   0          4m
blockchain-orderer-596ccc458f-thdgn     1/1       Running   0          4m
blockchain-org1peer1-747d6bdff4-4kzts   1/1       Running   0          4m
blockchain-org2peer1-7794d9b8c5-sn2qf   1/1       Running   0          4m
blockchain-org3peer1-59b6d99c45-dhtbp   1/1       Running   0          4m
blockchain-org4peer1-6b6c99c45-wz9wm    1/1       Running   0          4m
```

Как упоминалось выше, скрипт объединяет все одноранговые узлы на один канал `channel1` и инициализирует цепочку blockchain на всех одноранговых узлах. Это означает, что мы можем выполнить команду invoke / query на любом равноправном узле, и ответ должен быть одинаковым для всех одноранговых узлов. Обратите внимание, что в этом шаблоне отключена служба сертификации, чтобы сократить время развертывания и сложность инструкции. Более детальная информация о развертывании Hyperledger Fabric может быть найдена [тут](https://hyperledger-fabric.readthedocs.io) 

Для запуска процесса выполнения blockchain запроса с любым партнером необходимо войти в оболочку bash однорангового узла, запустить запрос и выйти из однорангового узла. Используйте следующую команду, чтобы попасть в оболочку bash однорангового узла:

  ```
  $ kubectl exec -it <blockchain-org1peer1 pod name> bash
  ```

Для выходы вы можете использовать команду:

  ```
  # exit
  ```

В исходном проекте был создан Chaincode со значениями `{a: 100, b: 200}`.  Выдадим запрос у узла `org1peer1` о текущем зачении ключа `a`, чтобы убедиться, что цепочный код был правильно создан.


```sh
root@blockchain-org1peer1-7d95cbfd64-ttmq2:/# peer chaincode query -C channel1 -n cc -c '{"Args":["query","a"]}'
2018-11-22 18:37:56.156 UTC [msp] GetLocalMSP -> DEBU 001 Returning existing local MSP
2018-11-22 18:37:56.156 UTC [msp] GetDefaultSigningIdentity -> DEBU 002 Obtaining default signing identity
2018-11-22 18:37:56.156 UTC [chaincodeCmd] checkChaincodeCmdParams -> INFO 003 Using default escc
2018-11-22 18:37:56.156 UTC [chaincodeCmd] checkChaincodeCmdParams -> INFO 004 Using default vscc
2018-11-22 18:37:56.156 UTC [chaincodeCmd] getChaincodeSpec -> DEBU 005 java chaincode disabled
2018-11-22 18:37:56.157 UTC [msp/identity] Sign -> DEBU 006 Sign: plaintext: 0AA3070A6308031A0B0884EFDBDF0510...120263631A0A0A0571756572790A0161 
2018-11-22 18:37:56.157 UTC [msp/identity] Sign -> DEBU 007 Sign: digest: 6B6CE906AE6133412FAD14FBC53533DD26B82EF44605243464334AD98B5F8C32 
Query Result: 100
2018-11-22 18:37:56.178 UTC [main] main -> INFO 008 Exiting.....

```


Теперь отправим запрос к `org1peer1`, чтобы переместить 20 единиц из ` a` в `b`. Будет создана новая транзакция, и после успешного завершения транзакции состояние будет обновлено.


```sh
root@blockchain-org1peer1-7d95cbfd64-ttmq2:/# peer chaincode invoke -o blockchain-orderer:31010 -C channel1 -n cc -c '{"Args":["invoke","a","b","20"]}'
2018-11-22 18:41:36.711 UTC [msp] GetLocalMSP -> DEBU 001 Returning existing local MSP
2018-11-22 18:41:36.711 UTC [msp] GetDefaultSigningIdentity -> DEBU 002 Obtaining default signing identity
2018-11-22 18:41:36.713 UTC [chaincodeCmd] checkChaincodeCmdParams -> INFO 003 Using default escc
2018-11-22 18:41:36.713 UTC [chaincodeCmd] checkChaincodeCmdParams -> INFO 004 Using default vscc
2018-11-22 18:41:36.714 UTC [chaincodeCmd] getChaincodeSpec -> DEBU 005 java chaincode disabled
2018-11-22 18:41:36.715 UTC [msp/identity] Sign -> DEBU 006 Sign: plaintext: 0AA4070A6408031A0C08E0F0DBDF0510...696E766F6B650A01610A01620A023230 
2018-11-22 18:41:36.715 UTC [msp/identity] Sign -> DEBU 007 Sign: digest: 4BCF82ACFD37554A86B19A3C1147BA3E473EF8CD6B1D2A1D5A1335DA4D51DD4D 
2018-11-22 18:41:36.735 UTC [msp/identity] Sign -> DEBU 008 Sign: plaintext: 0AA4070A6408031A0C08E0F0DBDF0510...DABE53824161E5265121E39183CCABED 
2018-11-22 18:41:36.735 UTC [msp/identity] Sign -> DEBU 009 Sign: digest: BFE329AFC2830609FAC722E0AC9230E73495B3360C85F830427F1BB7FC12483C 
2018-11-22 18:41:36.741 UTC [chaincodeCmd] chaincodeInvokeOrQuery -> DEBU 00a ESCC invoke result: version:1 response:<status:200 message:"OK" > payload:"\n c*\203\322\"k\351\336\240\215\260\353\347\n\252\t\3319'v\240\365\355\313J\362f>\3540f\300\022S\nA\022+\n\002cc\022%\n\007\n\001a\022\002\010\001\n\007\n\001b\022\002\010\001\032\007\n\001a\032\00280\032\010\n\001b\032\003220\022\022\n\004lscc\022\n\n\010\n\002cc\022\002\010\001\032\003\010\310\001\"\t\022\002cc\032\0031.0" endorsement:<endorser:"\n\007Org1MSP\022\222\006-----BEGIN CERTIFICATE-----\nMIICGDCCAb+gAwIBAgIQKtNDOa1IlNQX9GocXWPpTjAKBggqhkjOPQQDAjBzMQsw\nCQYDVQQGEwJVUzETMBEGA1UECBMKQ2FsaWZvcm5pYTEWMBQGA1UEBxMNU2FuIEZy\nYW5jaXNjbzEZMBcGA1UEChMQb3JnMS5leGFtcGxlLmNvbTEcMBoGA1UEAxMTY2Eu\nb3JnMS5leGFtcGxlLmNvbTAeFw0xODExMjIxODI3MTdaFw0yODExMTkxODI3MTda\nMFsxCzAJBgNVBAYTAlVTMRMwEQYDVQQIEwpDYWxpZm9ybmlhMRYwFAYDVQQHEw1T\nYW4gRnJhbmNpc2NvMR8wHQYDVQQDExZwZWVyMC5vcmcxLmV4YW1wbGUuY29tMFkw\nEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAE34RrdhgwrExCzne7t2Q/gPgQ21m+c5G+\naCCuBGfDceVS+mol+PC39FePtMP3c0iDVDhwPI9UGTTeM316C0lpg6NNMEswDgYD\nVR0PAQH/BAQDAgeAMAwGA1UdEwEB/wQCMAAwKwYDVR0jBCQwIoAggca8Yy4TN3A+\nGWL+fxflCScOOh5+PfHHqjY0wWuDanYwCgYIKoZIzj0EAwIDRwAwRAIgUN6Z8R5b\nrELp0gFyzeSoxWW1StUttju8v4m+XOLxCI4CIB5/b8cm+gU5ouvPs1iza6H7F35D\nHO9ZpVREzqu7H/lz\n-----END CERTIFICATE-----\n" signature:"0D\002 D\003\t:\013DX\243Pu<f4\244<\363\034\035\333{\224'\350\376\327\350W\351L\343\017\257\002 rv\024H\312\250\t\236F\363\365%PS\231\355\332\276S\202Aa\345&Q!\343\221\203\314\253\355" > 
2018-11-22 18:41:36.741 UTC [chaincodeCmd] chaincodeInvokeOrQuery -> INFO 00b Chaincode invoke successful. result: status:200 
2018-11-22 18:41:36.742 UTC [main] main -> INFO 00c Exiting.....
```

Давайте подтвердим, что наш предыдущий вызов выполнен правильно. Мы инициализировали ключ `a` со значением 100 и просто удалили 20 с помощью нашего предыдущего вызова. Поэтому ключ `a` должен показывать 80, ключ ` b` должен показывать 220. 

```sh
root@blockchain-org1peer1-7d95cbfd64-ttmq2:/# peer chaincode query -C channel1 -n cc -c '{"Args":["query","a"]}'
2018-11-22 18:41:52.035 UTC [msp] GetLocalMSP -> DEBU 001 Returning existing local MSP
2018-11-22 18:41:52.035 UTC [msp] GetDefaultSigningIdentity -> DEBU 002 Obtaining default signing identity
2018-11-22 18:41:52.035 UTC [chaincodeCmd] checkChaincodeCmdParams -> INFO 003 Using default escc
2018-11-22 18:41:52.035 UTC [chaincodeCmd] checkChaincodeCmdParams -> INFO 004 Using default vscc
2018-11-22 18:41:52.035 UTC [chaincodeCmd] getChaincodeSpec -> DEBU 005 java chaincode disabled
2018-11-22 18:41:52.036 UTC [msp/identity] Sign -> DEBU 006 Sign: plaintext: 0AA3070A6308031A0B08F0F0DBDF0510...120263631A0A0A0571756572790A0161 
2018-11-22 18:41:52.036 UTC [msp/identity] Sign -> DEBU 007 Sign: digest: B7968F08A80E4F09FCB7E714A5741386C9206AB896103A0E883F2B6030B38EA2 
Query Result: 80
2018-11-22 18:41:52.053 UTC [main] main -> INFO 008 Exiting.....
```

и

```sh
root@blockchain-org1peer1-7d95cbfd64-ttmq2:/# peer chaincode query -C channel1 -n cc -c '{"Args":["query","b"]}'
2018-11-22 18:45:11.948 UTC [msp] GetLocalMSP -> DEBU 001 Returning existing local MSP
2018-11-22 18:45:11.948 UTC [msp] GetDefaultSigningIdentity -> DEBU 002 Obtaining default signing identity
2018-11-22 18:45:11.949 UTC [chaincodeCmd] checkChaincodeCmdParams -> INFO 003 Using default escc
2018-11-22 18:45:11.949 UTC [chaincodeCmd] checkChaincodeCmdParams -> INFO 004 Using default vscc
2018-11-22 18:45:11.950 UTC [chaincodeCmd] getChaincodeSpec -> DEBU 005 java chaincode disabled
2018-11-22 18:45:11.951 UTC [msp/identity] Sign -> DEBU 006 Sign: plaintext: 0AA4070A6408031A0C08B7F2DBDF0510...120263631A0A0A0571756572790A0162 
2018-11-22 18:45:11.951 UTC [msp/identity] Sign -> DEBU 007 Sign: digest: AA2A7E3E751EA702819BA4386FF82E602783B359BE9F152EA799FDC9634026D5 
Query Result: 220
2018-11-22 18:45:11.963 UTC [main] main -> INFO 008 Exiting.....

```

Теперь выпустите запроса на `org2peer1`, `org3peer1` и` org4peer1` и проверьте идентичность ключей.


## Просмотр панели Kubernetes <a name="616"></a>

Получите токен, используя следующую команду для проверки подлинности панели инструментов Kubernetes.

  ```
  $ kubectl config view -o jsonpath = '{.users[0].user.auth-provider.config.id-token}'
  ```

Скопируйте токен. Запустите панель управления Kubernetes с портом 8001 по умолчанию.

  ```
  $ kubectl proxy
  ```

Откройте URL-адрес http://localhost:8001/ui в веб-браузере  на вашем компьютере, чтобы увидеть панель инструментов `Kubernetes`. Пройдите аутентификацию.

  ![](assets/provide-token-for-dashboard.png)

Предоставьте токен и `SIGN-IN`. На вкладке «Нагрузки» вы можете увидеть ресурсы, созданные с помощью скриптов.

  ![](assets/kubernetes-dashboard.png)

Тепеь blockchain сеть готова к использованию. Вы можете приступить к разработке своих программных блоков с помощью `sdk` или `url` развернутой сети.

## Подключение к сети с помощью клиентского SDK <a name="617"></a>

Для разработки вашего `blockchain`-приложения в развернутой сети вам необходимо подключиться к этой сети с помощью клиентского SDK. Для подключения к сети:

* Получите публичный IP-адрес своего кластера кубернетов из IBM Cloud Dashboard.

* Подключите этот публичный IP-адрес и порты, открытые с помощью [services](https://github.com/IBM/blockchain-network-on-kubernetes/blob/master/configFiles/blockchain-services.yaml).

Например: Порт узла равен «30054», поэтому URL-адрес клиент будет `http://<общедоступный IP-адрес вашего кластера>:30054/`

Таким образом, клиент может быть создан как:

  ```
  fabric_ca_client = new Fabric_CA_Client ('http://<общедоступный IP-адрес вашего кластера>:30054/', tlsOptions, 'CA1', crypto_suite);
  ```

Аналогичным образом, следующий код может использоваться для настройки сети.

  ```
  // setup the fabric network
  var fabric_client = new Fabric_Client();
  
  var channel = fabric_client.newChannel('channel1');
  var peer = fabric_client.newPeer('grpc://< public IP of your cluster >:30110');
  channel.addPeer(peer);
  var order = fabric_client.newOrderer('grpc://< public IP of your cluster >:31010')
  channel.addOrderer(order);
  ```


## Полезные ссылки к дню 5 <a name="618"></a>

* [Примеры и учебные материалы по Hyperledger Fabric](https://github.com/CATechnologies/blockchain-tutorials)

* [Hyperledger Fabric](https://hyperledger-fabric.readthedocs.io/en/release-1.1/)

* [Развертывание Fabric](https://github.com/IBM/blockchain-network-on-kubernetes/blob/master/README.md)

* [Пример Fabric nodejs](https://github.com/hyperledger/fabric-samples/blob/release/fabcar/query.js)

* [Kubernetes](https://kubernetes.io/docs/concepts/)

* [Управление кластером Kubernetes в IBM Cloud](https://console.bluemix.net/docs/containers/cs_clusters.html#planning_clusters)


# День 6 <a name="day6"></a>

## Разработка приложения для доступа к кластеру *Hyperledger Fabric* <a name="71"></a>

Разработаем приложение, которое образается к развернутому нами кластеру `Hyperledger Fabric`. Для этого узнаем `ip` адрес и порты управляющего пода канала (`blockchain-ca`), секвенсера запросов (`blockchain-orderer`) и одного из пиров (`blockchain-org1peer1`). 

```
$ kubectl get svc
NAME                   TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)                           AGE
blockchain-ca          NodePort       172.21.74.249    <none>        30054:30054/TCP                   3d
blockchain-orderer     NodePort       172.21.235.98    <none>        31010:31010/TCP                   3d
blockchain-org1peer1   NodePort       172.21.30.78     <none>        30110:30110/TCP,30111:30111/TCP   3d
blockchain-org2peer1   NodePort       172.21.204.175   <none>        30210:30210/TCP,30211:30211/TCP   3d
blockchain-org3peer1   NodePort       172.21.243.238   <none>        30310:30310/TCP,30311:30311/TCP   3d
blockchain-org4peer1   NodePort       172.21.184.139   <none>        30410:30410/TCP,30411:30411/TCP   3d
kubernetes             ClusterIP      172.21.0.1       <none>        443/TCP                           43d
mycluster03            LoadBalancer   172.21.155.180   <pending>     2022:32022/TCP                    43d
```

Данные адреса понадобятся в приложении, которое будет обращаться к кластеру и выполнять тразакции.
Пример приложение вы можете скачать [тут](https://github.com/maxim218/medicsBlockChain/)

Далее необходимо установить Node.js приложение на Вашем сервере ICP (см. день 4). 


Внутри папки **chaincode/fabcar/node** ставим библиотеки NodeJS

```
npm install
```

Внутри папки **fabcar** ставим библиотеки NodeJS

```
npm install
```

Заходим в папку **fabcar**

```
cd fabcar
```

Запускаем fabric

```
sudo bash ./startFabric.sh node
```

Добавляем админа

```
node enrollAdmin.js
```

Добавляем пользователя

```
node registerUser.js
```

Запускаем сервер

```
npm start
```

При этом нужно настроить ряд параметров для коммуникации: 


![Изменения в настройках приложения](assets/hyperledger_example.png)

![Изменения в настройках приложения](assets/hyperledger_example1.png)


Далее вы можете использовать `Python` скрипт. Скрипт может быть запущен как на сервере ICP, так и на машине пользователя. В последнем случае необходимо поменять ip адрес с `Localhost` на адрес сервера.


```
python ./send.py
```




