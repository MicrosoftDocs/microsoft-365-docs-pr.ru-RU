---
title: Сайт SharePoint для строго конфиденциальных цифровых активов корпорации Contoso
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/04/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: Сводка. сведения о том, как компания Contoso реализовала сайт SharePoint для строго регулируемых данных, чтобы упростить совместную работу между ее справочными группами.
ms.openlocfilehash: 08676f9fa89d9cbf932f9d70664ad1d17a153e3b
ms.sourcegitcommit: 80dc9ceb14e3eb3ae61b0fc2c8c3d73d564a7ef9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "37617257"
---
# <a name="sharepoint-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="9773b-103">Сайт SharePoint для строго конфиденциальных цифровых активов корпорации Contoso</span><span class="sxs-lookup"><span data-stu-id="9773b-103">SharePoint site for highly confidential digital assets of the Contoso Corporation</span></span>

 <span data-ttu-id="9773b-104">**Сводка:** Сведения о том, как компания Contoso реализовала сайт SharePoint для строго регулируемых данных для упрощения совместной работы между справочными группами.</span><span class="sxs-lookup"><span data-stu-id="9773b-104">**Summary:** How Contoso implemented a SharePoint site for highly regulated data for easier collaboration between its research teams.</span></span>
  
<span data-ttu-id="9773b-105">Наиболее ценные активы компании Contoso являются интеллектуальным свойством в виде коммерческих секретов, таких как специализированные приемы производства и конструктивные спецификации для продуктов, которые разрабатываются в разработке.</span><span class="sxs-lookup"><span data-stu-id="9773b-105">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="9773b-106">Эти ресурсы были в цифровом формате, которые были сохранены в виде файлов на сайте SharePoint Server 2016.</span><span class="sxs-lookup"><span data-stu-id="9773b-106">These assets were in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="9773b-107">Когда компания Contoso развернула Microsoft 365 корпоративный, они хотят перенести свои локальные цифровые ресурсы в облако для упрощения доступа и более тесного взаимодействия в Teams по Teams в Париж, Москва, Нью Йорк, Пекин и Бангалоре.</span><span class="sxs-lookup"><span data-stu-id="9773b-107">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="9773b-108">Однако из-за их конфиденциальной природы доступ к этим файлам должен выполняться следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9773b-108">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="9773b-109">Ограничен набором пользователей, которым разрешен доступ к ним.</span><span class="sxs-lookup"><span data-stu-id="9773b-109">Restricted to the set of people who are allowed access them.</span></span> 
- <span data-ttu-id="9773b-110">Защита с помощью политики защиты от потери данных (DLP), чтобы запретить пользователям распространять их за границы сайта.</span><span class="sxs-lookup"><span data-stu-id="9773b-110">Protected with a Data Loss Prevention (DLP) policy to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="9773b-111">Шифровать и защитить с помощью разрешений, чтобы предотвратить несанкционированный доступ к их содержимому, даже если они распределены извне сайта.</span><span class="sxs-lookup"><span data-stu-id="9773b-111">Encrypted and protected with permissions to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="9773b-112">Администраторы безопасности и SharePoint в ИТ-отделе компании Contoso решили использовать [сайт SharePoint для строго регулируемых данных](teams-sharepoint-online-sites-highly-regulated-data.md).</span><span class="sxs-lookup"><span data-stu-id="9773b-112">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="9773b-113">Компания Contoso использовала эти действия, чтобы создать и защитить сайты группы SharePoint для исследовательских групп.</span><span class="sxs-lookup"><span data-stu-id="9773b-113">Contoso used these steps to create and secure a SharePoint team sites for their research teams.</span></span>

## <a name="step-1-created-a-private-sharepoint-team-site"></a><span data-ttu-id="9773b-114">Шаг 1: создание частного сайта группы SharePoint</span><span class="sxs-lookup"><span data-stu-id="9773b-114">Step 1: Created a private SharePoint team site</span></span>

