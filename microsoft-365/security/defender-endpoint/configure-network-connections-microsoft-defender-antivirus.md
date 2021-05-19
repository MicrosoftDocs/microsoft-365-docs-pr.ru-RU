---
title: Настройка и проверка сетевого подключения антивирусной программы "Защитник Windows"
description: Настройка и проверка подключения к службе антивирусная программа в Microsoft Defender облачной защиты.
keywords: антивирус, антивирусная программа в Microsoft Defender, антивирусное программное обеспечение, безопасность, защита, облако, агрессивность, уровень защиты
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
ms.openlocfilehash: 5e754c2f4b5406d4b91ef624415f3819d3171305
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536026"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Настройка и проверка сетевого подключения антивирусной программы "Защитник Windows"

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Чтобы обеспечить антивирусная программа в Microsoft Defender надстройки, необходимо настроить сеть, чтобы разрешить подключение между конечными точками и определенными серверами Майкрософт. В этой статье перечислены подключения, которые необходимо разрешить, например с помощью правил брандмауэра, и перечислены инструкции по проверке подключения. Правильная настройка защиты позволяет получить наилучшее значение от облачных служб защиты.

Некоторые сведения о подключении к сети см. в публикации "Важные изменения в конечной точке [Службы](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) активной защиты Майкрософт".

> [!TIP]
> Вы также можете посетить веб-сайт демонстрации Microsoft Defender для конечной точки [в demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) чтобы подтвердить, что работают следующие функции:
>
> - Облачная защита
> - Быстрое обучение (включая блок с первого взгляда)
> - Блокировка потенциально нежелательных приложений

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Разрешить подключение к облачной антивирусная программа в Microsoft Defender службе

Облачная антивирусная программа в Microsoft Defender обеспечивает быструю и мощную защиту конечных точек. Включение облачной службы защиты является необязательным, однако она настоятельно рекомендуется, так как обеспечивает важную защиту от вредоносных программ в конечных точках и в сети.

> [!NOTE]
> Облачная антивирусная программа в Microsoft Defender — это механизм доставки обновленной защиты в сеть и конечные точки. Несмотря на то, что она называется облачной службой, она не просто обеспечивает защиту файлов, хранимых в облаке, а использует распределенные ресурсы и машинное обучение для обеспечения защиты конечных точек со скоростью, значительно более быстрой, чем традиционные обновления службы безопасности.

Сведения [](enable-cloud-protection-microsoft-defender-antivirus.md) о том, как включить службу с помощью см. в приложении Intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell или отдельных клиентов в приложении Безопасность Windows. 

После включения службы может потребоваться настроить сеть или брандмауэр, чтобы разрешить подключение между ней и конечными точками.

Так как ваша защита является облачной службой, компьютеры должны иметь доступ к Интернету и получать доступ к microsoft Defender для Office 365 машинного обучения. Не исключайте URL-адрес `*.blob.core.windows.net` любого вида сетевой проверки. 

В таблице ниже перечислены службы и связанные с ними URL-адреса. Убедитесь, что нет брандмауэра или правил фильтрации сети, отказывающих в доступе к этим URL-адресам, или вам может потребоваться создать правило разрешить специально для них (за исключением `*.blob.core.windows.net` URL-адреса). Ниже приведены URL-адреса, использующие порт 443 для связи.


