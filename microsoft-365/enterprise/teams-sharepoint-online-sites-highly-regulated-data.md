---
title: Сайты SharePoint для жестко регламентированных данных
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/04/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Создайте безопасный сайт группы SharePoint для хранения наиболее важных и конфиденциальных файлов.
ms.openlocfilehash: dc604870826075cee645dd466b82f908e1571339
ms.sourcegitcommit: e1ffb98ac8159d1dc814930fe388d3e37cbdc7e2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/05/2019
ms.locfileid: "37403194"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a><span data-ttu-id="5f1f9-103">Сайты SharePoint для жестко регламентированных данных</span><span class="sxs-lookup"><span data-stu-id="5f1f9-103">Microsoft Teams and SharePoint Online sites for highly regulated data</span></span>

<span data-ttu-id="5f1f9-104">*Этот сценарий применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="5f1f9-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="5f1f9-p101">Решение Microsoft 365 корпоративный содержит полный набор облачных служб, предназначенных для создания, хранения и защиты жестко регламентированных данных, хранящихся в файлах. К их числу относятся:</span><span class="sxs-lookup"><span data-stu-id="5f1f9-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, and secure your highly regulated data. This includes data that is:</span></span>

- <span data-ttu-id="5f1f9-107">данные, на которые распространяется действие региональных нормативных актов;</span><span class="sxs-lookup"><span data-stu-id="5f1f9-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="5f1f9-108">наиболее важные для предприятия данные, например коммерческие тайны, информация о финансовой деятельности или данные о персонале и стратегии организации.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

<span data-ttu-id="5f1f9-109">Облачный сценарий Microsoft 365 корпоративный, который соответствует такой бизнес-потребности предприятия, потребует от вас:</span><span class="sxs-lookup"><span data-stu-id="5f1f9-109">A Microsoft 365 Enterprise cloud-based scenario that meets this business need requires that you:</span></span>

- <span data-ttu-id="5f1f9-110">хранения файлов (документов, презентаций, электронных таблиц и т. д.) на сайте группы SharePoint;</span><span class="sxs-lookup"><span data-stu-id="5f1f9-110">Store digital assets (documents, slide decks, spreadsheets, etc.) in a SharePoint Online team site or in the Files tab of a Microsoft Teams team.</span></span>
- <span data-ttu-id="5f1f9-111">блокировки сайта, чтобы предотвратить:</span><span class="sxs-lookup"><span data-stu-id="5f1f9-111">Lock down the site or team to prevent:</span></span>
  - <span data-ttu-id="5f1f9-112">предоставление доступа пользователям, не являющимся участниками группы Office 365 для этого сайта;</span><span class="sxs-lookup"><span data-stu-id="5f1f9-112">Access to users who are not members of the Office 365 group for the site.</span></span>
  - <span data-ttu-id="5f1f9-113">предоставление участниками сайта доступа третьим лицам;</span><span class="sxs-lookup"><span data-stu-id="5f1f9-113">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="5f1f9-114">запросы на доступ к сайту от лиц, которые не являются участниками сайта;</span><span class="sxs-lookup"><span data-stu-id="5f1f9-114">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="5f1f9-115">настройки метки хранения Office 365 для сайтов SharePoint по умолчанию, чтобы блокировать пользователей при отправке файлов за пределы организации;</span><span class="sxs-lookup"><span data-stu-id="5f1f9-115">Configure an Office 365 retention label for your SharePoint sites as a default way to block users from sending files outside the organization.</span></span>
