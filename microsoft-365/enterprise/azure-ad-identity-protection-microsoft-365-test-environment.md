---
title: Защита удостоверений Azure AD для тестовой среды Microsoft 365 корпоративный
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
description: Настройка защиты идентификации Azure AD и анализ текущих учетных записей в тестовой среде Microsoft 365 Enterprise.
ms.openlocfilehash: 3f3740e42c7ec909f44a3c761dfc743359b3f030
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633647"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b9489-103">Защита удостоверений Azure AD для тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="b9489-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="b9489-104">*Это руководство по лаборатории тестирования можно использовать только для тестовых сред Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="b9489-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="b9489-105">Защита удостоверений Azure Active Directory (Azure AD) позволяет обнаруживать потенциальные уязвимости, затрагивающие удостоверения вашей организации, настраивать автоматические ответы и изучению инцидентов.</span><span class="sxs-lookup"><span data-stu-id="b9489-105">Azure Active Directory (Azure AD) Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="b9489-106">В этой статье описано, как использовать защиту удостоверений Azure AD для просмотра анализа учетных записей тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="b9489-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="b9489-107">Настройка защиты идентификации Azure AD в тестовой среде Microsoft 365 Enterprise состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="b9489-107">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="b9489-108">Создайте среду тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="b9489-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="b9489-109">Используйте защиту удостоверений Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b9489-109">Use Azure AD Identity Protection.</span></span>

![Руководства по лаборатории тестирования для Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="b9489-111">Щелкните [здесь](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="b9489-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b9489-112">Этап 1. Создание собственной тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="b9489-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="b9489-113">Если вы хотите просто протестировать защиту удостоверения Azure AD в упрощенном виде с минимальными требованиями, следуйте инструкциям, приведенным в разделе [облегченная базовая конфигурация](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="b9489-113">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="b9489-114">Если вы хотите протестировать защиту удостоверения Azure AD в имитируемой Организации, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="b9489-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b9489-115">Для тестирования защиты удостоверений Azure AD не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="b9489-115">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="b9489-116">Он предоставляется в качестве варианта, чтобы можно было протестировать защиту удостоверения Azure AD и поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="b9489-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="b9489-117">Этап 2: использование системы защиты удостоверений Azure AD</span><span class="sxs-lookup"><span data-stu-id="b9489-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="b9489-118">Откройте частный экземпляр браузера и войдите на портал Azure, [https://portal.azure.com](https://portal.azure.com) используя учетную запись глобального администратора вашей тестовой среды Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b9489-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="b9489-119">На портале Azure введите **Защита удостоверений** в поле поиска, а затем щелкните элемент **Защита удостоверений Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="b9489-119">In the Azure portal, type **identity protection** in the search box, and then click **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="b9489-120">В колонке **Защита удостоверений — обзор** выберите каждый из отчетов, чтобы увидеть их отчеты.</span><span class="sxs-lookup"><span data-stu-id="b9489-120">In the **Identity Protection - Overview** blade, click on each of the reports to see what they are reporting.</span></span>
4. <span data-ttu-id="b9489-121">В разделе **уведомите**щелкните **Пользователи под угрозой риск обнаруженные оповещения**.</span><span class="sxs-lookup"><span data-stu-id="b9489-121">Under **Notify**, click **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="b9489-122">В области **оповещения пользователей на обнаруженных угрозах** выберите **средний**.</span><span class="sxs-lookup"><span data-stu-id="b9489-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="b9489-123">Для **отправки сообщений электронной почты следующим пользователям**выберите **включен** и убедитесь, что ваша учетная запись глобального администратора входит в список выбранных участников.</span><span class="sxs-lookup"><span data-stu-id="b9489-123">For **Emails are sent to the following users**, click **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="b9489-124">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b9489-124">Click **Save**.</span></span>

<span data-ttu-id="b9489-125">Выберите другие политики в разделе **Защита** , чтобы узнать, как их настроить.</span><span class="sxs-lookup"><span data-stu-id="b9489-125">Click through the different policies under **Protect** to see how to configure them.</span></span> <span data-ttu-id="b9489-126">Если вы создаете и активируете политику, убедитесь, что она не блокирует доступ к слишком широкому объему условий, или вы не можете войти в систему, даже в качестве глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="b9489-126">If you create and activate a policy, make sure it is not blocking access for too wide a scope of conditions, or you might not be able to sign in, even as the global admin.</span></span>

<span data-ttu-id="b9489-127">Дополнительные сведения о тестировании и экспериментах приведены в разделе [моделирование событий риска](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="b9489-127">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="b9489-128">Чтобы получить сведения и ссылки на странице "Защита удостоверений Azure AD" в рабочей среде, ознакомьтесь со статьей " [Защита от кражи учетных данных](identity-secure-user-sign-ins.md#identity-ident-prot) " на этапе идентификации.</span><span class="sxs-lookup"><span data-stu-id="b9489-128">See the [Protect against credential compromise](identity-secure-user-sign-ins.md#identity-ident-prot) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="b9489-129">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="b9489-129">Next step</span></span>

<span data-ttu-id="b9489-130">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="b9489-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9489-131">См. также</span><span class="sxs-lookup"><span data-stu-id="b9489-131">See also</span></span>

[<span data-ttu-id="b9489-132">Шаг 2. Идентификация</span><span class="sxs-lookup"><span data-stu-id="b9489-132">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="b9489-133">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="b9489-133">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b9489-134">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="b9489-134">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b9489-135">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="b9489-135">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