| **Служба**| **Описание** |**URL-адрес** |
| :--: | :-- | :-- |
| антивирусная программа в Microsoft Defender облачной службы защиты, также именуемой Microsoft Active Protection Service (MAPS)|Используется антивирусная программа в Microsoft Defender для обеспечения облачной защиты|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| Служба обновления Майкрософт (MU) <br/> Windows Служба обновления (WU)|  Сведения о безопасности и обновления продуктов   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> Сведения [см. в материале Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|Сведения о безопасности обновляют альтернативное расположение загрузки (ADL)|   Альтернативное расположение для антивирусная программа в Microsoft Defender службы безопасности, если установленная разведка безопасности устарела (отстает от 7 или более дней)|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br>  `go.microsoft.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| Хранение отправки вредоносных программ|Upload для файлов, отправленных в Корпорацию Майкрософт с помощью формы отправки или автоматической отправки образца    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| Список отзыва сертификатов (CRL)|Используется Windows при создании подключения SSL к MAPS для обновления CRL   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| Магазин символов|Используется антивирусная программа в Microsoft Defender для восстановления определенных критически важных файлов во время потоков исправлений  | `https://msdl.microsoft.com/download/symbols` |
| Клиент универсальной телеметрии| Используется Windows для отправки диагностических данных клиента; антивирусная программа в Microsoft Defender телеметрии для мониторинга качества продукции   | Обновление использует SSL (TCP Port 443) для скачивания манифестов и отправки диагностических данных в Корпорацию Майкрософт, которая использует следующие конечные точки DNS:   `vortex-win.data.microsoft.com` <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>Проверка подключений между сетью и облаком

Разрешив указанные выше URL-адреса, вы можете проверить, подключены ли вы к облачной службе антивирусная программа в Microsoft Defender и правильно отчитываться и получать информацию, чтобы обеспечить полную защиту.

**Используйте средство cmdline для проверки облачной защиты:**

Используйте следующий аргумент с помощью антивирусная программа в Microsoft Defender командной строки , чтобы убедиться, что ваша сеть может общаться с антивирусная программа в Microsoft Defender `mpcmdrun.exe` облачной службой:

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> Необходимо открыть версию командной подсказки на уровне администратора. Щелкните правой кнопкой мыши элемент в меню "Пуск", нажмите кнопку **Запустить** в качестве администратора и нажмите **кнопку Да** по запросу разрешений. Эта команда будет работать только на Windows 10 версии 1703 или выше.

Дополнительные сведения см. в [антивирусная программа в Microsoft Defender с помощью средства mpcmdrun.exe командной линии.](command-line-arguments-microsoft-defender-antivirus.md)

**Попытка скачать поддельный файл вредоносных программ из Microsoft:**

Вы можете скачать пример файла, который антивирусная программа в Microsoft Defender будет обнаруживать и блокировать, если вы правильно подключены к облаку.

Скачайте файл, посетив [https://aka.ms/ioavtest](https://aka.ms/ioavtest) .

> [!NOTE]
> Этот файл не является фактическим вредоносным программным обеспечением. Это поддельный файл, который предназначен для проверки правильного подключения к облаку.

Если вы подключены должным образом, вы увидите предупреждение антивирусная программа в Microsoft Defender уведомления.

Если вы используете Microsoft Edge, вы также увидите сообщение уведомления:

![Microsoft Edge сообщить пользователю об обнаружении вредоносных программ](images/defender/wdav-bafs-edge.png)

Аналогичное сообщение возникает, если вы используете Internet Explorer:

![антивирусная программа в Microsoft Defender уведомления о обнаружении вредоносных программ](images/defender/wdav-bafs-ie.png)

В разделе История сканирования  в приложении Безопасность Windows также  будет обнаружено обнаружение под карантинными угрозами.

1. Откройте приложение Безопасность Windows, щелкнув значок щита в панели задач или нажав меню пусков для **Defender.**

2. Выберите **плитку защиты &** вирусов (или значок щита в левой панели меню), а затем метку **истории сканирования:**

    ![Снимок экрана метки истории сканирования в приложении Безопасность Windows](images/defender/wdav-history-wdsc.png)

3. В разделе **Карантин** угроз выберите **См.** полную историю обнаружения поддельных вредоносных программ.

   > [!NOTE]
   > Версии Windows 10 версии 1703 имеют другой пользовательский интерфейс. См. [антивирусная программа в Microsoft Defender в приложении Безопасность Windows.](microsoft-defender-security-center-antivirus.md)

   В журнале Windows событий также Защитник Windows клиентского события [ID 1116](troubleshoot-microsoft-defender-antivirus.md).

## <a name="related-articles"></a>Связанные статьи

- [Антивирусная программа в Microsoft Defender (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)

- [Включение облачной защиты](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Аргументы командной строки](command-line-arguments-microsoft-defender-antivirus.md)

- [Важные изменения конечной точки Службы активной защиты Майкрософт](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)
