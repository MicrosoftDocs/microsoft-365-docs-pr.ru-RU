---
title: Развертывание защиты информации для норм конфиденциальности данных с помощью Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: Настройка инфраструктуры безопасности и обслуживания для защиты данных и соблюдения нормативных требований.
ms.openlocfilehash: 35ccfb21accd969c2a2cbdddde9a4ec1c7eeed64
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695114"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a><span data-ttu-id="75d61-103">Развертывание защиты информации для норм конфиденциальности данных с помощью Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="75d61-103">Deploy information protection for data privacy regulations with Microsoft 365</span></span>

<span data-ttu-id="75d61-104">Это решение предоставляет рекомендации по планированию и защите персональных данных, хранящихся в службах Microsoft 365, и потенциально могут подчиняться нормативам, связанным с конфиденциальностью данных, например, к общему законодательству по защите данных (GDPR) Европейского союза.</span><span class="sxs-lookup"><span data-stu-id="75d61-104">This solution provides guidance on how to plan for and protect personal data that is stored in Microsoft 365 services and potentially subject to data privacy regulations such as the European Union's General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="75d61-105">Это решение относится к применимым функциям защиты информации и соответствия требованиям корпорации Майкрософт, оценки соответствия требованиям Майкрософт и средствам оценки, которые помогут вам узнать ваши данные.</span><span class="sxs-lookup"><span data-stu-id="75d61-105">This solution focuses on applicable Microsoft information protection and compliance features, Microsoft Compliance Score, and assessment tools to help you know your data.</span></span> 
 
<span data-ttu-id="75d61-106">Дополнительные сведения также предоставляются при использовании средств управления удостоверениями, устройствами и защитой от угроз для удовлетворения требований к защите данных, а также для обнаружения и реагирования на обнаружение инцидентов данных.</span><span class="sxs-lookup"><span data-stu-id="75d61-106">Additional information is also provided on the use of Microsoft identity, device, and threat protection controls for your data privacy needs, as well as data incident discovery and response tools.</span></span> 

## <a name="organization-of-this-guidance-material"></a><span data-ttu-id="75d61-107">Организация этих справочных материалов</span><span class="sxs-lookup"><span data-stu-id="75d61-107">Organization of this guidance material</span></span>

<span data-ttu-id="75d61-108">Чтобы получить представление о средствах Microsoft 365, доступных для идентификации и управления личными данными, а также для наблюдения за ними, в отношении одного или нескольких нормативных требований, эти рекомендации организованы по разделам.</span><span class="sxs-lookup"><span data-stu-id="75d61-108">To help you understand the Microsoft 365 tools available to identify, manage, control, and monitor personal data subject to one or more privacy-related regulations, this guidance is organized into sections.</span></span>
 
![Развертывание защиты информации для норм конфиденциальности данных](../media/information-protection-deploy/information-protection-deploy-grid.png)

<span data-ttu-id="75d61-110">Каждый из этих разделов соответствует отдельной статье в этом решении.</span><span class="sxs-lookup"><span data-stu-id="75d61-110">Each of these sections correspond to a separate article in this solution.</span></span>

>[!Note]
><span data-ttu-id="75d61-111">Если вы уже знакомы с вашими обязательствами по конфиденциальности данных и их работами с существующим планом, вы можете сосредоточиться на этой статье: предотвращение, защита, сохранение и исследование.</span><span class="sxs-lookup"><span data-stu-id="75d61-111">If you are already familiar with your data privacy obligations and are executing against an existing plan, you may want to focus on the Prevent, Protect, Retain, and Investigate guidance.</span></span>

>[!Important]
><span data-ttu-id="75d61-112">Следуя этим рекомендациям, не обязательно забудьте в соответствии с требованиями к конфиденциальности данных, особенно учитывая количество действий, необходимых вне контекста компонентов.</span><span class="sxs-lookup"><span data-stu-id="75d61-112">Following this guidance will not necessarily make you compliant with any data privacy regulation, especially considering the number of steps required that are outside the context of the features.</span></span> <span data-ttu-id="75d61-113">Вы несете ответственность за обеспечение соответствия требованиям и соблюдение юридических и нормативных групп, а также поиск рекомендаций и советов от сторонних производителей, специализирующихся на соответствие требованиям.</span><span class="sxs-lookup"><span data-stu-id="75d61-113">You are responsible for ensuring your compliance and to consult your legal and compliance teams or to seek guidance and advice from third parties that specialize in compliance.</span></span>
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a><span data-ttu-id="75d61-114">Plan: Оценка рисков конфиденциальности данных и определение конфиденциальных элементов</span><span class="sxs-lookup"><span data-stu-id="75d61-114">Plan: Assess data privacy risks and identify sensitive items</span></span> 

