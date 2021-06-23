---
title: Используйте Microsoft Defender для Office 365 совместно с Microsoft Defender для конечной точки
f1.keywords:
- NOCSH
keywords: интеграция, Microsoft Defender, Microsoft Defender для конечной точки
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/10/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Используйте Microsoft Defender для Office 365 совместно с Microsoft Defender для конечной точки, чтобы получить более подробные сведения об угрозах в отношении устройств и контента электронной почты.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fed3a04a7a699b4689cd9d6d9d335a8ba51d2fd8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083384"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Используйте Microsoft Defender для Office 365 совместно с Microsoft Defender для конечной точки

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender для Office 365](defender-for-office-365.md) можно настроить для работы с [Microsoft Defender для конечной точки](/windows/security/threat-protection).

Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки может помочь группе безопасности отслеживать и быстро принимать меры, если устройства пользователей находятся под угрозой. Например, после включения интеграции группа операций безопасности сможет видеть устройства, которые потенциально затронуты обнаруженным сообщением электронной почты, а также количество последних оповещений для этих устройств в Microsoft Defender для Endpoint.

На следующем изображении изображено, как выглядит вкладка **Devices** при включенной интеграции Microsoft Defender для конечной точки:

![Когда включен Microsoft Defender для конечной точки, вы можете увидеть список устройств с оповещениями.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

В этом примере можно увидеть, что получатели обнаруженного сообщения электронной почты имеют четыре устройства и одно имеет оповещение. Щелкнув ссылку для устройства, откроет свою страницу на портале Microsoft 365 Defender [(ранее](../defender-endpoint/microsoft-defender-security-center.md) центр безопасности Microsoft Defender).

> [!TIP]
> Портал Microsoft 365 Defender заменяет Центр безопасности в Microsoft Defender. См. [в Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).

## <a name="requirements"></a>Requirements

- Ваша организация должна иметь Microsoft Defender для Office 365 (или Office 365 E5) и Microsoft Defender для конечной точки.

- Вы должны быть глобальным администратором или иметь роль администратора безопасности (например, администратора безопасности), назначенную в Microsoft 365. Дополнительные сведения см. в статье [Разрешения на портале Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

- Вы должны иметь доступ к Explorer (или обнаружения [в режиме реального времени).](threat-explorer.md)

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки

Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки настроена как в Defender для конечной точки, так и в Defender для Office 365.

1. В качестве глобального администратора или администратора безопасности откройте портал Microsoft 365 Defender () и перейдите в обозреватель <https://security.microsoft.com> **&** \> **электронной почты.** Чтобы перейти непосредственно на **страницу Explorer,** используйте <https://security.microsoft.com/threatexplorer> .

2. На странице **Explorer** в правом верхнем углу экрана нажмите **кнопку MDE Параметры**.

3. В **вылете подключения к** конечной точке Microsoft **Defender для конечной** точки включите Подключение microsoft Defender для конечной точки ![ (Toggle on), а затем нажмите кнопку Закрыть значок ](../../media/scc-toggle-on.png) ![ ](../../media/m365-cc-sc-close-icon.png) **Закрыть**.

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="Подключение к MDE":::

4. Возвращаясь в области навигации, выберите **Параметры**. На странице **Параметры** выберите **конечные точки**

5. На **открываемой странице Конечные** точки выберите **расширенные функции.**

6. Прокрутите **вниз Office 365 подключения к службе сведении** об угрозах и включите его ![ (чтобы ](../../media/scc-toggle-on.png) включить).

   По завершению нажмите кнопку **Сохранить предпочтения.**

## <a name="related-articles"></a>Статьи по теме

[Возможности расследования и реагирования на угрозы в Office 365](office-365-ti.md)

[Microsoft Defender для Office 365](defender-for-office-365.md)

[Microsoft Defender для конечной точки](/windows/security/threat-protection)
