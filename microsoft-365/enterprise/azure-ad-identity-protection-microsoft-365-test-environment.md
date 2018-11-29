---
title: Azure AD защиту для вашего предприятия 365 Microsoft тестовой среды
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Настройка защиты удостоверения Azure AD и анализ текущих учетных записей в тестовой среде Microsoft 365 для предприятия.
ms.openlocfilehash: 165667ad2122839336ef0790ab5661cff53ca32b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870523"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="fe736-103">Azure AD защиту для вашего предприятия 365 Microsoft тестовой среды</span><span class="sxs-lookup"><span data-stu-id="fe736-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="fe736-p101">Azure AD защиту позволяет определить потенциальные, влияющие на удостоверения вашей организации, Настройка автоматических ответов и исследовать происшествия. В этой статье описывается, как включить защиту Azure AD и Просмотр анализа учетные записи тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="fe736-p101">Azure AD Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents. This article describes how to enable Azure AD Identity Protection and view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="fe736-106">Существует два этапа по настройке Azure AD защиту в тестовой среде Microsoft 365 для предприятия.</span><span class="sxs-lookup"><span data-stu-id="fe736-106">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="fe736-107">Создание тестовой среды Microsoft 365 для предприятия.</span><span class="sxs-lookup"><span data-stu-id="fe736-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="fe736-108">Включение и использование Azure AD защиту.</span><span class="sxs-lookup"><span data-stu-id="fe736-108">Enable and use Azure AD Identity Protection.</span></span>

![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="fe736-110">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="fe736-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="fe736-111">Этап 1: Создание масштабирование тестовой среды Microsoft 365 для предприятия</span><span class="sxs-lookup"><span data-stu-id="fe736-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="fe736-112">Если необходимо проверить Azure AD защиту в облегченный путь с минимальным требованиям, следуйте инструкциям в [упрощенной базовой конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="fe736-112">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="fe736-113">Если вы хотите проверить Azure AD защиту в имитации enterprise, следуйте инструкциям в [сквозная проверка подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="fe736-113">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="fe736-p102">Тестирование защиту Azure AD не требует тестовой среды имитации предприятия, включающая имитации интрасети, подключенных к Интернету и синхронизации каталогов для леса Windows Server AD. Предоставляется здесь как вариант, чтобы проверить Azure AD защиту и экспериментировать с его в среде, которая представляет типичное организации.</span><span class="sxs-lookup"><span data-stu-id="fe736-p102">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a><span data-ttu-id="fe736-116">Этап 2: Включение и использование защиты удостоверения Azure AD</span><span class="sxs-lookup"><span data-stu-id="fe736-116">Phase 2: Enable and use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="fe736-117">Откройте закрытый экземпляр браузера и войдите в портал Azure в [https://portal.azure.com](https://portal.azure.com) с учетной записью глобального администратора из тестовой среды Microsoft 365 для предприятия.</span><span class="sxs-lookup"><span data-stu-id="fe736-117">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="fe736-118">На портале Azure щелкните **всех служб > Marketplace**.</span><span class="sxs-lookup"><span data-stu-id="fe736-118">In the Azure portal, click **All services > Marketplace**.</span></span>
3. <span data-ttu-id="fe736-119">Введите **Azure AD защиту** и нажмите кнопку.</span><span class="sxs-lookup"><span data-stu-id="fe736-119">Type **Azure AD Identity Protection** and then click it.</span></span>
4. <span data-ttu-id="fe736-120">На blade **Приступая к работе** нажмите кнопку **Onboard** в разделе **Параметры**, выберите команду **прикрепить к панели мониторинга**и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="fe736-120">On the **Getting Started** blade, click **Onboard** under **Settings**, click **Pin to dashboard**, and then click **Create**.</span></span>
5. <span data-ttu-id="fe736-121">На портале Azure щелкните **Azure AD защиту** на панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="fe736-121">In the Azure portal, click **Azure AD Identity Protection** on the dashboard.</span></span> 

   <span data-ttu-id="fe736-p103">Вы должны увидеть blade **Azure AD удостоверения защиты — Общие сведения о** панели мониторинга. В разделе **уязвимые места системы**Обратите внимание на то, что его определить число учетных записей пользователей без регистрации многофакторной проверки подлинности. Это число зависит от предыдущих Microsoft 365 Enterprise руководствах по лаборатории тестирования, необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="fe736-p103">You should see an **Azure AD Identity Protection-Overview** blade with a dashboard. Under **Vulnerabilities**, notice that it determined the number of user accounts without multi-factor authentication registration. This number will vary based on previous Microsoft 365 Enterprise Test Lab Guides that you have done.</span></span>

6. <span data-ttu-id="fe736-125">Нажмите кнопку по категориям для **Проверить** изучить, если все пользователи или события, которые были обнаружены.</span><span class="sxs-lookup"><span data-stu-id="fe736-125">Click through the categories for **Investigate** to see if there are any users or events that have been detected.</span></span>

<span data-ttu-id="fe736-126">Для дальнейшего тестирования и экспериментов просмотра [событий риска Simulating](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="fe736-126">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="fe736-127">См [защитить с учетными данными безопасности](identity-azure-ad-identity-protection.md) на этапе Identity сведения и ссылки на развертывание Azure AD защиту в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="fe736-127">See the [Protect against credential compromise](identity-azure-ad-identity-protection.md) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="fe736-128">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="fe736-128">Next step</span></span>

<span data-ttu-id="fe736-129">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="fe736-129">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe736-130">См. также</span><span class="sxs-lookup"><span data-stu-id="fe736-130">See also</span></span>

[<span data-ttu-id="fe736-131">Этап 2. Идентификация</span><span class="sxs-lookup"><span data-stu-id="fe736-131">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="fe736-132">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="fe736-132">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="fe736-133">Развертывание Microsoft 365 для предприятия</span><span class="sxs-lookup"><span data-stu-id="fe736-133">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="fe736-134">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="fe736-134">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
