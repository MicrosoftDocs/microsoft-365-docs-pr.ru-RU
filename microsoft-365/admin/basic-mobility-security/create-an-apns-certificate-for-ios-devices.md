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
ms.openlocfilehash: 85baef2defa79255d560f848e57120353fd4fa2e
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877084"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="8f1f4-103">Создание сертификата APN для устройств с iOS</span><span class="sxs-lookup"><span data-stu-id="8f1f4-103">Create an APNs certificate for iOS devices</span></span>

<span data-ttu-id="8f1f4-104">Чтобы управлять устройствами iOS, такими как iPads и iPhone в Basic Mobility and Security, создайте сертификат APNs.</span><span class="sxs-lookup"><span data-stu-id="8f1f4-104">To manage iOS devices such as iPads and iPhones in Basic Mobility and Security, create an APNs certificate.</span></span>

1. <span data-ttu-id="8f1f4-105">Во входе Microsoft 365 с глобальной учетной записью администратора.</span><span class="sxs-lookup"><span data-stu-id="8f1f4-105">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="8f1f4-106">В браузере введите  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="8f1f4-106">In your browser, type [https://protection.office.com](https://protection.office.com/).</span></span>

3. <span data-ttu-id="8f1f4-107">Выберите  **управление устройствами для** предотвращения   >  **потери данных** и выберите сертификат **APNs для устройств iOS.**</span><span class="sxs-lookup"><span data-stu-id="8f1f4-107">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>

4. <span data-ttu-id="8f1f4-108">На странице Apple Push Notification Certificate Параметры выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8f1f4-108">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>

5. <span data-ttu-id="8f1f4-109">Выберите Скачайте CSR-файл и сохраните запрос на подписание сертификата где-нибудь на вашем компьютере, который вы запомните.</span><span class="sxs-lookup"><span data-stu-id="8f1f4-109">Select Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="8f1f4-110">Выберите  **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8f1f4-110">Select  **Next**.</span></span>

6. <span data-ttu-id="8f1f4-111">На странице Создание сертификата APNs:</span><span class="sxs-lookup"><span data-stu-id="8f1f4-111">On the Create an APNs certificate page:</span></span>  

    1. <span data-ttu-id="8f1f4-112">Выберите портал APNS Apple, чтобы открыть портал push-сертификатов Apple.</span><span class="sxs-lookup"><span data-stu-id="8f1f4-112">Select  Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>

    2. <span data-ttu-id="8f1f4-113">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="8f1f4-113">Sign in with an Apple ID.</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="8f1f4-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="8f1f4-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    3. <span data-ttu-id="8f1f4-116">Выберите  **Создать сертификат и** принять условия   использования.</span><span class="sxs-lookup"><span data-stu-id="8f1f4-116">Select  **Create a Certificate**  and accept the Terms of Use.</span></span>

    4. <span data-ttu-id="8f1f4-117">Просмотрите запрос на подписание сертификата, загруженный на компьютер с Microsoft 365, и выберите **Upload**.</span><span class="sxs-lookup"><span data-stu-id="8f1f4-117">Browse to the certificate signing request you downloaded to your computer from Microsoft 365, and select **Upload**.</span></span>

        <span data-ttu-id="8f1f4-118">Скачайте на компьютер сертификат APNs, созданный порталом push-сертификатов Apple.</span><span class="sxs-lookup"><span data-stu-id="8f1f4-118">Download the APNs certificate created by the Apple Push Certificate Portal to your computer.</span></span>

       >[!TIP]
       ><span data-ttu-id="8f1f4-119">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="8f1f4-119">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="8f1f4-120">Возвращайся к Microsoft 365 и выберите **Далее,** чтобы попасть на страницу Upload     **ANS.**  </span><span class="sxs-lookup"><span data-stu-id="8f1f4-120">Go back to Microsoft 365, and select **Next**  to get to the  **Upload APNS certificate** page.</span></span>

8. <span data-ttu-id="8f1f4-121"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="8f1f4-121">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>

9. <span data-ttu-id="8f1f4-122">Выберите  **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8f1f4-122">Select  **Finish**.</span></span>

<span data-ttu-id="8f1f4-123">Чтобы завершить настройку, перейдите к Центру & безопасности >управления  \*\*\*\*   >  \*\*\*\*   >  \*\*\*\* устройствами.</span><span class="sxs-lookup"><span data-stu-id="8f1f4-123">To complete setup, go back to the Security & Compliance Center > **Security policies** > **Device management** > **Manage settings**.</span></span>
