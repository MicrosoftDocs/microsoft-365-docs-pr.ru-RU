---
title: Выполнение внутреннего поглощения администратора
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Узнайте, как проверить право собственности на электронную почту и домен, чтобы взять на себя неуправленный клиент, созданный пользователем самообслуживательной регистрации в Microsoft 365.
ms.openlocfilehash: f6378c708e0533c2da2d38bfe5eb8009515423c7
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393851"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="13294-103">Выполнение внутреннего поглощения администратора</span><span class="sxs-lookup"><span data-stu-id="13294-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="13294-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="13294-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="13294-105">Если вы администратор и хотите взять на себя неуправленный клиент, созданный в результате регистрации пользователя самообслуживателя, вы можете сделать это с внутренним захватом администратора.</span><span class="sxs-lookup"><span data-stu-id="13294-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="13294-106">Самообслуживка для любой облачной службы, использующей Azure AD, добавит пользователя в неуправленный или "теневой" каталог Azure AD и создаст неустановляемого клиента.</span><span class="sxs-lookup"><span data-stu-id="13294-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="13294-107">Неуправленный клиент — это каталог без глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="13294-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="13294-108">Чтобы определить, управляется или не управляется клиент, см. введите [определение типа клиента.](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)</span><span class="sxs-lookup"><span data-stu-id="13294-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="13294-109">Шаг 1. Проверка адреса электронной почты</span><span class="sxs-lookup"><span data-stu-id="13294-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="13294-110">Если в клиенте включена самообслужка, пользователи могут самостоятельно подписаться на бесплатные службы, например Power BI.</span><span class="sxs-lookup"><span data-stu-id="13294-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="13294-111">Эти действия предполагают, что подписка на пользователя с самообслуживателем создала неуправленный клиент, который вы хотите взять на себя в качестве администратора. На первом этапе вы создаете пользовательский контекст в неугодном клиенте, используя Power BI для иллюстрации пути поглощения администратора.</span><span class="sxs-lookup"><span data-stu-id="13294-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="13294-112">Чтобы зарегистрироваться для Power BI, перейдите [](https://powerbi.com) на Power BI и выберите бесплатную пробную Power BI Pro Start  >   Free Start.</span><span class="sxs-lookup"><span data-stu-id="13294-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="13294-113">Подпишитесь на учетную запись пользователя, которая использует доменное имя организации `powerbiadmin@contoso.com` (например).</span><span class="sxs-lookup"><span data-stu-id="13294-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="13294-114">Если ваша учетная запись уже используется, впишитесь с помощью текущего пароля.</span><span class="sxs-lookup"><span data-stu-id="13294-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="13294-115">Проверьте электронную почту на код **проверки** и введите код для проверки адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="13294-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="13294-116">Шаг 2. Создание новой учетной записи</span><span class="sxs-lookup"><span data-stu-id="13294-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="13294-117">При вводе кода проверки вы будете доставлены на страницу, на которой можно создать новую учетную запись.</span><span class="sxs-lookup"><span data-stu-id="13294-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="13294-118">Заполните поля имени пользователя и паролей учетной записью, которую вы хотите использовать, а затем выберите **Начните**.</span><span class="sxs-lookup"><span data-stu-id="13294-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="13294-119">Шаг 3. Проверка владения доменом и стать администратором</span><span class="sxs-lookup"><span data-stu-id="13294-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="13294-120">Откроется **мастер "Стань мастером** администратора".</span><span class="sxs-lookup"><span data-stu-id="13294-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="13294-121">Если мастер не затеет, найми плитку **администратора** и выберите ее.</span><span class="sxs-lookup"><span data-stu-id="13294-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="13294-122">Выберите **Да, я хочу быть администратором**.</span><span class="sxs-lookup"><span data-stu-id="13294-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="13294-123">Убедитесь, что вы владеете доменом, который необходимо взять на себя, добавив запись TXT в регистратор домена.</span><span class="sxs-lookup"><span data-stu-id="13294-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="13294-124">Мастер предоставит вам запись TXT для добавления, а также укажет ссылку на веб-сайт регистратора и ссылку на пошаговую инструкцию.</span><span class="sxs-lookup"><span data-stu-id="13294-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="13294-125">После того как вы добавили запись TXT на сайт регистратора, вернись к мастеру и выберите **Окей, я добавил запись**.</span><span class="sxs-lookup"><span data-stu-id="13294-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="13294-126">Принятие на себя теневого клиента не повлияет на существующие сведения или службы.</span><span class="sxs-lookup"><span data-stu-id="13294-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="13294-127">Однако если какие-либо пользователи в домене подписались на службы, для которых требуется лицензия, вам будет предложено приобрести лицензии для них в рамках принятия роли администратора.</span><span class="sxs-lookup"><span data-stu-id="13294-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="13294-128">Вы можете купить или удалить лицензии после завершения процесса установки администратора.</span><span class="sxs-lookup"><span data-stu-id="13294-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-content"></a><span data-ttu-id="13294-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="13294-129">Related content</span></span>

<span data-ttu-id="13294-130">YouTube: [3 действия,](https://www.youtube.com/watch?v=xt5EsrQBZZk) чтобы сделать захват ИТ-администратора для Power BI и Microsoft 365 (видео)</span><span class="sxs-lookup"><span data-stu-id="13294-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk) (video)</span></span>\
<span data-ttu-id="13294-131">[Администрирование в Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (статья)</span><span class="sxs-lookup"><span data-stu-id="13294-131">[Admin takeover in Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (article)</span></span>\
<span data-ttu-id="13294-132">[Использование самообслуживной регистрации в организации](self-service-sign-up.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="13294-132">[Using self-service sign up in your organization](self-service-sign-up.md) (article)</span></span>\
<span data-ttu-id="13294-133">[Понимание роли администратора Power BI службы](/power-bi/service-admin-role) (статья)</span><span class="sxs-lookup"><span data-stu-id="13294-133">[Understanding the Power BI service administrator role](/power-bi/service-admin-role) (article)</span></span>