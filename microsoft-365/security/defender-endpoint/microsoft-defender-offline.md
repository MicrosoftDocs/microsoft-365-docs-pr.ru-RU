---
title: автономный Microsoft Defender в Windows 10
description: Вы можете использовать автономный Microsoft Defender прямо из антивирусная программа приложения. Вы также можете управлять развертываемой сетью.
keywords: сканирование, защитник, автономно
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: a25a2ec513cd7c25f9f6ddf3d5e328928837bf2d
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275148"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>Запуск и просмотр результатов проверки в автономном Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

автономный Microsoft Defender это средство сканирования антивирусных программ, которое позволяет загрузить и запустить сканирование из надежной среды. Сканирование выполняется за пределами обычного Windows, поэтому оно может быть нацелено на вредоносные программы, которые пытаются обойти оболочку Windows, например вирусы и корневые наборы, которые заражают или переоценивают запись основной загрузки (MBR).

Вы можете использовать автономный Microsoft Defender, если вы подозреваете заражение вредоносными программами или хотите подтвердить тщательную очистку конечной точки после вспышки вредоносных программ.

В Windows 10 автономный Microsoft Defender можно выполнить одним щелчком мыши непосредственно из [Безопасность Windows приложения](microsoft-defender-security-center-antivirus.md). В предыдущих версиях Windows пользователю приходилось устанавливать автономный Microsoft Defender для загрузки мультимедиа, перезапускать конечную точку и загружать загружаемые носитли.

## <a name="prerequisites-and-requirements"></a>необходимые условия и требования

автономный Microsoft Defender в Windows 10 имеет те же требования к оборудованию, что и Windows 10. 

Дополнительные сведения о требованиях Windows 10 см. в следующих темах:

- [Минимальные требования к оборудованию](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [Инструкции по компонентам оборудования](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> автономный Microsoft Defender не поддерживается на машинах с ARM процессорами или Windows единицах сохраняемого сервера.

Чтобы выполнить автономный Microsoft Defender с конечной точки, пользователь должен войти в систему с привилегиями администратора.
 
## <a name="microsoft-defender-offline-updates"></a>автономный Microsoft Defender обновления

автономный Microsoft Defender использует последние обновления защиты, доступные в конечной точке; он обновляется при антивирусная программа обновления. 

> [!NOTE]
> Перед запуском автономного сканирования необходимо попытаться обновить защиту авт.майкрософт защитника. Вы можете либо принудить обновление с помощью групповой политики, либо обычно развертывать обновления в конечные точки, либо вручную скачать и установить последние обновления защиты из [Центр Майкрософт по защите от вредоносных программ](https://www.microsoft.com/security/portal/definitions/adl.aspx).

Дополнительные [сведения см. в разделе Антивирусная программа в Microsoft Defender обновления службы](manage-protection-updates-microsoft-defender-antivirus.md) безопасности.

## <a name="usage-scenarios"></a>Сценарии использования

В Windows 10 версии 1607 можно вручную принудить к автономному сканированию. Кроме того, если Защитник Windows определяет, что автономный Microsoft Defender необходимо выполнить, он будет подсказок пользователю на конечной точке. 

Необходимость выполнения автономного сканирования также будет обнаружена в Microsoft Endpoint Manager, если вы используете его для управления конечными точками.

Запрос может происходить с помощью уведомления, аналогично следующему:

![Windows уведомления с требованием запуска автономный Microsoft Defender](images/defender/notification.png)

Пользователь также будет уведомлен в клиенте Защитник Windows клиента.

В диспетчере конфигурации можно определить состояние конечных точек, перенаправление в Службу мониторинга > обзор > безопасности **> Endpoint Protection состояние > System Center Endpoint Protection состояние**. 

автономный Microsoft Defender проверки указаны в состоянии **исправление вредоносных** программ, как **автономное сканирование требуется**.

![Microsoft Endpoint Manager, указывающее, автономный Microsoft Defender требуется проверка](images/defender/sccm-wdo.png)

## <a name="configure-notifications"></a>Настройка уведомлений

автономный Microsoft Defender настраиваются в том же параметре политики, что и другие уведомления Microsoft Defender AV.

Дополнительные сведения об уведомлениях в Защитник Windows см. в разделе Настройка уведомлений, которые отображаются в разделе [конечные точки.](configure-notifications-microsoft-defender-antivirus.md)

## <a name="run-a-scan"></a>Запустить сканирование 

> [!IMPORTANT]
> Перед использованием автономный Microsoft Defender убедитесь, что вы сохраните все файлы и отключите запущенные программы. Проверка автономный Microsoft Defender занимает около 15 минут. Она перезапустит конечную точку после завершения проверки. Сканирование выполняется за пределами обычной Windows среды. Пользовательский интерфейс будет выглядеть иначе, чем обычная проверка, выполняемая Защитник Windows. После завершения сканирования конечная точка будет перезапущена и Windows будет загружаться нормально.

Вы можете выполнить автономный Microsoft Defender проверку со следующими следующими примерами:

- PowerShell
- Инструментарий управления Windows (WMI)
- Приложение Безопасность Windows



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>Для запуска автономного сканирования используйте cmdlets PowerShell

Используйте следующие cmdlets:

```PowerShell
Start-MpWDOScan
```

Дополнительные сведения об использовании PowerShell с антивирусной программой в Microsoft Defender см. в разделах [Использование командлетов PowerShell для настройки и запуска антивирусной программы в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Командлеты Defender](/powershell/module/defender/).

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>Использование Windows управления (WMI) для запуска автономного сканирования

Используйте класс [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для запуска автономного сканирования.

В следующем фрагменте сценария WMI будет немедленно выполнить автономный Microsoft Defender, что приведет к перезапуску конечной точки, запуску автономного сканирования, а затем перезапуску и загрузке в Windows.

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

Дополнительные сведения см. в следующих сведениях:
- [Защитник Windows API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>Использование приложения Защитник Windows безопасности для запуска автономного сканирования

1. Откройте приложение Безопасность Windows, щелкнув значок щита в панели задач или нажав меню пусков для **Defender.**

2. Щелкните **плитку защиты &** вирусов (или значок щита в левой панели меню), а затем метку **Advanced scan:**
    
3. Выберите **автономный Microsoft Defender и** нажмите **кнопку Сканирование сейчас**.

    > [!NOTE]
    > В Windows 10 версии 1607 автономное сканирование можно выполнить из Windows Параметры Update & безопасности Защитник Windows или Защитник Windows  >    >   клиента.


## <a name="review-scan-results"></a>Просмотр результатов сканирования

автономный Microsoft Defender результаты сканирования будут перечислены в разделе История сканирования [приложения Безопасность Windows.](microsoft-defender-security-center-antivirus.md) 


## <a name="related-articles"></a>Статьи по теме

- [Настройка, инициирование и проверка результатов проверки и устранения](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [антивирусная программа в Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)