- <span data-ttu-id="5f1f9-116">шифрования наиболее конфиденциальных файлов сайта таким образом, чтобы файл оставался зашифрованным при перемещении;</span><span class="sxs-lookup"><span data-stu-id="5f1f9-116">Encrypt the most sensitive files of the site with encryption that travels with the file.</span></span>
- <span data-ttu-id="5f1f9-117">добавления разрешений к наиболее конфиденциальным файлам. Чтобы открыть такие файлы, даже если они будут доступны вне сайта, потребуются действительные учетные данные учетной записи пользователя с соответствующим разрешением. </span><span class="sxs-lookup"><span data-stu-id="5f1f9-117">Add permissions to the most sensitive digital assets so that if even if they get shared outside of the site, opening the asset still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="5f1f9-118">В приведенной ниже таблице сопоставляются требования этого сценария и функции Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-118">The following table maps the requirements of this scenario to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="5f1f9-119">**Требования**</span><span class="sxs-lookup"><span data-stu-id="5f1f9-119">**Requirement**</span></span> | <span data-ttu-id="5f1f9-120">**Функция Microsoft 365 корпоративный**</span><span class="sxs-lookup"><span data-stu-id="5f1f9-120">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="5f1f9-121">Хранение файлов</span><span class="sxs-lookup"><span data-stu-id="5f1f9-121">4. Store files online</span></span> | <span data-ttu-id="5f1f9-122">Сайты групп SharePoint</span><span class="sxs-lookup"><span data-stu-id="5f1f9-122">Sensitive SharePoint Online team sites</span></span> |
| <span data-ttu-id="5f1f9-123">Блокировка сайта</span><span class="sxs-lookup"><span data-stu-id="5f1f9-123">Lock down the site</span></span> | <span data-ttu-id="5f1f9-124">Разрешения для групп Azure Active Directory (Azure AD) и сайта группы SharePoint</span><span class="sxs-lookup"><span data-stu-id="5f1f9-124">Azure Active Directory (Azure AD) groups and SharePoint team site permissions</span></span> |
| <span data-ttu-id="5f1f9-125">Пометка файлов сайта</span><span class="sxs-lookup"><span data-stu-id="5f1f9-125">Label the digital assets of the site</span></span> | <span data-ttu-id="5f1f9-126">Метки хранения Office 365</span><span class="sxs-lookup"><span data-stu-id="5f1f9-126">Office 365 retention labels</span></span> |
| <span data-ttu-id="5f1f9-127">Блокирование пользователей при отправке файлов за пределы организации</span><span class="sxs-lookup"><span data-stu-id="5f1f9-127">Block users when sending files outside the organization</span></span> | <span data-ttu-id="5f1f9-128">Политики защиты от потери данных в Office 365</span><span class="sxs-lookup"><span data-stu-id="5f1f9-128">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="5f1f9-129">Шифрование всех файлов сайта</span><span class="sxs-lookup"><span data-stu-id="5f1f9-129">Encrypt all of the digital assets of the site</span></span> | <span data-ttu-id="5f1f9-130">Вложенные метки конфиденциальности Office 365</span><span class="sxs-lookup"><span data-stu-id="5f1f9-130">Office 365 sensitivity sublabels</span></span> |
| <span data-ttu-id="5f1f9-131">Добавление разрешений к файлам сайта</span><span class="sxs-lookup"><span data-stu-id="5f1f9-131">Add permissions to the digital assets of the site</span></span> | <span data-ttu-id="5f1f9-132">Вложенные метки конфиденциальности Office 365</span><span class="sxs-lookup"><span data-stu-id="5f1f9-132">Office 365 sensitivity sublabels</span></span> |
|||

<span data-ttu-id="5f1f9-133">Ниже приведена конфигурация безопасного сайта SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-133">Here is the configuration for a SharePoint Online site.</span></span>

