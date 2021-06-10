---
title: Стратегия управления устройством в Microsoft 365
keywords: Microsoft 365, Microsoft 365 корпоративной, Microsoft 365 документации, управления мобильными устройствами, Intune
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
description: Дорожная карта для организации управления устройствами для Microsoft 365.
ms.openlocfilehash: ec284a96fc8e7285f89e8a909b76c782b4469ce1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051464"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Стратегия управления устройством в Microsoft 365

Microsoft 365 для предприятия включает функции, которые помогают управлять устройствами и их приложениями в организации. Управление мобильными устройствами помогает обеспечить безопасность и защиту ресурсов организации.

Существует два варианта управления устройствами:

- [Microsoft Intune](#microsoft-intune)
- [Basic Mobility + Security](#basic-mobility-and-security)

## <a name="microsoft-intune"></a>Microsoft Intune

Вы можете использовать Microsoft Intune для управления доступом к организации с помощью управления мобильными устройствами или управления мобильными приложениями. Управление мобильными устройствами — это когда пользователи "регистрировать" свои устройства в Intune. После регистрации устройства это управляемое устройство; поэтому он может получать политики, правила и параметры вашей организации. Например, можно установить определенные приложения, создать политику паролей, установить VPN-подключение и другие.

Пользователи со своими личными устройствами могут не захоть зарегистрироваться на своих устройствах или управляться политиками Intune и вашей организации. Но все равно необходимо защитить ресурсы и данные организации. В этом сценарии можно защитить приложения с помощью управления мобильными приложениями. Например, можно использовать политику управления мобильными приложениями, которая требует от пользователя ввести ПИН-код при доступе SharePoint в Интернете на устройстве.

Вы также определите, как управлять личными устройствами и устройствами, которые принадлежат организации. Может потребоваться по-разному относиться к устройствам в зависимости от их использования.

## <a name="basic-mobility-and-security"></a>Basic Mobility + Security

Это встроено в Microsoft 365 и помогает обеспечить безопасность мобильных устройств пользователей, таких как iPhone, iPad, Android и Windows телефонов. Вы можете создавать политики безопасности устройств и управлять ими, удаленно очищать устройства и просматривать подробные отчеты об устройствах.

## <a name="choose-between-the-two-options"></a>Выбор между двумя вариантами

Чтобы лучше оценить, какой вариант управления устройствами лучше всего для вас, см. в справке Выберите между [Basic Mobility Security и Intune.](/office365/securitycompliance/choose-between-mdm-and-intune)

На основе вашей оценки начинайте управлять устройствами с помощью:

- [Intune](/mem/intune/fundamentals/planning-guide)
- [Basic Mobility + Security](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a>Рекомендации по доступу для удостоверений и устройств

Корпорация Майкрософт предоставляет набор рекомендаций для [удостоверений и доступа к устройству](../security/defender-365-security/microsoft-365-policies-configurations.md) с целью обеспечения безопасности и эффективности работы сотрудников. Для доступа к устройству используйте рекомендации и параметры в этих статьях:

- [Необходимые компоненты](../security/defender-365-security/identity-access-prerequisites.md)
- [Основные политики доступа для удостоверений и устройств](../security/defender-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Как Contoso сделал управление устройствами для Microsoft 365

Сведения о том, как вымышленный, но представительный многонациональный бизнес развернул инфраструктуру управления мобильными устройствами Microsoft 365 облачными службами, см. в книге Управление мобильными устройствами [для Contoso.](contoso-mdm.md)