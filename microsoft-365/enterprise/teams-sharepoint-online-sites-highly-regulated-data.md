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
ms.openlocfilehash: ece6547ba596fe53c4f3b3f6bfbaa6570a724c6a
ms.sourcegitcommit: db580dc2626328d324f65c7380a5816a500688a7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2019
ms.locfileid: "37437829"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a><span data-ttu-id="e4a1e-103">Сайты SharePoint для жестко регламентированных данных</span><span class="sxs-lookup"><span data-stu-id="e4a1e-103">SharePoint sites for highly regulated data</span></span>

<span data-ttu-id="e4a1e-104">*Этот сценарий применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="e4a1e-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="e4a1e-p101">Решение Microsoft 365 корпоративный содержит полный набор облачных служб, предназначенных для создания, хранения и защиты жестко регламентированных данных, хранящихся в файлах, а также для управления ими. К их числу относятся:</span><span class="sxs-lookup"><span data-stu-id="e4a1e-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, and secure your highly regulated data stored in files. This includes data that is:</span></span>

- <span data-ttu-id="e4a1e-107">данные, на которые распространяется действие региональных нормативных актов;</span><span class="sxs-lookup"><span data-stu-id="e4a1e-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="e4a1e-108">наиболее важные для предприятия данные, например коммерческие тайны, информация о финансовой деятельности или данные о персонале и стратегии организации.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

>[!Note]
> <span data-ttu-id="e4a1e-109">Аналогичный сценарий с использованием Microsoft Teams находится в разработке.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-109">A similar scenario using Microsoft Teams is in development.</span></span>
>

<span data-ttu-id="e4a1e-110">Облачный сценарий Microsoft 365 корпоративный, который соответствует такой бизнес-потребности предприятия, потребует от вас:</span><span class="sxs-lookup"><span data-stu-id="e4a1e-110">A Microsoft 365 Enterprise cloud-based scenario that meets this business need requires that you:</span></span>

- <span data-ttu-id="e4a1e-111">хранения файлов (документов, презентаций, электронных таблиц и т. д.) на сайте группы SharePoint;</span><span class="sxs-lookup"><span data-stu-id="e4a1e-111">Store files (documents, slide decks, spreadsheets, etc.) in a SharePoint team site.</span></span>
- <span data-ttu-id="e4a1e-112">блокировки сайта, чтобы предотвратить:</span><span class="sxs-lookup"><span data-stu-id="e4a1e-112">Lock down the site to prevent:</span></span>
  - <span data-ttu-id="e4a1e-113">предоставление доступа пользователям, не являющимся участниками группы Office 365 для этого сайта;</span><span class="sxs-lookup"><span data-stu-id="e4a1e-113">Access to users who are not members of the Office 365 group for the site.</span></span>
  - <span data-ttu-id="e4a1e-114">предоставление участниками сайта доступа третьим лицам;</span><span class="sxs-lookup"><span data-stu-id="e4a1e-114">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="e4a1e-115">запросы на доступ к сайту от лиц, которые не являются участниками сайта;</span><span class="sxs-lookup"><span data-stu-id="e4a1e-115">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="e4a1e-116">настройки метки хранения Office 365 для сайтов SharePoint по умолчанию, чтобы блокировать пользователей при отправке файлов за пределы организации;</span><span class="sxs-lookup"><span data-stu-id="e4a1e-116">Configure an Office 365 retention label for your SharePoint sites as a default way to block users from sending files outside the organization.</span></span>
