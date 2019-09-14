---
title: Этап 4. Office 365 профессиональный плюс
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/29/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как развернуть инфраструктуру Office 365 профессиональный плюс для Microsoft 365 корпоративный.
ms.openlocfilehash: f20435edc4cdc675d0308774eb493a67723054f4
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982770"
---
# <a name="phase-4-office-365-proplus"></a><span data-ttu-id="53a38-103">Этап 4. Office 365 профессиональный плюс</span><span class="sxs-lookup"><span data-stu-id="53a38-103">Phase 4: Office 365 ProPlus</span></span>

![](./media/deploy-foundation-infrastructure/O365proplus_icon.png)

<span data-ttu-id="53a38-104">*Этот этап применяется к планам E3 и E5 Microsoft 365 корпоративный и Microsoft 365 для образования.*</span><span class="sxs-lookup"><span data-stu-id="53a38-104">*This applies to both the E3 and E5 versions of Microsoft 365 Enterprise and Microsoft 365 Education*</span></span>

<span data-ttu-id="53a38-p101">Microsoft 365 корпоративный включает Office 365 профессиональный плюс — предоставляемую по подписке версию Office. Как и Office 2016, Office 365 профессиональный плюс включает все приложения Office, устанавливаемые непосредственно на клиентских устройствах. В отличие от Office 2016, в Office 365 профессиональный плюс регулярно добавляются новые функции и используется модель лицензирования на основе пользователей, позволяющая им устанавливать Office на 5 устройствах. Дополнительные сведения см. в статье [Office 365 профессиональный плюс на предприятии](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span><span class="sxs-lookup"><span data-stu-id="53a38-p101">Microsoft 365 Enterprise includes Office 365 ProPlus, the subscription version of Office. Like Office 2016, Office 365 ProPlus includes all the Office applications, and those applications are installed directly on your client devices. Unlike Office 2016, Office 365 ProPlus is updated with new features on a regular basis and has a user-based licensing model that allows people to install Office on up to 5 devices. For more details, see [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span></span>

<span data-ttu-id="53a38-p102">На этом этапе мы развернем Office 365 профессиональный плюс на клиентских устройствах в составе Microsoft 365 корпоративный. Помимо этого руководства, рекомендуем использовать [Microsoft Fastrack](https://fasttrack.microsoft.com/office) для развертывания.</span><span class="sxs-lookup"><span data-stu-id="53a38-p102">In this phase, you deploy Office 365 ProPlus to client devices as part of Microsoft 365 Enterprise. In addition to this guidance, we recommend you use [Microsoft Fastrack](https://fasttrack.microsoft.com/office) to help with your deployment.</span></span> 

<span data-ttu-id="53a38-111">Если вы уже развернули Office 365 профессиональный плюс, см. [критерии выхода](office365proplus-exit-criteria.md) для этого этапа, чтобы убедиться, что выполнены обязательные условия для Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="53a38-111">If you already have Office 365 ProPlus deployed, please see the [exit criteria](office365proplus-exit-criteria.md) for this phase to make sure that it meets the required conditions for Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="53a38-112">Для совместного развертывания Windows 10 Корпоративная и Office 365 профессиональный плюс обратитесь к статье [Центр развертывания компьютеров](desktop-deployment-center-home.md).</span><span class="sxs-lookup"><span data-stu-id="53a38-112">To deploy both Windows 10 Enterprise and Office 365 ProPlus together, see the [Desktop Deployment Center](desktop-deployment-center-home.md).</span></span>
>

## <a name="step-1-assess-your-environment"></a><span data-ttu-id="53a38-113">Шаг 1. Оценка среды</span><span class="sxs-lookup"><span data-stu-id="53a38-113">Step 1: Assess your environment</span></span>

<span data-ttu-id="53a38-p103">Перед развертыванием Office 365 профессиональный плюс следуйте инструкциям из статьи [Оценка среды и требований для развертывания Office 365 профессиональный плюс](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). Эта оценка включает проверку требований к системе, сведений о клиентских устройствах (например, архитектурах и необходимых языках), требований к лицензированию, сетевых возможностей и совместимости приложений. Эта проверка поможет вам принять ключевые решения в ходе планирования развертывания.</span><span class="sxs-lookup"><span data-stu-id="53a38-p103">Before deploying Office 365 ProPlus, follow the guidance in [Assess your environment and requirements for deploying Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). This assessment includes system requirements, details of your client devices (such as architectures and required languages), licensing requirements, network capability, and application compatibility. Completing the assessment will help you make key decisions as part of planning your deployment.</span></span>

## <a name="step-2-plan-your-deployment"></a><span data-ttu-id="53a38-117">Действие 2. Планирование развертывания</span><span class="sxs-lookup"><span data-stu-id="53a38-117">Step 2: Plan your deployment</span></span>

<span data-ttu-id="53a38-p104">После оценки среды следуйте инструкциям из статьи [Планирование развертывания Office 365 профессиональный плюс](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus), чтобы создать план развертывания. Этот план включает следующие решения:</span><span class="sxs-lookup"><span data-stu-id="53a38-p104">After assessing your environment, follow the guidance in [Plan your deployment of Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) to create a deployment plan. This plan includes the following decisions:</span></span> 

- <span data-ttu-id="53a38-120">Как развернуть Office, в том числе какое средство использовать (например, System Center Configuration Manager или средство развертывания Office) и откуда установить Office</span><span class="sxs-lookup"><span data-stu-id="53a38-120">How to deploy Office, including what tool to use (such as System Center Configuration Manager or the Office Deployment Tool [ODT]) and where to install Office from</span></span>
- <span data-ttu-id="53a38-121">способ управления обновлениями Office;</span><span class="sxs-lookup"><span data-stu-id="53a38-121">How to manage updates to Office</span></span>
- <span data-ttu-id="53a38-122">используемые каналы обновления (каналы обновления Office определяют, как часто пользователи получают обновления функций своих приложений Office);</span><span class="sxs-lookup"><span data-stu-id="53a38-122">Which update channels to use (update channels for Office control how frequently your users receive feature updates to their Office applications)</span></span>
- <span data-ttu-id="53a38-123">установочные пакеты и группы развертывания Office, которые требуется использовать, в том числе приложения Office и языки, которые требуется установить для тех или иных пользователей.</span><span class="sxs-lookup"><span data-stu-id="53a38-123">The Office installation packages and deployment groups you want to use, including which Office applications and languages should be installed for which users</span></span>

<span data-ttu-id="53a38-124">В [статье, посвященной планированию](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus), представлены рекомендации по всем этим вопросам, включая управление развертыванием, управление обновлениями, определение установочных пакетов и создание групп развертывания.</span><span class="sxs-lookup"><span data-stu-id="53a38-124">The [planning article](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) includes best practices for all these options, including managing your deployment, managing your updates, defining installation packages, and creating deployment groups.</span></span> 

## <a name="step-3-deploy"></a><span data-ttu-id="53a38-125">Действие 3. Развертывание</span><span class="sxs-lookup"><span data-stu-id="53a38-125">Step 3: Deploy</span></span>

<span data-ttu-id="53a38-126">В соответствии с планом развертывания из действия 2 выберите способ развертывания.</span><span class="sxs-lookup"><span data-stu-id="53a38-126">Based on your deployment plan from step 2, choose how you want to deploy:</span></span>

- <span data-ttu-id="53a38-127">**[Развертывание Office 365 профессиональный плюс с помощью System Center Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** управляйте развертыванием с помощью Configuration Manager, скачав и установив Office из точек распространения в сети.</span><span class="sxs-lookup"><span data-stu-id="53a38-127">**[Deploy Office 365 ProPlus with System Center Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Manage your deployment with Configuration Manager, and download and deploy Office from distribution points on your network</span></span>

- <span data-ttu-id="53a38-128">**[Развертывание Office 365 профессиональный плюс с помощью ODT из облака](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** управляйте развертыванием с помощью ODT, установив Office на клиентских устройствах непосредственно из сети CDN Office</span><span class="sxs-lookup"><span data-stu-id="53a38-128">**[Deploy Office 365 ProPlus with the ODT from the cloud](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Manage your deployment with the ODT, and install Office on client devices directly from the Office CDN</span></span>
 
- <span data-ttu-id="53a38-129">**[Развертывание Office 365 профессиональный плюс с помощью ODT из локального источника](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-a-local-source):** управляйте развертыванием с помощью ODT, скачав и развернув Office из локального источника в сети.</span><span class="sxs-lookup"><span data-stu-id="53a38-129">**[Deploy Office 365 ProPlus with the ODT from a local source](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-a-local-source):** Manage your deployment with the ODT, and download and deploy Office from a local source on your network</span></span> 

- <span data-ttu-id="53a38-130">**[Самостоятельная установка Office 365 профессиональный плюс с портала Office](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** управляйте развертыванием на портале Office. Пользователи будут устанавливать Office на своих клиентских устройствах непосредственно с портала.</span><span class="sxs-lookup"><span data-stu-id="53a38-130">**[Self-install Office 365 ProPlus from the Office portal](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** Manage your deployment from the Office portal and have your users install Office on their client devices directly from the portal</span></span>

<span data-ttu-id="53a38-p105">Во многих организациях для разных пользователей используются разные варианты. Например, для большинства пользователей развертывание Office может быть выполнено с помощью Configuration Manager, но для небольшая группа сотрудников, которые нечасто подключаются ко внутренней сети, установит Office самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="53a38-p105">Many organizations will use a combination of these options for different users. For example, an organization might use Configuration Manager to deploy Office to most of their users, but enable self-install for a small group of workers who are not frequently connected to the internal network.</span></span> 

<span data-ttu-id="53a38-p106">Если в вашей организации используется Configuration Manager, рекомендуем выполнить обновление до Current Branch и текущего выпуска. Дополнительные сведения см. в статье [Какую ветвь Configuration Manager следует использовать?](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)</span><span class="sxs-lookup"><span data-stu-id="53a38-p106">If your organization uses Configuration Manager, we recommend upgrading to the Current Branch and updating to the current release. For more details, see [Which branch of Configuration Manager should I use?](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="53a38-135">Как корпорация Майкрософт реализует Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="53a38-135">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="53a38-136">Узнайте, как эксперты Майкрософт [развертывают обновления для Office 365 профессиональный плюс и управляют ими](https://www.microsoft.com/ru-RU/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span><span class="sxs-lookup"><span data-stu-id="53a38-136">Learn how the experts at Microsoft are [deploying and mananging updates for Office 365 ProPlus](https://www.microsoft.com/ru-RU/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="53a38-137">Как корпорация Contoso реализовала Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="53a38-137">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="53a38-138">См. статью с описанием показательного примера [развертывания Office 365 профессиональный плюс](contoso-o365pp.md) корпорацией Contoso — вымышленной глобальной организацией.</span><span class="sxs-lookup"><span data-stu-id="53a38-138">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Office 365 ProPlus](contoso-o365pp.md).</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="53a38-139">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="53a38-139">Next step</span></span>

[<span data-ttu-id="53a38-140">Условия, при выполнении которых можно считать инфраструктуру Office 365 профессиональный плюс настроенной</span><span class="sxs-lookup"><span data-stu-id="53a38-140">Office 365 ProPlus infrastructure exit criteria</span></span>](office365proplus-exit-criteria.md)
