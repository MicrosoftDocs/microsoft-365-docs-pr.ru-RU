---
title: Настройка и проверка сетевого подключения антивирусной программы "Защитник Windows"
description: Настройте и проверьте подключение к службе антивирусная программа в Microsoft Defender облачной защиты.
keywords: антивирус, антивирусная программа в Microsoft Defender, антивекальную программу, безопасность, защиту, облако, агрессивность, уровень защиты
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ef5a9ffdf45a2f8e7f262ae7f969cd19e848b7a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572529"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Настройка и проверка сетевого подключения антивирусной программы "Защитник Windows"

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Для обеспечения антивирусная программа в Microsoft Defender, как облачная защита работает должным образом, необходимо настроить сеть, чтобы обеспечить соединения между конечных точками и определенными серверами Майкрософт. В этой статье перечислены соединения, которые должны быть разрешены, например, с помощью правил брандмауэра, и содержатся инструкции по проверке соединения. Правильное настройка защиты помогает вам получить наилучшее значение от служб защиты, предоставляемых в облаке.

Для получения подробной информации [о подключении к сети можно найти в](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) блоге важные изменения в конечной точке службы активной защиты Майкрософт.

> [!TIP]
> Вы также можете посетить демо-сайт Microsoft Defender for Endpoint [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) чтобы подтвердить, что работают следующие функции:
>
> - Облачная защита
> - Быстрое обучение (включая блок с первого взгляда)
> - Потенциально нежелательная блокировка приложений

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Разрешить подключение к антивирусная программа в Microsoft Defender сервису

Облачный антивирусная программа в Microsoft Defender обеспечивает быструю и сильную защиту конечных точек. Включение облачной службы защиты является необязательным, однако это настоятельно рекомендуется, поскольку обеспечивает важную защиту от вредоносных программ в конечных точках и по всей сети.

> [!NOTE]
> Облачное антивирусная программа в Microsoft Defender является механизмом обеспечения обновленной защиты сети и конечных точек. Хотя это называется облачным сервисом, это не просто защита файлов, хранящихся в облаке, а использование распределенных ресурсов и машинного обучения для обеспечения защиты конечных точек со скоростью, которая намного быстрее, чем традиционные обновления разведки безопасности.

Подробную [информацию о предоставлении услуг с](enable-cloud-protection-microsoft-defender-antivirus.md) помощью Intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell или отдельных клиентов в приложении «Безопасность Windows» можно получить в облачной защите. 

После включения службы может потребоваться настроить сеть или брандмауэр, чтобы обеспечить соединения между ней и конечными точками.

Поскольку ваша защита является облачным сервисом, компьютеры должны иметь доступ к Интернету и обратиться в Microsoft Defender для Office 365 машинного обучения. Не исключайте URL-адрес из `*.blob.core.windows.net` любого вида сетевой проверки. 

В таблице ниже перечислены службы и связанные с ними URL-адреса. Убедитесь, что нет никаких правил фильтрации брандмауэра или сети, отрицающих доступ к этим URL-адресам, или вам может понадобиться создать правило позволяют специально для них (за исключением `*.blob.core.windows.net` URL). Ниже упоминаются URL-адреса используют порт 443 для связи.


