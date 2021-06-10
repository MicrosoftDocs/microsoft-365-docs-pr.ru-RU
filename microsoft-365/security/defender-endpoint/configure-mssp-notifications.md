---
title: Настройка уведомлений оповещений, отправленных в MSSPs
description: Настройка уведомлений оповещений, отправленных в MSSPs
keywords: поставщик управляемых служб безопасности, mssp, настройка, интеграция
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 67f7081e72b5ecc8bdb077f0537cf0cf92df38b9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166057"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a>Настройка уведомлений оповещений, отправленных в MSSPs 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)


>[!NOTE]
>Этот шаг может быть сделан клиентом MSSP или MSSP. MsSPs должны быть предоставлены соответствующие разрешения для настройки этого от имени клиента MSSP.

После предоставления доступа к порталу можно создать правила оповещения, чтобы сообщения электронной почты отправлялись в MSSPs при создания оповещений, связанных с клиентом, и удовлетворены заданные условия.

 
Дополнительные сведения см. в [сообщении Create rules for alert notifications.](configure-email-notifications.md#create-rules-for-alert-notifications)
 

Эти флажки должны быть проверены:
- **Включайте имя организации** . Имя клиента будет добавлено в уведомления электронной почты
- **Включайте** ссылку портала для клиента - URL-адрес ссылки оповещения будет иметь определенный параметр клиента (tid=target_tenant_id), который позволяет прямой доступ к целевому порталу клиента.


## <a name="related-topics"></a>Статьи по теме
- [Предоставление MSSP доступа к порталу](grant-mssp-access.md)
- [Получение доступа к порталу клиентов MSSP](access-mssp-portal.md)
- [Получение оповещений от владельца клиента](fetch-alerts-mssp.md)
