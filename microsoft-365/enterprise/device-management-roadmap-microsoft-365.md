---
title: План управления устройствами для Microsoft 365
keywords: Microsoft 365, Microsoft 365 для предприятий, документация по Microsoft 365, управление мобильными устройствами, Intune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 08/10/2020
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
description: План по настройкам управления устройствами для Microsoft 365.
ms.openlocfilehash: 79be47d6bc83c124f2203866986e06181a1f7f3d
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749543"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>План управления устройствами для Microsoft 365

Microsoft 365 для предприятий включает функции для управления устройствами и их приложениями в организации. Управление мобильными устройствами помогает защитить ресурсы организации.

Существует два варианта управления устройствами:

- [Microsoft Intune](#microsoft-intune)
- [Basic Mobility + Security](#basic-mobility-and-security)

## <a name="microsoft-intune"></a>Microsoft Intune

Microsoft Intune можно использовать для управления доступом к организации с помощью управления мобильными устройствами или мобильных приложений. Управление мобильными устройствами происходит, когда пользователи "регистрировать" свои устройства в Intune. После регистрации устройство является управляемым; таким образом, она может получать политики, правила и параметры вашей организации. Например, вы можете установить определенные приложения, создать политику паролей, установить VPN-подключение и много другое.

Пользователи с личными устройствами могут не захоть зарегистрироваться на своих устройствах или управляться с помощью Intune и политик вашей организации. Однако вам все равно необходимо защитить ресурсы и данные организации. В этом сценарии вы можете защитить свои приложения с помощью управления мобильными приложениями. Например, можно использовать политику управления мобильными приложениями, которая требует, чтобы пользователь ввести ПИН-код при доступе к SharePoint Online на устройстве.

Вы также определите, как вы собираетесь управлять личными устройствами и устройствами, которые принадлежат организации. Вам может потребоваться по-разному обрабатывать устройства в зависимости от их использования.

## <a name="basic-mobility-and-security"></a>Basic Mobility + Security

Эта возможность встроена в Microsoft 365 и помогает защитить мобильные устройства пользователей, такие как iPhone, iPad, Android и телефоны с Windows, а также управлять ими. Вы можете создавать политики безопасности устройств и управлять ими, удаленно очищать устройства и просматривать подробные отчеты об устройствах.

## <a name="choose-between-the-two-options"></a>Выбор между двумя вариантами

Чтобы лучше оценить оптимальный вариант управления устройствами, см. "Выбор [между Basic Mobility Security и Intune".](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune)

В зависимости от оценки управляющего устройствами вы можете начать с:

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)
- [Basic Mobility + Security](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a>Рекомендации по доступу для удостоверений и устройств

Корпорация Майкрософт предоставляет набор рекомендаций для [удостоверений и доступа к устройству](../security/office-365-security/microsoft-365-policies-configurations.md) с целью обеспечения безопасности и эффективности работы сотрудников. Для доступа к устройствам используйте рекомендации и параметры, указанные в этих статьях:

- [Необходимые компоненты](../security/office-365-security/identity-access-prerequisites.md)
- [Основные политики доступа для удостоверений и устройств](../security/office-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Управление устройствами в Contoso для Microsoft 365

Сведения о развертывании инфраструктуры управления мобильными устройствами с помощью облачных служб Microsoft 365 вымышленной, но представительной мультиязычной компанией см. в руководстве по управлению мобильными устройствами [для Contoso.](contoso-mdm.md)
