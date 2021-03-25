---
title: Доступ на клиентский портал Центра безопасности Microsoft Defender MSSP
description: Доступ на клиентский портал Центра безопасности Microsoft Defender MSSP
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
ms.openlocfilehash: 97122decede91e8b4f059b3b66999ac12b300172
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164861"
---
# <a name="access-the-microsoft-defender-security-center-mssp-customer-portal"></a>Доступ на клиентский портал Центра безопасности Microsoft Defender MSSP

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

>Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
>Этот набор действий направлен в направлении MSSP. 

По умолчанию клиенты MSSP имеют доступ к клиенту Центра безопасности Microsoft Defender по следующему URL-адресу: `https://securitycenter.windows.com` .
 

MsSPs, однако, необходимо использовать URL-адрес клиента в следующем формате: для доступа  `https://securitycenter.windows.com?tid=customer_tenant_id` к порталу клиентов MSSP. 

В общем, msSPs необходимо будет добавить в каждый клиент MSSP Azure AD, который они намерены управлять.


Используйте следующие действия, чтобы получить ID клиента MSSP, а затем использовать ID для доступа к URL-адресу клиента:

1. В качестве msSP войдите в Azure AD с учетными данными. 

2. Переключение каталога на клиента MSSP.

3.  Выберите **свойства Azure Active Directory >.** В поле Directory ID вы найдете ИД клиента. 

4. Доступ на клиентский портал MSSP, заменив значение в `customer_tenant_id` следующем URL-адресе: `https://securitycenter.windows.com?tid=customer_tenant_id` .


## <a name="related-topics"></a>Статьи по теме
- [Предоставление доступа MSSP к порталу](grant-mssp-access.md)
- [Настройка уведомлений оповещений](configure-mssp-notifications.md)
- [Извлечение оповещений от клиента-клиента](fetch-alerts-mssp.md)
