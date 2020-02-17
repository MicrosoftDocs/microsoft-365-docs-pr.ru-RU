---
title: Сайт SharePoint для строго конфиденциальных цифровых активов корпорации Contoso
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: Сводка. сведения о том, как компания Contoso реализовала сайт SharePoint для строго регулируемых данных, чтобы упростить совместную работу между ее справочными группами.
ms.openlocfilehash: a1ffb336e85eb6eb850b53ed14adf947b56642cc
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068283"
---
# <a name="sharepoint-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="75523-103">Сайт SharePoint для строго конфиденциальных цифровых активов корпорации Contoso</span><span class="sxs-lookup"><span data-stu-id="75523-103">SharePoint site for highly confidential digital assets of the Contoso Corporation</span></span>

<span data-ttu-id="75523-104">Наиболее ценные активы компании Contoso являются интеллектуальным свойством в виде коммерческих секретов, таких как специализированные приемы производства и конструктивные спецификации для продуктов, которые разрабатываются в разработке.</span><span class="sxs-lookup"><span data-stu-id="75523-104">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="75523-105">Эти ресурсы были в цифровом формате, которые были сохранены в виде файлов на сайте SharePoint Server 2016.</span><span class="sxs-lookup"><span data-stu-id="75523-105">These assets were in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="75523-106">Когда компания Contoso развернула Microsoft 365 корпоративный, они хотят перенести свои локальные цифровые ресурсы в облако для упрощения доступа и более тесного взаимодействия в Teams по Teams в Париж, Москва, Нью Йорк, Пекин и Бангалоре.</span><span class="sxs-lookup"><span data-stu-id="75523-106">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="75523-107">Однако из-за их конфиденциальной природы доступ к этим файлам должен выполняться следующим образом:</span><span class="sxs-lookup"><span data-stu-id="75523-107">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="75523-108">Ограничен набором пользователей, которым разрешен доступ к ним.</span><span class="sxs-lookup"><span data-stu-id="75523-108">Restricted to the set of people who are allowed access them.</span></span> 
- <span data-ttu-id="75523-109">Защита с помощью политики защиты от потери данных (DLP), чтобы запретить пользователям распространять их за границы сайта.</span><span class="sxs-lookup"><span data-stu-id="75523-109">Protected with a Data Loss Prevention (DLP) policy to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="75523-110">Шифровать и защитить с помощью разрешений, чтобы предотвратить несанкционированный доступ к их содержимому, даже если они распределены извне сайта.</span><span class="sxs-lookup"><span data-stu-id="75523-110">Encrypted and protected with permissions to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="75523-111">Администраторы безопасности и SharePoint в ИТ-отделе компании Contoso решили использовать [сайт SharePoint для строго регулируемых данных](teams-sharepoint-online-sites-highly-regulated-data.md).</span><span class="sxs-lookup"><span data-stu-id="75523-111">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="75523-112">Компания Contoso использовала эти действия, чтобы создать и защитить сайты группы SharePoint для исследовательских групп.</span><span class="sxs-lookup"><span data-stu-id="75523-112">Contoso used these steps to create and secure a SharePoint team sites for their research teams.</span></span>

## <a name="step-1-created-a-private-sharepoint-team-site"></a><span data-ttu-id="75523-113">Шаг 1: создание частного сайта группы SharePoint</span><span class="sxs-lookup"><span data-stu-id="75523-113">Step 1: Created a private SharePoint team site</span></span>

