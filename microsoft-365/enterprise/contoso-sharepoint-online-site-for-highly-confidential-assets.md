---
title: Сайт SharePoint Online для конфиденциальными цифровых активов корпорации Contoso
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/01/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Architecture
description: 'Сводка: Как Contoso реализован сайт SharePoint Online для очень регулируемого данных для упрощения совместной работы между его research группы.'
ms.openlocfilehash: 697ddb27b56fd529e9c73b89d9f07b8731ad76c3
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871030"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="cb6b9-103">Сайт SharePoint Online для конфиденциальными цифровых активов корпорации Contoso</span><span class="sxs-lookup"><span data-stu-id="cb6b9-103">SharePoint Online site for highly confidential digital assets of the Contoso Corporation</span></span>

 <span data-ttu-id="cb6b9-104">**Сводка:** Каким образом Contoso реализовывать сайт SharePoint Online для очень регулируемого данных для упрощения совместной работы между его исследовательские группы.</span><span class="sxs-lookup"><span data-stu-id="cb6b9-104">**Summary:** How Contoso implemented a SharePoint Online site for highly regulated data for easier collaboration between its research teams.</span></span>
  
<span data-ttu-id="cb6b9-p101">Наиболее важных активов организации Contoso являются его интеллектуальной собственности в виде Торговые секреты, такие как собственный условиях и Разработка спецификаций для продуктов, которые находятся в разработке. Эти средства являются в цифровой форме, изначально хранятся в виде файлов на сайте SharePoint Server 2016. При развертывании Microsoft 365 Enterprise Contoso хотели перенос своих локальных цифровых активов в облако для упрощения доступа и совместной работы более open через исследовательские группы в Париж, Москва, Нью-Йорк, Пекин и Бангалора.</span><span class="sxs-lookup"><span data-stu-id="cb6b9-p101">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development. These assets are in digital form, originally stored as files on a SharePoint Server 2016 site. When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="cb6b9-108">Тем не менее из-за их характер конфиденциальных доступ к этим файлам должен быть:</span><span class="sxs-lookup"><span data-stu-id="cb6b9-108">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="cb6b9-109">Ограниченный набор пользователей, которые могут просмотреть или изменить их, с помощью текущие разрешения для сайта, управляются SharePoint "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="cb6b9-109">Restricted to the set of people who are allowed to view or change them, with ongoing permissions for the site administered only by SharePoint admins.</span></span> 
- <span data-ttu-id="cb6b9-110">Для защиты с предотвращения потери данных (DLP) чтобы пользователи не могли их распространения за пределами сайта.</span><span class="sxs-lookup"><span data-stu-id="cb6b9-110">Protected with Data Loss Prevention (DLP) to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="cb6b9-111">Управления доступом на зашифрованные и защищенные с помощью списков, чтобы запретить неавторизованным пользователям доступ к их содержимое даже в том случае, если они распространяются за пределами сайта.</span><span class="sxs-lookup"><span data-stu-id="cb6b9-111">Encrypted and protected with access control lists to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="cb6b9-112">Администраторы безопасности и SharePoint в Contoso ИТ-отделу принял решение использовать [сайт SharePoint Online для очень регулируемого данных](teams-sharepoint-online-sites-highly-regulated-data.md).</span><span class="sxs-lookup"><span data-stu-id="cb6b9-112">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint Online site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="cb6b9-113">Contoso используется следующие действия для создания и обеспечения безопасности SharePoint Online сайты рабочих групп для соответствующих групп на необходимые справочные материалы.</span><span class="sxs-lookup"><span data-stu-id="cb6b9-113">Contoso used these steps to create and secure a SharePoint Online team sites for their research teams.</span></span>

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a><span data-ttu-id="cb6b9-114">Шаг 1: Анализа и проверки члены групп группы справочных материалов</span><span class="sxs-lookup"><span data-stu-id="cb6b9-114">Step 1: Reviewed and verified the members of research team groups</span></span>

<span data-ttu-id="cb6b9-p102">Contoso ИТ-администраторов выполнить анализ набор групп безопасности для соответствующих групп на необходимые справочные материалы. Они удалены всем пользователям, которые не исследователя или доступ к исследования активов не требуется.</span><span class="sxs-lookup"><span data-stu-id="cb6b9-p102">Contoso IT admins performed a review of the set of security groups for their research teams. They removed anyone who was not a researcher or did not need access to research assets.</span></span> 

<span data-ttu-id="cb6b9-117">Они также и создания этих новых групп безопасности:</span><span class="sxs-lookup"><span data-stu-id="cb6b9-117">They also and created these new security groups:</span></span>