<span data-ttu-id="75d61-115">Оценка требований к конфиденциальности данных и рисков, на которые распространяется ваша организация, является ключевым первым шагом, прежде чем приступить к внедрению усовершенствований, в том числе доступных с помощью конфигурации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="75d61-115">Assessing data privacy regulations and risks that your organization is subject to is a key first step to take before starting to implement improvements, including those achievable through Microsoft 365 configuration.</span></span> <span data-ttu-id="75d61-116">Это может быть полная оценка готовности или идентификация определенных типов конфиденциальной информации, которые подчиняются нормативным требованиям, а также их появлениям в среде Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="75d61-116">This may include an overall readiness assessment or identification of particular sensitive information types that are subject to regulatory controls your organization needs to comply with, as well as the occurrence of them in your Microsoft 365 environment.</span></span>

<span data-ttu-id="75d61-117">Дополнительную информацию можно узнать в статье [Оценка рисков конфиденциальности данных и определение конфиденциальных элементов](information-protection-deploy-assess.md).</span><span class="sxs-lookup"><span data-stu-id="75d61-117">For more information, see [Assess data privacy risks and identify sensitive items](information-protection-deploy-assess.md).</span></span>

## <a name="track-use-compliance-score-and-compliance-manager"></a><span data-ttu-id="75d61-118">Отслеживание: использование оценки соответствия требованиям и диспетчера соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="75d61-118">Track: Use Compliance Score and Compliance Manager</span></span> 

<span data-ttu-id="75d61-119">Оценка соответствия требованиям и диспетчер соответствия требованиям предоставляют интегрированный набор средств, доступных в центре администрирования соответствия требованиям Microsoft 365 и доверенном портале.</span><span class="sxs-lookup"><span data-stu-id="75d61-119">Compliance Score and Compliance Manager provide an integrated set of tools available in the Microsoft 365 Compliance admin center and Services Trust Portal.</span></span> <span data-ttu-id="75d61-120">В совокупности эти средства предоставляют встроенную возможность отслеживания и управления действиями по улучшению в целом, а также в отношении нескольких нормативных требований к данным, к которым вы подчиняются.</span><span class="sxs-lookup"><span data-stu-id="75d61-120">Together, these tools provide you with a built-in ability to track and manage improvement actions overall as well as those related to multiple data privacy regulations to which you are subjected.</span></span>

<span data-ttu-id="75d61-121">Кроме того, эти средства позволяют использовать встроенные шаблоны оценки, относящиеся к каждому конкретному подстановке, где можно отслеживать элементы действий для каждого выбранного шаблона оценки, а также просматривать определенные нормативные элементы управления и связывать их с определенными действиями.</span><span class="sxs-lookup"><span data-stu-id="75d61-121">The tools also allow you to leverage built in assessment templates specific to each regulation, where you can track action items for each assessment template selected, as well as view specific regulatory controls, and relate them to specific actions.</span></span>

