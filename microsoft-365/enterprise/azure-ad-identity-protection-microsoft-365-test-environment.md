---
title: Azure AD Identity Protection для Microsoft 365 для корпоративной тестовой среды
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
description: Настройка azure AD Identity Protection и анализ текущих учетных записей в Microsoft 365 для корпоративной тестовой среды.
ms.openlocfilehash: 0cb0acf3faee13676573b04178bd6b4d3d36da4d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905348"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="1ef8e-103">Azure AD Identity Protection для Microsoft 365 для корпоративной тестовой среды</span><span class="sxs-lookup"><span data-stu-id="1ef8e-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="1ef8e-104">*Это руководство по тестовой лаборатории можно использовать только для Microsoft 365 для корпоративных тестовых сред.*</span><span class="sxs-lookup"><span data-stu-id="1ef8e-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="1ef8e-105">Вы можете использовать Azure Active Directory (Azure AD) Identity Protection для обнаружения потенциальных уязвимостей, влияющих на удостоверения организации, настройки автоматизированных ответов и расследования инцидентов.</span><span class="sxs-lookup"><span data-stu-id="1ef8e-105">You can use Azure Active Directory (Azure AD) Identity Protection to detect potential vulnerabilities that affect your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="1ef8e-106">В этой статье описывается использование Azure AD Identity Protection для просмотра анализа учетных записей тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="1ef8e-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="1ef8e-107">Настройка azure AD Identity Protection в Microsoft 365 для корпоративной тестовой среды включает два этапа:</span><span class="sxs-lookup"><span data-stu-id="1ef8e-107">Setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="1ef8e-108">Этап 1. Создание microsoft 365 для корпоративной тестовой среды</span><span class="sxs-lookup"><span data-stu-id="1ef8e-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="1ef8e-109">Этап 2. Использование защиты удостоверений Azure AD</span><span class="sxs-lookup"><span data-stu-id="1ef8e-109">Phase 2: Use Azure AD Identity Protection</span></span>](#phase-2-use-azure-ad-identity-protection)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="1ef8e-111">Чтобы получить визуальную карту для всех статей в стеке Руководство по корпоративной тестовой лаборатории Microsoft 365, перейдите в [Microsoft 365 для](../downloads/Microsoft365EnterpriseTLGStack.pdf)корпоративного руководства по тестовой лаборатории.</span><span class="sxs-lookup"><span data-stu-id="1ef8e-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="1ef8e-112">Этап 1. Создание microsoft 365 для корпоративной тестовой среды</span><span class="sxs-lookup"><span data-stu-id="1ef8e-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="1ef8e-113">Если вы хотите протестировать Azure AD Identity Protection в легком режиме с минимальными требованиями, следуйте инструкциям в [базовой конфигурации Lightweight.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="1ef8e-113">If you want to only test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="1ef8e-114">Если вы хотите протестировать Azure AD Identity Protection в смоделированном предприятии, следуйте инструкциям в сквозной [проверке подлинности.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="1ef8e-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1ef8e-115">Тестирование Azure AD Identity Protection не требует имитации тестовой среды предприятия, которая включает смоделированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для леса служб домена Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="1ef8e-115">Testing Azure AD Identity Protection doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="1ef8e-116">Он предоставляется здесь в качестве параметра, чтобы можно было протестировать Azure AD Identity Protection и поэкспериментировать с ним в среде, которая представляет типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="1ef8e-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="1ef8e-117">Этап 2. Использование защиты удостоверений Azure AD</span><span class="sxs-lookup"><span data-stu-id="1ef8e-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="1ef8e-118">Откройте частный экземпляр браузера и вопишитесь на портал Azure с учетной записью глобального администратора [https://portal.azure.com](https://portal.azure.com) microsoft 365 для корпоративной тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="1ef8e-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="1ef8e-119">На портале Azure введите защиту **удостоверений** в поле поиска и выберите **Azure AD Identity Protection**.</span><span class="sxs-lookup"><span data-stu-id="1ef8e-119">In the Azure portal, type **identity protection** in the search box, and then select **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="1ef8e-120">В **лезвии Защита удостоверений — обзор** выберите каждый отчет, чтобы узнать, какие отчеты он представляет.</span><span class="sxs-lookup"><span data-stu-id="1ef8e-120">In the **Identity Protection - Overview** blade, select each report to see what it's reporting.</span></span>
4. <span data-ttu-id="1ef8e-121">В **статье Notify** выберите **оповещений пользователей,** которые находятся в опасности.</span><span class="sxs-lookup"><span data-stu-id="1ef8e-121">Under **Notify**, select **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="1ef8e-122">В области **обнаружения оповещений** о рисках выберите **Medium**.</span><span class="sxs-lookup"><span data-stu-id="1ef8e-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="1ef8e-123">Для **отправки электронных сообщений** следующим пользователям выберите **Включено** и убедитесь, что ваша учетная запись глобального администратора находится в списке выбранных членов.</span><span class="sxs-lookup"><span data-stu-id="1ef8e-123">For **Emails are sent to the following users**, select **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="1ef8e-124">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1ef8e-124">Select **Save**.</span></span>

<span data-ttu-id="1ef8e-125">В **статье Protect** выберите различные полицейские органы, чтобы узнать, как их настроить.</span><span class="sxs-lookup"><span data-stu-id="1ef8e-125">Under **Protect**, select various polices to see how to configure them.</span></span> <span data-ttu-id="1ef8e-126">Если вы создаете и активируете политику, убедитесь, что она не блокирует доступ для всех пользователей, или вы не сможете войти.</span><span class="sxs-lookup"><span data-stu-id="1ef8e-126">If you create and activate a policy, make sure that it's not blocking access for all users, or you might not be able to sign in.</span></span> <span data-ttu-id="1ef8e-127">Чтобы предотвратить это, исключить определенные учетные записи пользователей, например глобальные администраторы.</span><span class="sxs-lookup"><span data-stu-id="1ef8e-127">To prevent this, exclude specific user accounts, such as global admins.</span></span>

<span data-ttu-id="1ef8e-128">Дополнительные проверки и эксперименты см. в этой ленте [Simulating risk events.](/azure/active-directory/active-directory-identityprotection-playbook)</span><span class="sxs-lookup"><span data-stu-id="1ef8e-128">For further testing and experimentation, see [Simulating risk events](/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="1ef8e-129">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="1ef8e-129">Next step</span></span>

<span data-ttu-id="1ef8e-130">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="1ef8e-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ef8e-131">См. также</span><span class="sxs-lookup"><span data-stu-id="1ef8e-131">See also</span></span>

[<span data-ttu-id="1ef8e-132">Дорожная карта удостоверений</span><span class="sxs-lookup"><span data-stu-id="1ef8e-132">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="1ef8e-133">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="1ef8e-133">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="1ef8e-134">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="1ef8e-134">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="1ef8e-135">Документация по Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="1ef8e-135">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)