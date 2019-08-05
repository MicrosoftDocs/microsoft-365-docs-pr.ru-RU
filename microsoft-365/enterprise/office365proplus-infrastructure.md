---
title: Этап 4. Office 365 профессиональный плюс
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/18/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как развернуть инфраструктуру Office 365 профессиональный плюс для Microsoft 365 корпоративный.
ms.openlocfilehash: cf698e4dbee17a811a4d2bc01d08d4d97d1961c1
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074179"
---
# <a name="phase-4-office-365-proplus"></a><span data-ttu-id="fbbf5-103">Этап 4. Office 365 профессиональный плюс</span><span class="sxs-lookup"><span data-stu-id="fbbf5-103">Phase 4: Office 365 ProPlus</span></span>

![](./media/deploy-foundation-infrastructure/O365proplus_icon.png)

<span data-ttu-id="fbbf5-104">*Этот этап применяется к планам E3 и E5 Microsoft 365 корпоративный и Microsoft 365 для образования.*</span><span class="sxs-lookup"><span data-stu-id="fbbf5-104">*This applies to both the E3 and E5 versions of Microsoft 365 Enterprise and Microsoft 365 Education*</span></span>

<span data-ttu-id="fbbf5-p101">Microsoft 365 корпоративный включает Office 365 профессиональный плюс — предоставляемую по подписке версию Office. Как и Office 2016, Office 365 профессиональный плюс включает все приложения Office, устанавливаемые непосредственно на клиентских устройствах. В отличие от Office 2016, в Office 365 профессиональный плюс регулярно добавляются новые функции и используется модель лицензирования на основе пользователей, позволяющая им устанавливать Office на 5 устройствах. Дополнительные сведения см. в статье [Office 365 профессиональный плюс на предприятии](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span><span class="sxs-lookup"><span data-stu-id="fbbf5-p101">Microsoft 365 Enterprise includes Office 365 ProPlus, the subscription version of Office. Like Office 2016, Office 365 ProPlus includes all the Office applications, and those applications are installed directly on your client devices. Unlike Office 2016, Office 365 ProPlus is updated with new features on a regular basis and has a user-based licensing model that allows people to install Office on up to 5 devices. For more details, see [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span></span>

<span data-ttu-id="fbbf5-p102">На этом этапе мы развернем Office 365 профессиональный плюс на клиентских устройствах в составе Microsoft 365 корпоративный. Помимо этого руководства, рекомендуем использовать [Microsoft Fastrack](https://fasttrack.microsoft.com/office) для развертывания.</span><span class="sxs-lookup"><span data-stu-id="fbbf5-p102">In this phase, you deploy Office 365 ProPlus to client devices as part of Microsoft 365 Enterprise. In addition to this guidance, we recommend you use [Microsoft Fastrack](https://fasttrack.microsoft.com/office) to help with your deployment.</span></span> 

<span data-ttu-id="fbbf5-111">Office 365 профессиональный плюс делает возможными эти стратегические бизнес-сценари для Microsoft 365 корпоративный:</span><span class="sxs-lookup"><span data-stu-id="fbbf5-111">Office 365 ProPlus enables these strategic business scenarios for Microsoft 365 Enterprise:</span></span>

- <span data-ttu-id="fbbf5-112">совместная работа над документами в режиме реального времени и в удобное для вас время для упрощения процесса совместного создания;</span><span class="sxs-lookup"><span data-stu-id="fbbf5-112">Collaborate on documents in real time or on your own time to simplify the cocreation process</span></span>
- <span data-ttu-id="fbbf5-113">обращение к опыту и знаниям сотрудников благодаря возможности находить и обрабатывать данные, файлы и идеи в организации, а также делиться ими;</span><span class="sxs-lookup"><span data-stu-id="fbbf5-113">Harness collective knowledge and expertise by empowering people to discover, share, and progress files, information, and ideas across your organization</span></span>
- <span data-ttu-id="fbbf5-114">преобразование бизнес-процессов и увеличение эффективности пользователей;</span><span class="sxs-lookup"><span data-stu-id="fbbf5-114">Empower users to transform business processes and increase efficiency</span></span>
- <span data-ttu-id="fbbf5-115">управление проектами, задачами и крайними сроками для достижения бизнес-целей;</span><span class="sxs-lookup"><span data-stu-id="fbbf5-115">Manage projects, tasks, and deadlines to meet your business objectives</span></span>
- <span data-ttu-id="fbbf5-116">интеллектуальная поддержка при создании, записи, поиске содержимого и не только для обеспечения эффективности работы;</span><span class="sxs-lookup"><span data-stu-id="fbbf5-116">Use intelligent assistance for design, writing, content discovery, and more to help your work shine</span></span>
- <span data-ttu-id="fbbf5-117">возможность анализировать данные и делиться результатами для того, чтобы помочь в принятии обоснованных решений;</span><span class="sxs-lookup"><span data-stu-id="fbbf5-117">Discover insights, analyze your data, and share your findings to help everyone make informed decisions</span></span>
- <span data-ttu-id="fbbf5-118">общение с членами команды, обеспечивающее информированность, слаженную работу и согласованность мнений;</span><span class="sxs-lookup"><span data-stu-id="fbbf5-118">Communicate with your team to stay informed, solicit input, and build cohesion and consensus</span></span>
- <span data-ttu-id="fbbf5-119">общение с партнерами, коллегами и клиентами по всему миру во время запланированных и незапланированных звонков, онлайн-собраний для любого количества участников;</span><span class="sxs-lookup"><span data-stu-id="fbbf5-119">Communicate with partners, colleagues, and customers around the world for scheduled and ad hoc calls and online meetings with groups of all sizes</span></span>
- <span data-ttu-id="fbbf5-120">возможность хранить файлы и делиться ими в организации и за ее пределами для обеспечения эффективности работы;</span><span class="sxs-lookup"><span data-stu-id="fbbf5-120">Store and share files inside and outside your organization to work seamlessly across organizational boundaries</span></span>
- <span data-ttu-id="fbbf5-121">безопасная работа на любых устройствах где угодно и когда угодно для обеспечения эффективности при гибком стиле работы;</span><span class="sxs-lookup"><span data-stu-id="fbbf5-121">Work securely from anywhere, anytime across your device to achieve more while maintaining a flexible workstyle</span></span>
- <span data-ttu-id="fbbf5-122">беспроблемное применение средств контроля и реализация прозрачности согласно глобальным стандартам обеспечения соответствия требованиям;</span><span class="sxs-lookup"><span data-stu-id="fbbf5-122">Provide peace-of-mind with controls and visibility for industry-verified conformity with global standards in compliance</span></span>
- <span data-ttu-id="fbbf5-123">защита данных и снижение риска утери данных;</span><span class="sxs-lookup"><span data-stu-id="fbbf5-123">Protect your information and reduce the risk of data loss</span></span>
- <span data-ttu-id="fbbf5-124">обновление программного обеспечения компьютера и других устройств до последней версии, снижение риска, связанного с нарушением безопасности, и увеличение эффективности ИТ-инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="fbbf5-124">Get current and stay current on your desktop software and devices while reducing security risks and maximizing IT efficiency</span></span>

<span data-ttu-id="fbbf5-125">Дополнительные сведения см. в статье [Цифровая трансформация с помощью Microsoft 365](http://transform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="fbbf5-125">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

<span data-ttu-id="fbbf5-126">Если вы уже развернули Office 365 профессиональный плюс, см. [критерии выхода](office365proplus-exit-criteria.md) для этого этапа, чтобы убедиться, что выполнены обязательные условия для Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="fbbf5-126">If you already have Office 365 ProPlus deployed, please see the [exit criteria](office365proplus-exit-criteria.md) for this phase to make sure that it meets the required conditions for Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="fbbf5-127">Для совместного развертывания Windows 10 Корпоративная и Office 365 профессиональный плюс обратитесь к статье [Центр развертывания компьютеров](desktop-deployment-center-home.md).</span><span class="sxs-lookup"><span data-stu-id="fbbf5-127">To deploy both Windows 10 Enterprise and Office 365 ProPlus together, see the [Desktop Deployment Center](desktop-deployment-center-home.md).</span></span>
>

## <a name="step-1-assess-your-environment"></a><span data-ttu-id="fbbf5-128">Шаг 1. Оценка среды</span><span class="sxs-lookup"><span data-stu-id="fbbf5-128">Step 1: Assess your environment</span></span>

<span data-ttu-id="fbbf5-p103">Перед развертыванием Office 365 профессиональный плюс следуйте инструкциям из статьи [Оценка среды и требований для развертывания Office 365 профессиональный плюс](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). Эта оценка включает проверку требований к системе, сведений о клиентских устройствах (например, архитектурах и необходимых языках), требований к лицензированию, сетевых возможностей и совместимости приложений. Эта проверка поможет вам принять ключевые решения в ходе планирования развертывания.</span><span class="sxs-lookup"><span data-stu-id="fbbf5-p103">Before deploying Office 365 ProPlus, follow the guidance in [Assess your environment and requirements for deploying Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). This assessment includes system requirements, details of your client devices (such as architectures and required languages), licensing requirements, network capability, and application compatibility. Completing the assessment will help you make key decisions as part of planning your deployment.</span></span>

## <a name="step-2-plan-your-deployment"></a><span data-ttu-id="fbbf5-132">Действие 2. Планирование развертывания</span><span class="sxs-lookup"><span data-stu-id="fbbf5-132">Step 2: Plan your deployment</span></span>

<span data-ttu-id="fbbf5-p104">После оценки среды следуйте инструкциям из статьи [Планирование развертывания Office 365 профессиональный плюс](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus), чтобы создать план развертывания. Этот план включает следующие решения:</span><span class="sxs-lookup"><span data-stu-id="fbbf5-p104">After assessing your environment, follow the guidance in [Plan your deployment of Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) to create a deployment plan. This plan includes the following decisions:</span></span> 

- <span data-ttu-id="fbbf5-135">Как развернуть Office, в том числе какое средство использовать (например, System Center Configuration Manager или средство развертывания Office) и откуда установить Office</span><span class="sxs-lookup"><span data-stu-id="fbbf5-135">How to deploy Office, including what tool to use (such as System Center Configuration Manager or the Office Deployment Tool [ODT]) and where to install Office from</span></span>
- <span data-ttu-id="fbbf5-136">способ управления обновлениями Office;</span><span class="sxs-lookup"><span data-stu-id="fbbf5-136">How to manage updates to Office</span></span>
- <span data-ttu-id="fbbf5-137">используемые каналы обновления (каналы обновления Office определяют, как часто пользователи получают обновления функций своих приложений Office);</span><span class="sxs-lookup"><span data-stu-id="fbbf5-137">Which update channels to use (update channels for Office control how frequently your users receive feature updates to their Office applications)</span></span>
- <span data-ttu-id="fbbf5-138">установочные пакеты и группы развертывания Office, которые требуется использовать, в том числе приложения Office и языки, которые требуется установить для тех или иных пользователей.</span><span class="sxs-lookup"><span data-stu-id="fbbf5-138">The Office installation packages and deployment groups you want to use, including which Office applications and languages should be installed for which users</span></span>

<span data-ttu-id="fbbf5-139">В [статье, посвященной планированию](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus), представлены рекомендации по всем этим вопросам, включая управление развертыванием, управление обновлениями, определение установочных пакетов и создание групп развертывания.</span><span class="sxs-lookup"><span data-stu-id="fbbf5-139">The [planning article](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) includes best practices for all these options, including managing your deployment, managing your updates, defining installation packages, and creating deployment groups.</span></span> 

## <a name="step-3-deploy"></a><span data-ttu-id="fbbf5-140">Действие 3. Развертывание</span><span class="sxs-lookup"><span data-stu-id="fbbf5-140">Step 3: Deploy</span></span>

<span data-ttu-id="fbbf5-141">В соответствии с планом развертывания из действия 2 выберите способ развертывания.</span><span class="sxs-lookup"><span data-stu-id="fbbf5-141">Based on your deployment plan from step 2, choose how you want to deploy:</span></span>

- <span data-ttu-id="fbbf5-142">**[Развертывание Office 365 профессиональный плюс с помощью System Center Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** управляйте развертыванием с помощью Configuration Manager, скачав и установив Office из точек распространения в сети.</span><span class="sxs-lookup"><span data-stu-id="fbbf5-142">**[Deploy Office 365 ProPlus with System Center Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Manage your deployment with Configuration Manager, and download and deploy Office from distribution points on your network</span></span>

- <span data-ttu-id="fbbf5-143">**[Развертывание Office 365 профессиональный плюс с помощью ODT из облака](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** управляйте развертыванием с помощью ODT, установив Office на клиентских устройствах непосредственно из сети CDN Office</span><span class="sxs-lookup"><span data-stu-id="fbbf5-143">**[Deploy Office 365 ProPlus with the ODT from the cloud](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Manage your deployment with the ODT, and install Office on client devices directly from the Office CDN</span></span>
 
- <span data-ttu-id="fbbf5-144">**[Развертывание Office 365 профессиональный плюс с помощью ODT из локального источника](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-a-local-source):** управляйте развертыванием с помощью ODT, скачав и развернув Office из локального источника в сети.</span><span class="sxs-lookup"><span data-stu-id="fbbf5-144">**[Deploy Office 365 ProPlus with the ODT from a local source](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-a-local-source):** Manage your deployment with the ODT, and download and deploy Office from a local source on your network</span></span> 

- <span data-ttu-id="fbbf5-145">**[Самостоятельная установка Office 365 профессиональный плюс с портала Office](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** управляйте развертыванием на портале Office. Пользователи будут устанавливать Office на своих клиентских устройствах непосредственно с портала.</span><span class="sxs-lookup"><span data-stu-id="fbbf5-145">**[Self-install Office 365 ProPlus from the Office portal](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** Manage your deployment from the Office portal and have your users install Office on their client devices directly from the portal</span></span>

<span data-ttu-id="fbbf5-p105">Во многих организациях для разных пользователей используются разные варианты. Например, для большинства пользователей развертывание Office может быть выполнено с помощью Configuration Manager, но для небольшая группа сотрудников, которые нечасто подключаются ко внутренней сети, установит Office самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="fbbf5-p105">Many organizations will use a combination of these options for different users. For example, an organization might use Configuration Manager to deploy Office to most of their users, but enable self-install for a small group of workers who are not frequently connected to the internal network.</span></span> 

<span data-ttu-id="fbbf5-p106">Если в вашей организации используется Configuration Manager, рекомендуем выполнить обновление до Current Branch и текущего выпуска. Дополнительные сведения см. в статье [Какую ветвь Configuration Manager следует использовать?](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)</span><span class="sxs-lookup"><span data-stu-id="fbbf5-p106">If your organization uses Configuration Manager, we recommend upgrading to the Current Branch and updating to the current release. For more details, see [Which branch of Configuration Manager should I use?](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="fbbf5-150">Как корпорация Майкрософт реализует Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="fbbf5-150">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="fbbf5-151">Узнайте, как эксперты Майкрософт [развертывают обновления для Office 365 профессиональный плюс и управляют ими](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span><span class="sxs-lookup"><span data-stu-id="fbbf5-151">Learn how the experts at Microsoft are [deploying and mananging updates for Office 365 ProPlus](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="fbbf5-152">Как корпорация Contoso реализовала Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="fbbf5-152">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="fbbf5-153">См. статью с описанием показательного примера [развертывания Office 365 профессиональный плюс](contoso-o365pp.md) корпорацией Contoso — вымышленной глобальной организацией.</span><span class="sxs-lookup"><span data-stu-id="fbbf5-153">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Office 365 ProPlus](contoso-o365pp.md).</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="fbbf5-154">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="fbbf5-154">Next step</span></span>

[<span data-ttu-id="fbbf5-155">Условия, при выполнении которых можно считать инфраструктуру Office 365 профессиональный плюс настроенной</span><span class="sxs-lookup"><span data-stu-id="fbbf5-155">Office 365 ProPlus infrastructure exit criteria</span></span>](office365proplus-exit-criteria.md)