<span data-ttu-id="75d61-122">Для получения дополнительных сведений см. [использование оценки соответствия и диспетчера соответствия требованиям для управления действиями по улучшению](information-protection-deploy-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="75d61-122">For more information, see [Use Compliance Score and Compliance Manager to manage improvement actions](information-protection-deploy-compliance.md).</span></span>

## <a name="prevent-use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="75d61-123">Запретить: использовать удостоверение, устройство и защиту от угроз для обеспечения конфиденциальности данных</span><span class="sxs-lookup"><span data-stu-id="75d61-123">Prevent: Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="75d61-124">Microsoft 365 предоставляет ряд возможностей по обеспечению конфиденциальности данных, устройств и угроз, которые можно использовать для соблюдения соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="75d61-124">Microsoft 365 provides a number of identity, device, and threat protection capabilities that you can use to help comply with data privacy regulatory compliance.</span></span> 

<span data-ttu-id="75d61-125">Дополнительные сведения см в статье [использование удостоверений, устройств и защиты от угроз для обеспечения конфиденциальности данных](information-protection-deploy-identity-device-threat.md).</span><span class="sxs-lookup"><span data-stu-id="75d61-125">For more information, see [Use identity, device, and threat protection for data privacy regulation](information-protection-deploy-identity-device-threat.md).</span></span>

<span data-ttu-id="75d61-126">В этой статье кратко описана информация о правилах конфиденциальности данных, которые обычно вызываются в этих областях, и приведен список связанных решений Microsoft 365 со ссылками на дополнительные сведения, которые помогут вам решить любые требования к реализации.</span><span class="sxs-lookup"><span data-stu-id="75d61-126">This article briefly describes what the data privacy regulations generally call for in these areas and provides a listing of related Microsoft 365 solutions, with links to more information to help you address any implementation requirements.</span></span> 

## <a name="protect-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="75d61-127">Защита данных в соответствии с нормами конфиденциальности данных</span><span class="sxs-lookup"><span data-stu-id="75d61-127">Protect information subject to data privacy regulation</span></span>

<span data-ttu-id="75d61-128">Требования к конфиденциальности данных определяют ряд средств защиты персональных данных, которые можно использовать в среде, в том числе более 40 для защиты информации в рамках всего четырех нормативных требований к данным в нашем образце набора GDPR, безопасности клиента в Калифорнии (ККПА), HIPAA-HITECH (ACT о конфиденциальности для США) и ACT защиты данных в Бразилии (ЛГПД).</span><span class="sxs-lookup"><span data-stu-id="75d61-128">Data privacy regulations dictate a number of personal information protection controls that can be employed in your environment, including more than forty Protect Information controls across just the four data privacy regulations in our sample set of GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="75d61-129">Дополнительную информацию можно узнать [в статье Защита конфиденциальных данных в соответствии с конфиденциальными сведениями в вашей организации](information-protection-deploy-protect-information.md).</span><span class="sxs-lookup"><span data-stu-id="75d61-129">For more information, see [Protect information subject to data privacy regulation in your organization](information-protection-deploy-protect-information.md).</span></span>

<span data-ttu-id="75d61-130">В этой статье описываются основные схемы управления, которые можно использовать для адресации требований к защите данных в Организации.</span><span class="sxs-lookup"><span data-stu-id="75d61-130">This article lays out the main control schemes that can be used for addressing information protection needs for data privacy in your organization.</span></span>

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="75d61-131">Сохранение: Управление сведениями, которые подчиняются нормам конфиденциальности данных</span><span class="sxs-lookup"><span data-stu-id="75d61-131">Retain: Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="75d61-132">Требования к конфиденциальности данных для управления персональными сведениями, которые можно использовать в вашей среде, в том числе более двадцати четырех элементов управления в рамках четырех правил конфиденциальности данных в нашем примере набора GDPR, ККПА, HIPAA/HITECH и ЛГПД.</span><span class="sxs-lookup"><span data-stu-id="75d61-132">Data privacy regulations call for personal information governance controls that can be employed in your environment, including more than twenty-four controls across the four data privacy regulations in our sample set of GDPR, CCPA, HIPAA-HITECH, and LGPD.</span></span>

<span data-ttu-id="75d61-133">Дополнительные сведения см в разделе Управление [сведениями, которые подчиняются конфиденциальности данных в вашей организации](information-protection-deploy-govern.md).</span><span class="sxs-lookup"><span data-stu-id="75d61-133">For more information, see [Govern information subject to data privacy regulation in your organization](information-protection-deploy-govern.md).</span></span>

<span data-ttu-id="75d61-134">Несмотря на то, что правила конфиденциальности данных могут быть неясными в отношении управления сведениями &mdash; , например хранения пурпосефул, удаления и архивации, &mdash; Эта статья посвящена основным схемам управления, в которых можно использовать информацию по управлению адресами для обеспечения конфиденциальности данных в Организации.</span><span class="sxs-lookup"><span data-stu-id="75d61-134">While the data privacy regulations can be vague regarding information governance&mdash;such as purposeful retention, deletion and archiving&mdash;this article lays out the primary control schemes that you can use address information governance needs for data privacy in your organization.</span></span>

## <a name="investigate-monitor-and-respond-subject-to-data-privacy-regulation"></a><span data-ttu-id="75d61-135">Исследование: отслеживание и реагирование на соблюдение конфиденциальности данных</span><span class="sxs-lookup"><span data-stu-id="75d61-135">Investigate: Monitor and respond subject to data privacy regulation</span></span>

<span data-ttu-id="75d61-136">Существуют функции Microsoft 365, которые помогают отслеживать, изучать и отвечать на инциденты конфиденциальности данных в вашей организации, как вы оператионализее связанные возможности.</span><span class="sxs-lookup"><span data-stu-id="75d61-136">There are Microsoft 365 features available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> 

<span data-ttu-id="75d61-137">Процесс, процедуры и другая документация для каждого из них могут быть важны для демонстрации соответствия нормативным требованиям.</span><span class="sxs-lookup"><span data-stu-id="75d61-137">Having processes, procedures, and other documentation for each of these can be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="75d61-138">Дополнительную информацию можно узнать [в статье мониторинг и реагирование на инциденты конфиденциальности данных в Организации](information-protection-deploy-monitor-respond.md).</span><span class="sxs-lookup"><span data-stu-id="75d61-138">For more information, see [Monitor and respond to data privacy incidents in your organization](information-protection-deploy-monitor-respond.md).</span></span>
