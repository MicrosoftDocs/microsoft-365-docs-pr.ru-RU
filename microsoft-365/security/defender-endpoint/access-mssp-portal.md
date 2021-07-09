---
title: Доступ к Microsoft 365 Defender клиентского портала MSSP
description: Доступ к Microsoft 365 Defender клиентского портала MSSP
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
ms.openlocfilehash: 8583b28adecd892ec6875faa934fd7ab08e5db11
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339590"
---
# <a name="access-the-microsoft-365-defender-mssp-customer-portal"></a>Доступ к Microsoft 365 Defender клиентского портала MSSP

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

>Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
>Этот набор действий направлен в направлении MSSP. 

По умолчанию клиенты MSSP имеют доступ к Центр безопасности в Microsoft Defender клиенту по следующему URL-адресу: `https://securitycenter.windows.com` .
 

MsSPs, однако, необходимо использовать URL-адрес клиента в следующем формате: для доступа  `https://securitycenter.windows.com?tid=customer_tenant_id` к порталу клиентов MSSP. 

В общем, msSPs необходимо будет добавить в каждый клиент MSSP Azure AD, который они намерены управлять.


Используйте следующие действия, чтобы получить ID клиента MSSP, а затем использовать ID для доступа к URL-адресу клиента:

1. В качестве msSP войдите в Azure AD с учетными данными. 

2. Переключение каталога на клиента MSSP.

3.  Выберите **Azure Active Directory > свойства**. В поле Directory ID вы найдете ИД клиента. 

4. Доступ на клиентский портал MSSP, заменив значение в `customer_tenant_id` следующем URL-адресе: `https://securitycenter.windows.com?tid=customer_tenant_id` .


## <a name="related-topics"></a>Статьи по теме
- [Предоставление MSSP доступа к порталу](grant-mssp-access.md)
- [Настройка уведомлений оповещений](configure-mssp-notifications.md)
- [Получение оповещений от владельца клиента](fetch-alerts-mssp.md)
