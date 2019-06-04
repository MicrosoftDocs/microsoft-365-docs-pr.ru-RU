---
title: Сайты Microsoft Teams и SharePoint Online для жестко регламентированных данных
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/03/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Создайте безопасный сайт группы SharePoint Online или группы Microsoft Teams для хранения наиболее ценных и конфиденциальных цифровых активов.
ms.openlocfilehash: d9740a27cdb90f8d490a6c9a323e968725876deb
ms.sourcegitcommit: e87c9aa4d6f4756c0a761d3de7c70492b43bf0b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2019
ms.locfileid: "34681074"
---
# <a name="microsoft-teams-and-sharepoint-online-sites-for-highly-regulated-data"></a><span data-ttu-id="748fa-103">Сайты Microsoft Teams и SharePoint Online для жестко регламентированных данных</span><span class="sxs-lookup"><span data-stu-id="748fa-103">Microsoft Teams and SharePoint Online sites for highly regulated data</span></span>

<span data-ttu-id="748fa-104">*Этот сценарий применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="748fa-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="748fa-p101">Решение Microsoft 365 корпоративный содержит полный набор облачных служб, предназначенных для создания, хранения и защиты жестко регламентированных данных. К их числу относятся:</span><span class="sxs-lookup"><span data-stu-id="748fa-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, and secure your highly regulated data. This includes data that is:</span></span>

- <span data-ttu-id="748fa-107">данные, на которые распространяется действие региональных нормативных актов;</span><span class="sxs-lookup"><span data-stu-id="748fa-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="748fa-108">наиболее важные для предприятия данные, например коммерческие тайны, информация о финансовой деятельности или данные о персонале и стратегии организации.</span><span class="sxs-lookup"><span data-stu-id="748fa-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

<span data-ttu-id="748fa-109">Облачный сценарий Microsoft 365 корпоративный, который соответствует такой бизнес-потребности предприятия, потребует от вас:</span><span class="sxs-lookup"><span data-stu-id="748fa-109">A Microsoft 365 Enterprise cloud-based solution that meets this business need requires that you:</span></span>

- <span data-ttu-id="748fa-110">хранения цифровых активов (документы, наборы слайдов, электронные таблицы, т. д.) на сайте группы SharePoint Online или во вкладке **Файлы** группы Microsoft Teams;</span><span class="sxs-lookup"><span data-stu-id="748fa-110">Store digital assets (documents, slide decks, spreadsheets, etc.) in a SharePoint Online team site or in the **Files** tab of a Microsoft Teams team.</span></span>
- <span data-ttu-id="748fa-111">блокировки сайта или группы, чтобы предотвратить:</span><span class="sxs-lookup"><span data-stu-id="748fa-111">Lock down the site or team to prevent:</span></span>
   - <span data-ttu-id="748fa-112">доступ только для конкретного набора учетных записей пользователей, определенного участием в группе; сюда входят пользователи, имеющие доступ к сайту группы SharePoint Online (с указанием уровня разрешения), и администраторы сайта;</span><span class="sxs-lookup"><span data-stu-id="748fa-112">Access to only a specific set of user accounts through group membership, which includes those who can access the SharePoint Online team site and at what level of permission, and those who can administer it.</span></span>
   - <span data-ttu-id="748fa-113">предоставление участниками сайта доступа третьим лицам;</span><span class="sxs-lookup"><span data-stu-id="748fa-113">Members of the site from granting access to others.</span></span>
   - <span data-ttu-id="748fa-114">запросы на доступ к сайту от лиц, которые не являются участниками сайта;</span><span class="sxs-lookup"><span data-stu-id="748fa-114">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="748fa-115">настройки метки хранения Office 365 для сайтов или групп SharePoint Online в качестве стандартного способа определения политик хранения для документов на сайте или в группе;</span><span class="sxs-lookup"><span data-stu-id="748fa-115">Configure an Office 365 retention label for your SharePoint Online sites or teams as a default way to define retention policies on the documents in the site or team.</span></span>
