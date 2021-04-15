---
title: Защитник Майкрософт в автономном режиме в Windows 10
description: Вы можете использовать Microsoft Defender в автономном режиме прямо из Защитник Windows антивирусного приложения. Вы также можете управлять развертываемой сетью.
keywords: сканирование, защитник, автономно
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b1e7e70c6ca217d3ad8859c1493598d71054f84
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765339"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>Запуск и просмотр результатов проверки в автономном Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Offline — это средство сканирования антивирусных программ, которое позволяет загрузить и запустить сканирование из надежной среды. Сканирование выполняется за пределами обычного ядра Windows, поэтому оно может быть нацелено на вредоносные программы, которые пытаются обойти оболочку Windows, например вирусы и корневые наборы, заражая или переописывая запись основной загрузки (MBR).

Вы можете использовать Microsoft Defender Offline, если вы подозреваете заражение вредоносными программами или хотите подтвердить тщательную очистку конечной точки после вспышки вредоносных программ.

В Windows 10 microsoft Defender Offline можно запускать одним щелчком мыши непосредственно из [приложения Безопасности Windows.](microsoft-defender-security-center-antivirus.md) В предыдущих версиях Windows пользователю пришлось установить Microsoft Defender Offline для загружаемых мультимедиа, перезапустить конечную точку и загрузить загружаемые носитли.

## <a name="prerequisites-and-requirements"></a>необходимые условия и требования

Microsoft Defender Offline в Windows 10 имеет те же требования к оборудованию, что и к Windows 10. 

Дополнительные сведения о требованиях к Windows 10 см. в следующих темах:

- [Минимальные требования к оборудованию](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [Рекомендации по компонентам оборудования](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> Microsoft Defender Offline не поддерживается на компьютерах с ARM процессорами или в подразделениях с запасами Windows Server.

Чтобы запустить Microsoft Defender в автономном режиме с конечной точки, пользователь должен войти в систему с привилегиями администратора.
 
## <a name="microsoft-defender-offline-updates"></a>Автономные обновления Защитника Майкрософт

Microsoft Defender Offline использует последние обновления защиты, доступные на конечной точке; он обновляется всякий раз, Защитник Windows антивирус обновляется. 

> [!NOTE]
> Перед запуском автономного сканирования необходимо попытаться обновить защиту авт.майкрософт защитника. Вы можете либо задействовать обновление с помощью групповой политики, либо обычно развертывать обновления в конечные точки, либо вручную загрузить и установить последние обновления защиты из Центр Майкрософт по защите от вредоносных программ [.](https://www.microsoft.com/security/portal/definitions/adl.aspx)

Дополнительные [сведения см.](manage-protection-updates-microsoft-defender-antivirus.md) в разделе Управление обновлениями антивирусной безопасности Защитника Майкрософт.

## <a name="usage-scenarios"></a>Сценарии использования

В Windows 10 версии 1607 можно вручную принудить к автономному сканированию. Кроме того, если Защитник Windows определяет, что Microsoft Defender Offline необходимо запустить, он будет подсказок пользователю на конечной точке. 

Необходимость выполнения автономного сканирования также будет обнаружена в Microsoft Endpoint Manager, если вы используете его для управления конечными точками.

Запрос может происходить с помощью уведомления, аналогично следующему:

![Уведомление Windows, показывающая требование для запуска в автономном режиме Microsoft Defender](images/defender/notification.png)

Пользователь также будет уведомлен в клиенте Защитник Windows клиента.

В диспетчере конфигурации можно определить состояние конечных точек, перенаправление в Службу мониторинга > **Обзор >** безопасности > Состояние защиты конечных точек > состояние защиты конечных точек центра системы . 

Сканирование Microsoft Defender Offline указывается в состоянии исправлений вредоносных программ, так как требуется **автономное сканирование.** 

![Microsoft Endpoint Manager, указывающая на то, что требуется проверка автономного доступа к защитнику Майкрософт](images/defender/sccm-wdo.png)

## <a name="configure-notifications"></a>Настройка уведомлений

Уведомления Microsoft Defender Offline настроены в том же параметре политики, что и другие уведомления microsoft Defender AV.

Дополнительные сведения об уведомлениях в Защитник Windows см. в разделе Настройка уведомлений, которые отображаются в разделе [конечные](configure-notifications-microsoft-defender-antivirus.md) точки.

## <a name="run-a-scan"></a>Запустить сканирование 

> [!IMPORTANT]
> Прежде чем использовать Microsoft Defender Offline, убедитесь, что вы сохраните все файлы и отключите запущенные программы. Автономное сканирование Защитника Майкрософт занимает около 15 минут. Она перезапустит конечную точку после завершения проверки. Сканирование выполняется вне обычной операционной среды Windows. Пользовательский интерфейс будет выглядеть иначе, чем обычная проверка, выполняемая Защитник Windows. После завершения проверки конечная точка будет перезапущена и Windows будет загружаться нормально.

Вы можете выполнить автономное сканирование Защитника Майкрософт со следующими следующими примерами:

- PowerShell
- Инструментарий управления Windows (WMI)
- Приложение Безопасности Windows



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>Для запуска автономного сканирования используйте cmdlets PowerShell

Используйте следующие cmdlets:

```PowerShell
Start-MpWDOScan
```

Дополнительные сведения о том, как использовать [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) с антивирусным вирусом Microsoft Defender и [Defender,](/powershell/module/defender/) см. в этой ссылке.

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>Использование инструкции по управлению Windows (WMI) для запуска автономного сканирования

Используйте класс [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для запуска автономного сканирования.

В следующем фрагменте скрипта WMI будет немедленно выполниться автономное сканирование Защитника Майкрософт, что приведет к перезапуску конечной точки, запуску автономного сканирования, а затем перезапуску и загрузке в Windows.

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

Дополнительные сведения см. в следующих сведениях:
- [Защитник Windows API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>Использование приложения Защитник Windows безопасности для запуска автономного сканирования

1. Откройте приложение Безопасности Windows, щелкнув значок щита в панели задач или нажав меню пусков для **Defender.**

2. Щелкните **плитку защиты &** вирусов (или значок щита в левой панели меню), а затем метку **Advanced scan:**
    
3. Выберите **microsoft Defender Автономное сканирование** и нажмите **кнопку Сканирование сейчас**.

    > [!NOTE]
    > В Windows 10 версии 1607 автономное сканирование можно выполнить из-под обновления параметров **Windows**& безопасности Защитник Windows или Защитник Windows  >    >   клиента.


## <a name="review-scan-results"></a>Просмотр результатов сканирования

Результаты автономного сканирования Microsoft Defender будут перечислены в разделе История сканирования приложения [Windows Security.](microsoft-defender-security-center-antivirus.md) 


## <a name="related-articles"></a>Статьи по теме

- [Настройка, инициирование и проверка результатов проверки и устранения](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Антивирус Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)