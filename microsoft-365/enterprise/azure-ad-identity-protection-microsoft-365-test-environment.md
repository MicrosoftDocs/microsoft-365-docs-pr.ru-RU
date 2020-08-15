---
title: Защита удостоверений Azure AD для тестовой среды Microsoft 365 для предприятий
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
description: Настройка защиты идентификации Azure AD и анализ текущих учетных записей в тестовой среде Microsoft 365 для предприятия.
ms.openlocfilehash: bd1e7560e978b13d24e9e93a99a2567adca95c75
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694994"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e26f2-103">Защита удостоверений Azure AD для тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="e26f2-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e26f2-104">*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для тестовых сред предприятия.*</span><span class="sxs-lookup"><span data-stu-id="e26f2-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="e26f2-105">Защита удостоверений Azure Active Directory (Azure AD) позволяет обнаруживать потенциальные уязвимости, затрагивающие удостоверения вашей организации, настраивать автоматические ответы и изучению инцидентов.</span><span class="sxs-lookup"><span data-stu-id="e26f2-105">Azure Active Directory (Azure AD) Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="e26f2-106">В этой статье описано, как использовать защиту удостоверений Azure AD для просмотра анализа учетных записей тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="e26f2-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="e26f2-107">Настройка защиты идентификации Azure AD в среде тестирования Microsoft 365 для предприятия состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="e26f2-107">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment:</span></span>

1. <span data-ttu-id="e26f2-108">Создайте тестовую среду Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="e26f2-108">Create the Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="e26f2-109">Используйте защиту удостоверений Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e26f2-109">Use Azure AD Identity Protection.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="e26f2-111">Щелкните [здесь](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 для крупных предприятий.</span><span class="sxs-lookup"><span data-stu-id="e26f2-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e26f2-112">Этап 1: создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="e26f2-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e26f2-113">Если вы хотите просто протестировать защиту удостоверения Azure AD в упрощенном виде с минимальными требованиями, следуйте инструкциям, приведенным в разделе [облегченная базовая конфигурация](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="e26f2-113">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="e26f2-114">Если вы хотите протестировать защиту удостоверения Azure AD в имитируемой Организации, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="e26f2-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e26f2-115">Для тестирования защиты удостоверений Azure AD не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="e26f2-115">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="e26f2-116">Он предоставляется в качестве варианта, чтобы можно было протестировать защиту удостоверения Azure AD и поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="e26f2-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="e26f2-117">Этап 2: использование системы защиты удостоверений Azure AD</span><span class="sxs-lookup"><span data-stu-id="e26f2-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="e26f2-118">Откройте частный экземпляр браузера и войдите на портал Azure, [https://portal.azure.com](https://portal.azure.com) используя учетную запись глобального администратора для тестовой среды Microsoft 365 для предприятия.</span><span class="sxs-lookup"><span data-stu-id="e26f2-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="e26f2-119">На портале Azure введите **Защита удостоверений** в поле поиска, а затем щелкните элемент **Защита удостоверений Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="e26f2-119">In the Azure portal, type **identity protection** in the search box, and then click **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="e26f2-120">В колонке **Защита удостоверений — обзор** выберите каждый из отчетов, чтобы увидеть их отчеты.</span><span class="sxs-lookup"><span data-stu-id="e26f2-120">In the **Identity Protection - Overview** blade, click on each of the reports to see what they are reporting.</span></span>
4. <span data-ttu-id="e26f2-121">В разделе **уведомите**щелкните **Пользователи под угрозой риск обнаруженные оповещения**.</span><span class="sxs-lookup"><span data-stu-id="e26f2-121">Under **Notify**, click **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="e26f2-122">В области **оповещения пользователей на обнаруженных угрозах** выберите **средний**.</span><span class="sxs-lookup"><span data-stu-id="e26f2-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="e26f2-123">Для **отправки сообщений электронной почты следующим пользователям**выберите **включен** и убедитесь, что ваша учетная запись глобального администратора входит в список выбранных участников.</span><span class="sxs-lookup"><span data-stu-id="e26f2-123">For **Emails are sent to the following users**, click **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="e26f2-124">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e26f2-124">Click **Save**.</span></span>

<span data-ttu-id="e26f2-125">Выберите другие политики в разделе **Защита** , чтобы узнать, как их настроить.</span><span class="sxs-lookup"><span data-stu-id="e26f2-125">Click through the different policies under **Protect** to see how to configure them.</span></span> <span data-ttu-id="e26f2-126">Если вы создаете и активируете политику, убедитесь, что она не блокирует доступ к слишком широкому объему условий, или вы не можете войти в систему, даже в качестве глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="e26f2-126">If you create and activate a policy, make sure it is not blocking access for too wide a scope of conditions, or you might not be able to sign in, even as the global admin.</span></span>

<span data-ttu-id="e26f2-127">Дополнительные сведения о тестировании и экспериментах приведены в разделе [моделирование событий риска](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="e26f2-127">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="e26f2-128">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="e26f2-128">Next step</span></span>

<span data-ttu-id="e26f2-129">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="e26f2-129">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e26f2-130">См. также</span><span class="sxs-lookup"><span data-stu-id="e26f2-130">See also</span></span>

[<span data-ttu-id="e26f2-131">Схема удостоверений</span><span class="sxs-lookup"><span data-stu-id="e26f2-131">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="e26f2-132">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="e26f2-132">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e26f2-133">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="e26f2-133">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="e26f2-134">Microsoft 365 для корпоративных документов</span><span class="sxs-lookup"><span data-stu-id="e26f2-134">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
