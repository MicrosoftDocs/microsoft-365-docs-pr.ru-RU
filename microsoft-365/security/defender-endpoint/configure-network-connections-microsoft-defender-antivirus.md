---
title: Настройка и проверка сетевого подключения антивирусной программы "Защитник Windows"
description: Настройка и проверка подключения к облачной службе защиты от антивирусных программ Microsoft Defender.
keywords: антивирус, антивирус Microsoft Defender, антивирусные программы, безопасность, защитник, облако, агрессивность, уровень защиты
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 06/17/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 6ccc2eb171e85793899a7862ed9a317815d89626
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007588"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Настройка и проверка сетевого подключения антивирусной программы "Защитник Windows"

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Чтобы обеспечить надстройку облачной защиты от антивируса Microsoft Defender, ваша группа безопасности должна настроить сеть, чтобы обеспечить подключение между конечными точками и определенными серверами Майкрософт. В этой статье перечислены подключения, которые необходимо разрешить, например с помощью правил брандмауэра, и перечислены инструкции по проверке подключения. Правильная настройка защиты позволяет получить наилучшее значение от облачных служб защиты.

Некоторые сведения о подключении к сети см. в публикации "Важные изменения в конечной точке [Службы](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) активной защиты Майкрософт".

> [!TIP]
> Посетите веб-сайт демонстрации Microsoft Defender for Endpoint [в demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) чтобы подтвердить, что работают следующие функции:
>
> - Облачная защита
> - Быстрое обучение (включая блок с первого взгляда)
> - Блокировка потенциально нежелательных приложений

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Разрешить подключение к облачной облачной службе Microsoft Defender Antivirus

Облачная служба антивирусной защиты Microsoft Defender обеспечивает быструю и мощную защиту конечных точек. Включение облачной службы защиты является необязательным, однако она настоятельно рекомендуется, так как обеспечивает важную защиту от вредоносных программ в конечных точках и в сети. Сведения о включив службу в intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell или отдельных клиентах в приложении Windows Security, см. в материале Enable [cloud-delivered protection.](enable-cloud-protection-microsoft-defender-antivirus.md) 

После включения службы может потребоваться настроить сеть или брандмауэр, чтобы разрешить подключение между ней и конечными точками. Поскольку ваша защита является облачной службой, компьютеры должны иметь доступ к Интернету и получать доступ к службам машинного обучения Microsoft Defender для Office 365. Не исключайте URL-адрес `*.blob.core.windows.net` любого вида сетевой проверки. 

> [!NOTE]
> Облачная служба антивирусной защиты Microsoft Defender — это механизм доставки обновленной защиты в сеть и конечные точки. Несмотря на то, что она называется облачной службой, она не просто обеспечивает защиту файлов, хранимых в облаке, а использует распределенные ресурсы и машинное обучение для обеспечения защиты конечных точек со скоростью, значительно более быстрой, чем традиционные обновления службы безопасности.

## <a name="services-and-urls"></a>Службы и URL-адреса

В таблице в этом разделе перечислены службы и связанные с ними веб-адреса веб-сайтов (URL-адреса). 

Убедитесь, что нет брандмауэра или правил фильтрации сети, отказывающих в доступе к этим URL-адресам. В противном случае может потребоваться создать правило разрешить специально для них (за исключением `*.blob.core.windows.net` URL-адреса). URL-адреса в следующей таблице используют порт 443 для связи.