<span data-ttu-id="9773b-115">Чтобы защитить доступ к сайту SharePoint, компания Contoso настроила [Рекомендуемые политики доступа к SharePoint](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="9773b-115">To protect access to the SharePoint site, Contoso IT configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="9773b-116">После этого администраторы ИТ Contoso откомпилирован список учетных записей пользователей для исследователей в Office, Москва, Нью Йорк, Пекин и Бангалоре.</span><span class="sxs-lookup"><span data-stu-id="9773b-116">Next, Contoso IT admins compiled a list of the user accounts for the researchers in their Paris, Moscow, New York, Beijing, and Bangalore offices.</span></span> 

<span data-ttu-id="9773b-117">Затем администратор Contoso создал новый частный сайт группы с именем **Research** и добавил все учетные записи пользователей для исследователей.</span><span class="sxs-lookup"><span data-stu-id="9773b-117">Next, a Contoso IT admin created a new private team site named **Research** and added all of the user accounts for its researchers.</span></span>

<span data-ttu-id="9773b-118">Затем они настроили дополнительные параметры разрешений для сайта, чтобы не допустить общего доступа к сайту, а также предотвратить запрос доступа к сайту.</span><span class="sxs-lookup"><span data-stu-id="9773b-118">Then they configured additional permission settings for the site to prevent researchers from sharing access to the site and to prevent non-researchers from requesting access to the site.</span></span>

## <a name="step-2-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="9773b-119">Шаг 2: Настройка сайта для ограниченной политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="9773b-119">Step 2: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="9773b-120">Во-первых, администраторы Contoso применили существующую метку хранения Office 365 с **высоким уровнем конфиденциальности** в папку документы **справочного** сайта.</span><span class="sxs-lookup"><span data-stu-id="9773b-120">First, Contoso admins applied the existing **Highly Confidential** Office 365 retention label to the Documents folder of the **Research** site.</span></span>

<span data-ttu-id="9773b-121">После этого создаются новые политики DLP Office 365 с именем **Research** , которые:</span><span class="sxs-lookup"><span data-stu-id="9773b-121">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="9773b-122">Использует метку хранения Office 365 с **высоким уровнем конфиденциальности** .</span><span class="sxs-lookup"><span data-stu-id="9773b-122">Uses the **Highly Confidential** Office 365 retention label.</span></span> 
- <span data-ttu-id="9773b-123">Блокирует пользователей при попытке поделиться цифровым активом в **справочном** сайте за преработкой в компании Contoso.</span><span class="sxs-lookup"><span data-stu-id="9773b-123">Blocks users when they attempt to share a digital asset on the **Research** site outside of Contoso.</span></span>

<span data-ttu-id="9773b-124">Сведения о конфигурации приведены в разделе [Защита файлов SharePoint с метками хранения и DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span><span class="sxs-lookup"><span data-stu-id="9773b-124">For the configuration details, see [Protect SharePoint files with retention labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-4-created-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="9773b-125">Шаг 4: создана Подметка Office 365 с учетом конфиденциальности для сайта</span><span class="sxs-lookup"><span data-stu-id="9773b-125">Step 4: Created an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="9773b-126">Администраторы Contoso создали новую подметку Office 365 "чувствительность" с именем " **исследование Teams** " в метке **строго конфиденциальной информации** , которая:</span><span class="sxs-lookup"><span data-stu-id="9773b-126">Contoso admins created a new Office 365 sensitivity sublabel named **Research Teams** of the **Highly Confidential** label that:</span></span>

- <span data-ttu-id="9773b-127">Требует шифрования.</span><span class="sxs-lookup"><span data-stu-id="9773b-127">Requires encryption.</span></span>
- <span data-ttu-id="9773b-128">Разрешение на совместное редактирование для группы **исследовательского исследования** Office 365</span><span class="sxs-lookup"><span data-stu-id="9773b-128">Allows Co-Author permissions for the **Research** Office 365 group</span></span>
- <span data-ttu-id="9773b-129">Применимо к группе **исследовательского исследования** Office 365</span><span class="sxs-lookup"><span data-stu-id="9773b-129">Applies to the **Research** Office 365 group</span></span>

<span data-ttu-id="9773b-130">Ниже показана итоговая Конфигурация сайта **справочной** группы для строго конфиденциальных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="9773b-130">Here is the resulting configuration of the **Research** team site for highly confidential assets.</span></span>

![Результирующая конфигурация сайта справочной группы для строго конфиденциальных активов](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="9773b-132">Файлы в папках **справочного** сайта защищены:</span><span class="sxs-lookup"><span data-stu-id="9773b-132">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="9773b-133">Разрешения сайта, которые позволяют получать доступ только к участникам группы " **исследование** Office 365".</span><span class="sxs-lookup"><span data-stu-id="9773b-133">The site permissions, which only allow access to members of the **Research** Office 365 group.</span></span>
- <span data-ttu-id="9773b-134">Политика **защиты от** потери данных, которая использует метку и параметры хранения **строго конфиденциальной информации** , которая запрещает доступ к файлу внешним пользователям.</span><span class="sxs-lookup"><span data-stu-id="9773b-134">The **Research** DLP policy, which uses the **Highly Confidential** retention label and settings that prevent the file from being shared with external users.</span></span>
- <span data-ttu-id="9773b-135">Подметка "Учетная **Группа исследовательских групп** " с шифрованием и разрешениями, которые передаются вместе с файлом при его перемещении или копировании с сайта **справочных материалов** .</span><span class="sxs-lookup"><span data-stu-id="9773b-135">The **Research Teams** sensitivity sublabel, with encryption and permissions that travel with the file if it is moved or copied from the **Research** site.</span></span>

<span data-ttu-id="9773b-136">Ниже приведен пример файла, хранящегося на сайте **справочных материалов** с назначенной подметкой "чувствительность **группового исследования** ".</span><span class="sxs-lookup"><span data-stu-id="9773b-136">Here is an example of a file stored in the **Research** site with the **Research Teams** sensitivity sublabel assigned.</span></span>

![Результирующая конфигурация сайта справочной группы для строго конфиденциальных активов](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config-example-file.png)


## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="9773b-138">Шаг 5: Перенос локальных данных исследований SharePoint</span><span class="sxs-lookup"><span data-stu-id="9773b-138">Step 5: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="9773b-139">Администраторы Contoso переехали все локальные файлы исследований на локальном сайте SharePoint Server 2016 в папки на новом сайте **центра исследований** SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9773b-139">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint site.</span></span>

## <a name="step-6-trained-their-researchers"></a><span data-ttu-id="9773b-140">Шаг 6: обучение исследователей</span><span class="sxs-lookup"><span data-stu-id="9773b-140">Step 6: Trained their researchers</span></span>

<span data-ttu-id="9773b-141">Сотрудники отдела безопасности Contoso обучены участниками группы **исследование** Office 365 в обязательном курсе, в котором их пошагово проходят:</span><span class="sxs-lookup"><span data-stu-id="9773b-141">Contoso security staff trained the members of the **Research** Office 365 group in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="9773b-142">Доступ к новому **справочному** сайту и его существующим файлам.</span><span class="sxs-lookup"><span data-stu-id="9773b-142">How to access the new **Research** site and its existing files.</span></span>
- <span data-ttu-id="9773b-143">как создавать файлы на сайте и отправлять новые файлы, которые хранятся локально;</span><span class="sxs-lookup"><span data-stu-id="9773b-143">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="9773b-144">Демонстрация того, как политика " **исследование** DLP" блокирует доступ к файлам извне.</span><span class="sxs-lookup"><span data-stu-id="9773b-144">A demonstration of how the **Research** DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="9773b-145">Пометка файлов с помощью подметки "чувствительность групп" в **справочных материалах** .</span><span class="sxs-lookup"><span data-stu-id="9773b-145">How to label files with the **Research Teams** sensitivity sublabel.</span></span>
- <span data-ttu-id="9773b-146">Демонстрация того, как суб-метка **исследовательских групп** защищает файл даже при его утечке с сайта.</span><span class="sxs-lookup"><span data-stu-id="9773b-146">A demonstration of how the **Research Teams** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="9773b-147">Конечный результат — это безопасная среда, в которой исходящие работники могут совместно работать в среде Contoso в безопасной среде для файлов, содержащих справочные сведения.</span><span class="sxs-lookup"><span data-stu-id="9773b-147">The end result is a secure environment in which the researchers can collaborate across Contoso in a secure environment on files containing research information.</span></span> 

<span data-ttu-id="9773b-148">Если справочный документ с подметкой **исследовательских групп** оставляет сайт **справочных** материалов, он шифруется и доступен только участникам группы **исследование** Office 365 с действительными учетными данными учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="9773b-148">If a research document with the **Research Teams** sublabel leaves the **Research** site, it is encrypted and accessible only to members of the **Research** Office 365 group with valid user account credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="9773b-149">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="9773b-149">Next step</span></span>

<span data-ttu-id="9773b-150">[Deploy (развертывание](deploy-microsoft-365-enterprise.md) ) Microsoft 365 корпоративный в Организации.</span><span class="sxs-lookup"><span data-stu-id="9773b-150">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="9773b-151">См. также</span><span class="sxs-lookup"><span data-stu-id="9773b-151">See also</span></span>

<span data-ttu-id="9773b-152">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="9773b-152">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