- <span data-ttu-id="e4a1e-117">шифрования наиболее конфиденциальных файлов сайта таким образом, чтобы файл оставался зашифрованным при перемещении;</span><span class="sxs-lookup"><span data-stu-id="e4a1e-117">Encrypt the most sensitive files of the site with encryption that travels with the file.</span></span>
- <span data-ttu-id="e4a1e-118">добавления разрешений к наиболее конфиденциальным файлам. Чтобы открыть такие файлы, даже если они будут доступны вне сайта, потребуются действительные учетные данные учетной записи пользователя с соответствующим разрешением. </span><span class="sxs-lookup"><span data-stu-id="e4a1e-118">Add permissions to the most sensitive files so that if even if they get shared outside of the site, opening the file still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="e4a1e-119">В приведенной ниже таблице сопоставляются требования этого сценария и функции Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-119">The following table maps the requirements of this scenario to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="e4a1e-120">**Требования**</span><span class="sxs-lookup"><span data-stu-id="e4a1e-120">**Requirement**</span></span> | <span data-ttu-id="e4a1e-121">**Функция Microsoft 365 корпоративный**</span><span class="sxs-lookup"><span data-stu-id="e4a1e-121">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="e4a1e-122">Хранение файлов</span><span class="sxs-lookup"><span data-stu-id="e4a1e-122">Store files</span></span> | <span data-ttu-id="e4a1e-123">Сайты групп SharePoint</span><span class="sxs-lookup"><span data-stu-id="e4a1e-123">SharePoint team sites</span></span> |
| <span data-ttu-id="e4a1e-124">Блокировка сайта</span><span class="sxs-lookup"><span data-stu-id="e4a1e-124">Lock down the site</span></span> | <span data-ttu-id="e4a1e-125">Разрешения для групп Azure Active Directory (Azure AD) и сайта группы SharePoint</span><span class="sxs-lookup"><span data-stu-id="e4a1e-125">Azure Active Directory (Azure AD) groups and SharePoint team site permissions</span></span> |
| <span data-ttu-id="e4a1e-126">Пометка файлов сайта</span><span class="sxs-lookup"><span data-stu-id="e4a1e-126">Label the files of the site</span></span> | <span data-ttu-id="e4a1e-127">Метки хранения Office 365</span><span class="sxs-lookup"><span data-stu-id="e4a1e-127">Office 365 retention labels</span></span> |
| <span data-ttu-id="e4a1e-128">Блокирование пользователей при отправке файлов за пределы организации</span><span class="sxs-lookup"><span data-stu-id="e4a1e-128">Block users when sending files outside the organization</span></span> | <span data-ttu-id="e4a1e-129">Политики защиты от потери данных в Office 365</span><span class="sxs-lookup"><span data-stu-id="e4a1e-129">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="e4a1e-130">Шифрование всех файлов сайта</span><span class="sxs-lookup"><span data-stu-id="e4a1e-130">Encrypt all of the files of the site</span></span> | <span data-ttu-id="e4a1e-131">Вложенные метки конфиденциальности Office 365</span><span class="sxs-lookup"><span data-stu-id="e4a1e-131">Office 365 sensitivity sublabels</span></span> |
| <span data-ttu-id="e4a1e-132">Добавление разрешений к файлам сайта</span><span class="sxs-lookup"><span data-stu-id="e4a1e-132">Add permissions to the files of the site</span></span> | <span data-ttu-id="e4a1e-133">Вложенные метки конфиденциальности Office 365</span><span class="sxs-lookup"><span data-stu-id="e4a1e-133">Office 365 sensitivity sublabels</span></span> |
|||

<span data-ttu-id="e4a1e-134">Ниже приведена конфигурация безопасного сайта SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-134">Here is the configuration for a secure SharePoint site.</span></span>