- <span data-ttu-id="748fa-116">запрета на отправку пользователями файлов за пределы организации;</span><span class="sxs-lookup"><span data-stu-id="748fa-116">Block users from sending files outside the organization.</span></span>
- <span data-ttu-id="748fa-117">шифрования наиболее конфиденциальных цифровых активов сайта или группы;</span><span class="sxs-lookup"><span data-stu-id="748fa-117">Encrypt the most sensitive digital assets of the site or team.</span></span>
- <span data-ttu-id="748fa-118">добавления разрешений к наиболее конфиденциальным активам. В этом случае, даже если такие активы окажутся за пределами сайта, чтобы их открыть потребуются действительные учетные данные пользователя учетной записи, который имеет соответствующее разрешение.</span><span class="sxs-lookup"><span data-stu-id="748fa-118">Add permissions to the most sensitive digital assets so that if even if they get shared outside of the site, opening the asset still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="748fa-119">В приведенной ниже таблице сопоставляются требования этого сценария и функции Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="748fa-119">The following table maps the requirements of this solution to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="748fa-120">**Требования**</span><span class="sxs-lookup"><span data-stu-id="748fa-120">**Requirement**</span></span> | <span data-ttu-id="748fa-121">**Функция Microsoft 365 корпоративный**</span><span class="sxs-lookup"><span data-stu-id="748fa-121">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="748fa-122">Хранение цифровых активов</span><span class="sxs-lookup"><span data-stu-id="748fa-122">Store digital assets</span></span> | <span data-ttu-id="748fa-123">Сайты групп и группы SharePoint Online в Office 365</span><span class="sxs-lookup"><span data-stu-id="748fa-123">SharePoint Online team sites and teams in Office 365</span></span> |
| <span data-ttu-id="748fa-124">Блокировка сайта</span><span class="sxs-lookup"><span data-stu-id="748fa-124">Lock down the site</span></span> | <span data-ttu-id="748fa-125">Разрешения для групп Azure AD и сайта группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="748fa-125">Azure AD groups and SharePoint Online team site permissions</span></span> |
| <span data-ttu-id="748fa-126">Добавление метки к цифровым активам сайта</span><span class="sxs-lookup"><span data-stu-id="748fa-126">Label the digital assets of the site</span></span> | <span data-ttu-id="748fa-127">Метки хранения Office 365</span><span class="sxs-lookup"><span data-stu-id="748fa-127">Office 365 retention labels</span></span> |
| <span data-ttu-id="748fa-128">Блокирование пользователей при отправке файлов за пределы организации</span><span class="sxs-lookup"><span data-stu-id="748fa-128">Block users when sending files outside the organization</span></span> | <span data-ttu-id="748fa-129">Политики защиты от потери данных в Office 365</span><span class="sxs-lookup"><span data-stu-id="748fa-129">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="748fa-130">Шифрование всех цифровых активов сайта</span><span class="sxs-lookup"><span data-stu-id="748fa-130">Encrypt all of the digital assets of the site</span></span> | <span data-ttu-id="748fa-131">Вложенные метки Azure Information Protection в Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="748fa-131">Azure Information Protection sub-labels in Enterprise Mobility + Security (EMS)</span></span> |
| <span data-ttu-id="748fa-132">Добавление разрешений ко всем цифровым активам сайта</span><span class="sxs-lookup"><span data-stu-id="748fa-132">Add permissions to the digital assets of the site</span></span> | <span data-ttu-id="748fa-133">Вложенные метки Azure Information Protection в EMS</span><span class="sxs-lookup"><span data-stu-id="748fa-133">Azure Information Protection sub-labels in EMS</span></span> |
|||

<span data-ttu-id="748fa-134">Конфигурация для сайта SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="748fa-134">Here is the configuration for a SharePoint Online site.</span></span>

