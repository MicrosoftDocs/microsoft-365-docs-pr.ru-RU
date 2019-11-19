---
title: Сайты SharePoint для жестко регламентированных данных
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Создайте безопасный сайт группы SharePoint для хранения наиболее важных и конфиденциальных файлов.
ms.openlocfilehash: f8ccda85256e1f590f80a9302897e2950c59d154
ms.sourcegitcommit: 0ceb79a633f7004e82b80e69b6f7a7329ccec7ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699749"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a><span data-ttu-id="26482-103">Сайты SharePoint для жестко регламентированных данных</span><span class="sxs-lookup"><span data-stu-id="26482-103">SharePoint sites for highly regulated data</span></span>

<span data-ttu-id="26482-104">*Этот сценарий применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="26482-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="26482-p101">Решение Microsoft 365 корпоративный содержит полный набор облачных служб, предназначенных для создания, хранения и защиты жестко регламентированных данных, хранящихся в файлах, а также для управления ими. К их числу относятся:</span><span class="sxs-lookup"><span data-stu-id="26482-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, secure, and manage your highly regulated data stored in files. This includes data that is:</span></span>

- <span data-ttu-id="26482-107">данные, на которые распространяется действие региональных нормативных актов;</span><span class="sxs-lookup"><span data-stu-id="26482-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="26482-108">наиболее важные для предприятия данные, например коммерческие тайны, информация о финансовой деятельности или данные о персонале и стратегии организации.</span><span class="sxs-lookup"><span data-stu-id="26482-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

