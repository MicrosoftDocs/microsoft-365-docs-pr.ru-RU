---
title: Этап 4. Office 365 профессиональный плюс
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как развернуть инфраструктуру Office 365 профессиональный плюс для Microsoft 365 корпоративный.
ms.openlocfilehash: 2b3ac311863249720a2dc1fba00ead9ebf6ac8e5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066457"
---
# <a name="phase-4-office-365-proplus"></a><span data-ttu-id="40946-103">Этап 4. Office 365 профессиональный плюс</span><span class="sxs-lookup"><span data-stu-id="40946-103">Phase 4: Office 365 ProPlus</span></span>

![Этап 4. Office 365 профессиональный плюс](../media/deploy-foundation-infrastructure/O365proplus_icon.png)

<span data-ttu-id="40946-105">*Этот этап применяется к планам E3 и E5 Microsoft 365 корпоративный и Microsoft 365 для образования.*</span><span class="sxs-lookup"><span data-stu-id="40946-105">*This applies to both the E3 and E5 versions of Microsoft 365 Enterprise and Microsoft 365 Education*</span></span>

<span data-ttu-id="40946-106">В состав Microsoft 365 корпоративный входит Office 365 профессиональный плюс — версия Office, доступная по подписке.</span><span class="sxs-lookup"><span data-stu-id="40946-106">Microsoft 365 Enterprise includes Office 365 ProPlus, the subscription version of Office.</span></span> <span data-ttu-id="40946-107">Как и Office 2019, Office 365 профессиональный плюс включает все приложения Office, устанавливающиеся непосредственно на клиентских устройствах.</span><span class="sxs-lookup"><span data-stu-id="40946-107">Like Office 2019, Office 365 ProPlus includes all the Office applications, and those applications are installed directly on your client devices.</span></span> <span data-ttu-id="40946-108">В отличие от Office 2019, Office 365 профессиональный плюс регулярно обновляется с добавлением новых возможностей и использует модель лицензирования на основе пользователей, позволяющую устанавливать Office на нескольких устройствах.</span><span class="sxs-lookup"><span data-stu-id="40946-108">Unlike Office 2019, Office 365 ProPlus is updated with new features on a regular basis and has a user-based licensing model that allows people to install Office on multiple devices.</span></span> <span data-ttu-id="40946-109">Дополнительные сведения см. в статье [Office 365 профессиональный плюс на предприятии](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span><span class="sxs-lookup"><span data-stu-id="40946-109">For more details, see [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span></span>

<span data-ttu-id="40946-p102">На этом этапе мы развернем Office 365 профессиональный плюс на клиентских устройствах в составе Microsoft 365 корпоративный. Помимо этого руководства, рекомендуем использовать [Microsoft Fastrack](https://fasttrack.microsoft.com/office) для развертывания.</span><span class="sxs-lookup"><span data-stu-id="40946-p102">In this phase, you deploy Office 365 ProPlus to client devices as part of Microsoft 365 Enterprise. In addition to this guidance, we recommend you use [Microsoft Fastrack](https://fasttrack.microsoft.com/office) to help with your deployment.</span></span> 

<span data-ttu-id="40946-112">Если вы уже развернули Office 365 профессиональный плюс, см. [критерии выхода](office365proplus-exit-criteria.md) для этого этапа, чтобы убедиться, что выполнены обязательные условия для Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="40946-112">If you already have Office 365 ProPlus deployed, please see the [exit criteria](office365proplus-exit-criteria.md) for this phase to make sure that it meets the required conditions for Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="40946-113">Для совместного развертывания Windows 10 Корпоративная и Office 365 профессиональный плюс обратитесь к статье [Центр развертывания компьютеров](desktop-deployment-center-home.md).</span><span class="sxs-lookup"><span data-stu-id="40946-113">To deploy both Windows 10 Enterprise and Office 365 ProPlus together, see the [Desktop Deployment Center](desktop-deployment-center-home.md).</span></span>
>

## <a name="step-1-assess-your-environment"></a><span data-ttu-id="40946-114">Шаг 1. Оценка среды</span><span class="sxs-lookup"><span data-stu-id="40946-114">Step 1: Assess your environment</span></span>

<span data-ttu-id="40946-p103">Перед развертыванием Office 365 профессиональный плюс следуйте инструкциям из статьи [Оценка среды и требований для развертывания Office 365 профессиональный плюс](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). Эта оценка включает проверку требований к системе, сведений о клиентских устройствах (например, архитектурах и необходимых языках), требований к лицензированию, сетевых возможностей и совместимости приложений. Эта проверка поможет вам принять ключевые решения в ходе планирования развертывания.</span><span class="sxs-lookup"><span data-stu-id="40946-p103">Before deploying Office 365 ProPlus, follow the guidance in [Assess your environment and requirements for deploying Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). This assessment includes system requirements, details of your client devices (such as architectures and required languages), licensing requirements, network capability, and application compatibility. Completing the assessment will help you make key decisions as part of planning your deployment.</span></span>

## <a name="step-2-plan-your-deployment"></a><span data-ttu-id="40946-118">Действие 2. Планирование развертывания</span><span class="sxs-lookup"><span data-stu-id="40946-118">Step 2: Plan your deployment</span></span>

<span data-ttu-id="40946-p104">После оценки среды следуйте инструкциям из статьи [Планирование развертывания Office 365 профессиональный плюс](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus), чтобы создать план развертывания. Этот план включает следующие решения:</span><span class="sxs-lookup"><span data-stu-id="40946-p104">After assessing your environment, follow the guidance in [Plan your deployment of Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) to create a deployment plan. This plan includes the following decisions:</span></span> 

- <span data-ttu-id="40946-121">способ развертывания Office, в том числе используемое средство (например, Microsoft Endpoint Configuration Manager или средство развертывания Office) и источник, из которого устанавливается Office;</span><span class="sxs-lookup"><span data-stu-id="40946-121">How to deploy Office, including what tool to use (such as Microsoft Endpoint Configuration Manager or the Office Deployment Tool) and where to install Office from</span></span>
- <span data-ttu-id="40946-122">способ управления обновлениями Office;</span><span class="sxs-lookup"><span data-stu-id="40946-122">How to manage updates to Office</span></span>
- <span data-ttu-id="40946-123">используемые каналы обновления (каналы обновления Office определяют, как часто пользователи получают обновления функций своих приложений Office);</span><span class="sxs-lookup"><span data-stu-id="40946-123">Which update channels to use (update channels for Office control how frequently your users receive feature updates to their Office applications)</span></span>
- <span data-ttu-id="40946-124">установочные пакеты и группы развертывания Office, которые требуется использовать, в том числе приложения Office и языки, которые требуется установить для тех или иных пользователей.</span><span class="sxs-lookup"><span data-stu-id="40946-124">The Office installation packages and deployment groups you want to use, including which Office applications and languages should be installed for which users</span></span>

<span data-ttu-id="40946-125">В [статье, посвященной планированию](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus), представлены рекомендации по всем этим вопросам, включая управление развертыванием, управление обновлениями, определение установочных пакетов и создание групп развертывания.</span><span class="sxs-lookup"><span data-stu-id="40946-125">The [planning article](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) includes best practices for all these options, including managing your deployment, managing your updates, defining installation packages, and creating deployment groups.</span></span> 

## <a name="step-3-deploy"></a><span data-ttu-id="40946-126">Действие 3. Развертывание</span><span class="sxs-lookup"><span data-stu-id="40946-126">Step 3: Deploy</span></span>

<span data-ttu-id="40946-127">В соответствии с планом развертывания выберите способ развертывания.</span><span class="sxs-lookup"><span data-stu-id="40946-127">Based on your deployment plan, choose how you want to deploy:</span></span>

- <span data-ttu-id="40946-128">**[Развертывание Office 365 профессиональный плюс с помощью Microsoft Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** управляйте развертыванием с помощью Configuration Manager, загружая и устанавливая Office из точек распространения в сети.</span><span class="sxs-lookup"><span data-stu-id="40946-128">**[Deploy Office 365 ProPlus with Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Manage your deployment with Configuration Manager, and download and deploy Office from distribution points on your network</span></span>

- <span data-ttu-id="40946-129">**[Развертывание Office 365 профессиональный плюс с помощью ODT из облака](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** управляйте развертыванием с помощью ODT, установив Office на клиентских устройствах непосредственно из сети CDN Office</span><span class="sxs-lookup"><span data-stu-id="40946-129">**[Deploy Office 365 ProPlus with the ODT from the cloud](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Manage your deployment with the ODT, and install Office on client devices directly from the Office CDN</span></span>
 
- <span data-ttu-id="40946-130">**[Самостоятельная установка Office 365 профессиональный плюс с портала Office](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** управляйте развертыванием на портале Office. Пользователи будут устанавливать Office на своих клиентских устройствах непосредственно с портала.</span><span class="sxs-lookup"><span data-stu-id="40946-130">**[Self-install Office 365 ProPlus from the Office portal](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** Manage your deployment from the Office portal and have your users install Office on their client devices directly from the portal</span></span>

<span data-ttu-id="40946-p105">Во многих организациях для разных пользователей используются разные варианты. Например, для большинства пользователей развертывание Office может быть выполнено с помощью Configuration Manager, но для небольшая группа сотрудников, которые нечасто подключаются ко внутренней сети, установит Office самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="40946-p105">Many organizations will use a combination of these options for different users. For example, an organization might use Configuration Manager to deploy Office to most of their users, but enable self-install for a small group of workers who are not frequently connected to the internal network.</span></span> 

<span data-ttu-id="40946-p106">Если в вашей организации используется Configuration Manager, рекомендуем выполнить обновление до Current Branch и текущего выпуска. Дополнительные сведения см. в статье [Какую ветвь Configuration Manager следует использовать?](https://docs.microsoft.com/configmgr/core/understand/which-branch-should-i-use)</span><span class="sxs-lookup"><span data-stu-id="40946-p106">If your organization uses Configuration Manager, we recommend upgrading to the Current Branch and updating to the current release. For more details, see [Which branch of Configuration Manager should I use?](https://docs.microsoft.com/configmgr/core/understand/which-branch-should-i-use)</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="40946-135">Как корпорация Майкрософт реализует Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="40946-135">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="40946-136">Узнайте, как эксперты Майкрософт [развертывают обновления для Office 365 профессиональный плюс и управляют ими](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span><span class="sxs-lookup"><span data-stu-id="40946-136">Learn how the experts at Microsoft are [deploying and managing updates for Office 365 ProPlus](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="40946-137">Как корпорация Contoso реализовала Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="40946-137">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="40946-138">См. статью с описанием показательного примера [развертывания Office 365 профессиональный плюс](contoso-o365pp.md) корпорацией Contoso — вымышленной глобальной организацией.</span><span class="sxs-lookup"><span data-stu-id="40946-138">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Office 365 ProPlus](contoso-o365pp.md).</span></span>

![Корпорация Contoso](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="40946-140">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="40946-140">Next step</span></span>

[<span data-ttu-id="40946-141">Условия, при выполнении которых можно считать инфраструктуру Office 365 профессиональный плюс настроенной</span><span class="sxs-lookup"><span data-stu-id="40946-141">Office 365 ProPlus infrastructure exit criteria</span></span>](office365proplus-exit-criteria.md)
