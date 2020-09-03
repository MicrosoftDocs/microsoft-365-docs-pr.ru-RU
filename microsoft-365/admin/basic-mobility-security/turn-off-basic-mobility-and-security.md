---
title: Отключение базовых функций мобильной связи и безопасности
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Удалите группы или политики, чтобы отключить основные функции мобильной работы и обеспечения безопасности.
ms.openlocfilehash: 54f78cc30e5259ad5244ce3a8fc6d0f46a395d7c
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337038"
---
# <a name="turn-off-basic-mobility-and-security"></a>Отключение базовых функций мобильной связи и безопасности

Чтобы эффективно отключить базовую мобильность и безопасность, удалите группы людей, определенные группами безопасности в политиках управления устройствами, или удалите сами политики.

- Удалите группы пользователей, удалив группы безопасности пользователей из созданных политик устройств.
    
- Отключите базовые мобильность и безопасность для всех, удалив все базовые политики устройств для мобильных устройств и безопасности.
    
Эти параметры изменяют базовую поддержку мобильных устройств и обеспечение безопасности для устройств в вашей организации. К сожалению, после настройки вы не можете просто отписаться на базовые мобильные решения и безопасность. 

>[!IMPORTANT]
>Учитывайте влияние на устройства пользователей при удалении групп безопасности пользователей из политик или удалении самих политик. Например, профили электронной почты и кэшированные сообщения электронной почты могут быть удалены в зависимости от устройства. Для получения дополнительных сведений о  [том, что происходит при удалении политики или удалении пользователя из политики?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Удаление групп безопасности пользователей из базовых политик мобильных устройств и устройств безопасности

1. В браузере введите:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Выберите политику устройства и нажмите **изменить политику**. 

3. На странице  **развертывание** нажмите   кнопку **Удалить**.
    
4. В разделе  **группы**выберите группу безопасности.

5. Нажмите кнопку  **Удалить**, а затем выберите **сохранить**.
    

## <a name="remove-basic-mobility-and-security-device-policies"></a>Удаление основных политик мобильных устройств и устройств безопасности

1.  В браузере введите:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) . 

2.  Выберите политику устройства, а затем выберите команду  **удалить политику**.
    
3.  В диалоговом окне предупреждения нажмите **кнопку Да**.

>[!NOTE] 
>Дополнительные действия, которые необходимо выполнить, чтобы разблокировать устройства, если их устройства находятся в заблокированном состоянии, обратитесь к разделу запись блога [Удаление управления доступом с мобильного устройства для Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).