---
title: Выполнение внутренних операций администратора
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
description: Узнайте, как подтвердить, что электронная почта и владение доменом берется через неуправляемый клиент в Microsoft 365
ms.openlocfilehash: 9c1d98616b10737553060bcbad62df9b3b4c0c9a
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814472"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="74d0d-103">Выполнение внутренних операций администратора</span><span class="sxs-lookup"><span data-stu-id="74d0d-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="74d0d-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="74d0d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="74d0d-105">Если вы администратор и хотите перейти на неуправляемый клиент, созданный при самостоятельной регистрации пользователя, это можно сделать с помощью внутреннего администратора.</span><span class="sxs-lookup"><span data-stu-id="74d0d-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="74d0d-106">Самостоятельной регистрацией в любой облачной службе, использующей Azure AD, добавит пользователя в неуправляемый или «тений» каталог Azure AD и создаст неуправляемый клиент.</span><span class="sxs-lookup"><span data-stu-id="74d0d-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="74d0d-107">Неуправляемый клиент является каталогом без глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="74d0d-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="74d0d-108">Чтобы определить, является ли клиент управляемым или неуправляемым, см. [статью Определение типа клиента.](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)</span><span class="sxs-lookup"><span data-stu-id="74d0d-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="74d0d-109">Шаг 1. Проверка электронного адреса</span><span class="sxs-lookup"><span data-stu-id="74d0d-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="74d0d-110">Если в клиенте включена функция самостоятельного обслуживания, пользователи могут самостоятельно подписываться на бесплатные службы, такие как Power BI.</span><span class="sxs-lookup"><span data-stu-id="74d0d-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="74d0d-111">В этом разделе предполагается, что подписка на самостоятельного создания самостоятельного пользователя создала неуправляемый клиент, который вы хотите принять в качестве администратора. На первом этапе вы создаете контекст пользователя в неуправляемом клиенте с помощью Power BI, чтобы проиллюстрировать путь переключения администратора.</span><span class="sxs-lookup"><span data-stu-id="74d0d-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="74d0d-112">Чтобы подписаться на Power BI, перейдите на сайт [Power BI](https://powerbi.com) и выберите пункт **"Начать**бесплатную  >  **бесплатную пробную версию"** (в поле "Общий доступ с Помощью Power BI Pro").</span><span class="sxs-lookup"><span data-stu-id="74d0d-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="74d0d-113">Для входа в систему используемое доменное имя вашей организации `powerbiadmin@contoso.com` (например, это).</span><span class="sxs-lookup"><span data-stu-id="74d0d-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="74d0d-114">Если ваша учетная запись уже используется, войдите в систему с помощью текущего пароля.</span><span class="sxs-lookup"><span data-stu-id="74d0d-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="74d0d-115">Проверьте адрес электронной почты **на наличие кода проверки** и введите код для проверки электронного адреса.</span><span class="sxs-lookup"><span data-stu-id="74d0d-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="74d0d-116">Шаг 2. Создание новой учетной записи</span><span class="sxs-lookup"><span data-stu-id="74d0d-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="74d0d-117">При вводе кода проверки вы увидите страницу, на которой можно создать учетную запись.</span><span class="sxs-lookup"><span data-stu-id="74d0d-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="74d0d-118">Укажите нужную учетную запись в полях имени пользователя и пароля, а затем нажмите кнопку **"Пуск".**</span><span class="sxs-lookup"><span data-stu-id="74d0d-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="74d0d-119">Шаг 3. Проверка владения доменом и получение прав администратора</span><span class="sxs-lookup"><span data-stu-id="74d0d-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="74d0d-120">**Откроется мастер настройки** администратора.</span><span class="sxs-lookup"><span data-stu-id="74d0d-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="74d0d-121">Если он не запускается, найдите плитку **"Администратор"** и выберите ее.</span><span class="sxs-lookup"><span data-stu-id="74d0d-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="74d0d-122">Выберите **"Да", я хочу бы администратором.**</span><span class="sxs-lookup"><span data-stu-id="74d0d-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="74d0d-123">Удостоверьтесь, что домен, которым вы хотите сделать, добавив запись TXT на сайте регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="74d0d-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="74d0d-124">Мастер предоставит запись TXT, которую нужно добавить, а также предоставит ссылку на веб-сайт вашего регистратора и ссылку на пошаговые инструкции.</span><span class="sxs-lookup"><span data-stu-id="74d0d-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="74d0d-125">Добавив запись TXT на сайт регистратора, вернитесь в мастер и нажмите кнопку **"Окей", добавлена запись.**</span><span class="sxs-lookup"><span data-stu-id="74d0d-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="74d0d-126">Удаление теневого клиента не влияет на существующие сведения или службы.</span><span class="sxs-lookup"><span data-stu-id="74d0d-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="74d0d-127">Однако, если любой пользователь в домене занес с вошел в службы, для которых требуется лицензия, вам будет предоставлено разрешение на приобретение лицензий для них в процессе получения роли администратора.</span><span class="sxs-lookup"><span data-stu-id="74d0d-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="74d0d-128">После завершения процесса настройки администраторов вы сможете покупать и удалить лицензии.</span><span class="sxs-lookup"><span data-stu-id="74d0d-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="74d0d-129">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="74d0d-129">Related articles</span></span>

<span data-ttu-id="74d0d-130">YouTube: [3 шага для получения данных ИТ-администратора в отношении Power BI и Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span><span class="sxs-lookup"><span data-stu-id="74d0d-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span></span>

[<span data-ttu-id="74d0d-131">Потенциал администратора в Azure AD</span><span class="sxs-lookup"><span data-stu-id="74d0d-131">Admin takeover in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[<span data-ttu-id="74d0d-132">Использование функции самостоятельной регистрации в организации</span><span class="sxs-lookup"><span data-stu-id="74d0d-132">Using self-service sign up in your organization</span></span>](self-service-sign-up.md)
  
[<span data-ttu-id="74d0d-133">Роль администратора службы Power BI</span><span class="sxs-lookup"><span data-stu-id="74d0d-133">Understanding the Power BI service administrator role</span></span>](https://docs.microsoft.com/power-bi/service-admin-role)