- <span data-ttu-id="cb6b9-118">**Администраторы справочных материалов**  Набор администраторов SharePoint, обладают полным доступом ко сайта, включая возможность изменения разрешений.</span><span class="sxs-lookup"><span data-stu-id="cb6b9-118">**Research-Admins**  The set of SharePoint admins that have full control over the site, including the ability to modify permissions.</span></span>
- <span data-ttu-id="cb6b9-119">**Члены справочных материалов**  Набор групп безопасности для исследовательские группы по всему миру.</span><span class="sxs-lookup"><span data-stu-id="cb6b9-119">**Research Members**  The set of security groups for the research teams around the world.</span></span>
- <span data-ttu-id="cb6b9-120">**Средства просмотра справочных материалов**  Набор пользователей управления, такие как руководители организации справочных материалов, которые могут просматривать ресурсы на сайте.</span><span class="sxs-lookup"><span data-stu-id="cb6b9-120">**Research-Viewers**  The set of management users, such as executives in the research organization, that can view the assets on the site.</span></span>

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="cb6b9-121">Шаг 2: Создан изолированной SharePoint Online сайт группы</span><span class="sxs-lookup"><span data-stu-id="cb6b9-121">Step 2: Created an isolated SharePoint Online team site</span></span> 

<span data-ttu-id="cb6b9-p103">Сначала создать новый сайт группы администраторов Contoso SharePoint с именем **справочных материалов**. Они затем настроить:</span><span class="sxs-lookup"><span data-stu-id="cb6b9-p103">Contoso SharePoint admins first created a new team site named **Research**. They then configured:</span></span>

- <span data-ttu-id="cb6b9-124">Уровень разрешений полного доступа, используйте группы владельцев SharePoint справочных материалов, имеющем группу **Администраторов Research** как члена группы</span><span class="sxs-lookup"><span data-stu-id="cb6b9-124">The Full Control permission level to use the Research Owners SharePoint group, which has the **Research-Admins** security group as a member</span></span>
- <span data-ttu-id="cb6b9-125">Изменить уровень разрешений, используйте группу SharePoint участники справочных материалов, насчитывающей группы безопасности **Члены Research** как члена группы</span><span class="sxs-lookup"><span data-stu-id="cb6b9-125">The Edit permission level to use the Research Members SharePoint group, which has the **Research Members** security group as a member</span></span>
- <span data-ttu-id="cb6b9-126">Уровень разрешений чтение для использования group SharePoint посетителей справочных материалов, который имеет группа безопасности **Средства просмотра Research** как члена группы</span><span class="sxs-lookup"><span data-stu-id="cb6b9-126">The Read permission level to use the Research Visitors SharePoint group, which has the **Research-Viewers** security group as a member</span></span>

<span data-ttu-id="cb6b9-127">Ниже приведены итоговый уровней разрешений SharePoint, групп SharePoint и их члены.</span><span class="sxs-lookup"><span data-stu-id="cb6b9-127">Here are the resulting SharePoint permission levels, SharePoint groups, and their members.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

<span data-ttu-id="cb6b9-128">После этого они настроены дополнительные ограничения для сайта.</span><span class="sxs-lookup"><span data-stu-id="cb6b9-128">Next, they configured additional restrictions for the site.</span></span>

