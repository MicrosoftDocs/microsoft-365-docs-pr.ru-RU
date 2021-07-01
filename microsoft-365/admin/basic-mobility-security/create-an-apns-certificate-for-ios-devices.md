---
title: Создание сертификата APN для устройств с iOS
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
description: Управление устройствами iOS в базовой мобильности и безопасности.
ms.openlocfilehash: 84f3589593ef26325397f5b6e90d5b21662d2352
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228247"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>Создание сертификата APN для устройств с iOS

Чтобы управлять устройствами iOS, такими как iPads и iPhone в Basic Mobility and Security, создайте сертификат APNs.

1. Во входе Microsoft 365 с глобальной учетной записью администратора.

2. В браузере введите  <https://protection.office.com/> .

3. Выберите  **управление устройствами для** предотвращения   >  **потери данных** и выберите сертификат **APNs для устройств iOS.**

4. На странице Apple Push Notification Certificate Параметры выберите **Далее**.

5. Выберите Скачайте CSR-файл и сохраните запрос на подписание сертификата где-нибудь на вашем компьютере, который вы запомните. Выберите  **Далее**.

6. На странице Создание сертификата APNs:

    1. Выберите портал APNS Apple, чтобы открыть портал push-сертификатов Apple.

    2. Sign in with an Apple ID.

       > [!IMPORTANT]
       > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. Выберите  **Создать сертификат и** принять условия   использования.

    4. Просмотрите запрос на подписание сертификата, загруженный на компьютер с Microsoft 365, и выберите **Upload**.

       Скачайте на компьютер сертификат APNs, созданный порталом push-сертификатов Apple.

       > [!TIP]
       > If you're having trouble downloading the certificate, refresh your browser.

7. Возвращайся к Microsoft 365 и выберите **Далее,** чтобы попасть на страницу Upload     **ANS.**  

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. Выберите  **Готово**.

Чтобы завершить настройку, перейдите к Центру & безопасности >управления  ****   >  ****   >  **** устройствами.
