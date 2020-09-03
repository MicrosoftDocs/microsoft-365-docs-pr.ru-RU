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
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="04a25-103">Создание сертификата APNs для устройств с iOS</span><span class="sxs-lookup"><span data-stu-id="04a25-103">Create an APNs certificate for iOS devices</span></span>

<span data-ttu-id="04a25-104">Для управления устройствами iOS, такими как iPad и iPhone, в базовой мобильности и безопасности создайте сертификат APNs.</span><span class="sxs-lookup"><span data-stu-id="04a25-104">To manage iOS devices such as iPads and iPhones in Basic Mobility and Security, create an APNs certificate.</span></span>

1. <span data-ttu-id="04a25-105">Войдите в Microsoft 365 с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="04a25-105">Sign in to Microsoft 365 with your global admin account.</span></span>
    
2. <span data-ttu-id="04a25-106">В браузере введите  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="04a25-106">In your browser, type [https://protection.office.com](https://protection.office.com/).</span></span>
    
3. <span data-ttu-id="04a25-107">Выберите  **Data loss prevention**   >  **Управление устройствами**защиты от потери данных и выберите **сертификат APNs для устройств с iOS**.</span><span class="sxs-lookup"><span data-stu-id="04a25-107">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>    

4. <span data-ttu-id="04a25-108">На странице Параметры сертификата push-уведомлений Apple нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="04a25-108">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>
    
5. <span data-ttu-id="04a25-109">Выберите Загрузить файл CSR и сохранить запрос подписи сертификата в любом месте на вашем компьютере, который вы забудете запомнить.</span><span class="sxs-lookup"><span data-stu-id="04a25-109">Select Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="04a25-110">Нажмите кнопку  **Далее**.</span><span class="sxs-lookup"><span data-stu-id="04a25-110">Select  **Next**.</span></span>
    
6. <span data-ttu-id="04a25-111">На странице Создание сертификата APNs:</span><span class="sxs-lookup"><span data-stu-id="04a25-111">On the Create an APNs certificate page:</span></span>  

    1. <span data-ttu-id="04a25-112">Выберите портал Apple APNS, чтобы открыть портал Apple Push Certificate.</span><span class="sxs-lookup"><span data-stu-id="04a25-112">Select  Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>
    
    2. <span data-ttu-id="04a25-113">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="04a25-113">Sign in with an Apple ID.</span></span>   

    >[!IMPORTANT]
    ><span data-ttu-id="04a25-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="04a25-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    3. <span data-ttu-id="04a25-116">Выберите  **создать сертификат**   и принять условия использования.</span><span class="sxs-lookup"><span data-stu-id="04a25-116">Select  **Create a Certificate**  and accept the Terms of Use.</span></span>
    
    4. <span data-ttu-id="04a25-117">Перейдите к запросу подписи сертификата, загруженному на компьютер, из Microsoft 365 и нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="04a25-117">Browse to the certificate signing request you downloaded to your computer from Microsoft 365, and select **Upload**.</span></span>
    
        <span data-ttu-id="04a25-118">Скачайте сертификат APNs, созданный порталом сертификатов Apple Push, на компьютер.</span><span class="sxs-lookup"><span data-stu-id="04a25-118">Download the APNs certificate created by the Apple Push Certificate Portal to your computer.</span></span>
    
       >[!TIP]
       ><span data-ttu-id="04a25-119">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="04a25-119">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="04a25-120">Вернитесь в Microsoft 365 и нажмите кнопку **Далее** ,   чтобы перейти на страницу  **отправка сертификата APNs**   .</span><span class="sxs-lookup"><span data-stu-id="04a25-120">Go back to Microsoft 365, and select **Next**  to get to the  **Upload APNS certificate** page.</span></span>
    
8. <span data-ttu-id="04a25-121"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="04a25-121">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>
    
9. <span data-ttu-id="04a25-122">Нажмите кнопку  **Готово**.</span><span class="sxs-lookup"><span data-stu-id="04a25-122">Select  **Finish**.</span></span>
    
<span data-ttu-id="04a25-123">Чтобы завершить установку, вернитесь в центр безопасности & соответствия требованиям > **политиками безопасности**управление   >  **Device management**   >  **параметрами**.</span><span class="sxs-lookup"><span data-stu-id="04a25-123">To complete setup, go back to the Security & Compliance Center > **Security policies** > **Device management** > **Manage settings**.</span></span>
