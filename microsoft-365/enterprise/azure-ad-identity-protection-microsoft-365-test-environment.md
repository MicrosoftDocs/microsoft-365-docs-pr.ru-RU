---
title: Защита идентификации Azure AD для тестовой среды Microsoft 365 для предприятий
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Настройте защиту идентификации Azure AD и проанализируйте текущие учетные записи в тестовой среде Microsoft 365 для предприятий.
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487712"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="3a91a-103">Защита идентификации Azure AD для тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="3a91a-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="3a91a-104">*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для корпоративных тестовых сред.*</span><span class="sxs-lookup"><span data-stu-id="3a91a-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="3a91a-105">Вы можете использовать защиту идентификации Azure Active Directory (Azure AD) для обнаружения потенциальных уязвимостей, влияющих на удостоверения вашей организации, настройки автоматизированных ответов и изучения инцидентов.</span><span class="sxs-lookup"><span data-stu-id="3a91a-105">You can use Azure Active Directory (Azure AD) Identity Protection to detect potential vulnerabilities that affect your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="3a91a-106">В этой статье описывается, как использовать защиту идентификации Azure AD для просмотра анализа учетных записей тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="3a91a-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="3a91a-107">Настройка защиты идентификации Azure AD в тестовой среде Microsoft 365 для предприятий состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="3a91a-107">Setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="3a91a-108">Этап 1. Создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="3a91a-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="3a91a-109">Этап 2. Использование защиты идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="3a91a-109">Phase 2: Use Azure AD Identity Protection</span></span>](#phase-2-use-azure-ad-identity-protection)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="3a91a-111">Чтобы получить визуальную карту со всеми статьями в руководстве по лаборатории тестирования Microsoft 365 для предприятий, перейдите в стек руководств по лаборатории тестирования [Microsoft 365 для предприятий.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="3a91a-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="3a91a-112">Этап 1. Создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="3a91a-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="3a91a-113">Если вы хотите протестировать защиту идентификации Azure AD в облегченом режиме с минимальными требованиями, следуйте инструкциям в базовой конфигурации с облегченной [базой.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="3a91a-113">If you want to only test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="3a91a-114">Если вы хотите протестировать защиту идентификации Azure AD на имитированном предприятии, следуйте инструкциям в сквозной [проверке подлинности.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="3a91a-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3a91a-115">Для тестирования защиты идентификации Azure AD не требуется тестовая среда имитации предприятия, которая включает имитированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="3a91a-115">Testing Azure AD Identity Protection doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="3a91a-116">Она предоставляется здесь в качестве варианта, чтобы вы могли протестировать защиту идентификации Azure AD и поэкспериментировать с ней в типичной для организации среде.</span><span class="sxs-lookup"><span data-stu-id="3a91a-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="3a91a-117">Этап 2. Использование защиты идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="3a91a-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="3a91a-118">Откройте частный экземпляр браузера и во sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span><span class="sxs-lookup"><span data-stu-id="3a91a-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="3a91a-119">На портале Azure введите защиту **удостоверений** в поле поиска, а затем выберите **"Защита идентификации Azure AD".**</span><span class="sxs-lookup"><span data-stu-id="3a91a-119">In the Azure portal, type **identity protection** in the search box, and then select **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="3a91a-120">В области **"Защита удостоверений — обзор"** выберите каждый отчет, чтобы узнать, что в нем сообщается.</span><span class="sxs-lookup"><span data-stu-id="3a91a-120">In the **Identity Protection - Overview** blade, select each report to see what it's reporting.</span></span>
4. <span data-ttu-id="3a91a-121">Under **Notify**, select **Users at risk detected alerts**.</span><span class="sxs-lookup"><span data-stu-id="3a91a-121">Under **Notify**, select **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="3a91a-122">В области **оповещений** об обнаруженных пользователях с риском выберите **"Средний".**</span><span class="sxs-lookup"><span data-stu-id="3a91a-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="3a91a-123">Для **сообщений электронной почты отправляются** следующим пользователям, **выберите** "Включено" и убедитесь, что учетная запись глобального администратора включена в список выбранных участников.</span><span class="sxs-lookup"><span data-stu-id="3a91a-123">For **Emails are sent to the following users**, select **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="3a91a-124">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3a91a-124">Select **Save**.</span></span>

<span data-ttu-id="3a91a-125">В **области "Защита"** выберите различные отделы, чтобы узнать, как их настроить.</span><span class="sxs-lookup"><span data-stu-id="3a91a-125">Under **Protect**, select various polices to see how to configure them.</span></span> <span data-ttu-id="3a91a-126">Если вы создаете и активируете политику, убедитесь, что она не блокирует доступ для всех пользователей или вы не сможете войти в систему.</span><span class="sxs-lookup"><span data-stu-id="3a91a-126">If you create and activate a policy, make sure that it's not blocking access for all users, or you might not be able to sign in.</span></span> <span data-ttu-id="3a91a-127">Чтобы предотвратить это, исключить определенные учетные записи пользователей, например глобальных администраторов.</span><span class="sxs-lookup"><span data-stu-id="3a91a-127">To prevent this, exclude specific user accounts, such as global admins.</span></span>

<span data-ttu-id="3a91a-128">Для дальнейшего тестирования и экспериментов [см. моделирование событий риска.](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)</span><span class="sxs-lookup"><span data-stu-id="3a91a-128">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="3a91a-129">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="3a91a-129">Next step</span></span>

<span data-ttu-id="3a91a-130">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="3a91a-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a91a-131">См. также</span><span class="sxs-lookup"><span data-stu-id="3a91a-131">See also</span></span>

[<span data-ttu-id="3a91a-132">План удостоверений</span><span class="sxs-lookup"><span data-stu-id="3a91a-132">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="3a91a-133">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="3a91a-133">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="3a91a-134">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="3a91a-134">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="3a91a-135">Документация по Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="3a91a-135">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
