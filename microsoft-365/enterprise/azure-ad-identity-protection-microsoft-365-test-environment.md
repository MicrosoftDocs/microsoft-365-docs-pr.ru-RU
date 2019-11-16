---
title: Защита удостоверений Azure AD для тестовой среды Microsoft 365 корпоративный
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Настройка защиты идентификации Azure AD и анализ текущих учетных записей в тестовой среде Microsoft 365 Enterprise.
ms.openlocfilehash: bc98ebbdd45e06481e2d95687fb4eb8c986533a3
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673245"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4324a-103">Защита удостоверений Azure AD для тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="4324a-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4324a-104">*Это руководство по лаборатории тестирования можно использовать только для тестовых сред Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4324a-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="4324a-105">Защита удостоверений Azure AD позволяет обнаруживать потенциальные уязвимости, затрагивающие удостоверения вашей организации, настраивать автоматические ответы и изучению инцидентов.</span><span class="sxs-lookup"><span data-stu-id="4324a-105">Azure AD Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="4324a-106">В этой статье описывается включение защиты удостоверений Azure AD и Просмотр анализа учетных записей тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="4324a-106">This article describes how to enable Azure AD Identity Protection and view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="4324a-107">Настройка защиты идентификации Azure AD в тестовой среде Microsoft 365 Enterprise состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="4324a-107">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="4324a-108">Создайте среду тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="4324a-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="4324a-109">Включение и использование защиты удостоверений Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4324a-109">Enable and use Azure AD Identity Protection.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="4324a-111">Щелкните [здесь](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="4324a-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4324a-112">Этап 1. Создание собственной тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="4324a-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4324a-113">Если вы хотите просто протестировать защиту удостоверения Azure AD в упрощенном виде с минимальными требованиями, следуйте инструкциям, приведенным в разделе [облегченная базовая конфигурация](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="4324a-113">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="4324a-114">Если вы хотите протестировать защиту удостоверения Azure AD в имитируемой Организации, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="4324a-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4324a-115">Для тестирования защиты удостоверений Azure AD не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="4324a-115">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="4324a-116">Он предоставляется в качестве варианта, чтобы можно было протестировать защиту удостоверения Azure AD и поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="4324a-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a><span data-ttu-id="4324a-117">Этап 2: Включение и использование средства защиты удостоверений Azure AD</span><span class="sxs-lookup"><span data-stu-id="4324a-117">Phase 2: Enable and use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="4324a-118">Откройте частный экземпляр браузера и войдите на портал Azure, [https://portal.azure.com](https://portal.azure.com) используя учетную запись глобального администратора вашей тестовой среды Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4324a-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="4324a-119">На портале Azure выберите **все службы > Marketplace**.</span><span class="sxs-lookup"><span data-stu-id="4324a-119">In the Azure portal, click **All services > Marketplace**.</span></span>
3. <span data-ttu-id="4324a-120">Введите **Azure AD Identity Protection** , а затем щелкните ее.</span><span class="sxs-lookup"><span data-stu-id="4324a-120">Type **Azure AD Identity Protection** and then click it.</span></span>
4. <span data-ttu-id="4324a-121">В колонке **Приступая к работе** щелкните **Встроенная** **Настройка**, нажмите кнопку **закрепить на панели мониторинга**, а затем нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="4324a-121">On the **Getting Started** blade, click **Onboard** under **Settings**, click **Pin to dashboard**, and then click **Create**.</span></span>
5. <span data-ttu-id="4324a-122">На портале Azure выберите на панели мониторинга **защиту удостоверений Azure AD** .</span><span class="sxs-lookup"><span data-stu-id="4324a-122">In the Azure portal, click **Azure AD Identity Protection** on the dashboard.</span></span> 

   <span data-ttu-id="4324a-123">Вы должны увидеть колонку " **Защита удостоверений Azure AD** " с панелью мониторинга.</span><span class="sxs-lookup"><span data-stu-id="4324a-123">You should see an **Azure AD Identity Protection-Overview** blade with a dashboard.</span></span> <span data-ttu-id="4324a-124">Обратите внимание, что в разделе **уязвимости**было определено количество учетных записей пользователей без регистрации многофакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="4324a-124">Under **Vulnerabilities**, notice that it determined the number of user accounts without multi-factor authentication registration.</span></span> <span data-ttu-id="4324a-125">Этот номер зависит от предыдущих руководств по лаборатории тестирования Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4324a-125">This number will vary based on previous Microsoft 365 Enterprise Test Lab Guides that you have done.</span></span>

6. <span data-ttu-id="4324a-126">Щелкните категории **для проверки, чтобы проверить** наличие обнаруженных пользователей или событий.</span><span class="sxs-lookup"><span data-stu-id="4324a-126">Click through the categories for **Investigate** to see if there are any users or events that have been detected.</span></span>

<span data-ttu-id="4324a-127">Дополнительные сведения о тестировании и экспериментах приведены в разделе [моделирование событий риска](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="4324a-127">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="4324a-128">Чтобы получить сведения и ссылки на странице "Защита удостоверений Azure AD" в рабочей среде, ознакомьтесь со статьей " [Защита от кражи учетных данных](identity-secure-user-sign-ins.md#identity-ident-prot) " на этапе идентификации.</span><span class="sxs-lookup"><span data-stu-id="4324a-128">See the [Protect against credential compromise](identity-secure-user-sign-ins.md#identity-ident-prot) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="4324a-129">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="4324a-129">Next step</span></span>

<span data-ttu-id="4324a-130">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="4324a-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4324a-131">См. также</span><span class="sxs-lookup"><span data-stu-id="4324a-131">See also</span></span>

[<span data-ttu-id="4324a-132">Шаг 2. Идентификация</span><span class="sxs-lookup"><span data-stu-id="4324a-132">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="4324a-133">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="4324a-133">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4324a-134">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="4324a-134">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="4324a-135">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="4324a-135">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
