---
title: Сайт SharePoint Online для строго конфиденциальных цифровых активов корпорации Contoso
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/15/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: Сводка. сведения о том, как компания Contoso реализовала сайт SharePoint Online для строго регулируемых данных, чтобы упростить совместную работу между ее справочными группами.
ms.openlocfilehash: 6c61d02c802a77afeb93a58b59114741c6630f9e
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369530"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="8f674-103">Сайт SharePoint Online для строго конфиденциальных цифровых активов корпорации Contoso</span><span class="sxs-lookup"><span data-stu-id="8f674-103">SharePoint Online site for highly confidential digital assets of the Contoso Corporation</span></span>

 <span data-ttu-id="8f674-104">**Сводка:** Как компания Contoso реализовала сайт SharePoint Online для строго регулируемых данных для упрощения совместной работы между группами исследований.</span><span class="sxs-lookup"><span data-stu-id="8f674-104">**Summary:** How Contoso implemented a SharePoint Online site for highly regulated data for easier collaboration between its research teams.</span></span>
  
<span data-ttu-id="8f674-105">Наиболее ценные активы компании Contoso являются интеллектуальным свойством в виде коммерческих секретов, таких как специализированные приемы производства и конструктивные спецификации для продуктов, которые разрабатываются в разработке.</span><span class="sxs-lookup"><span data-stu-id="8f674-105">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="8f674-106">Эти ресурсы находятся в цифровой форме, которые были сохранены в виде файлов на сайте SharePoint Server 2016.</span><span class="sxs-lookup"><span data-stu-id="8f674-106">These assets are in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="8f674-107">Когда компания Contoso развернула Microsoft 365 корпоративный, они хотят перенести свои локальные цифровые ресурсы в облако для упрощения доступа и более тесного взаимодействия в Teams по Teams в Париж, Москва, Нью Йорк, Пекин и Бангалоре.</span><span class="sxs-lookup"><span data-stu-id="8f674-107">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="8f674-108">Однако из-за их конфиденциальной природы доступ к этим файлам должен выполняться следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8f674-108">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="8f674-109">Ограничен набором пользователей, которым разрешено просматривать или изменять их, с текущими разрешениями для сайта, контролируемого только администраторами SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8f674-109">Restricted to the set of people who are allowed to view or change them, with ongoing permissions for the site administered only by SharePoint admins.</span></span> 
- <span data-ttu-id="8f674-110">Защита от потери данных (DLP) без защиты от потери данных (DLP), чтобы запретить пользователям распространять их за границы сайта.</span><span class="sxs-lookup"><span data-stu-id="8f674-110">Protected with Data Loss Prevention (DLP) to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="8f674-111">Шифруются и защищаются с помощью списков управления доступом, чтобы предотвратить несанкционированный доступ к их содержимому, даже если они распределены извне сайта.</span><span class="sxs-lookup"><span data-stu-id="8f674-111">Encrypted and protected with access control lists to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="8f674-112">Администраторы безопасности и SharePoint в отделе ИТ компании Contoso решили использовать [сайт SharePoint Online для строго регулируемых данных](teams-sharepoint-online-sites-highly-regulated-data.md).</span><span class="sxs-lookup"><span data-stu-id="8f674-112">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint Online site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="8f674-113">Компания Contoso использовала эти действия, чтобы создать и защитить сайты группы SharePoint Online для исследовательских групп.</span><span class="sxs-lookup"><span data-stu-id="8f674-113">Contoso used these steps to create and secure a SharePoint Online team sites for their research teams.</span></span>

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a><span data-ttu-id="8f674-114">Шаг 1: проверенные и проверенные участники групп исследований</span><span class="sxs-lookup"><span data-stu-id="8f674-114">Step 1: Reviewed and verified the members of research team groups</span></span>

<span data-ttu-id="8f674-115">Администраторы ИТ Contoso выполнили проверку набора групп безопасности для исследовательских групп.</span><span class="sxs-lookup"><span data-stu-id="8f674-115">Contoso IT admins performed a review of the set of security groups for their research teams.</span></span> <span data-ttu-id="8f674-116">Никто, кто не являлся, или не получил доступ к справочным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="8f674-116">They removed anyone who was not a researcher or did not need access to research assets.</span></span> 

