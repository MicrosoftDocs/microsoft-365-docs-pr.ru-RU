---
title: Application Guard для Office 365 (общедоступная Предварительная версия) для администраторов
keywords: Application Guard, Protection, изоляция, изолированный контейнер, изоляция оборудования
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Получите последнюю версию в разделе изоляция на основе оборудования. Предотвращение текущих и новых атак, таких как эксплойты или вредоносные ссылки, не нарушая продуктивность сотрудников и корпоративную безопасность.
ms.openlocfilehash: d0a89e8f8874c9ad298bf862384019b9e1ace0bf
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867504"
---
# <a name="application-guard-for-office-public-preview-for-admins"></a>Application Guard для Office (общедоступная Предварительная версия) для администраторов


**Применимо к:** Word, Excel и PowerPoint для Microsoft 365, Windows 10 Корпоративная

>[!IMPORTANT]
>Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.


Защитник Microsoft Defender Application Guard для Office (Application Guard для Office) помогает предотвратить доступ к доверенным ресурсам для ненадежных файлов, обеспечивая надежную защиту от новых и новых атак. В этой статье администраторы проходят настройку устройств для предварительного просмотра Application Guard для Office. Он содержит сведения о требованиях к системе и действиях по установке для включения Application Guard для Office на устройстве.

## <a name="prerequisites"></a>Предварительные требования

### <a name="minimum-hardware-requirements"></a>Минимальные требования к оборудованию

* **ЦП**: 64-разрядный, 4 ядра (физический или виртуальный), расширения виртуализации (Intel VT-x или AMD-V), основной i5 эквивалент или более высокий уровень
* **Физическая память**: 8 ГБ ОЗУ
* **Жесткий диск**: 10 ГБ свободного места на системном диске (рекомендуется SSD)

### <a name="minimum-software-requirements"></a>Минимальные требования к программному обеспечению