>[!Note]
> <span data-ttu-id="26482-109">Аналогичный сценарий с использованием Microsoft Teams представлен [здесь](secure-teams-highly-regulated-data-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="26482-109">A similar scenario using Microsoft Teams is [here](secure-teams-highly-regulated-data-scenario.md).</span></span>
>

<span data-ttu-id="26482-110">Облачный сценарий Microsoft 365 корпоративный, который соответствует такой бизнес-потребности предприятия, потребует от вас:</span><span class="sxs-lookup"><span data-stu-id="26482-110">A Microsoft 365 Enterprise cloud-based scenario that meets this business need requires that you:</span></span>

- <span data-ttu-id="26482-111">хранения файлов (документов, презентаций, электронных таблиц и т. д.) на сайте группы SharePoint;</span><span class="sxs-lookup"><span data-stu-id="26482-111">Store files (documents, slide decks, spreadsheets, etc.) in a SharePoint team site.</span></span>
- <span data-ttu-id="26482-112">блокировки сайта, чтобы предотвратить:</span><span class="sxs-lookup"><span data-stu-id="26482-112">Lock down the site to prevent:</span></span>
  - <span data-ttu-id="26482-113">предоставление доступа пользователям, не являющимся участниками группы Office 365 для этого сайта;</span><span class="sxs-lookup"><span data-stu-id="26482-113">Access to users who are not members of the Office 365 group for the site.</span></span>
  - <span data-ttu-id="26482-114">предоставление участниками сайта доступа третьим лицам;</span><span class="sxs-lookup"><span data-stu-id="26482-114">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="26482-115">запросы на доступ к сайту от лиц, которые не являются участниками сайта;</span><span class="sxs-lookup"><span data-stu-id="26482-115">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="26482-116">настройки метки хранения Office 365 для сайтов SharePoint по умолчанию, чтобы блокировать пользователей при отправке файлов за пределы организации;</span><span class="sxs-lookup"><span data-stu-id="26482-116">Configure an Office 365 retention label for your SharePoint sites as a default way to block users from sending files outside the organization.</span></span>
- <span data-ttu-id="26482-117">шифрования наиболее конфиденциальных файлов сайта таким образом, чтобы файл оставался зашифрованным при перемещении;</span><span class="sxs-lookup"><span data-stu-id="26482-117">Encrypt the most sensitive files of the site with encryption that travels with the file.</span></span>
- <span data-ttu-id="26482-118">добавления разрешений к наиболее конфиденциальным файлам. Чтобы открыть такие файлы, даже если они будут доступны вне сайта, потребуются действительные учетные данные учетной записи пользователя с соответствующим разрешением. </span><span class="sxs-lookup"><span data-stu-id="26482-118">Add permissions to the most sensitive files so that if even if they get shared outside of the site, opening the file still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="26482-119">В приведенной ниже таблице сопоставляются требования этого сценария и функции Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="26482-119">The following table maps the requirements of this scenario to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="26482-120">**Требования**</span><span class="sxs-lookup"><span data-stu-id="26482-120">**Requirement**</span></span> | <span data-ttu-id="26482-121">**Функция Microsoft 365 корпоративный**</span><span class="sxs-lookup"><span data-stu-id="26482-121">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="26482-122">Хранение файлов</span><span class="sxs-lookup"><span data-stu-id="26482-122">Store files</span></span> | <span data-ttu-id="26482-123">Сайты групп SharePoint</span><span class="sxs-lookup"><span data-stu-id="26482-123">SharePoint team sites</span></span> |
| <span data-ttu-id="26482-124">Блокировка сайта</span><span class="sxs-lookup"><span data-stu-id="26482-124">Lock down the site</span></span> | <span data-ttu-id="26482-125">Разрешения для групп Office 365 и сайта группы SharePoint</span><span class="sxs-lookup"><span data-stu-id="26482-125">Office 365 groups and SharePoint team site permissions</span></span> |
| <span data-ttu-id="26482-126">Пометка файлов сайта</span><span class="sxs-lookup"><span data-stu-id="26482-126">Label the files of the site</span></span> | <span data-ttu-id="26482-127">Метки хранения Office 365</span><span class="sxs-lookup"><span data-stu-id="26482-127">Office 365 retention labels</span></span> |
| <span data-ttu-id="26482-128">Блокирование пользователей при отправке файлов за пределы организации</span><span class="sxs-lookup"><span data-stu-id="26482-128">Block users when sending files outside the organization</span></span> | <span data-ttu-id="26482-129">Политики защиты от потери данных в Office 365</span><span class="sxs-lookup"><span data-stu-id="26482-129">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="26482-130">Шифрование всех файлов сайта</span><span class="sxs-lookup"><span data-stu-id="26482-130">Encrypt all of the files of the site</span></span> | <span data-ttu-id="26482-131">Метки или вложенные метки конфиденциальности Office 365</span><span class="sxs-lookup"><span data-stu-id="26482-131">Office 365 sensitivity labels or sublabels</span></span> |
| <span data-ttu-id="26482-132">Добавление разрешений к файлам сайта</span><span class="sxs-lookup"><span data-stu-id="26482-132">Add permissions to the files of the site</span></span> | <span data-ttu-id="26482-133">Метки или вложенные метки конфиденциальности Office 365</span><span class="sxs-lookup"><span data-stu-id="26482-133">Office 365 sensitivity labels or sublabels</span></span> |
|||

<span data-ttu-id="26482-134">Ниже приведен пример конфигурации безопасного сайта SharePoint.</span><span class="sxs-lookup"><span data-stu-id="26482-134">Here is an example configuration for a secure SharePoint site.</span></span>

![Сценарий сайтов SharePoint для жестко регламентированных данных](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="26482-136">Этот сценарий требует, чтобы у вас уже были развернуты:</span><span class="sxs-lookup"><span data-stu-id="26482-136">This scenario requires that you have already deployed:</span></span>

- <span data-ttu-id="26482-137">этап [удостоверений](identity-infrastructure.md) и шаги 1 и 2 этапа [защиты информации](infoprotect-infrastructure.md) для базовой инфраструктуры;</span><span class="sxs-lookup"><span data-stu-id="26482-137">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="26482-138">[SharePoint](sharepoint-online-onedrive-workload.md).</span><span class="sxs-lookup"><span data-stu-id="26482-138">[SharePoint](sharepoint-online-onedrive-workload.md).</span></span>

<span data-ttu-id="26482-139">Описанные ниже поэтапные шаги помогут выполнить проектирование, настройку и внедрение сайтов SharePoint  для жестко регламентированных данных.</span><span class="sxs-lookup"><span data-stu-id="26482-139">The following phases step you through designing, configuring, and driving adoption for SharePoint sites for highly regulated data.</span></span>

<a name="poster"></a> <span data-ttu-id="26482-140">Одностраничную сводку этого сценария см. на плакате [Сайты SharePoint для жестко регламентированных данных](./media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf).</span><span class="sxs-lookup"><span data-stu-id="26482-140">For a 1-page summary of this scenario, see the [SharePoint sites for highly regulated data poster](./media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf).</span></span>

<span data-ttu-id="26482-141">[Плакат ![Сайты SharePoint для жестко регламентированных данных](./media/teams-sharepoint-online-sites-highly-regulated-data/sharepoint-sites-highly-regulated-data-poster.png)](./media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)</span><span class="sxs-lookup"><span data-stu-id="26482-141">[![SharePoint sites for highly regulated data poster](./media/teams-sharepoint-online-sites-highly-regulated-data/sharepoint-sites-highly-regulated-data-poster.png)](./media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)</span></span>

<span data-ttu-id="26482-142">Вы также можете скачать этот плакат в формате [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf) или [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/teams-sharepoint-online-sites-highly-regulated-data/SharePoint-Sites-Highly-Regulated-Data.pptx) и распечатать его на бумаге размера letter, legal или tabloid (11 x 17).</span><span class="sxs-lookup"><span data-stu-id="26482-142">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf) or [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/teams-sharepoint-online-sites-highly-regulated-data/SharePoint-Sites-Highly-Regulated-Data.pptx) formats and print it on letter, legal, or tabloid (11 x 17)-sized paper.</span></span>


## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="26482-143">Необходимые компоненты для идентификации и доступа к устройству</span><span class="sxs-lookup"><span data-stu-id="26482-143">Identity and device access prerequisites</span></span>

<span data-ttu-id="26482-144">Чтобы защитить доступ к сайту SharePoint, убедитесь, что вы настроили [политики идентификации и доступа к устройству](identity-access-policies.md), а также [рекомендуемые политики доступа к SharePoint](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="26482-144">To protect access to the SharePoint site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="26482-145">Этап 1. Проектирование</span><span class="sxs-lookup"><span data-stu-id="26482-145">Phase 1: Design</span></span>

<span data-ttu-id="26482-146">Чтобы создать сайт SharePoint для жестко регламентированных данных, сначала необходимо определить его назначение.</span><span class="sxs-lookup"><span data-stu-id="26482-146">To create a SharePoint site for highly regulated data, you must first identify its purpose.</span></span> <span data-ttu-id="26482-147">Например, отделу исследований и разработок производственного предприятия сайт SharePoint необходим для хранения текущих проектных спецификаций существующих продуктов, а также для совместной работы над новыми продуктами.</span><span class="sxs-lookup"><span data-stu-id="26482-147">For example, the research and development department of a manufacturing organization needs a SharePoint site to store current design specifications for existing products and a place to collaborate on new products.</span></span> <span data-ttu-id="26482-148">Доступ к сайту будет разрешен только членам отдела исследований и разработок и избранным руководителям.</span><span class="sxs-lookup"><span data-stu-id="26482-148">Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="26482-149">Такое назначение сайта потребует определения основных элементов конфигурации, таких как:</span><span class="sxs-lookup"><span data-stu-id="26482-149">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="26482-150">метка хранения Office 365 для назначения разделу сайта "Документы" и набор политик защиты от потери данных для нее;</span><span class="sxs-lookup"><span data-stu-id="26482-150">The Office 365 retention label to assign to the Documents portion of the site and DLP policies for the label</span></span>
- <span data-ttu-id="26482-151">параметры вложенной метки конфиденциальности Office 365, которая применяется к высоко конфиденциальным файлам, хранящимся на сайте.</span><span class="sxs-lookup"><span data-stu-id="26482-151">The settings of an Office 365 sensitivity sublabel that users apply to highly sensitive files stored in the site</span></span>

<span data-ttu-id="26482-152">Как только эти параметры будут определены, вы сможете использовать их для настройки сайта на этапе 2.</span><span class="sxs-lookup"><span data-stu-id="26482-152">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="26482-153">Шаг 1. Метки хранения Office 365 и политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="26482-153">Step 1 Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="26482-154">При применении меток хранения Office 365 к разделу "Документы" сайта группы SharePoint указывается заданный по умолчанию метод классификации всех файлов, хранящихся на этом сайте.</span><span class="sxs-lookup"><span data-stu-id="26482-154">When applied to the Documents portion of a SharePoint team site, Office 365 retention labels provide a default method of classifying all files stored on the site.</span></span>
 
<span data-ttu-id="26482-155">В отношении сайтов SharePoint для жестко регламентированных данных необходимо определить, какую метку хранения Office 365 следует использовать.</span><span class="sxs-lookup"><span data-stu-id="26482-155">For SharePoint sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="26482-156">Вопросы проектирования меток Office 365 рассмотрены в статье [Классификация и метки Office 365](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="26482-156">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="26482-p103">Для защиты конфиденциальной информации и предотвращения ее случайного или преднамеренного разглашения используются политики защиты от потери данных. Дополнительные сведения о них см. в этом [обзоре](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span><span class="sxs-lookup"><span data-stu-id="26482-p103">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="26482-159">В отношении сайтов SharePoint для жестко регламентированных данных необходимо настроить политику защиты от потери данных для метки хранения Office 365, назначенной такому сайту. Это позволит блокировать пользователей при попытке предоставить доступ к файлам внешним пользователям.</span><span class="sxs-lookup"><span data-stu-id="26482-159">For SharePoint sites, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share files with external users.</span></span> 

### <a name="step-2-your-office-365-sensitivity-sublabel"></a><span data-ttu-id="26482-160">Шаг 2. Вложенная метка конфиденциальности Office 365</span><span class="sxs-lookup"><span data-stu-id="26482-160">Step 2: Your Office 365 sensitivity sublabel</span></span>

<span data-ttu-id="26482-161">Чтобы обеспечить шифрование и набор разрешений для наиболее конфиденциальных файлов, нужно применить метку или вложенную метку конфиденциальности Office 365.</span><span class="sxs-lookup"><span data-stu-id="26482-161">To provide encryption and a set of permissions to your most sensitive files, users must apply an Office 365 sensitivity label or sublabel.</span></span> <span data-ttu-id="26482-162">Вложенная метка существует в имеющейся метке.</span><span class="sxs-lookup"><span data-stu-id="26482-162">A sublabel exists under an existing label.</span></span> 

<span data-ttu-id="26482-163">Используйте метку конфиденциальности, если требуется небольшое число меток для общих и отдельных закрытых команд.</span><span class="sxs-lookup"><span data-stu-id="26482-163">Use a sensitivity label when you need is a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="26482-164">Используйте вложенную метку конфиденциальности, если у вас большое число меток или нужно упорядочить метки для безопасных сайтов под меткой строго регулируемых данных.</span><span class="sxs-lookup"><span data-stu-id="26482-164">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for secure sites the under your highly regulated label.</span></span> 

<span data-ttu-id="26482-165">Параметры примененной метки или вложенной метки сохраняются при перемещении файла.</span><span class="sxs-lookup"><span data-stu-id="26482-165">The settings of the applied label or sublabel travel with the file.</span></span> <span data-ttu-id="26482-166">Даже в случае утечки за пределы сайта файл можно открыть только с помощью учетных записей пользователей, прошедших проверку подлинности, которые имеют разрешения.</span><span class="sxs-lookup"><span data-stu-id="26482-166">Even if it is leaked outside the site, only authenticated user accounts that have permissions can open it.</span></span>

### <a name="design-results"></a><span data-ttu-id="26482-167">Результаты проектирования</span><span class="sxs-lookup"><span data-stu-id="26482-167">Design results</span></span>

<span data-ttu-id="26482-168">Вы уже определили:</span><span class="sxs-lookup"><span data-stu-id="26482-168">You have determined the following:</span></span>

- <span data-ttu-id="26482-169">соответствующую метку хранения Office 365 и политику защиты от потери данных, связанную с этой меткой;</span><span class="sxs-lookup"><span data-stu-id="26482-169">The appropriate Office 365 retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="26482-170">параметры вложенной метки конфиденциальности Office 365, в том числе шифрование и разрешения.</span><span class="sxs-lookup"><span data-stu-id="26482-170">The settings of the Office 365 sensitivity sublabel that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="26482-171">Этап 2. Настройка</span><span class="sxs-lookup"><span data-stu-id="26482-171">Phase 2: Configure</span></span>

<span data-ttu-id="26482-172">На этом этапе параметры, определенные на этапе 1, реализуются с целью создания сайта SharePoint для жестко регламентированных данных.</span><span class="sxs-lookup"><span data-stu-id="26482-172">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-office-365-group"></a><span data-ttu-id="26482-173">Шаг 1. Создание частного сайта группы SharePoint владельцами и участниками соответствующей группы Office 365</span><span class="sxs-lookup"><span data-stu-id="26482-173">Step 1: Create a private SharePoint team site with owners and members of the corresponding Office 365 group</span></span>

<span data-ttu-id="26482-174">Чтобы создать частный сайт группы SharePoint, следуйте [инструкциям]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8).</span><span class="sxs-lookup"><span data-stu-id="26482-174">Follow [these instructions]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) to create a private SharePoint team site.</span></span>

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a><span data-ttu-id="26482-175">Шаг 2. Настройка параметров дополнительных разрешений для сайта группы SharePoint</span><span class="sxs-lookup"><span data-stu-id="26482-175">Step 2: Configure additional permissions settings for the SharePoint team site</span></span>

<span data-ttu-id="26482-176">Настройте параметры разрешений на сайте SharePoint.</span><span class="sxs-lookup"><span data-stu-id="26482-176">From the SharePoint site, configure these permission settings.</span></span>

1. <span data-ttu-id="26482-177">На панели инструментов щелкните значок параметров и выберите вариант **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="26482-177">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="26482-178">В области **Разрешения для сайта** в разделе **Параметры общего доступа** щелкните **Изменить параметры общего доступа**.</span><span class="sxs-lookup"><span data-stu-id="26482-178">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="26482-179">В разделе **Разрешения на предоставление общего доступа** установите флажок **Только владельцы сайта могут делиться файлами, папками и сайтом**.</span><span class="sxs-lookup"><span data-stu-id="26482-179">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="26482-180">Отключите параметр **Разрешить запросы на доступ** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="26482-180">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="26482-181">С помощью этих параметров можно отключить возможность предоставлять общий доступ к сайту другим пользователям для участников группы сайта, а также возможность запрашивать доступ к сайту для лиц, не являющихся участниками.</span><span class="sxs-lookup"><span data-stu-id="26482-181">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

### <a name="step-3-configure-the-site-for-an-office-365-retention-label"></a><span data-ttu-id="26482-182">Шаг 3. Настройка сайта для использования метки хранения Office 365</span><span class="sxs-lookup"><span data-stu-id="26482-182">Step 3: Configure the site for an Office 365 retention label</span></span>

<span data-ttu-id="26482-183">Используйте инструкции, приведенные в статье [Защита файлов SharePoint с помощью меток Office 365 и политики защиты от потери данных](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp), для:</span><span class="sxs-lookup"><span data-stu-id="26482-183">Use the instructions in [Protect SharePoint files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="26482-184">создания и публикации метки хранения для жестко регламентированных данных (при необходимости);</span><span class="sxs-lookup"><span data-stu-id="26482-184">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="26482-185">настройки сайта для использования метки хранения, созданной на шаге 1;</span><span class="sxs-lookup"><span data-stu-id="26482-185">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="26482-186">создания политики защиты от потери данных для жестко регламентированных данных, которая будет использовать метку хранения, созданную на шаге 2, и блокировать пользователей при отправке файлов за пределы организации.</span><span class="sxs-lookup"><span data-stu-id="26482-186">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span>

#### <a name="step-4-create-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="26482-187">Шаг 4. Создание вложенной метки конфиденциальности Office 365 для сайта</span><span class="sxs-lookup"><span data-stu-id="26482-187">Step 4: Create an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="26482-188">В отличие от метки конфиденциальности для жестко регламентированных данных, которую любой пользователь может применить к любому файлу, защищенный сайт должен иметь собственную вложенную метку, чтобы файлы, которым она назначена:</span><span class="sxs-lookup"><span data-stu-id="26482-188">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="26482-189">были зашифрованы и оставались зашифрованными при перемещении;</span><span class="sxs-lookup"><span data-stu-id="26482-189">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="26482-190">содержали настраиваемые разрешения, благодаря которым их могут открыть только участники группы сайта.</span><span class="sxs-lookup"><span data-stu-id="26482-190">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="26482-191">Чтобы установить этот дополнительный уровень безопасности для файлов, хранящихся на сайте, необходимо настроить новую метку конфиденциальности или вложенную метку общей метки файлов с жестко регламентированными данными.</span><span class="sxs-lookup"><span data-stu-id="26482-191">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label or a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="26482-192">Только участники группы сайта будут видеть ее в списке вложенных меток для метки жестко регламентированных данных.  </span><span class="sxs-lookup"><span data-stu-id="26482-192">Only group members for the site will see it in the list of sublabels for the highly regulated label.</span></span>

<span data-ttu-id="26482-193">Следуя инструкциям [здесь](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels), настройте метку или вложенную метку для метки, используемой для файлов с жестко регламентированными данными, со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="26482-193">Use the instructions [here](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a label or a sublabel of the label you are using for highly regulated files with the following settings:</span></span>

- <span data-ttu-id="26482-194">имя метки или вложенной метки должно содержать имя сайта, чтобы легко возникали ассоциации при назначении метки или вложенной метки файлу;</span><span class="sxs-lookup"><span data-stu-id="26482-194">The name of the label or sublabel contains the name of the site for easy association when assigning the label or sublabel to a file.</span></span>
- <span data-ttu-id="26482-195">необходимо включить шифрование;</span><span class="sxs-lookup"><span data-stu-id="26482-195">Encryption is enabled.</span></span>
- <span data-ttu-id="26482-196">группа сайта должна иметь разрешения на совместное редактирование.</span><span class="sxs-lookup"><span data-stu-id="26482-196">The site group has Co-Author permissions.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="26482-197">Результаты настройки</span><span class="sxs-lookup"><span data-stu-id="26482-197">Configuration results</span></span>

<span data-ttu-id="26482-198">Вы настроили:</span><span class="sxs-lookup"><span data-stu-id="26482-198">You have configured the following:</span></span>

- <span data-ttu-id="26482-199">более строгие параметры разрешений на сайте SharePoint;</span><span class="sxs-lookup"><span data-stu-id="26482-199">More restrictive permission settings on the SharePoint site</span></span>
- <span data-ttu-id="26482-200">метку хранения Office 365, назначенную разделу "Документы" сайта SharePoint;</span><span class="sxs-lookup"><span data-stu-id="26482-200">An Office 365 retention label assigned to the Documents portion of the SharePoint site</span></span>
- <span data-ttu-id="26482-201">политику защиты от потери данных для метки хранения Office 365;</span><span class="sxs-lookup"><span data-stu-id="26482-201">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="26482-202">метку или вложенную метку конфиденциальности Office 365, которую пользователи могут применить к наиболее конфиденциальным файлам, хранящимся на сайте. Эта метка шифрует файл и предоставляет доступ для совместного редактирования только участникам группы сайта команды.</span><span class="sxs-lookup"><span data-stu-id="26482-202">An Office 365 sensitivity label or sublabel that users can apply to the most sensitive files stored in the site, which encrypts the file and only allows Co-Author access for members of the team site group</span></span> 

<span data-ttu-id="26482-203">Ниже представлена итоговая конфигурация, использующая вложенную метку для метки жестко регламентированных данных.</span><span class="sxs-lookup"><span data-stu-id="26482-203">Here is the resulting configuration that uses a sublabel of the Highly regulated label.</span></span>

![Сценарий сайтов SharePoint для жестко регламентированных данных](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="26482-205">Ниже показан пример применения вложенной метки к файлу, хранящемуся на сайте.</span><span class="sxs-lookup"><span data-stu-id="26482-205">Here is an example of a user that has applied the sublabel to a file stored in the site.</span></span>

![Сценарий сайтов SharePoint для жестко регламентированных данных](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="26482-207">Этап 3. Внедрение среди пользователей</span><span class="sxs-lookup"><span data-stu-id="26482-207">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="26482-208">Сайт SharePoint для жестко регламентированных данных может защищать данные только в том случае, если он постоянно используется для хранения и доступа к конфиденциальным файлам.</span><span class="sxs-lookup"><span data-stu-id="26482-208">A SharePoint site for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive files.</span></span> <span data-ttu-id="26482-209">Это наиболее сложный этап, так как он предполагает изменение привычек и предпочтений пользователей. </span><span class="sxs-lookup"><span data-stu-id="26482-209">This is the hardest phase because it relies on users changing their habits and preferences.</span></span> 

<span data-ttu-id="26482-210">Например, сотрудники, которые ранее хранили конфиденциальные файлы на USB-накопителях или в личных облачных хранилищах, теперь будут вынуждены хранить их только на сайте SharePoint для жестко регламентированных данных.</span><span class="sxs-lookup"><span data-stu-id="26482-210">For example, employees that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="26482-211">Шаг 1. Обучение пользователей</span><span class="sxs-lookup"><span data-stu-id="26482-211">Step 1: Train your users</span></span>

<span data-ttu-id="26482-212">После завершения настройки обучите пользователей, являющихся участниками сайта, рассказав им:</span><span class="sxs-lookup"><span data-stu-id="26482-212">After completing your configuration, train the set of users who are members of the site:</span></span>

- <span data-ttu-id="26482-213">насколько важно использовать новый сайт для защиты ценных файлов, а также о последствиях утечки жестко регламентированных данных, таких как юридические последствия, штрафные санкции за несоблюдение нормативно-правовых актов, появление программ-шантажистов или потеря конкурентного преимущества;</span><span class="sxs-lookup"><span data-stu-id="26482-213">On the importance of using the new site to protect valuable files and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="26482-214">как получить доступ к сайту и его файлам;</span><span class="sxs-lookup"><span data-stu-id="26482-214">How to access the site and its files.</span></span>
- <span data-ttu-id="26482-215">как создавать файлы на сайте и отправлять новые файлы, которые хранятся локально;</span><span class="sxs-lookup"><span data-stu-id="26482-215">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="26482-216">каким образом политика защиты от потери данных блокирует пользователей при попытке отправить файлы за пределы организации;</span><span class="sxs-lookup"><span data-stu-id="26482-216">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="26482-217">как пометить наиболее конфиденциальные файлы с помощью метки или вложенной метки для сайта;</span><span class="sxs-lookup"><span data-stu-id="26482-217">How to label the most sensitive files with the label or sublabel for the site.</span></span>
- <span data-ttu-id="26482-218">как метка или вложенная метка защищает файл даже в случае утечки с сайта.</span><span class="sxs-lookup"><span data-stu-id="26482-218">How the label or sublabel protects a file even when it is leaked off the site.</span></span>

<span data-ttu-id="26482-219">В программу такого обучения следует включить практические занятия, где пользователи смогут опробовать эти операции и ознакомиться с результатами.</span><span class="sxs-lookup"><span data-stu-id="26482-219">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="26482-220">Шаг 2. Проведение периодических проверок использования и файлов</span><span class="sxs-lookup"><span data-stu-id="26482-220">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="26482-221">Через несколько недель после обучения администратор SharePoint может выполнить следующие действия в отношении сайта SharePoint:</span><span class="sxs-lookup"><span data-stu-id="26482-221">In the weeks after training, the SharePoint administrator for the SharePoint site can:</span></span>

- <span data-ttu-id="26482-222">проанализировать использование сайта и сравнить результаты с требованиями к использованию;</span><span class="sxs-lookup"><span data-stu-id="26482-222">Analyze usage for the site and compare it with usage expectations.</span></span>
- <span data-ttu-id="26482-223">убедиться, что наиболее конфиденциальные файлы были надлежащим образом помечены с помощью метки или вложенной метки конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="26482-223">Verify that highly sensitive files have been properly labeled with the sensitivity label or sublabel.</span></span>

  <span data-ttu-id="26482-224">Вы можете узнать, каким файлам присвоены метки, просмотрев папку в SharePoint и добавив столбец **Конфиденциальность** с помощью параметра **Показать/скрыть столбцы** элемента **Добавить столбец**.</span><span class="sxs-lookup"><span data-stu-id="26482-224">You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>


<span data-ttu-id="26482-225">При необходимости следует провести повторное обучение пользователей.</span><span class="sxs-lookup"><span data-stu-id="26482-225">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="26482-226">Результаты адаптации пользователей к новым требованиям</span><span class="sxs-lookup"><span data-stu-id="26482-226">User adoption results</span></span>

<span data-ttu-id="26482-227">Файлы с жестко регламентированными данными хранятся только на сайтах SharePoint для жестко регламентированных данных, а к наиболее конфиденциальным файлам применяется метка или вложенная метка конфиденциальности для сайта.</span><span class="sxs-lookup"><span data-stu-id="26482-227">Highly regulated files are stored exclusively on SharePoint sites for highly regulated data and the most sensitive files have the sensitivity label or sublabel for the site applied.</span></span>

## <a name="how-the-contoso-corporation-used-a-sharepoint-site-for-highly-regulated-data"></a><span data-ttu-id="26482-228">Как корпорация Contoso использовала сайт SharePoint для строго регулируемых данных</span><span class="sxs-lookup"><span data-stu-id="26482-228">How the Contoso Corporation used a SharePoint site for highly regulated data</span></span>

<span data-ttu-id="26482-229">Корпорация Contoso — вымышленная показательная транснациональная промышленная компания-конгломерат.</span><span class="sxs-lookup"><span data-stu-id="26482-229">The Contoso Corporation is a fictional but representative global manufacturing conglomerate.</span></span> <span data-ttu-id="26482-230">Посмотрите, как корпорация Contoso разработала, настроила и внедрила [надежный сайт SharePoint](contoso-sharepoint-online-site-for-highly-confidential-assets.md) для исследовательских команд в Париже, Москве, Нью-Йорке, Пекине и Бангалоре.</span><span class="sxs-lookup"><span data-stu-id="26482-230">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="26482-231">См. также</span><span class="sxs-lookup"><span data-stu-id="26482-231">See also</span></span>

[<span data-ttu-id="26482-232">Teams для строго регулируемых данных</span><span class="sxs-lookup"><span data-stu-id="26482-232">Teams for highly regulated data</span></span>](secure-teams-highly-regulated-data-scenario.md)

[<span data-ttu-id="26482-233">Рабочие нагрузки и сценарии Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="26482-233">Microsoft 365 Enterprise workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="26482-234">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="26482-234">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="26482-235">Руководство по развертыванию</span><span class="sxs-lookup"><span data-stu-id="26482-235">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