![Сценарий сайтов SharePoint для жестко регламентированных данных](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="e4a1e-136">Этот сценарий требует, чтобы у вас уже были развернуты:</span><span class="sxs-lookup"><span data-stu-id="e4a1e-136">This scenario requires that you have already deployed:</span></span>

- <span data-ttu-id="e4a1e-137">этап [удостоверений](identity-infrastructure.md) и шаги 1 и 2 этапа [защиты информации](infoprotect-infrastructure.md) для базовой инфраструктуры;</span><span class="sxs-lookup"><span data-stu-id="e4a1e-137">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="e4a1e-138">[SharePoint](sharepoint-online-onedrive-workload.md).</span><span class="sxs-lookup"><span data-stu-id="e4a1e-138">[SharePoint](sharepoint-online-onedrive-workload.md).</span></span>

<span data-ttu-id="e4a1e-139">Описанные ниже поэтапные шаги помогут выполнить проектирование, настройку и внедрение сайтов SharePoint  для жестко регламентированных данных.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-139">The following phases step you through designing, configuring, and driving adoption for SharePoint sites for highly regulated data.</span></span>

<span data-ttu-id="e4a1e-140">Чтобы узнать, как корпорация Contoso — вымышленная показательная транснациональная компания — разработала сайт SharePoint для исследовательских групп, см. [пример конфигурации](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span><span class="sxs-lookup"><span data-stu-id="e4a1e-140">To see how the Contoso Corporation, a fictional but representative multi-national organization, designed a SharePoint site for its research teams, see this [example configuration](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span></span>

## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="e4a1e-141">Необходимые компоненты для идентификации и доступа к устройству</span><span class="sxs-lookup"><span data-stu-id="e4a1e-141">Identity and device access prerequisites</span></span>

<span data-ttu-id="e4a1e-142">Чтобы защитить доступ к сайту SharePoint, убедитесь, что вы настроили [политики идентификации и доступа к устройству](identity-access-policies.md), а также [рекомендуемые политики доступа к SharePoint](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e4a1e-142">To protect access to the SharePoint site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="e4a1e-143">Этап 1. Проектирование</span><span class="sxs-lookup"><span data-stu-id="e4a1e-143">Phase 1: Design</span></span>

<span data-ttu-id="e4a1e-144">Чтобы создать сайт SharePoint для жестко регламентированных данных, сначала необходимо определить его назначение.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-144">To create a SharePoint site for highly regulated data, you must first identify its purpose.</span></span> <span data-ttu-id="e4a1e-145">Например, отделу исследований и разработок производственного предприятия сайт SharePoint необходим для хранения текущих проектных спецификаций существующих продуктов, а также для совместной работы над новыми продуктами.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-145">For example, the research and development department of a manufacturing organization needs a SharePoint site to store current design specifications for existing products and a place to collaborate on new products.</span></span> <span data-ttu-id="e4a1e-146">Доступ к сайту будет разрешен только членам отдела исследований и разработок и избранным руководителям.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-146">Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="e4a1e-147">Такое назначение сайта потребует определения основных элементов конфигурации, таких как:</span><span class="sxs-lookup"><span data-stu-id="e4a1e-147">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="e4a1e-148">метка хранения Office 365 для назначения разделу сайта "Документы" и набор политик защиты от потери данных для нее;</span><span class="sxs-lookup"><span data-stu-id="e4a1e-148">The Office 365 retention label to assign to the Documents portion of the site and DLP policies for the label</span></span>
- <span data-ttu-id="e4a1e-149">параметры вложенной метки конфиденциальности Office 365, которая применяется к высоко конфиденциальным файлам, хранящимся на сайте.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-149">The settings of an Office 365 sensitivity sublabel that users apply to highly sensitive files stored in the site</span></span>

<span data-ttu-id="e4a1e-150">Как только эти параметры будут определены, вы сможете использовать их для настройки сайта на этапе 2.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-150">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="e4a1e-151">Шаг 1. Метки хранения Office 365 и политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="e4a1e-151">Step 1 Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="e4a1e-152">При применении меток хранения Office 365 к разделу "Документы" сайта группы SharePoint указывается заданный по умолчанию метод классификации всех файлов, хранящихся на этом сайте.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-152">When applied to the Documents portion of a SharePoint team site, Office 365 retention labels provide a default method of classifying all files stored on the site.</span></span>
 
<span data-ttu-id="e4a1e-153">В отношении сайтов SharePoint для жестко регламентированных данных необходимо определить, какую метку хранения Office 365 следует использовать.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-153">For SharePoint sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="e4a1e-154">Вопросы проектирования меток Office 365 рассмотрены в статье [Классификация и метки Office 365](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="e4a1e-154">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="e4a1e-p103">Для защиты конфиденциальной информации и предотвращения ее случайного или преднамеренного разглашения используются политики защиты от потери данных. Дополнительные сведения о них см. в этом [обзоре](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span><span class="sxs-lookup"><span data-stu-id="e4a1e-p103">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="e4a1e-157">В отношении сайтов SharePoint для жестко регламентированных данных необходимо настроить политику защиты от потери данных для метки хранения Office 365, назначенной такому сайту. Это позволит блокировать пользователей при попытке предоставить доступ к файлам внешним пользователям.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-157">For SharePoint sites, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share files with external users.</span></span> 

### <a name="step-2-your-office-365-sensitivity-sublabel"></a><span data-ttu-id="e4a1e-158">Шаг 2. Вложенная метка конфиденциальности Office 365</span><span class="sxs-lookup"><span data-stu-id="e4a1e-158">Step 2: Your Office 365 sensitivity sublabel</span></span>

<span data-ttu-id="e4a1e-159">Чтобы обеспечить шифрование и набор разрешений для наиболее конфиденциальных файлов, нужно применить вложенную метку конфиденциальности Office 365.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-159">To provide encryption and a set of permissions to your most sensitive files, users must apply an Office 365 sensitivity sublabel.</span></span>

<span data-ttu-id="e4a1e-160">Вложенная метка существует в имеющейся метке.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-160">A sublabel exists under an existing label.</span></span> <span data-ttu-id="e4a1e-161">Например, вы можете создать вложенную метку "Исследования и разработки" для метки "Жестко регламентированные данные".</span><span class="sxs-lookup"><span data-stu-id="e4a1e-161">For example, you can create a Research & Development sublabel under the Highly Regulated label.</span></span> <span data-ttu-id="e4a1e-162">Разрешения для сайтов SharePoint для жестко регламентированных данных настраиваются таким образом, чтобы только участники сайта могли открывать и изменять файл, которому присвоена вложенная метка.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-162">For SharePoint sites for highly regulated data, you configure the permissions so that only site members can open and change the file to which the sublabel is attached.</span></span>

<span data-ttu-id="e4a1e-163">Параметры примененной вложенной метки сохраняются при перемещении файла.  </span><span class="sxs-lookup"><span data-stu-id="e4a1e-163">The settings of the applied sublabel travel with the file.</span></span> <span data-ttu-id="e4a1e-164">Даже в случае утечки за пределы сайта файл можно открыть только с помощью учетных записей пользователей, прошедших проверку подлинности, которые имеют разрешения.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-164">Even if it is leaked outside the site, only authenticated user accounts that have permissions can open it.</span></span>


### <a name="design-results"></a><span data-ttu-id="e4a1e-165">Результаты проектирования</span><span class="sxs-lookup"><span data-stu-id="e4a1e-165">Design results</span></span>

<span data-ttu-id="e4a1e-166">Вы уже определили:</span><span class="sxs-lookup"><span data-stu-id="e4a1e-166">You have determined the following:</span></span>

- <span data-ttu-id="e4a1e-167">соответствующую метку хранения Office 365 и политику защиты от потери данных, связанную с этой меткой;</span><span class="sxs-lookup"><span data-stu-id="e4a1e-167">The appropriate Office 365 retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="e4a1e-168">параметры вложенной метки конфиденциальности Office 365, в том числе шифрование и разрешения.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-168">The settings of the Office 365 sensitivity sublabel that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="e4a1e-169">Этап 2. Настройка</span><span class="sxs-lookup"><span data-stu-id="e4a1e-169">Phase 2: Configure</span></span>

<span data-ttu-id="e4a1e-170">На этом этапе параметры, определенные на этапе 1, реализуются с целью создания сайта SharePoint для жестко регламентированных данных.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-170">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-office-365-group"></a><span data-ttu-id="e4a1e-171">Шаг 1. Создание частного сайта группы SharePoint владельцами и участниками соответствующей группы Office 365</span><span class="sxs-lookup"><span data-stu-id="e4a1e-171">Step 1: Create a private SharePoint team site with owners and members of the corresponding Office 365 group</span></span>

<span data-ttu-id="e4a1e-172">Чтобы создать частный сайт группы SharePoint, следуйте [инструкциям]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8).</span><span class="sxs-lookup"><span data-stu-id="e4a1e-172">Follow [these instructions]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) to create a private SharePoint team site.</span></span>

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a><span data-ttu-id="e4a1e-173">Шаг 2. Настройка параметров дополнительных разрешений для сайта группы SharePoint</span><span class="sxs-lookup"><span data-stu-id="e4a1e-173">Step 2: Configure additional permissions settings for the SharePoint team site</span></span>

<span data-ttu-id="e4a1e-174">Настройте параметры разрешений на сайте SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-174">From the SharePoint site, configure these permission settings.</span></span>

1.  <span data-ttu-id="e4a1e-175">На панели инструментов щелкните значок параметров и выберите вариант **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-175">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="e4a1e-176">В области **Разрешения для сайта** щелкните **Параметры дополнительных разрешений**.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-176">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
3.  <span data-ttu-id="e4a1e-177">На новой вкладке браузера **Разрешения** щелкните **Параметры запроса доступа**.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-177">On the new **Permissions** tab of your browser, click **Access Request Settings**.</span></span>
4.  <span data-ttu-id="e4a1e-178">В диалоговом окне **Параметры запросов на доступ** снимите флажки **Разрешить участникам совместный доступ к этому сайту, а также отдельным файлам и папкам** и **Разрешить запросы на доступ** (все три флажка должны быть сняты), а затем нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-178">In the **Access Requests Settings** dialog box, clear **Allow member to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>

<span data-ttu-id="e4a1e-179">С помощью этих параметров можно отключить возможность предоставлять общий доступ к сайту другим пользователям для участников группы сайта, а также возможность запрашивать доступ к сайту для лиц, не являющихся участниками.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-179">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

### <a name="step-3-configure-the-site-for-an-office-365-retention-label"></a><span data-ttu-id="e4a1e-180">Шаг 3. Настройка сайта для использования метки хранения Office 365</span><span class="sxs-lookup"><span data-stu-id="e4a1e-180">Step 3: Configure the site for an Office 365 retention label</span></span>

<span data-ttu-id="e4a1e-181">Используйте инструкции, приведенные в статье [Защита файлов SharePoint с помощью меток Office 365 и политики защиты от потери данных](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp), для:</span><span class="sxs-lookup"><span data-stu-id="e4a1e-181">Use the instructions in [Protect SharePoint files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="e4a1e-182">создания и публикации метки хранения для жестко регламентированных данных (при необходимости);</span><span class="sxs-lookup"><span data-stu-id="e4a1e-182">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="e4a1e-183">настройки сайта для использования метки хранения, созданной на шаге 1;</span><span class="sxs-lookup"><span data-stu-id="e4a1e-183">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="e4a1e-184">создания политики защиты от потери данных для жестко регламентированных данных, которая будет использовать метку хранения, созданную на шаге 2, и блокировать пользователей при отправке файлов за пределы организации.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-184">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span>

#### <a name="step-4-create-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="e4a1e-185">Шаг 4. Создание вложенной метки конфиденциальности Office 365 для сайта</span><span class="sxs-lookup"><span data-stu-id="e4a1e-185">Step 4: Create an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="e4a1e-186">В отличие от метки конфиденциальности для жестко регламентированных данных, которую любой пользователь может применить к любому файлу, защищенный сайт должен иметь собственную вложенную метку, чтобы файлы, которым она назначена:</span><span class="sxs-lookup"><span data-stu-id="e4a1e-186">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="e4a1e-187">были зашифрованы и оставались зашифрованными при перемещении;</span><span class="sxs-lookup"><span data-stu-id="e4a1e-187">Are encrypted and the encryption travels with the file.</span></span>
-   <span data-ttu-id="e4a1e-188">содержали настраиваемые разрешения, благодаря которым их могут открыть только участники группы сайта.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-188">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="e4a1e-189">Чтобы установить этот дополнительный уровень безопасности для файлов, хранящихся на сайте, необходимо настроить новую метку конфиденциальности, являющуюся вложенной меткой для общей метки файлов с жестко регламентированными данными.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-189">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label that is a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="e4a1e-190">Только участники группы сайта будут видеть ее в списке вложенных меток для метки жестко регламентированных данных.  </span><span class="sxs-lookup"><span data-stu-id="e4a1e-190">Only group members for the site will see it in the list of sublabels for the highly regulated label.</span></span>

<span data-ttu-id="e4a1e-191">Следуя инструкциям [здесь](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels), настройте вложенную метку для метки, которую вы используете для файлов с жестко регламентированными данными, со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="e4a1e-191">Use the instructions [here](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a sublabel of the label you are using for highly regulated files with the following settings:</span></span>

- <span data-ttu-id="e4a1e-192">имя вложенной метки должно содержать имя сайта, чтобы легко возникали ассоциации при ее назначении файлу;</span><span class="sxs-lookup"><span data-stu-id="e4a1e-192">The name of the sublabel contains the name of the site for easy association when assign the sublabel to a file.</span></span>
- <span data-ttu-id="e4a1e-193">необходимо включить шифрование;</span><span class="sxs-lookup"><span data-stu-id="e4a1e-193">Encryption is enabled.</span></span>
- <span data-ttu-id="e4a1e-194">группа сайта должна иметь разрешения на совместное редактирование.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-194">The site group has Co-Author permissions.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="e4a1e-195">Результаты настройки</span><span class="sxs-lookup"><span data-stu-id="e4a1e-195">Configuration results</span></span>

<span data-ttu-id="e4a1e-196">Вы настроили:</span><span class="sxs-lookup"><span data-stu-id="e4a1e-196">You have configured the following:</span></span>

- <span data-ttu-id="e4a1e-197">более строгие параметры разрешений на сайте SharePoint;</span><span class="sxs-lookup"><span data-stu-id="e4a1e-197">More restrictive permission settings on the SharePoint site</span></span>
- <span data-ttu-id="e4a1e-198">метку хранения Office 365, назначенную разделу "Документы" сайта SharePoint;</span><span class="sxs-lookup"><span data-stu-id="e4a1e-198">An Office 365 retention label assigned to the Documents portion of the SharePoint site</span></span>
- <span data-ttu-id="e4a1e-199">политику защиты от потери данных для метки хранения Office 365;</span><span class="sxs-lookup"><span data-stu-id="e4a1e-199">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="e4a1e-200">вложенную метку конфиденциальности Office 365, которую пользователи могут применить к наиболее конфиденциальным файлам, хранящимся на сайте. Эта метка шифрует файл и предоставляет доступ для совместного редактирования только участникам сайта группы.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-200">An Office 365 sensitivity sublabel that users can apply to the most sensitive files stored in the site that encrypts the file and only allows Co-Author access for members of the team site group</span></span> 

<span data-ttu-id="e4a1e-201">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-201">Here is the resulting configuration.</span></span>

![Сценарий сайтов SharePoint для жестко регламентированных данных](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)


<span data-ttu-id="e4a1e-203">Ниже показан пример применения вложенной метки конфиденциальности к файлу, хранящемуся на сайте.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-203">Here is an example of a user that has applied the sensitivity sublabel to a file stored in the site.</span></span>

![Сценарий сайтов SharePoint для жестко регламентированных данных](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="e4a1e-205">Этап 3. Внедрение среди пользователей</span><span class="sxs-lookup"><span data-stu-id="e4a1e-205">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="e4a1e-206">Сайт SharePoint для жестко регламентированных данных может защищать данные только в том случае, если он постоянно используется для хранения и доступа к конфиденциальным файлам.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-206">A SharePoint site for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive files.</span></span> <span data-ttu-id="e4a1e-207">Это наиболее сложный этап, так как он предполагает изменение привычек и предпочтений пользователей. </span><span class="sxs-lookup"><span data-stu-id="e4a1e-207">This is the hardest phase because it relies on users changing their habits and preferences.</span></span> 

<span data-ttu-id="e4a1e-208">Например, сотрудники, которые ранее хранили конфиденциальные файлы на USB-накопителях или в личных облачных хранилищах, теперь будут вынуждены хранить их только на сайте SharePoint для жестко регламентированных данных.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-208">For example, employees that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="e4a1e-209">Шаг 1. Обучение пользователей</span><span class="sxs-lookup"><span data-stu-id="e4a1e-209">Step 1: Train your users</span></span>

<span data-ttu-id="e4a1e-210">После завершения настройки обучите пользователей, входящих в группы доступа к сайту, рассказав им:</span><span class="sxs-lookup"><span data-stu-id="e4a1e-210">After completing your configuration, train the set of users who are members of the site access groups:</span></span>

- <span data-ttu-id="e4a1e-211">насколько важно использовать новый сайт для защиты ценных файлов, а также о последствиях утечки жестко регламентированных данных, таких как юридические последствия, штрафные санкции за несоблюдение нормативно-правовых актов, появление программ-шантажистов или потеря конкурентного преимущества;</span><span class="sxs-lookup"><span data-stu-id="e4a1e-211">On the importance of using the new site to protect valuable files and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="e4a1e-212">как получить доступ к сайту и его файлам;</span><span class="sxs-lookup"><span data-stu-id="e4a1e-212">How to access the site and its files.</span></span>
- <span data-ttu-id="e4a1e-213">как создавать файлы на сайте и отправлять новые файлы, которые хранятся локально;</span><span class="sxs-lookup"><span data-stu-id="e4a1e-213">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="e4a1e-214">каким образом политика защиты от потери данных блокирует пользователей при попытке отправить файлы за пределы организации;</span><span class="sxs-lookup"><span data-stu-id="e4a1e-214">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="e4a1e-215">как пометить наиболее конфиденциальные файлы с помощью вложенной метки для сайта;</span><span class="sxs-lookup"><span data-stu-id="e4a1e-215">How to label the most sensitive files with the sublabel for the site.</span></span>
- <span data-ttu-id="e4a1e-216">как вложенная метка защищает файл даже в случае утечки с сайта.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-216">How the sublabel protects a file even when it is leaked off the site.</span></span>

<span data-ttu-id="e4a1e-217">В программу такого обучения следует включить практические занятия, где пользователи смогут опробовать эти операции и ознакомиться с результатами.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-217">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="e4a1e-218">Шаг 2. Проведение периодических проверок использования и файлов</span><span class="sxs-lookup"><span data-stu-id="e4a1e-218">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="e4a1e-219">Через несколько недель после обучения администратор SharePoint может выполнить следующие действия в отношении сайта SharePoint:</span><span class="sxs-lookup"><span data-stu-id="e4a1e-219">In the weeks after training, the SharePoint administrator for the SharePoint site can:</span></span>

- <span data-ttu-id="e4a1e-220">проанализировать использование сайта и сравнить результаты с требованиями к использованию;</span><span class="sxs-lookup"><span data-stu-id="e4a1e-220">Analyze usage for the site and compare it with usage expectations.</span></span>
- <span data-ttu-id="e4a1e-221">убедиться, что наиболее конфиденциальные файлы были надлежащим образом помечены с помощью вложенной метки конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-221">Verify that highly sensitive files have been properly labeled with the sensitivity sublabel.</span></span>

<span data-ttu-id="e4a1e-222">При необходимости следует провести повторное обучение пользователей.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-222">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="e4a1e-223">Результаты адаптации пользователей к новым требованиям</span><span class="sxs-lookup"><span data-stu-id="e4a1e-223">User adoption results</span></span>

<span data-ttu-id="e4a1e-224">Файлы с жестко регламентированными данными хранятся только на сайтах SharePoint для жестко регламентированных данных, а к наиболее конфиденциальным файлам применяется вложенная метка конфиденциальности для сайта. </span><span class="sxs-lookup"><span data-stu-id="e4a1e-224">Highly regulated files are stored exclusively on SharePoint sites for highly regulated data and the most sensitive files have the sensitivity sublabel for the site applied.</span></span>

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a><span data-ttu-id="e4a1e-225">Как корпорация Contoso выполнила развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="e4a1e-225">How the Contoso Corporation deployed Microsoft 365 Enterprise</span></span>

<span data-ttu-id="e4a1e-226">Корпорация Contoso — вымышленная показательная транснациональная промышленная компания-конгломерат с главным офисом в Париже.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-226">The Contoso Corporation is a fictional but representative global manufacturing conglomerate with its headquarters in Paris, France.</span></span> <span data-ttu-id="e4a1e-227">Посмотрите, как корпорация Contoso разработала, настроила и внедрила [надежный сайт SharePoint](contoso-sharepoint-online-site-for-highly-confidential-assets.md) для исследовательских команд в Париже, Москве, Нью-Йорке, Пекине и Бангалоре.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-227">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="e4a1e-228">См. также</span><span class="sxs-lookup"><span data-stu-id="e4a1e-228">See also</span></span>

[<span data-ttu-id="e4a1e-229">Руководство по развертыванию</span><span class="sxs-lookup"><span data-stu-id="e4a1e-229">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="e4a1e-230">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="e4a1e-230">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