* **Windows 10**: Windows 10 Enterprise Edition, Клиентская сборка версии 2004 (20H1) Build 19041
* **Office**: сборка канала Office Beta версии 2008 16.0.13212 или более поздней версии
* **Пакет обновления**: Windows 10 накопительных обновлений для системы безопасности ( [KB4566782](https://support.microsoft.com/help/4566782/windows-10-update-kb4566782) ) 

Для получения подробных сведений о требованиях к системе обратитесь к разделу [требования к системе для Application Guard в защитнике Microsoft](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard). Чтобы узнать больше о сборках Insider Preview для Office, ознакомьтесь со статьей [Начало работы по развертыванию сборок для участников программы предварительной оценки Office](https://insider.office.com/business/deploy).

### <a name="licensing-requirements"></a>Требования к лицензированию
* Microsoft 365 в ~ или Microsoft 365 в систему безопасности

## <a name="deploy-application-guard-for-office"></a>Развертывание Application Guard для Office

### <a name="enable-application-guard-for-office"></a>Включение Application Guard для Office

1.  Загрузите и установите **накопительные пакеты обновления для системы безопасности KB4566782 для Windows 10**. 

2. Скачайте и установите [**пакет включения Application Guard для Office**](https://download.microsoft.com/download/e/4/c/e4c1180a-fcff-462a-8324-4151c44973a8/Windows%20Preview%20-%20WDAG%20Office%20070920%2001.msi). Этот пакет устанавливает групповую политику с именем "KB4559004 Issue 001 Preview" в разделе **Конфигурация компьютера \ административные шаблоны**. Установите для этой групповой политики значение **Enabled**.
     ![Редактор локальных групповых политик](../../media/ag01-deploy.png)

     ![KB4559004ная ошибка 001 Preview](../../media/ag02-deploy.png)

    Вы также можете напрямую задать следующие разделы реестра: 
    
    ```
    reg add HKLM\SYSTEM\CurrentControlSet\Policies\Microsoft\FeatureManagement\Overrides /v 3457697930 /t REG_DWORD /d 1 
    ```
    ```
    reg add HKLM\SYSTEM\CurrentControlSet\Policies\Microsoft\FeatureManagement\Overrides /v 94539402 /t REG_DWORD /d 1 
    ```
    Затем выполните следующую команду PowerShell: 
    
    ```powershell
    Get-ScheduledTask -TaskName "ReconcileFeatures" -TaskPath "\Microsoft\Windows\Flighting\FeatureConfig\" | Start-ScheduledTask 
    ```

3.  Выберите **Application Guard в защитнике Microsoft** в разделе Компоненты Windows и нажмите кнопку **ОК**. При использовании функции Application Guard будет выдаваться запрос на перезагрузку системы. Вы можете выполнить перезагрузку сейчас или после шага 4.

    ![Диалоговое окно "компоненты Windows", в котором отображается AG](../../media/ag03-deploy.png)
    
    Кроме того, можно включить эту функцию, выполнив следующую команду PowerShell от имени администратора: 

    ```powershell
    Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard 
    ```

4.  Найдите Application Guard в защитнике Майкрософт в групповой политике управляемого режима, расположенном в разделе **Конфигурация компьютера \\ Административные шаблоны \\ Windows компоненты \\ Application Guard в защитнике Microsoft Application Guard**. Включите эту политику, задав значение в разделе параметры как **2** или **3** нажмите **кнопку ОК** или **Применить**.

    ![Включение AG в управляемом режиме](../../media/ag04-deploy.png)
  
    Кроме того, можно настроить соответствующую политику CSP: 

    OMA — URI: **./девице/вендор/мсфт/виндовсдефендераппликатионгуард/Сеттингс/алловвиндовсдефендераппликатионгуард** 
    <br>Тип данных: **целое число** 
    <br>Значение: **2**


5.  Перезагрузите систему.

### <a name="set-diagnostics--feedback-to-send-full-data"></a>Настройка диагностики & обратной связи для отправки полных данных

Этот шаг гарантирует, что данные, необходимые для определения и устранения проблем, достигнут корпорацией Майкрософт. Выполните следующие действия, чтобы включить диагностику на устройстве с Windows:

1.  Откройте **Параметры** из меню "Пуск".

    ![Меню "Пуск"](../../media/ag05-diagnostic.png)

2.  В меню **Параметры Windows**выберите **Конфиденциальность**.

    ![Меню "Параметры Windows"](../../media/ag06-diagnostic.png)

3.  В разделе Конфиденциальность выберите пункт **диагностика & отзывов** и выберите **дополнительные диагностические данные**.

    ![Меню диагностики и обратной связи](../../media/ag07a-diagnostic.png)

Для получения дополнительных сведений о настройке параметров диагностики Windows, обратитесь к разделу [Настройка диагностических данных Windows в Организации](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>Убедитесь, что Application Guard для Office включено и работает.

Перед подтверждением того, что Application Guard для Office включено, запустите Word, Excel или PowerPoint на устройстве с развернутыми политиками. Убедитесь, что приложение Office активировано. Для активации продукта Office может потребоваться использовать рабочий идентификатор.

Чтобы убедиться, что Application Guard для Office теперь включено, запустите Word, Excel или PowerPoint и откройте документ, не являющийся доверенным. Например, можно открыть документ, загруженный из Интернета или из вложения в сообщение электронной почты от кого-либо из пользователей, не входящих в вашу организацию.

При первом запуске ненадежного файла вы можете увидеть экран-заставку Office, как показано ниже. Он может отображаться некоторое время, пока не будет активирован Application Guard для Office и открыт файл. Последующие запуска недоверенных файлов должны выполняться быстрее.

![Экран-заставка приложения Office](../../media/ag08-confirm.png)


После открытия файл должен отображать несколько визуальных индикаторов, которые файл был открыт в Application Guard для Office:

* Выноска на ленте

    ![Файл doc с примечанием для небольшой защиты приложений](../../media/ag09-confirm.png)
* Значок приложения с защитой на панели задач 

    ![Значок на панели задач](../../media/ag12-limitations.png)



## <a name="configure-application-guard-for-office"></a>Настройка Application Guard для Office
В Office поддерживаются следующие политики, позволяющие настроить возможности Application Guard для Office. Эти политики можно настроить с помощью групповых политик или через службу Microsoft Cloud Policy. 

>[!NOTE] 
> Эти политики скоро станут доступны.
>Кроме того, Настройка этих политик может отключить некоторые функциональные возможности для файлов, открытых в Application Guard для Office.

| Политика                                                                          | Описание                                                                                                                                                                                                                                                                                             |
|---------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Отключение Application Guard для Office                                            | При включении этой политики в Word, Excel и PowerPoint будет использоваться защищенный контейнер изоляции просмотра вместо Application Guard для Office. С помощью этой политики можно временно отключить Application Guard для Office при наличии проблем, связанных с выходом из пограничного сервера.                                  |
| Отключение копирования и вставки для документов, открытых в Application Guard                    | Включение этой политики не позволит пользователю копировать и вставлять контент из документа, открытого в Application Guard для Office, в документ, Открытый за пределами приложения.                                                                                                                                   |
| Запретить пользователям удалять защиту Application Guard для файлов               | Включение этой политики удалит параметр (в интерфейсе приложений Office), чтобы отключить защиту Application Guard или открыть файл за пределами Application Guard. <br><br>**Примечание:** Пользователи по-прежнему могут обойти эту политику, вручную удалив свойство метки веб-сайта из файла или переместив документ в надежное расположение. |
| Ограничение печати документов, открытых в Application Guard                    | Включение этой политики ограничит принтеры, на которых пользователь может выполнять печать, из файла, открытого в Application Guard для Office. Например, вы можете использовать эту политику, чтобы ограничить пользователям печать только в PDF-файл.                              |
| Отключение доступа к камере и микрофону для документов, открытых в Application Guard | Включение этой политики приведет к удалению доступа Office к камере и микрофону внутри Application Guard для Office.                                                                                                                                                                                                     |
>[!NOTE] 
>Для вступления в силу следующих политик необходимо выйти из системы и повторно войти в Windows.
> 
> *  Отключение копирования и вставки для документов, открытых в Application Guard
>*  Ограничение печати документов, открытых в Application Guard
> *  Отключение доступа к камерам и микрофонам для документов, открытых в Application Guard


## <a name="submit-feedback"></a>Отправить отзыв

### <a name="submit-feedback-via-feedback-hub"></a>Отправка отзывов через центр отзывов

Если при запуске Application Guard для Office возникли проблемы, рекомендуется отправить отзыв через центр отзывов:

1.  Откройте **приложение центра отзывов** и войдите в систему.

2.  Если при запуске Application Guard выводится диалоговое окно с сообщением об ошибке, выберите в диалоговом окне сообщения об ошибке пункт **Report** , чтобы начать новую отправку отзывов. В противном случае перейдите к <https://aka.ms/wdagoffice-fb> разделу, чтобы выбрать правильную категорию Application Guard, а затем нажмите кнопку **+ Добавить новую обратную связь** в правом верхнем углу.

3.  Заполните поле **сводка отзыва** , если оно еще не заполнено.

4.  Заполните поле **Подробнее в подробном подробностях** , указав подробное описание возникшей вами ситуации и действия, которые вы сделали, а затем нажмите кнопку **Далее**.

5.  Выберите всплывающее сообщение рядом с элементом проблема. Убедитесь, что выбрана категория **безопасность и конфиденциальность \> защитник Microsoft Defender Application Guard — Office**, а затем нажмите кнопку **Далее**.

6.  Выберите **создать отзыв**, а затем нажмите кнопку **Далее**.

7.  Сбор трассировок о возникшей ошибке:

    1. Разверните элемент **повторно создать** плитку с проблемой.

    2.  Если проблема возникает во время выполнения Application Guard, откройте экземпляр Application Guard. Это позволяет собирать дополнительные трассировки в контейнере Application Guard.

    3.  Выберите **начать запись** и дождитесь, пока плитка не перестанет вращаться, а затем *остановите запись*.

    4.  Полное воспроизведение проблемы с Application Guard. Это может быть попытка запустить экземпляр Application Guard и подождать, пока она не будет пройдена, или воссоздать ошибку в работающем экземпляре Application Guard.

    5.  Выберите плитку **остановить запись** .

    6.  Сохраните все запущенные экземпляры Application Guard в любом открытом экземпляре (даже до нескольких минут после отправки), чтобы также можно было собрать диагностические сведения о контейнере.

8.  Присоедините все соответствующие снимки экрана или файлы, связанные с проблемой.

9.  Выберите **Отправить**.



### <a name="submit-feedback-via-office-customer-voice"></a>Отправка отзывов с помощью голосовых вызовов пользователей Office

Вы также можете отправить отзыв в Office, если проблема возникает при открытии документов Office в Application Guard. Сведения о том, как отправить отзыв, можно найти в [руководстве по предварительной работе Office](https://insider.office.com/handbook) .

## <a name="integration-with-microsoft-defender-atp-and-office-atp"></a>Интеграция с защитником Майкрософт и пакетом Office ATP

Application Guard для Office интегрировано с авансовым защитником Майкрософт (ATP), чтобы обеспечить мониторинг и оповещение о вредоносных действиях, происходящих в изолированной среде.

Пакет ATP для защитника Майкрософт — это платформа безопасности, позволяющая корпоративным сетям предотвращать, обнаруживать и отвечать на дополнительные угрозы. Для получения дополнительных сведений об этой платформе посетите страницу [Advanced Threat Protection в защитнике Майкрософт](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) . Узнайте больше о переносе устройств на эту платформу на [встроенных устройствах в службу Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).

Вы также можете настроить Office 365 ATP для работы с пакетом ATP для защитника Microsoft. Обратитесь к разделу [Интеграция Office 365 ATP с защитником Microsoft для пакета ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp?view=o365-worldwide).

## <a name="limitations-and-considerations"></a>Ограничения и рекомендации

* Application Guard для Office — это ограниченный режим, который изолирует недоверенные документы от доступа к доверенным корпоративным ресурсам, интрасети, удостоверению пользователя и произвольным файлам, присутствующим на компьютере. В результате, если пользователь пытается получить доступ к компоненту, который имеет зависимость от такого доступа, например, при вставке изображения из локального файла на диске произойдет ошибка, и будет выдаваться запрос, подобный показанному ниже. Чтобы разрешить недоверенному документу доступ к доверенным ресурсам, пользователи должны удалить защиту Application Guard из документа.

    ![Диалоговое окно с сообщением о том, что для обеспечения безопасности эта функция недоступна](../../media/ag10-limitations.png)

    >[!NOTE]    
    >Посоветуйте пользователям удалить защиту только в том случае, если они доверяют файлу и источнику или откуда он поступил.

* Активное содержимое документов, таких как макросы и элементы управления ActiveX, отключено в Application Guard для Office. Для включения активного содержимого пользователям необходимо удалить защиту Application Guard.

* Недоверенные файлы, открытые из общих сетевых ресурсов или файлов, предоставленных из OneDrive, OneDrive для бизнеса или SharePoint Online из другой организации, открываются в Application Guard только для чтения. Пользователи могут сохранить локальную копию таких файлов, чтобы продолжить работу в контейнере, или отключить защиту для непосредственной работы с исходным файлом.

* Файлы, защищенные службой управления правами на доступ к данным (IRM), продолжают открываться в режиме защищенного просмотра.
* Все настройки приложений Office в Application Guard для Office не будут сохранены после выхода пользователя из системы и повторного входа в систему или перезагрузки устройства. 

* Специальные возможности для файлов, открытых в Application Guard для Office, доступны только в средствах специальных возможностей, которые используют модель UIA Framework.

* Сетевое подключение необходимо для первого запуска Application Guard после установки. Это необходимо для проверки лицензии приложением Application Guard.
* В разделе сведения о документе *Последнее изменение* свойства может отображать вдагутилитяккаунт в качестве пользователя. Это анонимный пользователь, настроенный в Application Guard в соответствии с тем, что удостоверение пользователя на рабочем столе не предоставляется в контейнере Application Guard. 

## <a name="performance-optimizations-for-application-guard"></a>Оптимизация производительности для Application Guard 

В этом разделе представлен обзор оптимизации производительности, используемой в Application Guard для Office. Эта информация поможет администраторам диагностировать отчеты от пользователей, связанных с производительностью Office или всей системы, когда включено Application Guard. 

Application Guard использует виртуализованный контейнер для изоляции документов, не заслуживающих доверия, от системы. Процесс создания контейнера и настройки контейнера Application Guard для открытия документов Office влияет на производительность, что может негативно повлиять на работу пользователей, когда пользователи открывают ненадежный документ. 


Чтобы предоставить пользователям доступ к ожидаемому открытому файлу, Application Guard использует логику для предварительного создания контейнера, если в системе выполняется следующий эвристический процесс: пользователь открыл файл в режиме защищенного просмотра или Application Guard за прошедшие 28 дней. 

При достижении этого эвристического алгоритма Office будет предварительно создать контейнер Application Guard для пользователя после входа в Windows. При выполнении этой операции, выполняемой перед созданием, может наблюдаться снижение производительности системы. Это будет устранено, как только завершится операция. 


>[!NOTE] 
>Рекомендации, необходимые для применения эвристического алгоритма для предварительного создания контейнера, создаются приложениями Office по мере их использования пользователями. Если пользователь устанавливает Office в новой системе, где включено Application Guard, Office не будет предварительно создавать контейнер до тех пор, пока пользователь не откроет ненадежный документ в системе. Пользователь будет видеть, что этот первый файл занимает больше времени, чем открытие в Application Guard. 

## <a name="known-issues-in-preview"></a>Известные проблемы в предварительной версии

* Щелчок по веб-ссылкам ( ```http``` или ```https``` ) не открывает браузер. 
* Обновления .NET приводят к сбою открытия файлов в Application Guard. В качестве обходного пути пользователи могут выполнить перезагрузку устройства при обнаружении этой проблемы.
    Узнайте больше об этой проблемы [при получении сообщения об ошибке при попытке открыть Application Guard в Защитнике Windows или в песочнице Windows](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).