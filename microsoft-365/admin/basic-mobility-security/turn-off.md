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
description: Удалите группы или политики, чтобы отключить базовые функции мобильности и безопасности.
ms.openlocfilehash: 0786ac8ebd190b9af3211c211cc6db2ea9e0ea48
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876844"
---
# <a name="turn-off-basic-mobility-and-security"></a>Отключение Basic Mobility + Security

Чтобы эффективно отключить функцию Basic Mobility and Security, вы удаляете группы людей, определенные группами безопасности, из политик управления устройствами или сами политики.

- Удалите группы пользователей, удалите группы безопасности пользователей из созданных вами политик устройств.

- Отключать базовую мобильность и безопасность для всех, удалив все политики устройств Basic Mobility and Security.

Эти параметры удаляют базовое обеспечение мобильности и безопасности для устройств в организации. К сожалению, вы не можете просто "отопрестить" базовую мобильность и безопасность после ее настроки. 

>[!IMPORTANT]
>Следует помнить о влиянии на устройства пользователей, когда вы удаляете группы безопасности пользователей из политик или сами политики. Например, профили электронной почты и кэшные сообщения электронной почты могут быть удалены в зависимости от устройства. Дополнительные сведения см. в сведениях о том, что происходит при удалении политики или  [удалении пользователя из политики?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Удаление групп безопасности пользователей из политик базовой мобильности и безопасности устройств

1. В браузере:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Выберите политику устройств и выберите политику **редактирования.** 

3. На  **** странице   "Развертывание" выберите **"Удалить".**

4. В  **группе** выберите группу безопасности.

5. Выберите  **"Удалить"** и **"Сохранить".**

## <a name="remove-basic-mobility-and-security-device-policies"></a>Удаление базовых политик мобильных устройств и устройств безопасности

1.  В браузере:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) . 

2.  Выберите политику устройств, а затем выберите  **"Удалить политику".**
    
3.  В диалоговом окне предупреждения выберите **"Да".**

>[!NOTE]
>Дополнительные действия по разблокировать устройства, если устройства организации по-прежнему находятся в заблокированном состоянии, см. в записи блога "Удаление контроля доступа из управления мобильными устройствами [для Office 365".](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)
