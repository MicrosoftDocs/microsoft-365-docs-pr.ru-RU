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
description: Управление устройствами iOS в Basic Mobility and Security.
ms.openlocfilehash: 85baef2defa79255d560f848e57120353fd4fa2e
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877084"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>Создание сертификата APN для устройств с iOS

Для управления устройствами iOS, такими как iPad и iPhone, в basic Mobility and Security создайте сертификат APNs.

1. Во sign in to Microsoft 365 with your global admin account.

2. Введите в браузере  [https://protection.office.com](https://protection.office.com/) .

3. Выберите  **управление устройствами** защиты от потери   >  **данных** и выберите **сертификат APNs для устройств с iOS.**

4. На странице "Параметры сертификата push-уведомлений Apple" нажмите кнопку **"Далее".**

5. Выберите "Скачать CSR-файл" и сохраните запрос подписи сертификата в нужное место на вашем компьютере. Выберите  **"Далее".**

6. На странице "Создание сертификата APNs":  

    1. Выберите портал Apple APNS, чтобы открыть портал push-сертификатов Apple.

    2. Sign in with an Apple ID.

    >[!IMPORTANT]
    >Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. Выберите  **"Создать сертификат"**   и примите условия использования.

    4. Перейдите к запросу подписи сертификата, загруженного на компьютер из Microsoft 365, и выберите **"Отправить".**

        Скачайте сертификат APNs, созданный порталом apple Push Certificate Portal, на свой компьютер.

       >[!TIP]
       >If you're having trouble downloading the certificate, refresh your browser.

7. Перейдите в Microsoft 365  и выберите "Далее", чтобы перейти на страницу отправки     **сертификата APNS.**  

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. Select  **Finish**.

Чтобы завершить настройку, снова перейдите в Центр безопасности  ****& соответствия >политики безопасности управления   >  ****   >  **устройствами.**