<span data-ttu-id="8f674-117">Они также создали новые группы безопасности:</span><span class="sxs-lookup"><span data-stu-id="8f674-117">They also and created these new security groups:</span></span>

- <span data-ttu-id="8f674-118">**Справочные материалы для администраторов**  Набор администраторов SharePoint, которые имеют полный контроль над сайтом, включая возможность изменения разрешений.</span><span class="sxs-lookup"><span data-stu-id="8f674-118">**Research-Admins**  The set of SharePoint admins that have full control over the site, including the ability to modify permissions.</span></span>
- <span data-ttu-id="8f674-119">**Исследование участников**  Набор групп безопасности для команд исследования, окружающих мир.</span><span class="sxs-lookup"><span data-stu-id="8f674-119">**Research-Members**  The set of security groups for the research teams around the world.</span></span>
- <span data-ttu-id="8f674-120">**Справочные материалы для зрителей**  Набор пользователей управления, например руководителей в исследовательской организации, которые могут только просматривать ресурсы на сайте.</span><span class="sxs-lookup"><span data-stu-id="8f674-120">**Research-Viewers**  The set of management users, such as executives in the research organization, that can only view the assets on the site.</span></span>

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="8f674-121">Шаг 2: Создание изолированного сайта группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8f674-121">Step 2: Created an isolated SharePoint Online team site</span></span> 

<span data-ttu-id="8f674-122">Администраторы Contoso SharePoint сначала создали новый сайт группы с именем **Research**.</span><span class="sxs-lookup"><span data-stu-id="8f674-122">Contoso SharePoint admins first created a new team site named **Research**.</span></span> <span data-ttu-id="8f674-123">Затем они настроили:</span><span class="sxs-lookup"><span data-stu-id="8f674-123">They then configured:</span></span>

- <span data-ttu-id="8f674-124">Уровень разрешений "полный доступ" для группы "владельцы справочных материалов", в которой в качестве участника используется группа " **Справочные материалы"** .</span><span class="sxs-lookup"><span data-stu-id="8f674-124">The Full Control permission level to use the Research Owners SharePoint group, which has the **Research-Admins** security group as a member</span></span>
- <span data-ttu-id="8f674-125">Уровень разрешений "Изменить" для использования группы "справочные материалы", в которой в качестве участника используется группа " **Участники справочных материалов** "</span><span class="sxs-lookup"><span data-stu-id="8f674-125">The Edit permission level to use the Research Members SharePoint group, which has the **Research Members** security group as a member</span></span>
- <span data-ttu-id="8f674-126">Уровень разрешений "чтение" используется для группы "Посетители" в справочных материалах, в которой в качестве участника используется группа безопасности " **Справочные материалы** "</span><span class="sxs-lookup"><span data-stu-id="8f674-126">The Read permission level to use the Research Visitors SharePoint group, which has the **Research-Viewers** security group as a member</span></span>

<span data-ttu-id="8f674-127">Ниже приведены итоговые уровни разрешений SharePoint, группы SharePoint и их участники.</span><span class="sxs-lookup"><span data-stu-id="8f674-127">Here are the resulting SharePoint permission levels, SharePoint groups, and their members.</span></span>

