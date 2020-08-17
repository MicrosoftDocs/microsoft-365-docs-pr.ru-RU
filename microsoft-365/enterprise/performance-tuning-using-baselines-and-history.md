---
title: Настройка производительности Office 365 с помощью базовых показателей и истории производительности
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/31/2017
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 1492cb94-bd62-43e6-b8d0-2a61ed88ebae
ms.collection:
- M365-security-compliance
- Ent_O365
- SPO_Content
description: Узнайте, как проверить историю подключений клиентских компьютеров, чтобы упростить обнаружение новых проблем.
ms.openlocfilehash: 2337b14542f894e9a62037b2f032632147e45e09
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693222"
---
# <a name="office-365-performance-tuning-using-baselines-and-performance-history"></a>Настройка производительности Office 365 с помощью базовых показателей и истории производительности

Существует несколько простых способов проверить производительность подключения между Office 365 и предприятием, которое позволит вам создать грубую базовую линию подключения. Сведения о том, как вести журнал производительности клиентских компьютеров, поможет обнаружить возникающие проблемы на ранних этапах, выявить и предсказать проблемы.
  
Если вы не используете проблемы с производительностью, эта статья поможет вам определить некоторые распространенные вопросы, например, как вы узнаете, что проблема связана с производительностью, а не инцидентом службы Office 365? Как вы можете спланировать хорошую производительность, долгосрочный срок? Как можно следить за производительностью? Если у вашей команды или клиентов низкая производительность при использовании Office 365, а вы хотите узнать о них, читайте здесь.
  
> [!IMPORTANT]
> **У вашего клиента и Office 365 прямо сейчас возникла ошибка производительности?** Выполните действия, описанные в статье [план устранения неполадок с производительностью для Office 365](performance-troubleshooting-plan.md). 
    
## <a name="something-you-should-know-about-office-365-performance"></a>Что нужно знать о производительности Office 365

Office 365 входит в состав выделенной сети Microsoft, которая постоянно отслеживается не только с помощью автоматизации, но и от реальных людей. Частью роли обслуживания облака Office 365 является настройка производительности и упрощение их там, где это возможно. Так как клиенты в облаке Office 365 должны подключаться через Интернет, существуют непрерывные усилия для точной настройки производительности в службах Office 365. Улучшения производительности никогда не останавливаются в облаке, и существует большой объем накопленного опыта, позволяющий обеспечить работоспособность и быструю работу облака. Если у вас возникла ошибка, связанная с производительностью, подключаясь к Office 365, лучше всего не начинать с него и ждать обращения в службу поддержки. Вместо этого следует начать исследование проблемы с "во внутренней сети". То есть, начать в сети и эффективно работать в Office 365. Прежде чем открыть дело с поддержкой Office 365, можно собрать данные и выполнить действия, которые позволят исследовать и устранять неполадку.
  
