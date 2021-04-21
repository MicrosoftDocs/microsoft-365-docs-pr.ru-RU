---
title: Обнаружение и блокировка потенциально нежелательных приложений с помощью Microsoft Defender для конечной точки на Linux
description: Обнаружение и блокировка потенциально нежелательных приложений (PUA) с помощью Microsoft Defender для конечной точки на Linux.
keywords: Microsoft, defender, atp, linux, pua, pus
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 9631fc2eb1cb791f48f107482474d1bb8e2fd62b
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903862"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-linux"></a>Обнаружение и блокировка потенциально нежелательных приложений с помощью Microsoft Defender для конечной точки на Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Функция защиты потенциально нежелательного приложения (PUA) в Defender for Endpoint для Linux может обнаруживать и блокировать файлы PUA в конечных точках сети.

Эти приложения не считаются вирусами, вредоносными программами или другими типами угроз, но могут выполнять действия в конечных точках, которые отрицательно влияют на их производительность или использование. PUA также может относиться к приложениям, которые считаются плохой репутацией.

Эти приложения могут повысить риск заражения сети вредоносными программами, привести к тому, что выявить вредоносные программы будет сложнее, и могут тратить ИТ-ресурсы на очистку приложений.

## <a name="how-it-works"></a>Принципы работы

Защитник для конечной точки для Linux может обнаруживать и сообщать о файлах PUA. При настройке в режиме блокировки файлы PUA перемещаются в карантин.

Когда puA обнаруживается на конечной точке, Defender for Endpoint для Linux ведет запись инфекции в истории угроз. Историю можно визуализировать на портале Центра безопасности Защитника Майкрософт или с помощью средства `mdatp` командной строки. Имя угрозы будет содержать слово "Application".

## <a name="configure-pua-protection"></a>Настройка защиты PUA

Защита PUA в Defender for Endpoint для Linux может быть настроена одним из следующих способов:

- **Отключено:** защита PUA отключена.
- **Аудит:** файлы PUA сообщаются в журналах продуктов, но не в Центре безопасности Защитника Майкрософт. Запись о заражении не хранится в истории угроз и продукт не будет принимать никаких действий.
- **Блок**: файлы PUA регистрируются в журналах продуктов и в Центре безопасности Защитника Майкрософт. Запись инфекции хранится в истории угроз, и продуктом принимаются меры.

>[!WARNING]
>По умолчанию защита PUA настраивается в **режиме аудита.**

Можно настроить обработку файлов PUA из командной строки или консоли управления.

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>Используйте средство командной строки для настройки защиты PUA:

В Терминале выполните следующую команду, чтобы настроить защиту PUA:

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>Используйте консоль управления для настройки защиты PUA:

На предприятии можно настроить защиту PUA с консоли управления, например Puppet или Ansible, аналогично настройке других параметров продукта. Дополнительные сведения см. в разделе [Параметры](linux-preferences.md#threat-type-settings) типа угрозы в статье [Set preferences for Defender for Endpoint for Linux.](linux-preferences.md)

## <a name="related-articles"></a>Статьи по теме

- [Настройка предпочтений для Defender для конечной точки для Linux](linux-preferences.md)