| Служба и описание | URL-адрес |
|----|---- |
| Облачная служба защиты от антивируса Microsoft Defender, также именуемая Службой активной защиты Microsoft (MAPS)<p>Эта служба используется антивирусом Microsoft Defender для обеспечения облачной защиты|`*.wdcp.microsoft.com` <p> `*.wdcpalt.microsoft.com` <p> `*.wd.microsoft.com`|
| Служба обновления Майкрософт (MU) и Служба обновления Windows (WU) <p>Эти службы позволяют использовать сведения о безопасности и обновления продуктов   |`*.update.microsoft.com` <p> `*.delivery.mp.microsoft.com`<p> `*.windowsupdate.com` <p> Дополнительные сведения см. в [материале Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|Сведения о безопасности обновляют альтернативное расположение загрузки (ADL)<p>Это альтернативное расположение для обновлений антивирусной безопасности Microsoft Defender, если установленная разведка безопасности устарела (на 7 или более дней)|  `*.download.microsoft.com`  <p> `*.download.windowsupdate.com`<p>  `go.microsoft.com`<p> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| Хранение отправки вредоносных программ <p>Это расположение для отправки файлов, отправленных в Корпорацию Майкрософт с помощью формы отправки или автоматической отправки образца. | `ussus1eastprod.blob.core.windows.net` <p>    `ussus2eastprod.blob.core.windows.net` <p>    `ussus3eastprod.blob.core.windows.net` <p>    `ussus4eastprod.blob.core.windows.net` <p>    `wsus1eastprod.blob.core.windows.net` <p>    `wsus2eastprod.blob.core.windows.net` <p>    `ussus1westprod.blob.core.windows.net` <p>    `ussus2westprod.blob.core.windows.net` <p>    `ussus3westprod.blob.core.windows.net` <p>    `ussus4westprod.blob.core.windows.net` <p>    `wsus1westprod.blob.core.windows.net` <p>    `wsus2westprod.blob.core.windows.net` <p>    `usseu1northprod.blob.core.windows.net` <p>    `wseu1northprod.blob.core.windows.net` <p>    `usseu1westprod.blob.core.windows.net` <p>    `wseu1westprod.blob.core.windows.net` <p>    `ussuk1southprod.blob.core.windows.net` <p>    `wsuk1southprod.blob.core.windows.net` <p>    `ussuk1westprod.blob.core.windows.net` <p>    `wsuk1westprod.blob.core.windows.net` |
| Список отзыва сертификатов (CRL) <p>Этот список используется Windows при создании подключения SSL к MAPS для обновления CRL   | `http://www.microsoft.com/pkiops/crl/` <p> `http://www.microsoft.com/pkiops/certs` <p>   `http://crl.microsoft.com/pki/crl/products` <p> `http://www.microsoft.com/pki/certs` |
| Магазин символов <p>Хранилище символов используется антивирусом Microsoft Defender для восстановления определенных критически важных файлов во время потоков исправлений   | `https://msdl.microsoft.com/download/symbols` |
| Клиент универсальной телеметрии <p>Этот клиент используется Windows для отправки диагностических данных клиента<p> Антивирус Microsoft Defender использует телеметрию для мониторинга качества продуктов    | Обновление использует SSL (TCP Port 443) для скачивания манифестов и отправки диагностических данных в Корпорацию Майкрософт, которая использует следующие конечные точки DNS: <p> `vortex-win.data.microsoft.com` <p>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>Проверка подключений между сетью и облаком

Разрешив указанные выше URL-адреса, вы можете проверить, подключены ли вы к облачной службе антивируса Microsoft Defender и правильно отчитываться и получать сведения, чтобы обеспечить полную защиту.

### <a name="use-the-cmdline-tool-to-validate-cloud-delivered-protection"></a>Использование средства cmdline для проверки облачной защиты

Чтобы убедиться, что ваша сеть может взаимодействовать с облачной службой антивирусных программ Microsoft Defender, используйте следующий `mpcmdrun.exe` аргумент:

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> Необходимо открыть версию командной подсказки на уровне администратора. Щелкните правой кнопкой мыши элемент в меню "Пуск", нажмите кнопку **Запустить** в качестве администратора и нажмите **кнопку Да** по запросу разрешений. Эта команда будет работать только в Windows 10, версии 1703 или выше.

Дополнительные сведения см. в [веб-сайте Управление](command-line-arguments-microsoft-defender-antivirus.md)антивирусом Microsoft Defender с помощью средства mpcmdrun.exe командной линии.

### <a name="attempt-to-download-a-fake-malware-file-from-microsoft"></a>Попытка скачать поддельный файл вредоносных программ из Microsoft

Вы можете скачать пример файла, который антивирус Microsoft Defender будет обнаруживать и блокировать, если вы правильно подключены к облаку.

Скачайте файл, посетив [https://aka.ms/ioavtest](https://aka.ms/ioavtest) .

> [!NOTE]
> Этот файл не является фактическим вредоносным программным обеспечением. Это поддельный файл, который предназначен для проверки правильного подключения к облаку.

Если вы подключены должным образом, вы увидите предупреждение о антивирусном оповещении Microsoft Defender.

Если вы используете Microsoft Edge, вы также увидите сообщение уведомления:

:::image type="content" source="../../media/wdav-bafs-edge.png" alt-text="Снимок экрана уведомления об обнаружении вредоносных программ в Edge":::

Аналогичное сообщение возникает, если вы используете Internet Explorer:

:::image type="content" source="../../media/wdav-bafs-ie.png" alt-text="Уведомление об обнаружении вредоносных программ в Microsoft Defender AV":::

Кроме того, в разделе  История сканирования в приложении Windows Security вы также увидите обнаружение под карантинными угрозами: 

1. Откройте приложение Безопасности Windows, щелкнув значок щита в панели задач или нажав меню "Пуск" для **обеспечения безопасности.**

2. Выберите **защиту & вирусов,** а затем выберите историю **защиты.**

3. В разделе **Карантин** угроз выберите **См.** полную историю обнаружения поддельных вредоносных программ.

   > [!NOTE]
   > Версии Windows 10 до версии 1703 имеют другой пользовательский интерфейс. См. [антивирус Microsoft Defender в приложении Windows Security.](microsoft-defender-security-center-antivirus.md)

   В журнале событий Windows также будет Защитник Windows [ИД события клиента 1116](troubleshoot-microsoft-defender-antivirus.md).

