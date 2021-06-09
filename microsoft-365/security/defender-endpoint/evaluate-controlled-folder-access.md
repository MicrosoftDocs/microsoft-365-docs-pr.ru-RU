---
title: Оценка контролируемого доступа к папкам
description: Узнайте, как управляемый доступ к папкам помогает защитить файлы от изменения вредоносными приложениями.
keywords: Защита от эксплойтов, Windows 10, защитник Windows, вымогателей, защита, оценка, тестирование, демонстрация, попытка
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 15ea4696052a6c987314e3c7b0dd282a49ed4df8
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842918"
---
# <a name="evaluate-controlled-folder-access"></a>Оценка контролируемого доступа к папкам

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


[Управляемый доступ к папкам](controlled-folders.md) — это функция, которая помогает защитить документы и файлы от изменений подозрительными или вредоносными приложениями. Управляемый доступ к папкам поддерживается на Windows Server 2019 и Windows 10 клиентах.

Это особенно полезно для защиты от [программ-вымогателей,](https://www.microsoft.com/wdsi/threats/ransomware) которые пытаются шифровать файлы и удерживать их в заложниках.

В этой статье вы можете оценить доступ к управляемой папке. В нем объясняется, как включить режим аудита, чтобы можно было протестировать функцию непосредственно в организации.

> [!TIP]
> Вы также можете посетить веб-сайт демонстрационных сценариев Microsoft Defender for Endpoint в demo.wd.microsoft.com, чтобы подтвердить, что функция работает, и посмотреть, как она работает. [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)

## <a name="use-audit-mode-to-measure-impact"></a>Использование режима аудита для измерения воздействия

Включить доступ к управляемой папке в режиме  аудита, чтобы увидеть запись о том, что произошло бы, если бы она была полностью включена. Проверьте, как эта функция будет работать в организации, чтобы убедиться, что она не влияет на ваши бизнес-приложения. Вы также можете получить представление о том, сколько попыток изменения подозрительных файлов обычно происходит в течение определенного периода времени.

Чтобы включить режим аудита, используйте следующий комдлет PowerShell:

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> Если вы хотите полностью проверять, как будет работать управляемый доступ к папкам в организации, вам потребуется использовать средство управления для развертывания этого параметра на устройствах в сети (s).
Вы также можете использовать групповую политику, intune, управление мобильными устройствами (MDM) или Microsoft Endpoint Manager для настройки и развертывания параметра, как описано в основной теме доступа к управляемым [папкам](controlled-folders.md).

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>Просмотр событий управляемого доступа к папкам в Windows просмотра событий

Следующие события управляемого доступа к папке отображаются в Windows в папке Microsoft/Windows/Защитник Windows/Operational.

Идентификатор события | Описание
-|-
 5007 | Событие при смене параметров
 1124 | Событие доступа к контролируемой управляемой папке
 1123 | Событие доступа к заблокированной управляемой папке

> [!TIP]
> Вы можете настроить подписку [Windows для](/windows/win32/wec/setting-up-a-source-initiated-subscription) централизованного сбора журналов. 

## <a name="customize-protected-folders-and-apps"></a>Настройка защищенных папок и приложений

Во время оценки вы можете добавить в список защищенных папок или разрешить некоторым приложениям изменять файлы.

См. в обзоре Protect important [folders with controlled folder access](controlled-folders.md) for configuring the feature with management tools, including Group Policy, PowerShell, and MDM configuration service providers (CSPs).

## <a name="see-also"></a>См. также

* [Защита важных папок с управляемым доступом к папкам](controlled-folders.md)
* [Microsoft Defender для конечной точки](evaluate-mde.md)
* [Использовать режим аудита](audit-windows-defender.md)
