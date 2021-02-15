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
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="cef0b-103">Создание сертификата APN для устройств с iOS</span><span class="sxs-lookup"><span data-stu-id="cef0b-103">Create an APNs certificate for iOS devices</span></span>

<span data-ttu-id="cef0b-104">Для управления устройствами iOS, такими как iPad и iPhone, в basic Mobility and Security создайте сертификат APNs.</span><span class="sxs-lookup"><span data-stu-id="cef0b-104">To manage iOS devices such as iPads and iPhones in Basic Mobility and Security, create an APNs certificate.</span></span>

1. <span data-ttu-id="cef0b-105">Во sign in to Microsoft 365 with your global admin account.</span><span class="sxs-lookup"><span data-stu-id="cef0b-105">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="cef0b-106">Введите в браузере  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="cef0b-106">In your browser, type [https://protection.office.com](https://protection.office.com/).</span></span>

3. <span data-ttu-id="cef0b-107">Выберите  **управление устройствами** защиты от потери   >  **данных** и выберите **сертификат APNs для устройств с iOS.**</span><span class="sxs-lookup"><span data-stu-id="cef0b-107">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>

4. <span data-ttu-id="cef0b-108">На странице "Параметры сертификата push-уведомлений Apple" нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="cef0b-108">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>

5. <span data-ttu-id="cef0b-109">Выберите "Скачать CSR-файл" и сохраните запрос подписи сертификата в нужное место на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="cef0b-109">Select Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="cef0b-110">Выберите  **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="cef0b-110">Select  **Next**.</span></span>

6. <span data-ttu-id="cef0b-111">На странице "Создание сертификата APNs":</span><span class="sxs-lookup"><span data-stu-id="cef0b-111">On the Create an APNs certificate page:</span></span>  

    1. <span data-ttu-id="cef0b-112">Выберите портал Apple APNS, чтобы открыть портал push-сертификатов Apple.</span><span class="sxs-lookup"><span data-stu-id="cef0b-112">Select  Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>

    2. <span data-ttu-id="cef0b-113">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="cef0b-113">Sign in with an Apple ID.</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="cef0b-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="cef0b-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    3. <span data-ttu-id="cef0b-116">Выберите  **"Создать сертификат"**   и примите условия использования.</span><span class="sxs-lookup"><span data-stu-id="cef0b-116">Select  **Create a Certificate**  and accept the Terms of Use.</span></span>

    4. <span data-ttu-id="cef0b-117">Перейдите к запросу подписи сертификата, загруженного на компьютер из Microsoft 365, и выберите **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="cef0b-117">Browse to the certificate signing request you downloaded to your computer from Microsoft 365, and select **Upload**.</span></span>

        <span data-ttu-id="cef0b-118">Скачайте сертификат APNs, созданный порталом apple Push Certificate Portal, на свой компьютер.</span><span class="sxs-lookup"><span data-stu-id="cef0b-118">Download the APNs certificate created by the Apple Push Certificate Portal to your computer.</span></span>

       >[!TIP]
       ><span data-ttu-id="cef0b-119">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="cef0b-119">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="cef0b-120">Перейдите в Microsoft 365  и выберите "Далее", чтобы перейти на страницу отправки     **сертификата APNS.**  </span><span class="sxs-lookup"><span data-stu-id="cef0b-120">Go back to Microsoft 365, and select **Next**  to get to the  **Upload APNS certificate** page.</span></span>

8. <span data-ttu-id="cef0b-121"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="cef0b-121">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>

9. <span data-ttu-id="cef0b-122">Select  **Finish**.</span><span class="sxs-lookup"><span data-stu-id="cef0b-122">Select  **Finish**.</span></span>

<span data-ttu-id="cef0b-123">Чтобы завершить настройку, снова перейдите в Центр безопасности  \*\*\*\*& соответствия >политики безопасности управления   >  \*\*\*\*   >  **устройствами.**</span><span class="sxs-lookup"><span data-stu-id="cef0b-123">To complete setup, go back to the Security & Compliance Center > **Security policies** > **Device management** > **Manage settings**.</span></span>
