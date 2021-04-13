---
title: Обнаружение и блокировка потенциально нежелательных приложений с помощью ATP Microsoft Defender для Mac
description: Обнаружение и блокировка потенциально нежелательных приложений (PUA) с помощью ATP Microsoft Defender для Mac.
keywords: Microsoft, defender, atp, mac, pua, pus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: cf61c6a501a53ac03d3c4cc28068f7af4c0f88d6
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688109"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-macos"></a>Обнаружение и блокировка потенциально нежелательных приложений с помощью Microsoft Defender для конечной точки на macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


Функция защиты потенциально нежелательного приложения (PUA) в Microsoft Defender для конечной точки на macOS может обнаруживать и блокировать файлы PUA в конечных точках сети.

Эти приложения не считаются вирусами, вредоносными программами или другими типами угроз, но могут выполнять действия в конечных точках, которые отрицательно влияют на их производительность или использование. PUA также может относиться к приложениям, которые считаются плохой репутацией.

Эти приложения могут повысить риск заражения сети вредоносными программами, привести к тому, что выявить вредоносные программы будет сложнее, и могут тратить ИТ-ресурсы на очистку приложений.

## <a name="how-it-works"></a>Принципы работы

Microsoft Defender для конечной точки на macOS может обнаруживать и сообщать о файлах PUA. При настройке в режиме блокировки файлы PUA перемещаются в карантин.

Когда puA обнаруживается на конечной точке, Microsoft Defender для конечной точки на macOS представляет пользователю уведомление, если уведомления не отключены. Имя угрозы будет содержать слово "Application".

## <a name="configure-pua-protection"></a>Настройка защиты PUA

Защита PUA в Microsoft Defender для конечной точки на macOS может быть настроена одним из следующих способов:

- **Отключено:** защита PUA отключена.
- **Аудит:** файлы PUA сообщаются в журналах продуктов, но не в Центре безопасности Защитника Майкрософт. Пользователю не будет представлено уведомление и продукт не будет принимать никаких действий.
- **Блок**: файлы PUA регистрируются в журналах продуктов и в Центре безопасности Защитника Майкрософт. Пользователю представлено уведомление, и продуктом принимаются действия.

>[!WARNING]
>По умолчанию защита PUA настраивается в **режиме аудита.**

Можно настроить обработку файлов PUA из командной строки или консоли управления.

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>Используйте средство командной строки для настройки защиты PUA:

В Терминале выполните следующую команду, чтобы настроить защиту PUA:

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>Используйте консоль управления для настройки защиты PUA:

В вашем предприятии можно настроить защиту PUA с консоли управления, например JAMF или Intune, аналогично настройке других параметров продукта. Дополнительные сведения см. в разделе [Параметры](mac-preferences.md#threat-type-settings) типа угрозы в разделе Настройка предпочтений для Microsoft Defender для конечной точки в [разделе MacOS.](mac-preferences.md)

## <a name="related-topics"></a>Статьи по теме

- [Настройка предпочтений для Microsoft Defender для конечной точки на macOS](mac-preferences.md)