| **Служба**| **Описание** |**URL-адрес** |
| :--: | :-- | :-- |
| антивирусная программа в Microsoft Defender облачной защиты, также именуемая Microsoft Active Protection Service (MAPS)|Используется антивирусная программа в Microsoft Defender для обеспечения облачной защиты|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| Служба обновления Майкрософт (MU) <br/> Windows Служба обновления (WU)|  Разведка безопасности и обновления продуктов   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> Для получения [подробной информации см. конечные точки соединения для Windows обновления](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|Разведка безопасности обновляет альтернативное местоположение загрузки (ADL)|   Альтернативное место для антивирусная программа в Microsoft Defender обновления разведки безопасности, если установленная разведка безопасности устарела (7 или более дней позади)|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br>  `go.microsoft.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| Хранение представления вредоносных программ|Upload файлов, представленных корпорации Майкрософт с помощью формы представления или автоматического представления образца    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| Список отзывов сертификатов (CRL)|Используется Windows при создании SSL-соединения с MAPS для обновления CRL   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| Магазин символов|Используется антивирусная программа в Microsoft Defender восстановления определенных критических файлов во время рекультивации потоков  | `https://msdl.microsoft.com/download/symbols` |
| Универсальный клиент телеметрии| Используется Windows для отправки диагностических данных клиентов; антивирусная программа в Microsoft Defender использует телеметрию для целей мониторинга качества продукции   | Обновление использует SSL (TCP Port 443) для загрузки манифестов и загрузки диагностических данных в корпорацию Майкрософт, которая использует следующие конечные точки DNS:   `vortex-win.data.microsoft.com` <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>Проверка связей между сетью и облаком

После разрешения URL-адресов, перечисленных выше, вы можете проверить, подключены ли вы к облачной службе антивирусная программа в Microsoft Defender и правильно отчитываелись и получали информацию, чтобы убедиться, что вы полностью защищены.

**Используйте инструмент cmdline для проверки облачной защиты:**

Используйте следующий аргумент с антивирусная программа в Microsoft Defender `mpcmdrun.exe` (), чтобы убедиться, что ваша сеть может общаться с антивирусная программа в Microsoft Defender облачным сервисом:

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> Необходимо открыть версию команды на уровне администратора. Нажмите кнопку "Справа" в меню "Пуск", **нажмите кнопку "Беги как администратор"** **и нажмите "Да"** по запросу разрешений. Эта команда будет работать только на Windows 10, версии 1703 или выше.

Для получения дополнительной информации [с антивирусная программа в Microsoft Defender м mpcmdrun.exe.](command-line-arguments-microsoft-defender-antivirus.md)

**Попытка загрузить поддельный файл вредоносных программ из Microsoft:**

Вы можете скачать образец файла, антивирусная программа в Microsoft Defender вы будете обнаруживать и блокировать, если вы должным образом подключены к облаку.

Скачать файл, посетив [https://aka.ms/ioavtest](https://aka.ms/ioavtest) .

> [!NOTE]
> Этот файл не является фактической частью вредоносных программ. Это поддельный файл, который предназначен для проверки, если вы должным образом подключены к облаку.

Если вы должным образом подключены, вы увидите предупреждение антивирусная программа в Microsoft Defender уведомления.

Если вы используете Microsoft Edge, вы также увидите сообщение-уведомление:

![Microsoft Edge пользователю, что вредоносная программа была найдена](images/defender/wdav-bafs-edge.png)

Аналогичное сообщение возникает, если вы используете Internet Explorer:

![антивирусная программа в Microsoft Defender уведомление, информирующее пользователя о том, что была найдена вредоносная программа](images/defender/wdav-bafs-ie.png)

Вы также увидите обнаружение под **карантинными угрозами в** разделе **История сканирования** в приложении Безопасность Windows:

1. Откройте приложение Безопасность Windows, нажав значок щита в баре задач или поиск меню старта для **безопасности.**

2. Выберите **вирус & защиту от угроз,** а затем выберите **историю защиты.**

3. В разделе **карантинных угроз выберите** Полную **историю, чтобы увидеть** обнаруженную поддельную вредоносную программу.

   > [!NOTE]
   > Версии Windows 10 версии 1703 имеют другой пользовательский интерфейс. Смотрите [антивирусная программа в Microsoft Defender в приложении Безопасность Windows .](microsoft-defender-security-center-antivirus.md)

   В Windows событий также будет Защитник Windows [идентификатор события клиента 1116.](troubleshoot-microsoft-defender-antivirus.md)

## <a name="related-articles"></a>Связанные статьи

- [Антивирусная программа в Microsoft Defender (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)

- [Включение облачной защиты](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Аргументы командной строки](command-line-arguments-microsoft-defender-antivirus.md)

- [Важные изменения в конечной точке службы активной защиты Майкрософт](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)