![Сценарий сайтов SharePoint для жестко регламентированных данных](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="5f1f9-135">Этот сценарий требует, чтобы у вас уже были развернуты:</span><span class="sxs-lookup"><span data-stu-id="5f1f9-135">This scenario requires that you have already deployed:</span></span>

- <span data-ttu-id="5f1f9-136">этап [удостоверений](identity-infrastructure.md) и шаги 1 и 2 этапа [защиты информации](infoprotect-infrastructure.md) для базовой инфраструктуры;</span><span class="sxs-lookup"><span data-stu-id="5f1f9-136">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="5f1f9-137">[SharePoint](sharepoint-online-onedrive-workload.md).</span><span class="sxs-lookup"><span data-stu-id="5f1f9-137">SharePoint</span></span>

<span data-ttu-id="5f1f9-138">Описанные ниже поэтапные шаги помогут выполнить проектирование, настройку и внедрение сайтов SharePoint  для жестко регламентированных данных.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-138">The following phases step you through designing, configuring, and driving adoption for SharePoint Online sites and teams for highly regulated data.</span></span>

<span data-ttu-id="5f1f9-139">Чтобы узнать, как корпорация Contoso — вымышленная показательная транснациональная компания — разработала сайт SharePoint для исследовательских групп, см. [пример конфигурации](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span><span class="sxs-lookup"><span data-stu-id="5f1f9-139">To see how the Contoso Corporation, a fictional but representative multi-national organization, designed a SharePoint Online site for its research teams, see this [example configuration](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span></span>

## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="5f1f9-140">Необходимые компоненты для идентификации и доступа к устройству</span><span class="sxs-lookup"><span data-stu-id="5f1f9-140">Identity and device access prerequisites</span></span>

<span data-ttu-id="5f1f9-141">Чтобы защитить доступ к сайту SharePoint, убедитесь, что вы настроили [политики идентификации и доступа к устройству](identity-access-policies.md), а также [рекомендуемые политики доступа к SharePoint](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5f1f9-141">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="5f1f9-142">Этап 1. Проектирование</span><span class="sxs-lookup"><span data-stu-id="5f1f9-142">Phase 1: Design</span></span>

<span data-ttu-id="5f1f9-143">Чтобы создать сайт SharePoint для жестко регламентированных данных, сначала необходимо определить его назначение.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-143">To create a SharePoint site for highly regulated data, you must first identify its purpose.</span></span> <span data-ttu-id="5f1f9-144">Например, отделу исследований и разработок производственного предприятия сайт SharePoint необходим для хранения текущих проектных спецификаций существующих продуктов, а также для совместной работы над новыми продуктами.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-144">To create a SharePoint Online site or team for highly regulated data, you must first identify its purpose. For example, the research and development department of a manufacturing organization needs a SharePoint Online site to store current design specifications for existing products and a place to collaborate on new products. Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span> <span data-ttu-id="5f1f9-145">Доступ к сайту будет разрешен только членам отдела исследований и разработок и избранным руководителям.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-145">Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="5f1f9-146">Такое назначение сайта потребует определения основных элементов конфигурации, таких как:</span><span class="sxs-lookup"><span data-stu-id="5f1f9-146">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="5f1f9-147">метка хранения Office 365 для назначения разделу сайта "Документы" и набор политик защиты от потери данных для нее;</span><span class="sxs-lookup"><span data-stu-id="5f1f9-147">The Office 365 retention label to assign to the site and the set of DLP policies for the label</span></span>
- <span data-ttu-id="5f1f9-148">параметры вложенной метки конфиденциальности Office 365, которая применяется к высоко конфиденциальным файлам, хранящимся на сайте.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-148">The settings of an Office 365 sensitivity sublabel that users apply to highly sensitive files stored in the site</span></span>

<span data-ttu-id="5f1f9-149">Как только эти параметры будут определены, вы сможете использовать их для настройки сайта на этапе 2.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-149">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="5f1f9-150">Шаг 1. Метки хранения Office 365 и политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="5f1f9-150">Step 2: Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="5f1f9-151">При применении меток хранения Office 365 к разделу "Документы" сайта группы SharePoint указывается заданный по умолчанию метод классификации всех файлов, хранящихся на этом сайте.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-151">When applied to a SharePoint Online team site, Office 365 retention labels provide a default method of classifying all digital assets stored on the site.</span></span>
 
<span data-ttu-id="5f1f9-152">В отношении сайтов SharePoint для жестко регламентированных данных необходимо определить, какую метку хранения Office 365 следует использовать.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-152">For SharePoint Online sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="5f1f9-153">Вопросы проектирования меток Office 365 рассмотрены в статье [Классификация и метки Office 365](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="5f1f9-153">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="5f1f9-p103">Для защиты конфиденциальной информации и предотвращения ее случайного или преднамеренного разглашения используются политики защиты от потери данных. Дополнительные сведения о них см. в этом [обзоре](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span><span class="sxs-lookup"><span data-stu-id="5f1f9-p103">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="5f1f9-156">В отношении сайтов SharePoint для жестко регламентированных данных необходимо настроить политику защиты от потери данных для метки хранения Office 365, назначенной такому сайту. Это позволит блокировать пользователей при попытке предоставить доступ к файлам внешним пользователям.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-156">For SharePoint Online sites for highly regulated data, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share digital assets with external users.</span></span> 

### <a name="step-2-your-office-365-sensitivity-sublabel"></a><span data-ttu-id="5f1f9-157">Шаг 2. Вложенная метка конфиденциальности Office 365</span><span class="sxs-lookup"><span data-stu-id="5f1f9-157">Step 2: Your Office 365 sensitivity sublabel</span></span>

<span data-ttu-id="5f1f9-158">Чтобы обеспечить шифрование и набор разрешений для наиболее конфиденциальных файлов, нужно применить вложенную метку конфиденциальности Office 365.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-158">To provide encryption and a set of permissions to your most sensitive files, users must apply an Office 365 sensitivity sublabel.</span></span>

<span data-ttu-id="5f1f9-159">Вложенная метка существует в имеющейся метке.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-159">A sublabel exists under an existing label.</span></span> <span data-ttu-id="5f1f9-160">Например, вы можете создать вложенную метку "Исследования и разработки" для метки "Жестко регламентированные данные".</span><span class="sxs-lookup"><span data-stu-id="5f1f9-160">For example, you can create a Research & Development sublabel under the Highly Regulated label.</span></span> <span data-ttu-id="5f1f9-161">Разрешения для сайтов SharePoint для жестко регламентированных данных настраиваются таким образом, чтобы только участники сайта могли открывать и изменять файл, которому присвоена вложенная метка.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-161">For SharePoint sites for highly regulated data, you configure the permissions so that only site members can open and change the file to which the sublabel is attached.</span></span>

<span data-ttu-id="5f1f9-162">Параметры примененной вложенной метки сохраняются при перемещении файла.  </span><span class="sxs-lookup"><span data-stu-id="5f1f9-162">The settings of the applied sublabel travel with the file.</span></span> <span data-ttu-id="5f1f9-163">Даже в случае утечки за пределы сайта файл можно открыть только с помощью учетных записей пользователей, прошедших проверку подлинности, которые имеют разрешения.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-163">The settings of the applied sub-label travel with the asset. Even if it is downloaded and shared outside the site, only authenticated user accounts that have permissions can open it.</span></span>


### <a name="design-results"></a><span data-ttu-id="5f1f9-164">Результаты проектирования</span><span class="sxs-lookup"><span data-stu-id="5f1f9-164">Design results</span></span>

<span data-ttu-id="5f1f9-165">Вы уже определили:</span><span class="sxs-lookup"><span data-stu-id="5f1f9-165">You have determined the following:</span></span>

- <span data-ttu-id="5f1f9-166">соответствующую метку хранения Office 365 и политику защиты от потери данных, связанную с этой меткой;</span><span class="sxs-lookup"><span data-stu-id="5f1f9-166">The appropriate Office 365 retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="5f1f9-167">параметры вложенной метки конфиденциальности Office 365, в том числе шифрование и разрешения.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-167">The settings of the Office 365 sensitivity sublabel that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="5f1f9-168">Этап 2. Настройка</span><span class="sxs-lookup"><span data-stu-id="5f1f9-168">Phase 2: Configure</span></span>

<span data-ttu-id="5f1f9-169">На этом этапе параметры, определенные на этапе 1, реализуются с целью создания сайта SharePoint для жестко регламентированных данных.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-169">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint Online site for highly regulated data.</span></span>

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-office-365-group"></a><span data-ttu-id="5f1f9-170">Шаг 1. Создание частного сайта группы SharePoint владельцами и участниками соответствующей группы Office 365</span><span class="sxs-lookup"><span data-stu-id="5f1f9-170">Step 1: Create a private SharePoint team site with owners and members of the corresponding Office 365 group</span></span>

<span data-ttu-id="5f1f9-171">Чтобы создать частный сайт группы SharePoint, следуйте [инструкциям]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8).</span><span class="sxs-lookup"><span data-stu-id="5f1f9-171">Follow [these instructions]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) to create a private SharePoint team site.</span></span>

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a><span data-ttu-id="5f1f9-172">Шаг 2. Настройка параметров дополнительных разрешений для сайта группы SharePoint</span><span class="sxs-lookup"><span data-stu-id="5f1f9-172">Step 2: Configure additional permissions settings for the SharePoint team site</span></span>

<span data-ttu-id="5f1f9-173">Настройте параметры разрешений на сайте SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-173">From the SharePoint site, configure these permission settings.</span></span>

1.  <span data-ttu-id="5f1f9-174">На панели инструментов щелкните значок параметров и выберите вариант **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-174">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="5f1f9-175">В области **Разрешения для сайта** щелкните **Параметры дополнительных разрешений**.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-175">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
3.  <span data-ttu-id="5f1f9-176">На новой вкладке браузера **Разрешения** щелкните **Параметры запроса доступа**.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-176">On the new **Permissions** tab of your browser, click **Access Request Settings**.</span></span>
4.  <span data-ttu-id="5f1f9-177">В диалоговом окне **Параметры запросов на доступ** снимите флажки **Разрешить участникам совместный доступ к этому сайту, а также отдельным файлам и папкам** и **Разрешить запросы на доступ** (все три флажка должны быть сняты), а затем нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-177">In the **Access Requests Settings** dialog box, clear **Allow member to share the site and individual files and folders** and \*\*Allow access requests \*\*(so that all three check boxes are cleared), and then click **OK**.</span></span>

<span data-ttu-id="5f1f9-178">С помощью этих параметров можно отключить возможность предоставлять общий доступ к сайту другим пользователям для участников группы сайта, а также возможность запрашивать доступ к сайту для лиц, не являющихся участниками.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-178">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

### <a name="step-3-configure-the-site-for-an-office-365-retention-label"></a><span data-ttu-id="5f1f9-179">Шаг 3. Настройка сайта для использования метки хранения Office 365</span><span class="sxs-lookup"><span data-stu-id="5f1f9-179">Step 2: Configure the site for an Office 365 retention label</span></span>

<span data-ttu-id="5f1f9-180">Используйте инструкции, приведенные в статье [Защита файлов SharePoint с помощью меток Office 365 и политики защиты от потери данных](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp), для:</span><span class="sxs-lookup"><span data-stu-id="5f1f9-180">Use the instructions in [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="5f1f9-181">создания и публикации метки хранения для жестко регламентированных данных (при необходимости);</span><span class="sxs-lookup"><span data-stu-id="5f1f9-181">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="5f1f9-182">настройки сайта для использования метки хранения, созданной на шаге 1;</span><span class="sxs-lookup"><span data-stu-id="5f1f9-182">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="5f1f9-183">создания политики защиты от потери данных для жестко регламентированных данных, которая будет использовать метку хранения, созданную на шаге 2, и блокировать пользователей при отправке файлов за пределы организации.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-183">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span>

#### <a name="step-4-create-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="5f1f9-184">Шаг 4. Создание вложенной метки конфиденциальности Office 365 для сайта</span><span class="sxs-lookup"><span data-stu-id="5f1f9-184">Step 4: Create an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="5f1f9-185">В отличие от метки конфиденциальности для жестко регламентированных данных, которую любой пользователь может применить к любому файлу, защищенный сайт должен иметь собственную вложенную метку, чтобы файлы, которым она назначена:</span><span class="sxs-lookup"><span data-stu-id="5f1f9-185">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="5f1f9-186">были зашифрованы и оставались зашифрованными при перемещении;</span><span class="sxs-lookup"><span data-stu-id="5f1f9-186">Are encrypted and the encryption travels with the file.</span></span>
-   <span data-ttu-id="5f1f9-187">содержали настраиваемые разрешения, благодаря которым их могут открыть только участники группы сайта.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-187">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="5f1f9-188">Чтобы установить этот дополнительный уровень безопасности для файлов, хранящихся на сайте, необходимо настроить новую метку конфиденциальности, являющуюся вложенной меткой для общей метки файлов с жестко регламентированными данными.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-188">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label that is a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="5f1f9-189">Только участники группы сайта будут видеть ее в списке вложенных меток для метки жестко регламентированных данных.  </span><span class="sxs-lookup"><span data-stu-id="5f1f9-189">Only group members for the site will see it in the list of sublabels for the highly regulated label.</span></span>

<span data-ttu-id="5f1f9-190">Следуя инструкциям [здесь](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels), настройте вложенную метку для метки, которую вы используете для файлов с жестко регламентированными данными, со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="5f1f9-190">Use the instructions [here](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a sublabel of the label you are using for highly regulated files with the following settings:</span></span>

- <span data-ttu-id="5f1f9-191">имя вложенной метки должно содержать имя сайта, чтобы легко возникали ассоциации при ее назначении файлу;</span><span class="sxs-lookup"><span data-stu-id="5f1f9-191">The name of the sublabel contains the name of the site for easy association when assign the sublabel to a file.</span></span>
- <span data-ttu-id="5f1f9-192">необходимо включить шифрование;</span><span class="sxs-lookup"><span data-stu-id="5f1f9-192">Encryption is enabled.</span></span>
- <span data-ttu-id="5f1f9-193">группа сайта должна иметь разрешения на совместное редактирование.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-193">The site group has Co-Author permissions.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="5f1f9-194">Результаты настройки</span><span class="sxs-lookup"><span data-stu-id="5f1f9-194">Configuration results</span></span>

<span data-ttu-id="5f1f9-195">Вы настроили:</span><span class="sxs-lookup"><span data-stu-id="5f1f9-195">You have configured the following:</span></span>

- <span data-ttu-id="5f1f9-196">более строгие параметры разрешений на сайте SharePoint;</span><span class="sxs-lookup"><span data-stu-id="5f1f9-196">More restrictive permission settings on the SharePoint site</span></span>
- <span data-ttu-id="5f1f9-197">метку хранения Office 365, назначенную разделу "Документы" сайта SharePoint;</span><span class="sxs-lookup"><span data-stu-id="5f1f9-197">An Office 365 retention label assigned to the SharePoint Online isolated site</span></span>
- <span data-ttu-id="5f1f9-198">политику защиты от потери данных для метки хранения Office 365;</span><span class="sxs-lookup"><span data-stu-id="5f1f9-198">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="5f1f9-199">вложенную метку конфиденциальности Office 365, которую пользователи могут применить к наиболее конфиденциальным файлам, хранящимся на сайте. Эта метка шифрует файл и предоставляет доступ для совместного редактирования только участникам сайта группы.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-199">An Office 365 sensitivity sublabel that users can apply to the most sensitive files stored in the site that encrypts the file and only allows Co-Author access for members of the team site group</span></span> 

<span data-ttu-id="5f1f9-200">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-200">Here is the resulting configuration.</span></span>

![Сценарий сайтов SharePoint для жестко регламентированных данных](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)


<span data-ttu-id="5f1f9-202">Ниже показан пример применения вложенной метки конфиденциальности к файлу, хранящемуся на сайте.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-202">Here is an example of a user that has applied the sensitivity sublabel to a file stored in the site.</span></span>

![Сценарий сайтов SharePoint для жестко регламентированных данных](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="5f1f9-204">Этап 3. Внедрение среди пользователей</span><span class="sxs-lookup"><span data-stu-id="5f1f9-204">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="5f1f9-205">Сайт SharePoint для жестко регламентированных данных может защищать данные только в том случае, если он постоянно используется для хранения и доступа к конфиденциальным файлам.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-205">A SharePoint Online site or team for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive digital assets. This is the hardest phase because it relies on users changing their ways.</span></span> <span data-ttu-id="5f1f9-206">Это наиболее сложный этап, так как он предполагает изменение привычек и предпочтений пользователей. </span><span class="sxs-lookup"><span data-stu-id="5f1f9-206">This is the hardest phase because it relies on users changing their habits and preferences.</span></span> 

<span data-ttu-id="5f1f9-207">Например, сотрудники, которые ранее хранили конфиденциальные файлы на USB-накопителях или в личных облачных хранилищах, теперь будут вынуждены хранить их только на сайте SharePoint для жестко регламентированных данных.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-207">For example, executives that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint Online site or team for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="5f1f9-208">Шаг 1. Обучение пользователей</span><span class="sxs-lookup"><span data-stu-id="5f1f9-208">Step 1: Train your users</span></span>

<span data-ttu-id="5f1f9-209">После завершения настройки обучите пользователей, входящих в группы доступа к сайту, рассказав им:</span><span class="sxs-lookup"><span data-stu-id="5f1f9-209">After completing your configuration, train the set of users who are members of the site access groups:</span></span>

- <span data-ttu-id="5f1f9-210">насколько важно использовать новый сайт для защиты ценных файлов, а также о последствиях утечки жестко регламентированных данных, таких как юридические последствия, штрафные санкции за несоблюдение нормативно-правовых актов, появление программ-шантажистов или потеря конкурентного преимущества;</span><span class="sxs-lookup"><span data-stu-id="5f1f9-210">On the importance of using the new site or team to protect valuable assets and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="5f1f9-211">как получить доступ к сайту и его файлам;</span><span class="sxs-lookup"><span data-stu-id="5f1f9-211">How to access the site and its assets.</span></span>
- <span data-ttu-id="5f1f9-212">как создавать файлы на сайте и отправлять новые файлы, которые хранятся локально;</span><span class="sxs-lookup"><span data-stu-id="5f1f9-212">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="5f1f9-213">каким образом политика защиты от потери данных блокирует пользователей при попытке отправить файлы за пределы организации;</span><span class="sxs-lookup"><span data-stu-id="5f1f9-213">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="5f1f9-214">как пометить наиболее конфиденциальные файлы с помощью вложенной метки для сайта;</span><span class="sxs-lookup"><span data-stu-id="5f1f9-214">How to label the most sensitive files with the sublabel for the site.</span></span>
- <span data-ttu-id="5f1f9-215">как вложенная метка защищает файл даже в случае утечки с сайта.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-215">How the sublabel protects a file even when it is leaked off the site.</span></span>

<span data-ttu-id="5f1f9-216">В программу такого обучения следует включить практические занятия, где пользователи смогут опробовать эти операции и ознакомиться с результатами.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-216">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="5f1f9-217">Шаг 2. Проведение периодических проверок использования и файлов</span><span class="sxs-lookup"><span data-stu-id="5f1f9-217">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="5f1f9-218">Через несколько недель после обучения администратор SharePoint может выполнить следующие действия в отношении сайта SharePoint:</span><span class="sxs-lookup"><span data-stu-id="5f1f9-218">In the weeks after training, the SharePoint administrator for the SharePoint Online site or team can:</span></span>

- <span data-ttu-id="5f1f9-219">проанализировать использование сайта и сравнить результаты с требованиями к использованию;</span><span class="sxs-lookup"><span data-stu-id="5f1f9-219">Analyze usage for the site or team and compare it with usage expectations.</span></span>
- <span data-ttu-id="5f1f9-220">убедиться, что наиболее конфиденциальные файлы были надлежащим образом помечены с помощью вложенной метки конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-220">Verify that sensitive or highly regulated files have been properly labeled with the appropriate sensitivity label.</span></span>

<span data-ttu-id="5f1f9-221">При необходимости следует провести повторное обучение пользователей.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-221">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="5f1f9-222">Результаты адаптации пользователей к новым требованиям</span><span class="sxs-lookup"><span data-stu-id="5f1f9-222">User adoption results</span></span>

<span data-ttu-id="5f1f9-223">Файлы с жестко регламентированными данными хранятся только на сайтах SharePoint для жестко регламентированных данных, а к наиболее конфиденциальным файлам применяется вложенная метка конфиденциальности для сайта. </span><span class="sxs-lookup"><span data-stu-id="5f1f9-223">Highly regulated files are stored exclusively on SharePoint sites for highly regulated data and the most sensitive files have the sensitivity sublabel for the site applied.</span></span>

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a><span data-ttu-id="5f1f9-224">Как корпорация Contoso выполнила развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="5f1f9-224">How the Contoso Corporation deployed Microsoft 365 Enterprise</span></span>

<span data-ttu-id="5f1f9-225">Корпорация Contoso — вымышленная показательная транснациональная промышленная компания-конгломерат с главным офисом в Париже.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-225">The Contoso Corporation is a fictional but representative global manufacturing conglomerate with its headquarters in Paris, France.</span></span> <span data-ttu-id="5f1f9-226">Посмотрите, как корпорация Contoso разработала, настроила и внедрила [надежный сайт SharePoint](contoso-sharepoint-online-site-for-highly-confidential-assets.md) для исследовательских команд в Париже, Москве, Нью-Йорке, Пекине и Бангалоре.</span><span class="sxs-lookup"><span data-stu-id="5f1f9-226">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint Online site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="5f1f9-227">См. также</span><span class="sxs-lookup"><span data-stu-id="5f1f9-227">See also</span></span>

[<span data-ttu-id="5f1f9-228">Руководство по развертыванию</span><span class="sxs-lookup"><span data-stu-id="5f1f9-228">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="5f1f9-229">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="5f1f9-229">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