> [!IMPORTANT]
> Помните о планировании и ограничении емкости в Office 365. Эти сведения помещают перед собой кривую при устранении проблем с производительностью. Ниже приведена ссылка на [Описание служб microsoft 365 и Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library). Это центральный центр, и все службы, предлагаемые Office 365, имеют ссылку на свои описания в службах. Это означает, что при необходимости увидеть стандартные пределы для SharePoint Online, например, следует щелкнуть [Описание службы SharePoint Online](https://technet.microsoft.com/library/sharepoint-online-service-description.aspx) и найти соответствующий [раздел SharePoint Online Limits](https://go.microsoft.com/fwlink/p/?LinkID=856113). 
  
Убедитесь, что вы перейдете к устранению неполадок с учетом того, что производительность является скользящим масштабом, но это не повлечет за собой неоптимальное значение и его поддержание без возможности восстановления (если вы считаете, что это так, то иногда задачи с большим количеством пропускной способности, такие как встроенное количество пользователей, или выполнение больших миграций данных будут сильно затруднить Кроме того, вы можете иметь грубое представление целевых показателей производительности, но большое количество переменных играют производительность, поэтому производительность варьируется. Это характер производительности. 
  
Устранение неполадок с производительностью не относится к конкретным целям собраний и не сохраняет эти номера в течение неопределенного периода, это сведения об улучшении существующих действий с учетом всех переменных. 
  
## <a name="okay-what-does-a-performance-problem-look-like"></a>Что же такое проблема с производительностью?

Для начала необходимо убедиться, что вы столкнулись с проблемой производительности, а не инцидентом службы. Проблема с производительностью отличается от инцидента службы в Office 365. Вот как их отличить.
  
Если у службы Office 365 возникли проблемы, это инцидент службы. В разделе **Текущая работоспособность** центра администрирования Microsoft 365 вы увидите значки красного или желтого цвета, Кроме того, вы можете заметить снижение производительности на клиентских компьютерах, подключающихся к Office 365. Например, если отчет о работоспособности выводится красным значком и **вы видите около** Exchange, вы также можете получить ряд вызовов от людей в вашей организации, которые занимаются неправильными почтовыми ящиками клиентов, использующих Exchange Online. В этом случае разумно предположить, что производительность Exchange Online сразу же стала жертвой проблем в службе. 
  
![Панель мониторинга работоспособности Office 365 со всеми рабочими нагрузками, в которых отображаются зеленые, за исключением Exchange, в котором показана восстановленная служба.](../media/ec7f0325-9e61-4e1a-bec0-64b87f4469be.PNG)
  
На этом шаге администратор Office 365 должен проверить **текущую работоспособность** , а затем **Просмотреть сведения и журнал**, как правило, чтобы последние даты обслуживания системы. Текущая панель мониторинга **работоспособности** была обновлена при изменении и проблемах в службе. Примечания и объяснения, записанные в журнал работоспособности, администратор для администраторов, помогут вам оценить влияние и сохранить текущую работу. 
  
![Изображение панели мониторинга работоспособности Office 365, в которой объясняется, что служба Exchange Online восстановлена и почему.](../media/66609554-426a-4448-8be6-ea09817f41ba.PNG)
  
Проблемы с производительностью не являются инцидентом службы, несмотря на то, что происшествия могут привести к снижению производительности. Проблема с производительностью выглядит следующим образом:
  
- Проблема с производительностью возникает независимо от того, какие сведения о **работоспособности** в центре администрирования поддаются отчетности для службы. 
    
-  Поведение, которое было бы относительно прозрачным, занимает много времени и не завершается. 
    
- Вы также можете реплицировать проблему, или, по крайней мере, вы знаете, что это произойдет, если выполнить нужную последовательность действий.
    
-  Если проблема повторяется, по-прежнему существует шаблон, например, если вы знаете, что у вас 10:00 вызовов от пользователей, которые не могут надежно получить доступ к Office 365, и что вызов будет нарушен по полудню. 
    
Возможно, это звучит знакомо; может быть знакомо. Когда вы узнаете, что проблема связана с производительностью, вопрос будет таким: "что делать дальше?" В оставшейся части этой статьи вы захотите точно определить, что.
  
## <a name="how-to-define-and-test-the-performance-problem"></a>Определение и тестирование проблемы с производительностью

Проблемы с производительностью часто возникают с течением времени, поэтому может быть непросто определить фактическую проблему. Вам необходимо создать хороший отчет о проблеме и получить хорошую идею контекста проблемы, а затем для этого необходимо выполнить повторяемые этапы тестирования. В противном случае вы можете потерять ошибку. Почему? Вот несколько примеров проблем с операторами, которые не предоставляют достаточно сведений:
  
- Переключиться из папки "Входящие" в календарь на что-то не заметить, а теперь это "кофе". Вы можете сделать так, чтобы он действовал?
    
- Отгрузка моих файлов в SharePoint Online идет очень долго. Почему он работает медленнее, но любое другое время это быстро? Не может работать достаточно быстро?
    
Существует несколько больших проблем, которые приводят к возникновению проблемных операторов выше. В частности, существует множество неоднозначностей, с которыми можно справиться. Пример:
  
- Неясно, как переключение между папкой "Входящие" и "Календарь", используемыми для работы на ноутбуке.
    
- Когда пользователь говорит: "не удается просто", "высокая"?
    
- Какова продолжительность "бессрочно"? Это может занять несколько секунд или минут, а пользователь может закончиться через десять минут после того, как пользователь возвратит запрос?
    
Все это не учитывается, что администратор и средство устранения неполадок не могут знать многие сведения о подобных операторах, подобные этим. Например, при возникновении проблемы. Пользователь работает из дома и в домашней сети видит только медленное переключение. Пользователь должен запустить несколько других приложений, интенсивно использующих ОЗУ, на локальном клиенте или запустить более раннюю версию операционной системы или не запускать последние обновления.
  
Если пользователи сообщают о проблеме с производительностью, сбор данных осуществляется очень подробно. Сбор этих сведений является частью процесса, который называется областью выпуска или исследованием. Ниже приведен список основных областей, которые можно использовать для сбора сведений о проблемах с производительностью. Этот список не является исчерпывающим, но существует место для самостоятельного запуска. 
  
- В какой дате возникла ошибка, и вокруг какого времени суток или ночью?
    
- Какой тип клиентского компьютера использовался и как он подключается к бизнес-сети (VPN, проводная связь, беспроводная связь)?
    
- Вы работали удаленно или в офисе?
    
- Вы попробуете выполнить те же действия на другом компьютере и видите такое же поведение?
    
- Пошаговые инструкции по предоставлению проблем, чтобы можно было записать действия, которые вы перейдете.
    
- Скорость работы в секундах или минутах
    
- Где вы находитесь в мире?
    
Некоторые из этих вопросов являются более очевидными, чем другие. Большинство пользователей понимают, что средство устранения неполадок требует точных действий для воспроизведения проблемы. В конце концов, как вы зарегистрируете неисправность и как еще можно будет проверить, устранена ли проблема? Менее очевидны вещи, такие как "какая дата и время возникли?" и "где вы находитесь в мире?", сведения, которые можно использовать совместно. В зависимости от того, когда пользователь работал, в некоторых часах разницы времени может означаться, что обслуживание уже выполняется в частях сети компании. Если, например, в вашей компании есть Гибридная реализация, например гибридный Поиск SharePoint, который может запрашивать индексы поиска в SharePoint Online и локальном экземпляре SharePoint Server 2013, обновления могут выполняться в локальной ферме. Если ваша организация работает в облаке, Обслуживание системы может включать в себя добавление или удаление сетевого оборудования, развертывание обновлений, предназначенных для всей компании, а также внесение изменений в DNS или другие основные инфраструктуры.
  
При устранении проблем с производительностью, как и в случае с помощью преступления, необходимо быть точным и наблюдаемым образом отображать все выводы из свидетельства. Для этого необходимо получить хороший отчет о проблеме, выполнив сбор доказательств. Он должен включать в себя контекст компьютера, контекст пользователя, при возникновении проблемы, а также точные действия, которые покрывают проблему с производительностью. Этот оператор задачи должен быть и оставаться самым верхней страницей в заметках. После того, как вы перейдете к решению проблемы, пошаговым руководством, вы протестируете и подтверждаете, были ли выполненные действия решают проблему. Это важно для того, чтобы знать, когда ваша работа выполнена.
  
## <a name="do-you-know-how-performance-used-to-look-when-it-was-good"></a>Знаете ли вы, как производительность будет выглядеть, когда она хорошая?

Если у вас есть несчастливые, никто не знает. Никто не имел цифр. Это означает, что никто не может ответить на простой вопрос "сведения о том, сколько секунд использовалось для получения папки" Входящие "в Office 365?", или "как долго использовалось время, когда руководитель приводился к собранию Lync Online?", который является распространенным сценарием для многих компаний.
  
Здесь нет базовых показателей производительности.
  
Базовые показатели дают вам контекст производительности. В зависимости от потребностей компании необходимо иногда использовать базовую линию. Если вы занимаетесь крупной компанией, Группа операций может использовать базовые уровни для локальной среды. Например, если вы исправляете все серверы Exchange Server в первый понедельник месяца и все серверы SharePoint в третьем понедельник, Группа операций, скорее всего, будет иметь список задач и сценариев, которые он выполняет после исправления, чтобы доказать, что критически важные функции работают. Например, откройте папку "Входящие", нажмите кнопку Отправить/получить и убедитесь, что папки обновлены, или в SharePoint перейдите на главную страницу сайта, перейдите на страницу Поиск в корпоративной среде и выполните поиск, возвращающий результаты.
  
Если ваши приложения находятся в Office 365, то некоторые основные базовые показатели можно оценить в течение времени (в миллисекундах) с клиентского компьютера внутри вашей сети, до точки выхода или в точке выхода из сети и переходе на Office 365. Ниже приведены некоторые полезные базовые показатели, которые можно исследовать и записывать.
  
- Определите устройства между клиентским компьютером и точкой выхода, например прокси-сервер.
    
  - Вам необходимо знать устройства, чтобы иметь контекст (IP-адреса, тип устройства, et Цетера) для проблем с производительностью.
    
  - Прокси-серверы — это распространенные точки выхода, поэтому вы можете проверить веб-браузер, чтобы узнать, какой прокси-сервер он использует (если он указан).
    
  - Существуют сторонние инструменты, которые могут обнаруживать и сопоставлять сеть, но самый безопасный способ узнать ваше устройство — попросить участника группы сети.
    
- Определите поставщика услуг Интернета, запишите сведения о контактах и Узнайте, сколько каналов пропускной способности.
    
- В вашей организации определите ресурсы для устройств между клиентом и точкой выхода, или определите контакт для экстренного реагирования, который будет обсуждать проблемы с сетью.
    
Ниже приведены некоторые базовые показатели, которые могут быть рассчитаны с помощью средств простого тестирования с помощью средств.
  
- Время с клиентского компьютера до точки выхода в миллисекундах
    
- Время с момента выхода на Office 365 (в миллисекундах)
    
- Расположение в мире сервера, которое разрешает URL-адреса для Office 365 при просмотре
    
- Скорость разрешения DNS поставщика услуг Интернета (в миллисекундах), несогласованности при поступлении пакетов (колебание сети), время отправки и загрузки в миллисекундах.
    
Если вы не знакомы с выполнением этих действий, мы рассмотрим более подробные сведения в этой статье. 
  
## <a name="what-is-a-baseline"></a>Что такое базовый план?

Вы узнаете, что в случае неисправности вы узнаете, но если вы не знаете исторических данных о производительности, невозможно создать контекст для того, насколько плохо он стал, и когда. Таким образом, без базового плана вы не можете понять, как решить головоломку: изображение в поле головоломки. При устранении неполадок с производительностью необходима точка  *сравнения*  . Простые базовые показатели производительности не трудно выполнить. В соответствии с расписанием Группа операций может выполнить эти задачи. Например, предположим, что ваше подключение выглядит следующим образом: 
  
![Основной сетевой график, демонстрирующий клиентский, прокси-сервер и Office 365 Cloud.](../media/c6ca7140-09f9-4c2d-a775-dbf2820eaa0c.PNG)
  
Это означает, что вы проверили свою команду сети и обнаружили, что ваша компания покидает Интернет через прокси-сервер, и этот прокси-сервер обрабатывает все запросы, которые клиентский компьютер отправляет в облако. В этом случае необходимо создать упрощенную версию подключения, в которой перечисляются все промежуточные устройства. Теперь вставьте инструменты, которые можно использовать для проверки производительности клиента, точки выхода (в которой вы покидаете сеть в Интернете) и облака Office 365.
  
![Простая сеть с клиентами, прокси-сервером и облаком, а также предложениями средств, PSPing, TraceTCP и Network traces.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
Эти параметры перечислены как **простые** и **Расширенные** возможности, необходимые для поиска данных о производительности. Трассировка сети может занять много времени, по сравнению с запущенными средствами командной строки, такими как PsPing и TraceTCP. Эти два средства командной строки были выбраны, так как они не используют пакеты ICMP, которые будут заблокированы в Office 365, так как они дают время в миллисекундах, необходимое для выхода клиентского компьютера или прокси-сервера (если у вас есть доступ) и поступления в Office 365. Все индивидуальные переходы с одного компьютера на другой будут иметь значение времени, что отлично для базовых планов! Как важно, эти средства командной строки позволяют добавить номер порта в команду, так как Office 365 обменивается данными через порт 443, который является портом, используемым протоколами Secure Sockets Layer и TLS и TLS. Тем не менее, другие сторонние инструменты могут оказаться более эффективными решениями в вашей ситуации. Корпорация Майкрософт не поддерживает все эти средства, поэтому если по какой – то причине не удается получить PsPing и TraceTCP, переходите к сетевой трассировке с помощью средства, такого как Netmon. 
  
Вы можете выполнить базовый план до рабочих часов, а затем снова использовать его, а затем снова через несколько часов. Это означает, что у вас может быть структура папок, которая выглядит так же, как в конце:
  
![Схема, на которой показан способ рассортировки данных о производительности по папкам.](../media/13e01ffa-f0f2-4d10-b89d-d5980ec89fae.png)
  
Кроме того, следует выбрать соглашение об именовании файлов. Ниже приводятся примеры:
  
- Feb_09_2015_9amPST_PerfBaseline_Netmon_ClientToEgress_Normal
    
- Jan_10_2015_3pmCST_PerfBaseline_PsPing_ClientToO365_bypassProxy_SLOW
    
- Feb_08_2015_2pmEST_PerfBaseline_BADPerf
    
- Feb_08_2015_8 30amEST_PerfBaseline_GoodPerf
    
Это можно сделать множеством разных способов, но **\<dateTime\>\<what's happening in the test\>** для начала рекомендуется использовать формат. Это поможет вам при устранении неполадок, которые могут быть продолжены позже. Позже вы сможете сказать: "я занял две трассировки 8 февраля, одна продемонстрировала хорошую производительность, и одна из них неисправна, поэтому мы можем сравнить их". Это чрезвычайно полезно для устранения неполадок. 
  
Необходимо иметь упорядоченный способ хранения исторических базовых показателей. В этом примере простые методы выдали три выходных выхода командной строки, а результаты были собраны как снимки экрана, но вместо этого могут быть файлы записи сети. Используйте метод, который лучше всего подходит для вас. Храните свои исторические базовые показатели и ссылаются на них в тех случаях, когда вы заметили изменения в работе веб-служб. 
  
## <a name="why-collect-performance-data-during-a-pilot"></a>Зачем собирать данные о производительности во время пилотного проекта?

Не рекомендуется начинать выполнение базовых планов, чем во время пилотного развертывания службы Office 365. У вашего офиса могут быть тысячи пользователей, сотни тысяч или пять, но даже небольшое количество пользователей, можно выполнять тесты для измерения колебаний производительности. В случае крупной компании репрезентативный пример нескольких сотен пользователей, пилотный пилотный проект Office 365, может быть проецирован на несколько тысяч, чтобы узнать, где могут возникнуть проблемы до их появления.
  
В случае с небольшой компанией, где при включенной серверной плате все пользователи отправляются в службу одновременно, и нет пилотного проекта, для отображения данных, которые могут поступать в устранении неполадок, связанных с недостаточной производительностью. Например, если вы заметили, что все внезапно вы можете проанализировать ваше построение в течение времени, которое занимается отправкой изображения среднего размера, в котором она выполнялась очень быстро.
  
## <a name="how-to-collect-baselines"></a>Сбор базовых планов

Для всех планов устранения неполадок необходимо как минимум:
  
- Клиентский компьютер, который вы используете (тип компьютера или устройства, IP-адрес и действия, вызвавшие эту неполадку).
    
- Место, где клиентский компьютер находится в мире (например, является ли этот пользователь VPN-подключением для сети, работает удаленно или в интрасети компании)
    
- Точка выхода клиентский компьютер использует сеть из сети (точка, в которой трафик покидает ваш бизнес для ISP или Интернет)
    
 Вы можете узнать макет сети у администратора сети. Если вы находитесь в небольшой сети, Взгляните на устройства, подключающиеся к Интернету, и позвоните своему поставщику услуг Интернета, если у вас возникнут вопросы о макете. Создайте график готовой структуры для ссылки. 
  
Этот раздел разбивается на простые средства командной строки и методы, а расширенные параметры инструментов. Сначала мы рассмотрим простые методы. Но если у вас проблема с производительностью, следует перейти к дополнительным методам и испытать пример плана действий по устранению неполадок с производительностью.
  
### <a name="simple-methods"></a>Простые методы

Цель этих простых методов состоит в том, чтобы изучать, разбирать и правильно хранить простые базовые показатели производительности с течением времени, чтобы получать сведения о производительности Office 365. Вот простая схема для простой, как показано выше:
  
![Простая сеть с клиентами, прокси-сервером и облаком, а также предложениями средств, PSPing, TraceTCP и Network traces.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
> [!NOTE]
> TraceTCP включается в этот снимок экрана, так как это удобно для отображения, в миллисекундах, продолжительности обработки запроса и количества прыжков сети или подключений от одного компьютера к другому, что делает запрос для достижения целевого значения. TraceTCP также может предоставлять имена серверов, используемых при переходах, что может быть полезен в средстве устранения неполадок Microsoft Office 365 в службе поддержки. > команды TraceTCP могут быть очень простыми, например: >  `tracetcp.exe outlook.office365.com:443`> не забудьте включить номер порта в команду! > [TraceTCP](https://simulatedsimian.github.io/tracetcp_download.html) — это бесплатная загрузка, но она основана на винкап. Винкап — это средство, которое также используется и устанавливается в Netmon. Кроме того, в разделе Дополнительные методы используется Netmon. 
  
 Если у вас несколько офисов, необходимо также хранить набор данных клиента в каждом расположении. Эта проверка измеряет задержку, в которой, в данном случае, является числовое значение, которое описывает время между клиентом, отправляющим запрос, на Office 365, а Office 365 отвечает на запрос. Тестирование исходит от домена на клиентском компьютере и выполняет поиск в измерении кругового пути в сети, исходящих через точку исходящего трафика, через Интернет в Office 365 и обратно. 
  
Существует несколько способов работы с точкой выхода (в данном случае — прокси-сервер). Можно выполнить трассировку от 1 до 2, а затем 2 – 3, а затем добавить числа в миллисекундах, чтобы получить итоговые итоги по краю сети. Вы также можете настроить подключение так, чтобы оно обходило адреса прокси-сервера для Office 365. В более крупной сети с брандмауэром, обратным прокси-сервером или некоторыми их сочетаниями может потребоваться сделать исключения на прокси-сервере, что позволит передавать трафик по большому URL-адресу. Список конечных точек, используемых в Office 365, представлен в статье [URL-адреса и диапазоны IP-адресов office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). Если у вас есть прокси-сервер с проверкой подлинности, начните проверку исключений для следующих компонентов:
  
- Порты 80 и 443
    
- TCP и HTTPs
    
- Подключения, исходящие через один из этих URL-адресов:
    
- \*. microsoftonline.com
    
- \*. microsoftonline-p.com
    
- \*.sharepoint.com
    
- \*. outlook.com
    
- \*. lync.com
    
- osub.microsoft.com
    
Всем пользователям необходимо разрешить пользователям получать доступ к этим адресам без помех или помех прокси-серверов. В сети меньшего размера их необходимо добавить в список обхода прокси-серверов в веб-браузере. 
  
Чтобы добавить их в список обхода прокси-серверов в Internet Explorer, откройте **меню Сервис** \> **Свойства** \> **подключения** \> **LAN параметры** подключения \> **Advanced**. Кроме того, на вкладке Дополнительно можно найти порт прокси-сервера и прокси-сервера. Возможно, вам потребуется установить флажок **использовать прокси-сервер для локальной сети**, чтобы получить доступ к кнопке **Advanced** . Необходимо убедиться, что флажок **обход прокси-сервера для локальных адресов** установлен. После нажатия кнопки **Дополнительно**отображается текстовое поле, в котором можно ввести исключения. Разделяйте приведенные выше URL-адреса с точками с запятой, например:
  
\*. microsoftonline.com; \*. SharePoint.com
  
После обхода прокси-сервера вы сможете использовать команду ping или PsPing непосредственно в URL-адресе Office 365. Следующий шаг будет тестировать ping **Outlook.Office365.com**. Кроме того, если вы используете PsPing или другое средство, которое позволит указать номер порта для команды, PsPing от **Portal.microsoftonline.com:443** , чтобы увидеть среднее время кругового пути в миллисекундах. 
  
Время кругового пути (или RTT) — это числовое значение, которое измеряет продолжительность отправки HTTP-запроса на сервер, например outlook.office365.com, и получения ответа, который подтверждает, что он знает сервер. Это сокращение иногда отображается как RTT. Это должен быть относительно короткий период времени.
  
Для выполнения этой проверки необходимо использовать [PSPing](https://technet.microsoft.com/sysinternals/jj729731.aspx) или другое средство, которое не использует пакеты ICMP, заблокированные в Office 365. 
  
 **Как использовать PsPing для получения общего времени кругового пути в миллисекундах непосредственно с URL-адреса Office 365**
  
1. Запустите командную строку с повышенными привилегиями, выполнив указанные ниже действия.
    
1. Нажмите кнопку **Начало**.
    
2. В поле **начать поиск** введите cmd, а затем нажмите клавиши CTRL + SHIFT + ВВОД.
    
3. Если появится диалоговое окно **Управление учетной записью пользователя**, убедитесь, что действие, указанное в окне, совпадает с тем, которое вы хотите выполнить, и нажмите **Продолжить**.
    
2. Перейдите к папке, в которой установлен инструмент (в данном случае PsPing), и протестируйте следующие URL-адреса Office 365:
    
  - psping portal.office.com:443
    
  - psping microsoft-my.sharepoint.com:443
    
  - psping outlook.office365.com:443
    
  - psping www.yammer.com:443
    
    ![Команда PSPing, которая переходит на microsoft-my.sharepoint.com порт 443.](../media/3258f620-4513-4e82-95c9-06b387fc3a82.PNG)
  
Обязательно укажите номер порта 443. Помните, что Office 365 работает на зашифрованном канале. Если вы PsPing без номера порта, ваш запрос завершится с ошибками. Если вы выполнили команду ping для короткого списка, найдите среднее время в миллисекундах (МС). Вот что вы хотите записать!
  
![Рисунок, на котором показан пример клиента для прокси-сервера PSPing с временем кругового пути 2,8 миллисекунд.](../media/96901aea-1093-4f1b-b5a3-6078e9035e6c.png)
  
Если вы не знакомы с обходом прокси-сервера, и предпочитаете пошаговое выполнение действий, необходимо сначала найти имя прокси-сервера. В Internet Explorer выберите в **меню Сервис** \> **Свойства** \> **подключения** \> **LAN параметры** подключения \> **расширены**. На вкладке **Дополнительно** отображается указанный прокси-сервер. Выполните команду ping для этого прокси-сервера в командной строки, выполнив следующую задачу: 
  
 **Проверка связи с прокси-сервером и получение значения кругового пути в миллисекундах для этапа 1 — 2**
  
1. Запустите командную строку с повышенными привилегиями, выполнив указанные ниже действия.
    
1. Нажмите кнопку **Начало**.
    
2. В поле **начать поиск** введите cmd, а затем нажмите клавиши CTRL + SHIFT + ВВОД.
    
3. Если появится диалоговое окно **Управление учетной записью пользователя**, убедитесь, что действие, указанное в окне, совпадает с тем, которое вы хотите выполнить, и нажмите **Продолжить**.
    
2. Введите команду ping \<the name of the proxy server your browser uses, or the IP address of the proxy server\> , а затем нажмите клавишу ВВОД. Если у вас есть PsPing или другое средство, то вы можете использовать это средство. 
    
    Команда может выглядеть, как в одном из следующих примеров: 
    
  - ping ourproxy.ourdomain.industry.business.com
    
  - ping 155.55.121.55
    
  - ping аурпрокси
    
  - psping ourproxy.ourdomain.industry.business.com:80
    
  - psping 155.55.121.55:80
    
  - psping аурпрокси: 80
    
3. Когда трассировка прекратит отправку тестовых пакетов, вы получите небольшой сводный список, в котором указывается среднее значение (в миллисекундах), а это значение, которое вы используете. Сделайте снимок экрана с запросом и сохраните его, используя ваше соглашение об именовании. На этом шаге также может помочь заполнить схему значением.
    
Возможно, Вы затратили трассировку на раннем утро, и клиент может быстро получить доступ к прокси-серверу (или к серверу выхода в Интернет). В этом случае ваши номера могут выглядеть следующим образом:
  
![График, показывающий время кругового пути от клиента до прокси-сервера 2,8 миллисекунд.](../media/1bd03544-23fc-47d4-bbae-c1feb466a5d8.PNG)
  
Если ваш клиентский компьютер является одним из нескольких выбранных серверов с доступом к прокси-серверу (или выходному серверу), можно выполнить следующий участок теста, удаленно подключаясь к этому компьютеру, запустив командную строку, чтобы PsPing в URL-адрес Office 365. Если у вас нет доступа к этому компьютеру, вы можете обратиться к сетевым ресурсам, чтобы получить справку по следующему подразделу и получить точные номера. Если это невозможно, выполните PsPing по указанному URL-адресу Office 365 и сравните его со временем PsPing или ping с прокси-сервером. 
  
Например, если у клиента 51,84 МС от клиента к URL-адресу Office 365, и у вас в течение 2,8 миллисекунд от клиента до прокси-сервера (или точки выхода), то в качестве выхода на Office 365 будет установлено 49,04 МС. Аналогичным образом, если у клиента в течение 12,25 мс от клиента к прокси-серверу в течение дня, а 62,01 миллисекунд от клиента до URL-адреса Office 365, то среднее значение прокси-сервера в URL-адресе Office 365 составляет 49,76 МС.
  
![Дополнительный рисунок, на котором показана проверка связи в миллисекундах от клиента к прокси-серверу рядом с клиентом до Office 365, поэтому значения можно вычесть.](../media/cd764e77-5154-44ba-a5cd-443a628eb2d9.PNG)
  
С точки зрения устранения неполадок вы можете найти нечто интересное о том, как хранить эти базовые планы. Например, если вы обнаружите, что в большинстве случаев около 40 59 мс задержки от прокси-сервера или выходного адреса в URL-адрес Office 365, и иметь клиент для прокси-сервера или Выходная точка выхода от 3 до 7 миллисекунд (в зависимости от объема сетевого трафика, который вы видите в это время суток), вы наверняка знаете, что что-то не так, если последние три клиента для прокси или выхода покажут задержку в 45 миллисекунд.
  
### <a name="advanced-methods"></a>Дополнительные методы

Если вы действительно хотите узнать, что происходит с Интернет-запросами до Office 365, необходимо ознакомиться с сетевыми трассировками. Не имеет значения, какие средства вы предпочитаете использовать для этих трассировок, HTTPWatch, NetMon, анализатор сообщений, Wireshark, Fiddler, средство для разработки панелей разработчика или любое другое, если это средство может записывать и фильтровать сетевой трафик. В этом разделе вы увидите, что для получения более полной картины проблемы можно использовать более одного из этих средств. При тестировании некоторые из этих средств также действуют как прокси-серверы в своих собственных подразделах. Средства, используемые в сопровождающей статье, [план устранения неполадок с производительностью для Office 365](performance-troubleshooting-plan.md), включают [Netmon 3,4](https://www.microsoft.com/download/details.aspx?id=4865), [HTTPWatch](https://www.httpwatch.com/download/)или [Wireshark](https://www.wireshark.org/).
  
Создание базового плана производительности является простой частью этого метода, и многие из них одинаковы, так же, как при устранении проблем с производительностью. Более сложные методы создания базовых планов для производительности требуют использования и хранения трассировок сети. В большинстве примеров, приведенных в этой статье, используется SharePoint Online, но необходимо разработать список общих действий в службах Office 365, на которые вы подписаны для тестирования и записи. Ниже приведен пример базового примера.
  
- Базовый список для SPO-* * Step 1: * * Обзор домашней страницы веб-сайта SPO и выполнение сетевой трассировки. Сохраните трассировку. 
    
- Базовый список для SPO- **Step 2:** поиск термина (например, название организации) с помощью Поиск в корпоративной среде и выполнение сетевой трассировки. Сохраните трассировку. 
    
- Базовый список для SPO- **Step 3:** отправьте большой файл в библиотеку документов SharePoint Online и выполните трассировку сети. Сохраните трассировку. 
    
- Базовый список для SPO- **Step 4:** Обзор домашней страницы веб-сайта OneDrive и выполнение сетевой трассировки. Сохраните трассировку. 
    
Этот список должен включать наиболее важные общие действия, выполняемые пользователями в SharePoint Online. Обратите внимание на то, что последний шаг для трассировки в OneDrive для бизнеса — сравнение нагрузки на домашнюю страницу SharePoint Online (часто настроенные компаниями) и домашняя страница OneDrive для бизнеса, которая настраивается редко. Это очень простой тест, когда он доходит до медленной загрузки сайта SharePoint Online. Вы можете создать запись об этом различии для тестирования.
  
Если вы в середине проблемы с производительностью, многие из них будут такими же, как при создании базового плана. Трассировка сети становится критической, поэтому мы обработаем,  *как*  далее выполнить важную трассировку. 
  
Чтобы устранить  *проблему с производительностью, необходимо*  провести трассировку на момент возникновения проблемы с производительностью. Необходимо иметь соответствующие средства для сбора журналов, а также план действий, то есть список действий по устранению неполадок, которые необходимо выполнить для сбора лучших сведений. Первое, что нужно сделать, — записать дату и время теста, чтобы файлы можно было сохранить в папке, в которой отражается время. Далее необходимо сузить область задач до проблем. Ниже приведены точные действия, которые необходимо использовать для тестирования. Не забывайте об основных принципах: Если проблема связана только с Outlook, убедитесь, что поведение проблемы возникает только в одной службе Office 365. Сужение области этой проблемы поможет сосредоточиться на том, что можно устранить. 
  
## <a name="see-also"></a>См. также

[Управление конечными точками Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