<span data-ttu-id="75523-114">Чтобы защитить доступ к сайту SharePoint, компания Contoso настроила [Рекомендуемые политики доступа к SharePoint](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="75523-114">To protect access to the SharePoint site, Contoso IT configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="75523-115">После этого администраторы ИТ Contoso откомпилирован список учетных записей пользователей для исследователей в Office, Москва, Нью Йорк, Пекин и Бангалоре.</span><span class="sxs-lookup"><span data-stu-id="75523-115">Next, Contoso IT admins compiled a list of the user accounts for the researchers in their Paris, Moscow, New York, Beijing, and Bangalore offices.</span></span> 

<span data-ttu-id="75523-116">Затем администратор Contoso создал новый частный сайт группы с именем **Research** и добавил все учетные записи пользователей для исследователей.</span><span class="sxs-lookup"><span data-stu-id="75523-116">Next, a Contoso IT admin created a new private team site named **Research** and added all of the user accounts for its researchers.</span></span>

<span data-ttu-id="75523-117">Затем они настроили дополнительные параметры разрешений для сайта, чтобы не допустить общего доступа к сайту, а также предотвратить запрос доступа к сайту.</span><span class="sxs-lookup"><span data-stu-id="75523-117">Then they configured additional permission settings for the site to prevent researchers from sharing access to the site and to prevent non-researchers from requesting access to the site.</span></span>

## <a name="step-2-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="75523-118">Шаг 2: Настройка сайта для ограниченной политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="75523-118">Step 2: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="75523-119">Во-первых, администраторы Contoso применили существующую метку хранения Office 365 с **высоким уровнем конфиденциальности** в папку документы **справочного** сайта.</span><span class="sxs-lookup"><span data-stu-id="75523-119">First, Contoso admins applied the existing **Highly Confidential** Office 365 retention label to the Documents folder of the **Research** site.</span></span>

<span data-ttu-id="75523-120">После этого создаются новые политики DLP Office 365 с именем **Research** , которые:</span><span class="sxs-lookup"><span data-stu-id="75523-120">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="75523-121">Использует метку хранения Office 365 с **высоким уровнем конфиденциальности** .</span><span class="sxs-lookup"><span data-stu-id="75523-121">Uses the **Highly Confidential** Office 365 retention label.</span></span> 
- <span data-ttu-id="75523-122">Блокирует пользователей при попытке поделиться цифровым активом в **справочном** сайте за преработкой в компании Contoso.</span><span class="sxs-lookup"><span data-stu-id="75523-122">Blocks users when they attempt to share a digital asset on the **Research** site outside of Contoso.</span></span>

<span data-ttu-id="75523-123">Сведения о конфигурации приведены в разделе [Защита файлов SharePoint с метками хранения и DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span><span class="sxs-lookup"><span data-stu-id="75523-123">For the configuration details, see [Protect SharePoint files with retention labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-3-created-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="75523-124">Шаг 3: создана Подметка Office 365 "чувствительность" для сайта</span><span class="sxs-lookup"><span data-stu-id="75523-124">Step 3: Created an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="75523-125">Администраторы Contoso создали новую подметку Office 365 "чувствительность" с именем " **исследование Teams** " в метке **строго конфиденциальной информации** , которая:</span><span class="sxs-lookup"><span data-stu-id="75523-125">Contoso admins created a new Office 365 sensitivity sublabel named **Research Teams** of the **Highly Confidential** label that:</span></span>

- <span data-ttu-id="75523-126">Требует шифрования.</span><span class="sxs-lookup"><span data-stu-id="75523-126">Requires encryption.</span></span>
- <span data-ttu-id="75523-127">Разрешение на совместное редактирование для группы **исследовательского исследования** Office 365</span><span class="sxs-lookup"><span data-stu-id="75523-127">Allows Co-Author permissions for the **Research** Office 365 group</span></span>
- <span data-ttu-id="75523-128">Применимо к группе **исследовательского исследования** Office 365</span><span class="sxs-lookup"><span data-stu-id="75523-128">Applies to the **Research** Office 365 group</span></span>

<span data-ttu-id="75523-129">Ниже показана итоговая Конфигурация сайта **справочной** группы для строго конфиденциальных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="75523-129">Here is the resulting configuration of the **Research** team site for highly confidential assets.</span></span>

![Результирующая конфигурация сайта справочной группы для строго конфиденциальных активов](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="75523-131">Файлы в папках **справочного** сайта защищены:</span><span class="sxs-lookup"><span data-stu-id="75523-131">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="75523-132">Разрешения сайта, которые позволяют получать доступ только к участникам группы " **исследование** Office 365".</span><span class="sxs-lookup"><span data-stu-id="75523-132">The site permissions, which only allow access to members of the **Research** Office 365 group.</span></span>
- <span data-ttu-id="75523-133">Политика **защиты от** потери данных, которая использует метку и параметры хранения **строго конфиденциальной информации** , которая запрещает доступ к файлу внешним пользователям.</span><span class="sxs-lookup"><span data-stu-id="75523-133">The **Research** DLP policy, which uses the **Highly Confidential** retention label and settings that prevent the file from being shared with external users.</span></span>
- <span data-ttu-id="75523-134">Подметка "Учетная **Группа исследовательских групп** " с шифрованием и разрешениями, которые передаются вместе с файлом при его перемещении или копировании с сайта **справочных материалов** .</span><span class="sxs-lookup"><span data-stu-id="75523-134">The **Research Teams** sensitivity sublabel, with encryption and permissions that travel with the file if it is moved or copied from the **Research** site.</span></span>

<span data-ttu-id="75523-135">Ниже приведен пример файла, хранящегося на сайте **справочных материалов** с назначенной подметкой "чувствительность **группового исследования** ".</span><span class="sxs-lookup"><span data-stu-id="75523-135">Here is an example of a file stored in the **Research** site with the **Research Teams** sensitivity sublabel assigned.</span></span>

![Результирующая конфигурация сайта справочной группы для строго конфиденциальных активов](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config-example-file.png)


## <a name="step-4-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="75523-137">Шаг 4: Перенос локальных данных исследования SharePoint</span><span class="sxs-lookup"><span data-stu-id="75523-137">Step 4: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="75523-138">Администраторы Contoso переехали все локальные файлы исследований на локальном сайте SharePoint Server 2016 в папки на новом сайте **центра исследований** SharePoint.</span><span class="sxs-lookup"><span data-stu-id="75523-138">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint site.</span></span>

## <a name="step-5-trained-their-researchers"></a><span data-ttu-id="75523-139">Шаг 5: обучение исследователей</span><span class="sxs-lookup"><span data-stu-id="75523-139">Step 5: Trained their researchers</span></span>

<span data-ttu-id="75523-140">Сотрудники отдела безопасности Contoso обучены участниками группы **исследование** Office 365 в обязательном курсе, в котором их пошагово проходят:</span><span class="sxs-lookup"><span data-stu-id="75523-140">Contoso security staff trained the members of the **Research** Office 365 group in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="75523-141">Доступ к новому **справочному** сайту и его существующим файлам.</span><span class="sxs-lookup"><span data-stu-id="75523-141">How to access the new **Research** site and its existing files.</span></span>
- <span data-ttu-id="75523-142">как создавать файлы на сайте и отправлять новые файлы, которые хранятся локально;</span><span class="sxs-lookup"><span data-stu-id="75523-142">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="75523-143">Демонстрация того, как политика " **исследование** DLP" блокирует доступ к файлам извне.</span><span class="sxs-lookup"><span data-stu-id="75523-143">A demonstration of how the **Research** DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="75523-144">Пометка файлов с помощью подметки "чувствительность групп" в **справочных материалах** .</span><span class="sxs-lookup"><span data-stu-id="75523-144">How to label files with the **Research Teams** sensitivity sublabel.</span></span>
- <span data-ttu-id="75523-145">Демонстрация того, как суб-метка **исследовательских групп** защищает файл даже при его утечке с сайта.</span><span class="sxs-lookup"><span data-stu-id="75523-145">A demonstration of how the **Research Teams** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="75523-146">Конечный результат — это безопасная среда, в которой исходящие работники могут совместно работать в среде Contoso в безопасной среде для файлов, содержащих справочные сведения.</span><span class="sxs-lookup"><span data-stu-id="75523-146">The end result is a secure environment in which the researchers can collaborate across Contoso in a secure environment on files containing research information.</span></span> 

<span data-ttu-id="75523-147">Если справочный документ с подметкой **исследовательских групп** оставляет сайт **справочных** материалов, он шифруется и доступен только участникам группы **исследование** Office 365 с действительными учетными данными учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="75523-147">If a research document with the **Research Teams** sublabel leaves the **Research** site, it is encrypted and accessible only to members of the **Research** Office 365 group with valid user account credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="75523-148">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="75523-148">Next step</span></span>

<span data-ttu-id="75523-149">[Deploy (развертывание](deploy-microsoft-365-enterprise.md) ) Microsoft 365 корпоративный в Организации.</span><span class="sxs-lookup"><span data-stu-id="75523-149">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="75523-150">См. также</span><span class="sxs-lookup"><span data-stu-id="75523-150">See also</span></span>

<span data-ttu-id="75523-151">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="75523-151">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
