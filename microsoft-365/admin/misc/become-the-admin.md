---
title: Выполнение внутреннего администратора
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Узнайте, как проверить владение электронной почтой и доменом, чтобы получить неугодный клиент в Microsoft 365
ms.openlocfilehash: 28359908576260218459d13b8c1c1b662b9a2c8f
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658067"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="d7ee9-103">Выполнение внутреннего администратора</span><span class="sxs-lookup"><span data-stu-id="d7ee9-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="d7ee9-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="d7ee9-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="d7ee9-105">Если вы администратор и хотите взять на себя неуправленный клиент, созданный самостоятельной регистрацией пользователей, это можно сделать с помощью внутреннего контроля администратора.</span><span class="sxs-lookup"><span data-stu-id="d7ee9-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="d7ee9-106">При самостоятельной регистрации в любой облачной службе, использующей Azure AD, пользователь будет добавлен в неуправленный или "теневой" каталог Azure AD и создаст неуправленный клиент.</span><span class="sxs-lookup"><span data-stu-id="d7ee9-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="d7ee9-107">Неуправленный клиент — это каталог без глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="d7ee9-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="d7ee9-108">Чтобы определить, управляется ли клиент или он неуправляем, см. определение [типа клиента.](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)</span><span class="sxs-lookup"><span data-stu-id="d7ee9-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="d7ee9-109">Шаг 1. Проверка адреса электронной почты</span><span class="sxs-lookup"><span data-stu-id="d7ee9-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="d7ee9-110">Если в клиенте включена самообслужка, пользователи могут самостоятельно подписаться на бесплатные службы, такие как Power BI.</span><span class="sxs-lookup"><span data-stu-id="d7ee9-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="d7ee9-111">При этом предполагается, что подписка самостоятельного пользователя создала неуправленный клиент, который вы хотите получить от имени администратора. На первом этапе вы создаете контекст пользователя в неугодном клиенте, иллюстрируете путь к перезаверке администратора с помощью Power BI.</span><span class="sxs-lookup"><span data-stu-id="d7ee9-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="d7ee9-112">Чтобы зарегистрироваться в Power BI, перейдите на сайт [Power BI](https://powerbi.com) и выберите **бесплатную** пробную версия start Free Start (в поле "Поделиться  >   с Power BI Pro").</span><span class="sxs-lookup"><span data-stu-id="d7ee9-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="d7ee9-113">Зарегистрив учетную запись пользователя, которая использует доменное имя вашей организации `powerbiadmin@contoso.com` (например, ).</span><span class="sxs-lookup"><span data-stu-id="d7ee9-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="d7ee9-114">Если ваша учетная запись уже используется, во sign in using your current password.</span><span class="sxs-lookup"><span data-stu-id="d7ee9-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="d7ee9-115">Проверьте код проверки **электронной почты** и введите код для проверки адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d7ee9-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="d7ee9-116">Шаг 2. Создание новой учетной записи</span><span class="sxs-lookup"><span data-stu-id="d7ee9-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="d7ee9-117">При вводе кода проверки вы увидите страницу, на которой можно создать новую учетную запись.</span><span class="sxs-lookup"><span data-stu-id="d7ee9-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="d7ee9-118">Заполните поля имени пользователя и пароля учетной записью, которую вы хотите использовать, а затем выберите **"Начните".**</span><span class="sxs-lookup"><span data-stu-id="d7ee9-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="d7ee9-119">Шаг 3. Проверка прав владельца домена и права администратора</span><span class="sxs-lookup"><span data-stu-id="d7ee9-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="d7ee9-120">Откроется **мастер "Стать** администратором".</span><span class="sxs-lookup"><span data-stu-id="d7ee9-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="d7ee9-121">Если мастер не запустится, наберем плитку **"Администратор"** и выберите ее.</span><span class="sxs-lookup"><span data-stu-id="d7ee9-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="d7ee9-122">Выберите **"Да", я хочу быть администратором.**</span><span class="sxs-lookup"><span data-stu-id="d7ee9-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="d7ee9-123">Убедитесь, что вы владеете доменом, который вы хотите получить, добавив запись TXT к регистратору доменных имен.</span><span class="sxs-lookup"><span data-stu-id="d7ee9-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="d7ee9-124">Мастер предоставит вам добавляемую запись TXT, а также ссылку на веб-сайт регистратора и ссылку на пошаговую инструкцию.</span><span class="sxs-lookup"><span data-stu-id="d7ee9-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="d7ee9-125">После того как вы добавили запись TXT на сайт регистратора, вернись к мастеру и выберите "Окей", я **добавил запись.**</span><span class="sxs-lookup"><span data-stu-id="d7ee9-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d7ee9-126">Принятие теневого клиента не повлияет на существующие сведения или службы.</span><span class="sxs-lookup"><span data-stu-id="d7ee9-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="d7ee9-127">Однако если какие-либо пользователи в домене подписались на службы, для которых требуется лицензия, вам будет предложено приобрести лицензии для них в рамках получения роли администратора.</span><span class="sxs-lookup"><span data-stu-id="d7ee9-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="d7ee9-128">Вы можете приобрести или удалить лицензии после завершения процесса настройки администратором.</span><span class="sxs-lookup"><span data-stu-id="d7ee9-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="d7ee9-129">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d7ee9-129">Related articles</span></span>

<span data-ttu-id="d7ee9-130">YouTube: 3 действия для перенастройки ИТ-администратора [для Power BI и Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span><span class="sxs-lookup"><span data-stu-id="d7ee9-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span></span>

[<span data-ttu-id="d7ee9-131">Переудать администратора в Azure AD</span><span class="sxs-lookup"><span data-stu-id="d7ee9-131">Admin takeover in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[<span data-ttu-id="d7ee9-132">Использование функции самостоятельной регистрации в организации</span><span class="sxs-lookup"><span data-stu-id="d7ee9-132">Using self-service sign up in your organization</span></span>](self-service-sign-up.md)
  
[<span data-ttu-id="d7ee9-133">Понимание роли администратора службы Power BI</span><span class="sxs-lookup"><span data-stu-id="d7ee9-133">Understanding the Power BI service administrator role</span></span>](https://docs.microsoft.com/power-bi/service-admin-role)