![Уровни разрешений SharePoint, группы SharePoint и их участники](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

<span data-ttu-id="8f674-129">Затем они настроили дополнительные ограничения для сайта.</span><span class="sxs-lookup"><span data-stu-id="8f674-129">Next, they configured additional restrictions for the site.</span></span>

<span data-ttu-id="8f674-130">Сведения о конфигурации приведены в разделе [Deploy a изолированного сайта группы SharePoint Online](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span><span class="sxs-lookup"><span data-stu-id="8f674-130">For the configuration details, see [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span></span>

## <a name="step-3-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="8f674-131">Шаг 3: Настройка сайта для ограниченной политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="8f674-131">Step 3: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="8f674-132">Во-первых, администраторы Contoso применили метку хранения Office 365 с **высоким уровнем конфиденциальности** на сайт **справочных материалов** .</span><span class="sxs-lookup"><span data-stu-id="8f674-132">First, Contoso admins applied the **Highly Confidential** Office 365 retention label to the **Research** site.</span></span>

<span data-ttu-id="8f674-133">После этого создаются новые политики DLP Office 365 с именем **Research** , которые:</span><span class="sxs-lookup"><span data-stu-id="8f674-133">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="8f674-134">Использует метку хранения Office 365 с **высоким уровнем конфиденциальности** .</span><span class="sxs-lookup"><span data-stu-id="8f674-134">Uses the **Highly Confidential** Office 365 retention label.</span></span> 
- <span data-ttu-id="8f674-135">Применяется к сайту **справочных материалов** .</span><span class="sxs-lookup"><span data-stu-id="8f674-135">Is applied to the **Research** site.</span></span>
- <span data-ttu-id="8f674-136">Блокирует пользователей при попытке поделиться цифровым активом в **справочном** сайте за преработкой в компании Contoso.</span><span class="sxs-lookup"><span data-stu-id="8f674-136">Blocks users when they attempt to share a digital asset on the **Research** site outside of Contoso.</span></span>

<span data-ttu-id="8f674-137">Сведения о конфигурации приведены в статье [Защита файлов SharePoint Online с метками хранения и DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span><span class="sxs-lookup"><span data-stu-id="8f674-137">For the configuration details, see [Protect SharePoint Online files with retention labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="8f674-138">Шаг 4: создана вложенная метка Azure Information Protection для сайта</span><span class="sxs-lookup"><span data-stu-id="8f674-138">Step 4: Created an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="8f674-139">Администраторы Contoso создали новую вложенную метку Azure Information Protection с именем " **исследование** **строго конфиденциальной** метки по умолчанию" в политике с областью, которая:</span><span class="sxs-lookup"><span data-stu-id="8f674-139">Contoso admins created a new Azure Information Protection sub-label named **Research** of the default **Highly Confidential** label in a scoped policy that:</span></span>

- <span data-ttu-id="8f674-140">Требует шифрования.</span><span class="sxs-lookup"><span data-stu-id="8f674-140">Requires encryption.</span></span>
- <span data-ttu-id="8f674-141">Разрешает полный доступ для членов группы безопасности " **исследование** ".</span><span class="sxs-lookup"><span data-stu-id="8f674-141">Allows full access by members of the **Research-Members** security group.</span></span>
- <span data-ttu-id="8f674-142">Разрешает доступ на чтение для членов группы безопасности " **Справочные материалы** ".</span><span class="sxs-lookup"><span data-stu-id="8f674-142">Allows read access by members of the **Research-Viewers** security group.</span></span>

<span data-ttu-id="8f674-143">После этого клиентская служба Azure Information Protection разворачивается на устройствах исследований участников группы.</span><span class="sxs-lookup"><span data-stu-id="8f674-143">Next, they deployed the Azure Information Protection client to the devices of research team members.</span></span>

<span data-ttu-id="8f674-144">Сведения о конфигурации можно найти в статье [Защита файлов SharePoint Online с помощью Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span><span class="sxs-lookup"><span data-stu-id="8f674-144">For the configuration details, see [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span></span> 

<span data-ttu-id="8f674-145">Ниже показана итоговая конфигурация **справочного** сайта для строго конфиденциальных активов.</span><span class="sxs-lookup"><span data-stu-id="8f674-145">Here is the resulting configuration of the **Research** site for highly confidential assets.</span></span>

![Результирующая конфигурация сайта \* \* Research \* \* для строго конфиденциальных активов](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="8f674-147">Файлы в папках **справочного** сайта защищены:</span><span class="sxs-lookup"><span data-stu-id="8f674-147">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="8f674-148">Подметка **исследование** Azure Information Protection, которая применяет шифрование и пермссионс к каждому файлу, который перемещается вместе с файлом, когда он перемещается или копируется с сайта **справочных материалов** .</span><span class="sxs-lookup"><span data-stu-id="8f674-148">The **Research** Azure Information Protection sublabel, which applies encryption and permssions to each file that travel with the file when it is moved or copied from the **Research** site.</span></span>
- <span data-ttu-id="8f674-149">Политика **защиты от** потери данных, которая использует метку и параметры **строго конфиденциального** хранения, которые запрещают доступ к файлу внешним пользователям.</span><span class="sxs-lookup"><span data-stu-id="8f674-149">The **Research** DLP policy, which uses the **Highly Sensitive** retention label and settings that prevent the file from being shared with external users.</span></span>
- <span data-ttu-id="8f674-150">Набор разрешений сайта, который разрешает доступ только членам групп безопасности " **исследование** " и " **Справочные** материалы" и "Администрирование" для участников группы " **исследование"** .</span><span class="sxs-lookup"><span data-stu-id="8f674-150">The set of site permissions, which only allow access to members of the **Research-Members** and **Research-Viewers** security groups and administration by members of the **Research-Admins** security group.</span></span>

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="8f674-151">Шаг 5: Перенос локальных данных исследований SharePoint</span><span class="sxs-lookup"><span data-stu-id="8f674-151">Step 5: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="8f674-152">Администраторы Contoso переехали все локальные файлы справочных материалов на локальном сайте SharePoint Server 2016 в папки нового **справочного** сайта SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8f674-152">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint Online site.</span></span>

## <a name="step-6-trained-their-users"></a><span data-ttu-id="8f674-153">Шаг 6: обучение пользователей</span><span class="sxs-lookup"><span data-stu-id="8f674-153">Step 6: Trained their users</span></span> 

<span data-ttu-id="8f674-154">Сотрудники отдела безопасности Contoso обучены командами исследования в обязательном курсе, в котором они выполнялись по следующим шагам:</span><span class="sxs-lookup"><span data-stu-id="8f674-154">Contoso security staff trained the research teams in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="8f674-155">Как получить доступ к новому сайту **исследования** SharePoint Online и существующим файлам.</span><span class="sxs-lookup"><span data-stu-id="8f674-155">How to access the new **Research** SharePoint Online site and its existing files.</span></span>
- <span data-ttu-id="8f674-156">как создавать файлы на сайте и отправлять новые файлы, которые хранятся локально;</span><span class="sxs-lookup"><span data-stu-id="8f674-156">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="8f674-157">Демонстрация того, как политика DLP блокирует доступ к файлам извне.</span><span class="sxs-lookup"><span data-stu-id="8f674-157">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="8f674-158">Использование клиента Azure Information Protection для метки справочных файлов с помощью подметки **справочных материалов** .</span><span class="sxs-lookup"><span data-stu-id="8f674-158">How to use the Azure Information Protection client to label research files with the **Research** sub-label.</span></span>
- <span data-ttu-id="8f674-159">Пример того, как вложенная подпись **справочных материалов** защищает файл даже при его утечке с сайта.</span><span class="sxs-lookup"><span data-stu-id="8f674-159">A demonstration of how the **Research** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="8f674-160">Конечный результат — это безопасная среда, в которой исходящие работники могут совместно работать в Организации в безопасной среде.</span><span class="sxs-lookup"><span data-stu-id="8f674-160">The end result is a secure environment in which the researchers can collaborate across the organization in a secure environment.</span></span> 

<span data-ttu-id="8f674-161">Если справочный документ с вложенной подписью **справочных** материалов был потерян из **справочного** сайта, он шифруется и доступен только участникам групп безопасности " **исследование** " и " **Справочные материалы** " с действительными учетными данными.</span><span class="sxs-lookup"><span data-stu-id="8f674-161">If a research document with the **Research** sub-label is leaked from the **Research** site, it is encrypted and accessible only to members of the **Research-Members** and **Research-Viewers** security groups with valid credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="8f674-162">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="8f674-162">Next step</span></span>

<span data-ttu-id="8f674-163">[Deploy (развертывание](deploy-microsoft-365-enterprise.md) ) Microsoft 365 корпоративный в Организации.</span><span class="sxs-lookup"><span data-stu-id="8f674-163">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

