---
title: Защита удостоверений Azure AD для тестовой среды Microsoft 365 корпоративный
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Настройка защиты идентификации Azure AD и анализ текущих учетных записей в тестовой среде Microsoft 365 Enterprise.
ms.openlocfilehash: bdac512f7645bf78c0a9c6bc5f71b35916bc4812
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279098"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="0363f-103">Защита удостоверений Azure AD для тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="0363f-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="0363f-104">Защита удостоверений Azure AD позволяет обнаруживать потенциальные уязвимости, затрагивающие удостоверения вашей организации, настраивать автоматические ответы и изучению инцидентов.</span><span class="sxs-lookup"><span data-stu-id="0363f-104">Azure AD Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="0363f-105">В этой статье описывается включение защиты удостоверений Azure AD и Просмотр анализа учетных записей тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="0363f-105">This article describes how to enable Azure AD Identity Protection and view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="0363f-106">Настройка защиты идентификации Azure AD в тестовой среде Microsoft 365 Enterprise состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="0363f-106">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="0363f-107">Создайте корпоративную тестовую среду Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0363f-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="0363f-108">Включение и использование защиты удостоверений Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0363f-108">Enable and use Azure AD Identity Protection.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="0363f-110">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="0363f-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="0363f-111">Этап 1: создание тестовой среды Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0363f-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="0363f-112">Если вы хотите просто протестировать защиту удостоверения Azure AD в упрощенном виде с минимальными требованиями, следуйте инструкциям, приведенным в разделе [облегченная базовая конфигурация](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="0363f-112">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="0363f-113">Если вы хотите протестировать защиту удостоверения Azure AD в имитируемой Организации, следуйте инструкциям в [сквозной проверке](pass-through-auth-m365-ent-test-environment.md)подлинности.</span><span class="sxs-lookup"><span data-stu-id="0363f-113">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0363f-114">Для тестирования защиты удостоверений Azure AD не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="0363f-114">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="0363f-115">Он предоставляется в качестве варианта, чтобы можно было протестировать защиту удостоверения Azure AD и поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="0363f-115">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a><span data-ttu-id="0363f-116">Этап 2: Включение и использование средства защиты удостоверений Azure AD</span><span class="sxs-lookup"><span data-stu-id="0363f-116">Phase 2: Enable and use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="0363f-117">Откройте частный экземпляр браузера и войдите на портал Azure, [https://portal.azure.com](https://portal.azure.com) используя учетную запись глобального администратора вашей тестовой среды Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="0363f-117">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="0363f-118">На портале Azure выберите **все службы _Гт_ Marketplace**.</span><span class="sxs-lookup"><span data-stu-id="0363f-118">In the Azure portal, click **All services > Marketplace**.</span></span>
3. <span data-ttu-id="0363f-119">Введите **Azure AD Identity Protection** , а затем щелкните ее.</span><span class="sxs-lookup"><span data-stu-id="0363f-119">Type **Azure AD Identity Protection** and then click it.</span></span>
4. <span data-ttu-id="0363f-120">В колонке **приступАя к работе** щелкните Встроенная **Настройка**, нажмите кнопку закрепить \*\*\*\* **на панели мониторинга**, а затем нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="0363f-120">On the **Getting Started** blade, click **Onboard** under **Settings**, click **Pin to dashboard**, and then click **Create**.</span></span>
5. <span data-ttu-id="0363f-121">На портале Azure выберите на панели мониторинга **защиту удостоверенИй Azure AD** .</span><span class="sxs-lookup"><span data-stu-id="0363f-121">In the Azure portal, click **Azure AD Identity Protection** on the dashboard.</span></span> 

   <span data-ttu-id="0363f-122">Вы должны увидеть колонку " **Защита удостоверенИй Azure AD** " с панелью мониторинга.</span><span class="sxs-lookup"><span data-stu-id="0363f-122">You should see an **Azure AD Identity Protection-Overview** blade with a dashboard.</span></span> <span data-ttu-id="0363f-123">Обратите внимание, что в разделе **уязвимости**было определено количество учетных записей пользователей без регистрации многофакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="0363f-123">Under **Vulnerabilities**, notice that it determined the number of user accounts without multi-factor authentication registration.</span></span> <span data-ttu-id="0363f-124">Этот номер зависит от предыдущих руководств по лаборатории тестирования Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="0363f-124">This number will vary based on previous Microsoft 365 Enterprise Test Lab Guides that you have done.</span></span>

6. <span data-ttu-id="0363f-125">Щелкните категории для проверки, \*\*\*\* чтобы проверить наличие обнаруженных пользователей или событий.</span><span class="sxs-lookup"><span data-stu-id="0363f-125">Click through the categories for **Investigate** to see if there are any users or events that have been detected.</span></span>

<span data-ttu-id="0363f-126">Дополнительные сведения о тестировании и экспериментах приведены в разделе [моделирование событий риска](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="0363f-126">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="0363f-127">Чтобы получить сведения и ссылки на странице "Защита удостоверений Azure AD" в рабочей среде, ознакомьтесь со статьей " [Защита от кражи учетных данных](identity-multi-factor-authentication.md#identity-ident-prot) " на этапе идентификации.</span><span class="sxs-lookup"><span data-stu-id="0363f-127">See the [Protect against credential compromise](identity-multi-factor-authentication.md#identity-ident-prot) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="0363f-128">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="0363f-128">Next step</span></span>

<span data-ttu-id="0363f-129">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="0363f-129">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="0363f-130">См. также</span><span class="sxs-lookup"><span data-stu-id="0363f-130">See also</span></span>

[<span data-ttu-id="0363f-131">Шаг 2. Идентификация</span><span class="sxs-lookup"><span data-stu-id="0363f-131">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="0363f-132">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="0363f-132">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="0363f-133">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="0363f-133">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="0363f-134">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="0363f-134">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
