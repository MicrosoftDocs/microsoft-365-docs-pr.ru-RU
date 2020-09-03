---
title: Создание сертификата APNs для устройств с iOS
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
description: Управление устройствами iOS в базовых мобильность и безопасности.
ms.openlocfilehash: 8b41c1c6c891a5d6cb98a6a381c65aa0310a1761
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337061"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>Создание сертификата APNs для устройств с iOS

Для управления устройствами iOS, такими как iPad и iPhone, в базовой мобильности и безопасности создайте сертификат APNs.

1. Войдите в Microsoft 365 с помощью учетной записи глобального администратора.
    
2. В браузере введите  [https://protection.office.com](https://protection.office.com/) .
    
3. Выберите  **Data loss prevention**   >  **Управление устройствами**защиты от потери данных и выберите **сертификат APNs для устройств с iOS**.    

4. На странице Параметры сертификата push-уведомлений Apple нажмите кнопку **Далее**.
    
5. Выберите Загрузить файл CSR и сохранить запрос подписи сертификата в любом месте на вашем компьютере, который вы забудете запомнить. Нажмите кнопку  **Далее**.
    
6. На странице Создание сертификата APNs:  

    1. Выберите портал Apple APNS, чтобы открыть портал Apple Push Certificate.
    
    2. Sign in with an Apple ID.   

    >[!IMPORTANT]
    >Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. Выберите  **создать сертификат**   и принять условия использования.
    
    4. Перейдите к запросу подписи сертификата, загруженному на компьютер, из Microsoft 365 и нажмите кнопку **Отправить**.
    
        Скачайте сертификат APNs, созданный порталом сертификатов Apple Push, на компьютер.
    
       >[!TIP]
       >If you're having trouble downloading the certificate, refresh your browser.

7. Вернитесь в Microsoft 365 и нажмите кнопку **Далее** ,   чтобы перейти на страницу  **отправка сертификата APNs**   .
    
8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.
    
9. Нажмите кнопку  **Готово**.
    
Чтобы завершить установку, вернитесь в центр безопасности & соответствия требованиям > **политиками безопасности**управление   >  **Device management**   >  **параметрами**.