<span data-ttu-id="cb6b9-129">Сведения о конфигурации см [изолированной SharePoint Online сайт группы](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span><span class="sxs-lookup"><span data-stu-id="cb6b9-129">For the configuration details, see [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span></span>

## <a name="step-3-configured-the-site-for-a-restrictive-office-365-label-dlp-policy"></a><span data-ttu-id="cb6b9-130">Шаг 3: Настройки сайта для ограничения Office 365 метки политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="cb6b9-130">Step 3: Configured the site for a restrictive Office 365 label DLP policy</span></span>

<span data-ttu-id="cb6b9-131">Во-первых администраторов Contoso применяется метку **Конфиденциальными** Office 365 на сайт **справочных материалов** .</span><span class="sxs-lookup"><span data-stu-id="cb6b9-131">First, Contoso admins applied the **Highly Confidential** Office 365 label to the **Research** site.</span></span>

<span data-ttu-id="cb6b9-132">Рассмотрим процедуру создания нового политики предотвращения потери данных Office 365 с именем **справочных материалов** , который:</span><span class="sxs-lookup"><span data-stu-id="cb6b9-132">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="cb6b9-133">Использует метку **Конфиденциальными** Office 365.</span><span class="sxs-lookup"><span data-stu-id="cb6b9-133">Uses the **Highly Confidential** Office 365 label.</span></span> 
- <span data-ttu-id="cb6b9-134">Применяется к сайту **справочных материалов** .</span><span class="sxs-lookup"><span data-stu-id="cb6b9-134">Is applied to the **Research** site.</span></span>
- <span data-ttu-id="cb6b9-135">Запрещает общий доступ к документам.</span><span class="sxs-lookup"><span data-stu-id="cb6b9-135">Prevents users from sharing documents.</span></span>

<span data-ttu-id="cb6b9-136">Сведения о конфигурации в разделе [Защита SharePoint Online файлов с Office 365 метки и защиты от потери данных](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span><span class="sxs-lookup"><span data-stu-id="cb6b9-136">For the configuration details, see [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="cb6b9-137">Шаг 4: Создан вложенный метку защита информации Azure для сайта</span><span class="sxs-lookup"><span data-stu-id="cb6b9-137">Step 4: Created an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="cb6b9-138">Создан новый дочерний метки защита информации Azure администраторов Contoso с именем **Справочные материалы** по умолчанию **Конфиденциальными** метки в заданной областью политики, который:</span><span class="sxs-lookup"><span data-stu-id="cb6b9-138">Contoso admins created a new Azure Information Protection sub-label named **Research** of the default **Highly Confidential** label in a scoped policy that:</span></span>

- <span data-ttu-id="cb6b9-139">Требует шифрования.</span><span class="sxs-lookup"><span data-stu-id="cb6b9-139">Requires encryption.</span></span>
- <span data-ttu-id="cb6b9-140">Полный доступ с членами группы безопасности **Члены справочных материалов** .</span><span class="sxs-lookup"><span data-stu-id="cb6b9-140">Allows full access by members of the **Research Members** security group.</span></span>
- <span data-ttu-id="cb6b9-141">Разрешает доступ на чтение членами группы безопасности **Средства просмотра справочных материалов** .</span><span class="sxs-lookup"><span data-stu-id="cb6b9-141">Allows read access by members of the **Research Viewers** security group.</span></span>

<span data-ttu-id="cb6b9-142">Затем они развернуты защита информации Azure клиента к устройствам члены группы.</span><span class="sxs-lookup"><span data-stu-id="cb6b9-142">Next, they deployed the Azure Information Protection client to the devices of research team members.</span></span>

<span data-ttu-id="cb6b9-143">Сведения о конфигурации в разделе [Защита SharePoint Online файлов с защитой сведения Azure](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span><span class="sxs-lookup"><span data-stu-id="cb6b9-143">For the configuration details, see [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span></span> 

<span data-ttu-id="cb6b9-144">Вот Результирующая конфигурация сайта **справочных материалов** для конфиденциальными активов.</span><span class="sxs-lookup"><span data-stu-id="cb6b9-144">Here is the resulting configuration of the **Research** site for highly confidential assets.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="cb6b9-145">Шаг 5: Перенесенных локальных данных справочных материалов SharePoint</span><span class="sxs-lookup"><span data-stu-id="cb6b9-145">Step 5: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="cb6b9-146">Все локальные исследование файлов на сайте SharePoint Server 2016 локальной папки в новый сайт SharePoint Online **Research** перемещения администраторов Contoso.</span><span class="sxs-lookup"><span data-stu-id="cb6b9-146">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint Online site.</span></span>

## <a name="step-6-trained-their-users"></a><span data-ttu-id="cb6b9-147">Шаг 6: Обучение пользователей</span><span class="sxs-lookup"><span data-stu-id="cb6b9-147">Step 6: Trained their users</span></span> 

<span data-ttu-id="cb6b9-148">Персонал Contoso безопасности обучение исследовательские группы обязательный курс, шаг с заходом их с помощью:</span><span class="sxs-lookup"><span data-stu-id="cb6b9-148">Contoso security staff trained the research teams in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="cb6b9-149">Как получить доступ к новый сайт SharePoint Online **справочных материалов** и существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="cb6b9-149">How to access the new **Research** SharePoint Online site and its existing files.</span></span>
- <span data-ttu-id="cb6b9-150">как создавать файлы на сайте и отправлять новые файлы, которые хранятся локально;</span><span class="sxs-lookup"><span data-stu-id="cb6b9-150">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="cb6b9-151">Как политики защиты от потери данных блокирует файлы из общего доступа извне.</span><span class="sxs-lookup"><span data-stu-id="cb6b9-151">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="cb6b9-152">Как использовать клиент защита информации Azure для метки файлам справочные материалы с меткой подменю **справочных материалов** .</span><span class="sxs-lookup"><span data-stu-id="cb6b9-152">How to use the Azure Information Protection client to label research files with the **Research** sub-label.</span></span>
- <span data-ttu-id="cb6b9-153">Как дочерний метки **справочных материалов** обеспечивает защиту файла даже в том случае, если он утечка с сайта.</span><span class="sxs-lookup"><span data-stu-id="cb6b9-153">A demonstration of how the **Research** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="cb6b9-154">Конечный результат является безопасной среде, в которой исследователями совместной работы в организации в безопасной среде.</span><span class="sxs-lookup"><span data-stu-id="cb6b9-154">The end result is a secure environment in which the researchers can collaborate across the organization in a secure environment.</span></span> 

<span data-ttu-id="cb6b9-155">Если документ справочные материалы с меткой подменю **справочных материалов** утечка с сайта **справочных материалов** , это зашифрованные и доступны только для членов группы безопасности **Члены справочные материалы** и **Средства просмотра Research** допустимые учетные данные.</span><span class="sxs-lookup"><span data-stu-id="cb6b9-155">If a research document with the **Research** sub-label is leaked from the **Research** site, it is encrypted and accessible only to members of the **Research Members** and **Research Viewers** security groups with valid credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="cb6b9-156">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="cb6b9-156">Next step</span></span>

<span data-ttu-id="cb6b9-157">[Развертывание](deploy-microsoft-365-enterprise.md) Microsoft 365 корпоративный в организации.</span><span class="sxs-lookup"><span data-stu-id="cb6b9-157">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

