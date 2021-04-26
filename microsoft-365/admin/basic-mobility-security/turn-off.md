---
title: Отключение Basic Mobility + Security
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
description: Удалите группы или политики, чтобы отключить базовую мобильность и безопасность.
ms.openlocfilehash: 1d81aed01193fb2ba821ebc055958ac6cd8ac382
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023873"
---
# <a name="turn-off-basic-mobility-and-security"></a>Отключение Basic Mobility + Security

Чтобы эффективно отключить базовую мобильность и безопасность, вы удалите группы людей, определенных группами безопасности, из политик управления устройствами или удалите сами политики.

- Удалите группы пользователей, удалите группы безопасности пользователей из созданных политик устройства.

- Отключить базовую мобильность и безопасность для всех, удалив все политики устройств Basic Mobility и Security.

Эти параметры удаляют правоприменители Basic Mobility и Security для устройств в организации. К сожалению, нельзя просто "отсутвить" базовую мобильность и безопасность после ее настройка. 

>[!IMPORTANT]
>Будьте в курсе влияния на устройства пользователей при удалите группы безопасности пользователей из политик или удалите сами политики. Например, профили электронной почты и кэшные сообщения могут быть удалены в зависимости от устройства. Дополнительные сведения см.  [в публикации What happens when you delete a policy or remove a user from the policy?](../../admin/basic-mobility-security/create-device-security-policies.md)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Удаление групп безопасности пользователей из политик устройств Basic Mobility и Security

1. В типе браузера:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Выберите политику устройства и выберите политику **редактирования.** 

3. На странице  **Развертывание**   выберите **Удалить**.

4. В  **группах** выберите группу безопасности.

5. Выберите  **Удалить** и **сохранить**.

## <a name="remove-basic-mobility-and-security-device-policies"></a>Удаление политик устройств с базовой мобильностью и безопасностью

1.  В типе браузера:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) . 

2.  Выберите политику устройства, а затем выберите  **политику Удаления.**
    
3.  В диалоговом окне Предупреждение выберите **Да**.

>[!NOTE]
>Дополнительные действия по разблокировать устройства, если устройства организации по-прежнему находятся в заблокированном состоянии, см. в блоге"Удаление управления доступом из управления мобильными устройствами для [Office 365.](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)