![Сайты Microsoft Teams и SharePoint Online для сценария жестко регламентированных данных](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="748fa-136">Этот сценарий требует, чтобы у вас уже были развернуты:</span><span class="sxs-lookup"><span data-stu-id="748fa-136">This solution requires that you have already deployed:</span></span>

- <span data-ttu-id="748fa-137">этап [удостоверений](identity-infrastructure.md) и шаги 1 и 2 этапа [защиты информации](infoprotect-infrastructure.md) для базовой инфраструктуры;</span><span class="sxs-lookup"><span data-stu-id="748fa-137">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="748fa-138">[SharePoint Online](sharepoint-online-onedrive-workload.md) (для жестко регламентированных данных на сайтах группы SharePoint Online);</span><span class="sxs-lookup"><span data-stu-id="748fa-138">For highly regulated data in SharePoint Online team sites, [SharePoint Online](sharepoint-online-onedrive-workload.md).</span></span>
- <span data-ttu-id="748fa-139">[Microsoft Teams](teams-workload.md) (для жестко регламентированных данных в группах Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="748fa-139">For highly regulated data in Microsoft Teams teams, [Microsoft Teams](teams-workload.md).</span></span>

<span data-ttu-id="748fa-140">Описанные ниже поэтапные шаги помогут выполнить проектирование, настройку и внедрение сайтов и групп SharePoint Online для жестко регламентированных данных.</span><span class="sxs-lookup"><span data-stu-id="748fa-140">The following phases step you through the design, configuration, and driving adoption for SharePoint Online sites and teams for highly regulated data.</span></span>

<span data-ttu-id="748fa-141">Чтобы узнать, как вымышленная корпорация Contoso, которая представляет типичные международные компании, разработала сайт SharePoint Online для исследовательских групп, см. [пример конфигурации](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span><span class="sxs-lookup"><span data-stu-id="748fa-141">To see how the Contoso Corporation, a fictional but representative multi-national organization, designed a SharePoint Online site for its research teams, see this [example configuration](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span></span>


<span data-ttu-id="748fa-p102">Группа для жестко регламентированных данных требует предварительного создания сайта группы SharePoint Online для жестко регламентированных данных и группы Office 365. Чтобы узнать больше, см. этап 2, шаг 4.</span><span class="sxs-lookup"><span data-stu-id="748fa-p102">A team for highly regulated data requires that you first create a SharePoint Online team site for highly regulated data. You then create a new team that uses the Office 365 group of the SharePoint Online team site. See Phase 2, Step 4 for more information.</span></span>

<span data-ttu-id="748fa-145">Конфигурация для команды.</span><span class="sxs-lookup"><span data-stu-id="748fa-145">Here is the configuration for a team.</span></span>

![Сайты Microsoft Teams и SharePoint Online для сценария жестко регламентированных данных](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-team.png)


## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="748fa-147">Необходимые компоненты для идентификации и доступа к устройству</span><span class="sxs-lookup"><span data-stu-id="748fa-147">Identity and device access prerequisites</span></span>

<span data-ttu-id="748fa-148">Чтобы защитить доступ к группе или сайту SharePoint Online, убедитесь, что вы настроили [политики идентификации и доступа к устройству](identity-access-policies.md), а также [рекомендуемые политики доступа к SharePoint Online](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="748fa-148">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="748fa-149">Этап 1. Проектирование</span><span class="sxs-lookup"><span data-stu-id="748fa-149">Phase 1: Design</span></span>

<span data-ttu-id="748fa-p103">Чтобы создать сайт или группу SharePoint Online для жестко регламентированных данных, сначала необходимо определить ее назначение. Например, отделу исследований и разработок какой-либо производственной организации требуется сайт SharePoint Online для хранения текущих проектных спецификаций на существующие продукты, а также место для совместной работы над новыми продуктами. Доступ к такому сайту должен быть разрешен только для сотрудников отдела исследований и разработок, а также для некоторых руководителей организации.</span><span class="sxs-lookup"><span data-stu-id="748fa-p103">To create a SharePoint Online site or team for highly regulated data, you must first identify its purpose. For example, the research and development department of a manufacturing organization needs a SharePoint Online site to store current design specifications for existing products and a place to collaborate on new products. Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="748fa-153">Такое назначение сайта потребует определения основных элементов конфигурации, таких как:</span><span class="sxs-lookup"><span data-stu-id="748fa-153">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="748fa-154">настройка наборов разрешений SharePoint Online и групп SharePoint;</span><span class="sxs-lookup"><span data-stu-id="748fa-154">The set of SharePoint Online permission sets and SharePoint groups</span></span>
- <span data-ttu-id="748fa-155">настройка групп доступа, групп безопасности Azure AD и их участников для добавления их в группы SharePoint;</span><span class="sxs-lookup"><span data-stu-id="748fa-155">The set of access groups, the Azure AD security groups and their members to add to the SharePoint groups</span></span>
- <span data-ttu-id="748fa-156">метка хранения Office 365 для назначения сайту и определение для нее набора политик защиты от потери данных;</span><span class="sxs-lookup"><span data-stu-id="748fa-156">The Office 365 retention label to assign to the site and the set of DLP policies for the label</span></span>
- <span data-ttu-id="748fa-157">параметры вложенной метки Azure Information Protection, которую пользователи применяют в отношении наиболее конфиденциальных цифровых активов, хранящихся на сайте.</span><span class="sxs-lookup"><span data-stu-id="748fa-157">The settings of an Azure Information Protection sub-label that users apply to highly sensitive digital assets stored in the site</span></span>

<span data-ttu-id="748fa-158">Как только эти параметры будут определены, вы сможете использовать их для настройки сайта на этапе 2.</span><span class="sxs-lookup"><span data-stu-id="748fa-158">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-an-isolated-sharepoint-online-site"></a><span data-ttu-id="748fa-159">Шаг 1. Изолированный сайт SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="748fa-159">Step 1: An isolated SharePoint Online site</span></span>

<span data-ttu-id="748fa-p104">Изолированным сайтом называется заблокированная версия сайта группы SharePoint Online. В отличие от параметров сайтов частных групп, устанавливаемых по умолчанию, настройка изолированных сайтов выполняется с целью предотвращения:</span><span class="sxs-lookup"><span data-stu-id="748fa-p104">The locked-down version of a SharePoint Online team site is known as an isolated site. Unlike the default settings of private team sites, isolated sites are configured to prevent:</span></span>

- <span data-ttu-id="748fa-162">доступа лиц, которые не являются участниками указанных групп;</span><span class="sxs-lookup"><span data-stu-id="748fa-162">Access to those who are not members of specified groups.</span></span>
- <span data-ttu-id="748fa-163">запроса на доступ;</span><span class="sxs-lookup"><span data-stu-id="748fa-163">The requesting of access.</span></span>
- <span data-ttu-id="748fa-164">несанкционированного предоставления разрешения на доступ текущими участниками указанных групп;</span><span class="sxs-lookup"><span data-stu-id="748fa-164">The unauthorized granting of access by current members of specified groups.</span></span>
- <span data-ttu-id="748fa-165">администрирования сайта путем получения доступа участниками группы.</span><span class="sxs-lookup"><span data-stu-id="748fa-165">Administration of the site by access group members.</span></span>

<span data-ttu-id="748fa-166">Надежность и безопасность сайтов групп SharePoint Online, которые содержат строго регулируемые активы, остается неизменной, кроме тех случаев, когда внесение изменений выполняется администратором сайта SharePoint.</span><span class="sxs-lookup"><span data-stu-id="748fa-166">The security of SharePoint Online team sites that contain highly regulated assets do not change unless done by a SharePoint administrator for the site.</span></span>

<span data-ttu-id="748fa-167">Чтобы определить наборы уровней разрешений, групп SharePoint, групп доступа и групп участников, см. дополнительные сведения в статье [Разработка изолированного сайта группы SharePoint Online](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site).</span><span class="sxs-lookup"><span data-stu-id="748fa-167">See [Design an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site) for the details to determine the set of permission levels, SharePoint groups, access groups, and group members.</span></span>

### <a name="step-2-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="748fa-168">Шаг 2. Метки хранения Office 365 и политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="748fa-168">Step 2: Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="748fa-169">Применяя к сайту группы SharePoint Online метки хранения Office 365, укажите заданный по умолчанию метод классификации всех цифровых активов, хранящихся на этом сайте.</span><span class="sxs-lookup"><span data-stu-id="748fa-169">When applied to a SharePoint Online team site, Office 365 retention labels provide a default method of classifying all digital assets stored on the site.</span></span>
 
<span data-ttu-id="748fa-170">В отношении сайтов SharePoint Online для жестко регламентированных данных необходимо определить, какую метку хранения Office 365 следует использовать.</span><span class="sxs-lookup"><span data-stu-id="748fa-170">For SharePoint Online sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="748fa-171">Вопросы проектирования меток Office 365 рассмотрены в статье [Классификация и метки Office 365](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="748fa-171">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="748fa-p105">Для защиты конфиденциальной информации и предотвращения ее случайного или преднамеренного разглашения используются политики защиты от потери данных. Дополнительные сведения о них см. в этом [обзоре](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span><span class="sxs-lookup"><span data-stu-id="748fa-p105">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="748fa-174">В отношении сайтов SharePoint Online для жестко регламентированных данных необходимо настроить политики защиты от потери данных для метки хранения Office 365, назначенной такому сайту. Это позволит блокировать пользователей, если они пытаются предоставить доступ к цифровым активам внешним пользователям.</span><span class="sxs-lookup"><span data-stu-id="748fa-174">For SharePoint Online sites for highly regulated data, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share digital assets with external users.</span></span> 

### <a name="step-3-your-azure-information-protection-sub-label"></a><span data-ttu-id="748fa-175">Шаг 3. Вложенная метка Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="748fa-175">Step 3: Your Azure Information Protection sub-label</span></span>

<span data-ttu-id="748fa-p106">Чтобы обеспечить шифрование и установить набор разрешений для наиболее конфиденциальных цифровых активов, пользователи должны применить метку Azure Information Protection с помощью одноименного клиента. Чтобы применить метки Azure Information Protection в отношении сайтов SharePoint Online для жестко регламентированных данных, необходимо настроить вложенную метку Azure Information Protection в политике области.</span><span class="sxs-lookup"><span data-stu-id="748fa-p106">To provide encryption and a set of permissions to your most sensitive digital assets, users must apply an Azure Information Protection label using the Azure Information Protection client. To use Azure Information Protection labels for SharePoint Online sites for highly regulated data, you must configure an Azure Information Protection sub-label in a scoped policy.</span></span> 

<span data-ttu-id="748fa-p107">Вложенная метка располагается под уже существующей. Например, можно создать вложенную метку отдела исследований и разработок под меткой "Строго конфиденциально". К подмножеству пользователей применяется только политика области. Для сайтов SharePoint Online для жестко регламентированных данных область представляет собой набор пользователей, являющихся участниками групп доступа к данному сайту.</span><span class="sxs-lookup"><span data-stu-id="748fa-p107">A sub-label exists under an existing label. For example, you can create a Research & Development sub-label under the Highly Confidential label. A scoped policy is one that applies only to a subset of users. For SharePoint Online sites for highly regulated data, the scope is the set of users that are members of the access groups for the site.</span></span>

<span data-ttu-id="748fa-p108">Параметры применяемой вложенной метки перемещаются вместе с активом. Даже если актив загружается и отправляется за пределы сайта, получить разрешение на его открытие могут только учетные записи пользователей, прошедшие проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="748fa-p108">The settings of the applied sub-label travel with the asset. Even if it is downloaded and shared outside the site, only authenticated user accounts that have permissions can open it.</span></span>

### <a name="design-results"></a><span data-ttu-id="748fa-184">Результаты проектирования</span><span class="sxs-lookup"><span data-stu-id="748fa-184">Design results</span></span>

<span data-ttu-id="748fa-185">Вы уже определили:</span><span class="sxs-lookup"><span data-stu-id="748fa-185">You have determined the following:</span></span>

- <span data-ttu-id="748fa-186">Набор групп SharePoint и уровни разрешений</span><span class="sxs-lookup"><span data-stu-id="748fa-186">The set of SharePoint groups and permission levels</span></span>
- <span data-ttu-id="748fa-187">Набор групп доступа и их участников для каждого уровня разрешений</span><span class="sxs-lookup"><span data-stu-id="748fa-187">The set of access groups and their members for each permission level</span></span>
- <span data-ttu-id="748fa-188">Соответствующую метку хранения Office 365 и политику защиты от потери данных, связанную с этой меткой</span><span class="sxs-lookup"><span data-stu-id="748fa-188">The appropriate Office 365 retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="748fa-189">Параметры вложенной метки Azure Information Protection, куда входят шифрование и разрешения</span><span class="sxs-lookup"><span data-stu-id="748fa-189">The settings of the Azure Information Protection sub-label that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="748fa-190">Этап 2. Настройка</span><span class="sxs-lookup"><span data-stu-id="748fa-190">Phase 2: Configure</span></span>

<span data-ttu-id="748fa-191">На этом этапе параметры, определенные на этапе 1, реализуются с целью создания сайта SharePoint Online для жестко регламентированных данных.</span><span class="sxs-lookup"><span data-stu-id="748fa-191">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint Online site for highly regulated data.</span></span>

### <a name="step-1-create-and-configure-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="748fa-192">Шаг 1. Создание и настройка изолированного сайта группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="748fa-192">Step 1: Create and configure an isolated SharePoint Online team site</span></span>

<span data-ttu-id="748fa-193">Используйте инструкции, изложенные в статье [Развертывание изолированного сайта группы SharePoint Online](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site), для:</span><span class="sxs-lookup"><span data-stu-id="748fa-193">Use the instructions in [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site) to:</span></span>

- <span data-ttu-id="748fa-194">создания и заполнения групп доступа для каждого уровня разрешений SharePoint, используемого на этом сайте;</span><span class="sxs-lookup"><span data-stu-id="748fa-194">Create and populate the access groups for each SharePoint permission level used on the site.</span></span>
- <span data-ttu-id="748fa-195">создания и настройки изолированного сайта группы.</span><span class="sxs-lookup"><span data-stu-id="748fa-195">Create and configure the isolated team site.</span></span>

### <a name="step-2-configure-the-site-for-an-office-365-retention-label-dlp-policy"></a><span data-ttu-id="748fa-196">Шаг 2. Настройка сайта для соблюдения политики защиты от потери данных метки хранения Office 365</span><span class="sxs-lookup"><span data-stu-id="748fa-196">Step 2: Configure the site for an Office 365 retention label DLP policy</span></span>

<span data-ttu-id="748fa-197">Используйте инструкции, изложенные в статье [Защита файлов SharePoint Online с помощью меток Office 365 и DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp), для:</span><span class="sxs-lookup"><span data-stu-id="748fa-197">Use the instructions in [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

- <span data-ttu-id="748fa-198">определения или создания метки хранения Office 365 и ее применения к изолированному сайту SharePoint Online;</span><span class="sxs-lookup"><span data-stu-id="748fa-198">Identify or create the Office 365 retention label and apply it to your isolated SharePoint Online site.</span></span>
- <span data-ttu-id="748fa-199">создания и настройки политики защиты от потери данных, которая блокирует пользователей, если они пытаются отправить цифровой актив с вашего сайта SharePoint Online за пределы организации.</span><span class="sxs-lookup"><span data-stu-id="748fa-199">Create and configure the DLP policy that blocks users when they attempt to share a digital asset on your SharePoint Online site outside the organization.</span></span>

### <a name="step-3-create-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="748fa-200">Шаг 3. Создание вложенной метки Azure Information Protection для сайта</span><span class="sxs-lookup"><span data-stu-id="748fa-200">Step 3: Create an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="748fa-201">Используйте инструкции, изложенные в статье [Защита файлов SharePoint Online с помощью Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection), для:</span><span class="sxs-lookup"><span data-stu-id="748fa-201">Use the instructions in [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection) to:</span></span> 

- <span data-ttu-id="748fa-202">создания и настройки вложенной метки Azure Information Protection в политике области;</span><span class="sxs-lookup"><span data-stu-id="748fa-202">Create and configure an Azure Information Protection sub-label in a scoped policy.</span></span>
- <span data-ttu-id="748fa-203">развертывания на компьютерах пользователя клиента Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="748fa-203">Deploy the Azure Information Protection client to user computers.</span></span>

### <a name="step-4-optional-create-a-team-for-the-highly-regulated-data"></a><span data-ttu-id="748fa-204">Шаг 4 (необязательный). Создание группы для жестко регламентированных данных</span><span class="sxs-lookup"><span data-stu-id="748fa-204">Step 4 (optional): Create a team for the highly regulated data</span></span>

<span data-ttu-id="748fa-p109">Если вы хотите создать группу для жестко регламентированных данных, сначала создайте сайт SharePoint Online для жестко регламентированных данных. В процессе создания исходного сайта частной группы SharePoint Online, укажите имя группы Office 365.</span><span class="sxs-lookup"><span data-stu-id="748fa-p109">If you want a team for highly regulated data, you first create a SharePoint Online site for highly regulated data. When you create the initial private SharePoint Online team site, you specify an Office 365 group name.</span></span>

<span data-ttu-id="748fa-207">По завершении полной настройки сайта SharePoint Online для жестко регламентированных данных следуйте инструкции ниже, чтобы преобразовать его в группу для жестко регламентированных данных.</span><span class="sxs-lookup"><span data-stu-id="748fa-207">After the SharePoint Online site for highly regulated data is fully configured, use these steps to convert it into a team for highly regulated data:</span></span>

1. <span data-ttu-id="748fa-208">Войдите в Office 365.</span><span class="sxs-lookup"><span data-stu-id="748fa-208">Sign in to Office 365.</span></span>
2. <span data-ttu-id="748fa-209">На вкладке **Microsoft Office** щелкните **Группы**.</span><span class="sxs-lookup"><span data-stu-id="748fa-209">From the **Microsoft Office Home** tab, click **Teams**.</span></span>
3. <span data-ttu-id="748fa-210">На вкладке **Microsoft Teams** в области **Присоединиться к или создать группу** щелкните **Создать группу**.</span><span class="sxs-lookup"><span data-stu-id="748fa-210">From the **Microsoft Teams** tab, in the **Join or create a team** pane, click **Create team**.</span></span>
4. <span data-ttu-id="748fa-211">В области **Создать свою группу** щелкните **Создать группу из существующей группы Office 365**.</span><span class="sxs-lookup"><span data-stu-id="748fa-211">In the **Create your team** pane, click **Create a team from an existing Office 365 group**.</span></span>
5. <span data-ttu-id="748fa-212">В списке групп Office 365 выберите название группы Office 365, которое соответствует сайту SharePoint Online для жестко регламентированных данных, а затем щелкните **Выбрать группу**.</span><span class="sxs-lookup"><span data-stu-id="748fa-212">In the list of Office 365 groups, select the name of the Office 365 group corresponding to the SharePoint Online site for highly regulated data, and then click **Choose team**.</span></span>

<span data-ttu-id="748fa-p110">Вкладка **Файлы** списков новых групп содержит папку **Общие** в области **Документы** соответствующего сайта SharePoint Online. Чтобы просмотреть остальные ресурсы сайта SharePoint Online для данной группы, щелкните многоточие, а затем выберите **Открыть в SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="748fa-p110">The **Files** tab of the new team lists the contents of the **General** folder of the **Documents** area of the corresponding SharePoint Online site. To see the rest of the resources of the SharePoint Online site for the team, click the ellipsis, and then click **Open in SharePoint**.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="748fa-215">Результаты настройки</span><span class="sxs-lookup"><span data-stu-id="748fa-215">Configuration results</span></span>

<span data-ttu-id="748fa-216">Вы настроили:</span><span class="sxs-lookup"><span data-stu-id="748fa-216">You have configured the following:</span></span>

- <span data-ttu-id="748fa-217">изолированный сайт SharePoint Online;</span><span class="sxs-lookup"><span data-stu-id="748fa-217">A SharePoint Online isolated site</span></span>
- <span data-ttu-id="748fa-218">метку хранения Office 365, назначенную изолированному сайту SharePoint Online;</span><span class="sxs-lookup"><span data-stu-id="748fa-218">An Office 365 retention label assigned to the SharePoint Online isolated site</span></span>
- <span data-ttu-id="748fa-219">политику защиты от потери данных для метки хранения Office 365;</span><span class="sxs-lookup"><span data-stu-id="748fa-219">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="748fa-220">вложенную метку Azure Information Protection для политики области, которую пользователи могут применить к наиболее конфиденциальным цифровым активам, хранящимся на сайте и которая выполняет шифрование актива, а также принудительно применяет разрешения;</span><span class="sxs-lookup"><span data-stu-id="748fa-220">An Azure Information Protection sub-label of a scoped policy that users can apply to the most sensitive digital assets stored in the site that encrypts the asset and enforces permissions</span></span>
- <span data-ttu-id="748fa-221">группу для жестко регламентированных данных на базе сайта SharePoint Online (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="748fa-221">If needed, a team for highly regulated data based on the SharePoint Online site</span></span>

## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="748fa-222">Этап 3. Внедрение среди пользователей</span><span class="sxs-lookup"><span data-stu-id="748fa-222">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="748fa-p111">Сайт или группа SharePoint Online для жестко регламентированных данных может защитить такие данные, только если регулярно используется для хранения конфиденциальных цифровых активов и доступа к ним. Этот этап является наиболее сложным, так как его реализация зависит от пользователей, которым придется отказаться от привычных способов хранения информации.</span><span class="sxs-lookup"><span data-stu-id="748fa-p111">A SharePoint Online site or team for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive digital assets. This is the hardest phase because it relies on users changing their ways.</span></span> 

<span data-ttu-id="748fa-225">Например, руководители организации, которые ранее хранили конфиденциальные файлы на USB-накопителях или в персональных облачных хранилищах, теперь будут вынуждены хранить их только на сайте или в группе SharePoint Online для жестко регламентированных данных.</span><span class="sxs-lookup"><span data-stu-id="748fa-225">For example, executives that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint Online site or team for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="748fa-226">Шаг 1. Обучение пользователей</span><span class="sxs-lookup"><span data-stu-id="748fa-226">Step 1: Train your users</span></span>

<span data-ttu-id="748fa-227">После завершения настройки обучите пользователей, входящих в группы доступа к сайту, рассказав им:</span><span class="sxs-lookup"><span data-stu-id="748fa-227">After completing your configuration, train the set of users who are members of the site access groups:</span></span>

- <span data-ttu-id="748fa-228">насколько важно использовать новый сайт или группу для защиты ценных активов, а также о последствиях утечки жестко регламентированных данных, таких как юридические последствия, штрафные санкции за несоблюдение нормативно-правовых актов, появление программ-шантажистов или потеря конкурентного преимущества;</span><span class="sxs-lookup"><span data-stu-id="748fa-228">On the importance of using the new site or team to protect valuable assets and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="748fa-229">как получить доступ к сайту и его активам;</span><span class="sxs-lookup"><span data-stu-id="748fa-229">How to access the site and its assets.</span></span>
- <span data-ttu-id="748fa-230">как создавать файлы на сайте и отправлять новые файлы, которые хранятся локально;</span><span class="sxs-lookup"><span data-stu-id="748fa-230">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="748fa-231">каким образом политика защиты от потери данных блокирует пользователей при попытке отправить файлы за пределы организации;</span><span class="sxs-lookup"><span data-stu-id="748fa-231">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="748fa-232">как использовать клиент Azure Information Protection чтобы с помощью настроенной вложенной метки присвоить метку наиболее конфиденциальным цифровым активам;</span><span class="sxs-lookup"><span data-stu-id="748fa-232">How to use the Azure Information Protection client to label the most sensitive digital assets with the configured sub-label.</span></span>
- <span data-ttu-id="748fa-233">как вложенная метка Azure Information Protection защищает актив даже в случае его утечки за пределы сайта или группы.</span><span class="sxs-lookup"><span data-stu-id="748fa-233">How the Azure Information Protection sub-label protects an asset even when it is leaked off the site or team.</span></span>

<span data-ttu-id="748fa-234">В программу такого обучения следует включить практические занятия, где пользователи смогут опробовать эти операции и ознакомиться с результатами.</span><span class="sxs-lookup"><span data-stu-id="748fa-234">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="748fa-235">Шаг 2. Проведение периодических проверок использования и файлов</span><span class="sxs-lookup"><span data-stu-id="748fa-235">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="748fa-236">Через несколько недель после обучения администратор SharePoint может выполнить следующие действия в отношении сайта или группы SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="748fa-236">In the weeks after training, the SharePoint administrator for the SharePoint Online site or team can:</span></span>

- <span data-ttu-id="748fa-237">проанализировать использование сайта или группы и сравнить результаты с требованиями к использованию;</span><span class="sxs-lookup"><span data-stu-id="748fa-237">Analyze usage for the site or team and compare it with usage expectations.</span></span>
- <span data-ttu-id="748fa-238">убедиться, что наиболее конфиденциальным файлы были надлежащим образом помечены с помощью вложенной метки Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="748fa-238">Verify that highly sensitive files have been properly labeled with the Azure Information Protection sub-label.</span></span>

<span data-ttu-id="748fa-239">При необходимости следует провести повторное обучение пользователей.</span><span class="sxs-lookup"><span data-stu-id="748fa-239">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="748fa-240">Результаты адаптации пользователей к новым требованиям</span><span class="sxs-lookup"><span data-stu-id="748fa-240">User adoption results</span></span>

<span data-ttu-id="748fa-241">Конфиденциальные цифровые активы хранятся только на сайтах или в группах SharePoint Online для жестко регламентированных данных. Пользователи выполнили настройку наиболее конфиденциальных активов с помощью вложенной метки Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="748fa-241">Sensitive digital assets are stored exclusively on SharePoint Online sites or teams for highly regulated data and that the most sensitive assets have the configured Azure Information Protection sub-label applied.</span></span>

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a><span data-ttu-id="748fa-242">Как корпорация Contoso выполнила развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="748fa-242">How the Contoso Corporation deployed Microsoft 365 Enterprise</span></span>

<span data-ttu-id="748fa-243">Корпорация Contoso — вымышленная показательная транснациональная промышленная компания-конгломерат с главным офисом в Париже.</span><span class="sxs-lookup"><span data-stu-id="748fa-243">The Contoso Corporation is a fictional but representative global manufacturing conglomerate with its headquarters in Paris, France.</span></span> <span data-ttu-id="748fa-244">Посмотрите, как корпорация Contoso разработала, настроила и внедрила [надежный сайт SharePoint Online](contoso-sharepoint-online-site-for-highly-confidential-assets.md) для исследовательских команд в Париже, Москве, Нью-Йорке, Пекине и Бангалоре.</span><span class="sxs-lookup"><span data-stu-id="748fa-244">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint Online site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="748fa-245">См. также</span><span class="sxs-lookup"><span data-stu-id="748fa-245">See also</span></span>

[<span data-ttu-id="748fa-246">Руководство по развертыванию</span><span class="sxs-lookup"><span data-stu-id="748fa-246">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="748fa-247">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="748fa-247">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="748fa-248">Защита сайтов SharePoint Online в среде разработки и тестирования</span><span class="sxs-lookup"><span data-stu-id="748fa-248">Secure SharePoint Online sites in a dev/test environment</span></span>](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-in-a-dev-test-environment)
