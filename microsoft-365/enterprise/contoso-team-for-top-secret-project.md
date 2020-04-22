---
title: Команда для сверхсекретного проекта корпорации Contoso
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
description: Сводка. сведения о том, как компания Contoso использовала группу для строго регулируемых данных для наиболее поднадзорного проекта, чтобы разработать новый набор продуктов и служб.
ms.openlocfilehash: 310ef33d4add7d71616aee8808515ca90536d8c1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636502"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="f5c53-103">Команда для сверхсекретного проекта корпорации Contoso</span><span class="sxs-lookup"><span data-stu-id="f5c53-103">Team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="f5c53-104">После того, как руководитель организации находится за пределами, Генеральный директор Contoso упорядочивает разработку нового набора продуктов и услуг, которые могут вдвое прибыли от компании Contoso в течение следующих пяти лет.</span><span class="sxs-lookup"><span data-stu-id="f5c53-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="f5c53-105">Проект верхнего уровня для разработки бизнес-, инженерного и маркетингового плана назывался **Project 2x** и основные сотрудники компании.</span><span class="sxs-lookup"><span data-stu-id="f5c53-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="f5c53-106">Временные шкалы для исследования и разработки были тесно выполнены, поэтому совместная работа должна быть эффективной и обеспечивать безопасное собрание, текущие беседы и хранение файлов.</span><span class="sxs-lookup"><span data-stu-id="f5c53-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="f5c53-107">Конечные результаты для проекта 2X: бизнес-планы, спецификации продуктов и технических материалов, а также маркетинговые материалы и расписания в виде файлов Word, Excel и PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="f5c53-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="f5c53-108">Из-за конфиденциальной природы доступ к этим файлам имел следующий вид:</span><span class="sxs-lookup"><span data-stu-id="f5c53-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="f5c53-109">Ограничено членами группы "проект 2X".</span><span class="sxs-lookup"><span data-stu-id="f5c53-109">Restricted to Project 2X team members.</span></span>
- <span data-ttu-id="f5c53-110">Защита от потери данных с помощью политики защиты от потери данных (DLP) для того, чтобы участники группы Project 2X не переключались за их прев группу.</span><span class="sxs-lookup"><span data-stu-id="f5c53-110">Protected with a Data Loss Prevention (DLP) policy to prevent Project 2X team members from sharing them outside the team.</span></span>
- <span data-ttu-id="f5c53-111">Зашифровать и защитить с помощью разрешений, чтобы предоставить доступ только членам группы Project 2X, даже если они были распределены за прев компании Contoso.</span><span class="sxs-lookup"><span data-stu-id="f5c53-111">Encrypted and protected with permissions to allow access only to Project 2X team members, even if the files were distributed outside of Contoso.</span></span>

<span data-ttu-id="f5c53-112">Сотрудники ИТ отдела Contoso использовали [команду для обеспечения высокой регулируемости данных](secure-teams-highly-regulated-data-scenario.md) в Project 2x и этих действий.</span><span class="sxs-lookup"><span data-stu-id="f5c53-112">Contoso IT staff used a [team for highly-regulated data](secure-teams-highly-regulated-data-scenario.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a><span data-ttu-id="f5c53-113">Шаг 1: создание частной команды и блокировка базового сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="f5c53-113">Step 1: Created a private team and locked down the underlying SharePoint site</span></span>

<span data-ttu-id="f5c53-114">Чтобы защитить доступ к базовому сайту SharePoint для группы, ИТ-администраторы Contoso настроили [Рекомендуемые политики доступа к SharePoint](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f5c53-114">To protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="f5c53-115">Затем администратор Contoso создал новую частную группу с именем Project 2X и добавила учетные записи пользователей в качестве участников Project 2X.</span><span class="sxs-lookup"><span data-stu-id="f5c53-115">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span>

<span data-ttu-id="f5c53-116">Затем они настроили дополнительные параметры разрешений для сайта, чтобы предотвратить общий доступ к сайту с помощью Project 2X и запретить другому пользователю запрашивать доступ к сайту.</span><span class="sxs-lookup"><span data-stu-id="f5c53-116">Next, they configured additional permission settings for the site to prevent Project 2X from sharing access to the site and to prevent other from requesting access to the site.</span></span>

<span data-ttu-id="f5c53-117">Сведения о конфигурации можно найти [в разделе Параметры SharePoint для строго регулируемой группы](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).</span><span class="sxs-lookup"><span data-stu-id="f5c53-117">For the configuration details, see [SharePoint settings for a highly regulated team](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).</span></span>

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a><span data-ttu-id="f5c53-118">Шаг 2: Настройка политики защиты от потери данных и базового сайта для метки хранения</span><span class="sxs-lookup"><span data-stu-id="f5c53-118">Step 2: Configured a DLP policy and the underlying site for a retention label</span></span> 

<span data-ttu-id="f5c53-119">Во-первых, администраторы Contoso применили существующую метку **строго конфиденциального** хранения к разделу " **документы** " на базовом сайте SharePoint для группы "проект 2x".</span><span class="sxs-lookup"><span data-stu-id="f5c53-119">First, Contoso admins applied the existing **Highly Confidential** retention label to the **Documents** section of the underlying SharePoint site of the Project 2X team.</span></span>

<span data-ttu-id="f5c53-120">После этого создаются новые политики DLP с именем **Project 2x** , которые:</span><span class="sxs-lookup"><span data-stu-id="f5c53-120">Next, they created a new DLP policy named **Project 2X** that:</span></span>

- <span data-ttu-id="f5c53-121">Использует метку хранения строго конфиденциально.</span><span class="sxs-lookup"><span data-stu-id="f5c53-121">Uses the Highly Confidential retention label.</span></span>
- <span data-ttu-id="f5c53-122">Блокирует пользователей при попытке предоставить общий доступ к файлу в группе "проект 2" за преходясь в компании Contoso.</span><span class="sxs-lookup"><span data-stu-id="f5c53-122">Blocks users when they attempt to share a file in the Project 2X team outside of Contoso.</span></span>

<span data-ttu-id="f5c53-123">Сведения о конфигурации приведены в разделе [Защита файлов в Teams с метками хранения и DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).</span><span class="sxs-lookup"><span data-stu-id="f5c53-123">For the configuration details, see [Protect files in teams with retention labels and DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).</span></span>

## <a name="step-3-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="f5c53-124">Шаг 3: создание метки чувствительности для группы проекта 2X</span><span class="sxs-lookup"><span data-stu-id="f5c53-124">Step 3: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="f5c53-125">Администраторы Contoso создали новую метку чувствительности с именем **Project 2x** , которая:</span><span class="sxs-lookup"><span data-stu-id="f5c53-125">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="f5c53-126">Требует шифрования.</span><span class="sxs-lookup"><span data-stu-id="f5c53-126">Requires encryption.</span></span>
- <span data-ttu-id="f5c53-127">Разрешает разрешения совместного редактирования для группы Microsoft 365 в проекте 2X.</span><span class="sxs-lookup"><span data-stu-id="f5c53-127">Allows Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>

<span data-ttu-id="f5c53-128">Ниже показана итоговая конфигурация команды Project 2X.</span><span class="sxs-lookup"><span data-stu-id="f5c53-128">Here is the resulting configuration of the Project 2X team.</span></span>

![Итоговая конфигурация команды Project 2X](../media/contoso-team-for-highly-confidential-assets/final-config.png)
 
<span data-ttu-id="f5c53-130">Файлы в разделе документы базового сайта SharePoint на 2X защищены:</span><span class="sxs-lookup"><span data-stu-id="f5c53-130">Files in the Documents section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="f5c53-131">Разрешения сайта, которые разрешают доступ только к участникам группы Microsoft 365 в проекте 2X.</span><span class="sxs-lookup"><span data-stu-id="f5c53-131">The site permissions, which only allow access to members of the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="f5c53-132">Метка хранения строго конфиденциальной информации, которая автоматически назначается новым файлам.</span><span class="sxs-lookup"><span data-stu-id="f5c53-132">The  Highly Confidential retention label, which is automatically assigned to new files.</span></span>
- <span data-ttu-id="f5c53-133">Политика защиты от потери данных, использующая метку хранения строго конфиденциальной информации и параметры, которые блокируют доступ внешних пользователей к файлу.</span><span class="sxs-lookup"><span data-stu-id="f5c53-133">A DLP policy that uses the Highly Confidential retention label and settings that block the file from being shared with external users.</span></span>
- <span data-ttu-id="f5c53-134">Метка "чувствительность к проекту 2X" с шифрованием и разрешениями, которые передаются вместе с файлом, если он перемещается или копируется с сайта.</span><span class="sxs-lookup"><span data-stu-id="f5c53-134">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="f5c53-135">Ниже приведен пример файла, хранящегося на базовом сайте с высоким уровнем поднадзорной метки хранения и назначенной метке о конфиденциальности для проекта 2X.</span><span class="sxs-lookup"><span data-stu-id="f5c53-135">Here is an example of a file stored in the underlying Project 2X site with the Highly Regulated retention label and the Project 2X sensitivity label assigned.</span></span>

![Пример файла, хранящегося на сайте базового проекта 2X](../media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="f5c53-137">Шаг 4: квалифицированные участники группы для Project 2X</span><span class="sxs-lookup"><span data-stu-id="f5c53-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="f5c53-138">Сотрудники отдела безопасности Contoso обучены членам группы "проект 2" в обязательном курсе, в котором их пошагово пройдет следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f5c53-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="f5c53-139">Как получить доступ к новой команде Project 2X, использовать собрания и беседы, а также как совместно работать с файлами группы.</span><span class="sxs-lookup"><span data-stu-id="f5c53-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="f5c53-140">Создание новых файлов в команде и отправка новых файлов, созданных локально.</span><span class="sxs-lookup"><span data-stu-id="f5c53-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="f5c53-141">Демонстрация того, как политика DLP блокирует доступ к файлам извне.</span><span class="sxs-lookup"><span data-stu-id="f5c53-141">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="f5c53-142">Пометка файлов с помощью метки чувствительности к проекту 2X.</span><span class="sxs-lookup"><span data-stu-id="f5c53-142">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="f5c53-143">Демонстрация того, как подпись проекта 2X защищает файл, даже если он покидает команду.</span><span class="sxs-lookup"><span data-stu-id="f5c53-143">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="f5c53-144">Конечный результат — это безопасная среда, в которой участники группы Project 2X совместно работают в безопасной среде для чатов, собраний и файлов.</span><span class="sxs-lookup"><span data-stu-id="f5c53-144">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="f5c53-145">В нескольких экземплярах участники группы Project 2X загрузили файлы, защищенные меткой проекта 2X, на локальный диск для работы в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="f5c53-145">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> <span data-ttu-id="f5c53-146">Однако после того как вы запрашиваете учетные данные при их открытии, они выдавали свои ошибки и удалили их.</span><span class="sxs-lookup"><span data-stu-id="f5c53-146">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="f5c53-147">Из-за среды совместной работы Teams и функций безопасности Microsoft 365 сведения о проекте 2X хранятся в секрете в течение проекта.</span><span class="sxs-lookup"><span data-stu-id="f5c53-147">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="f5c53-148">Компания Contoso объявила о своих планах и в процессе развертывания новых продуктов и служб в сведения своих клиентов и инвесторов и Чагрин конкурентов.</span><span class="sxs-lookup"><span data-stu-id="f5c53-148">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="f5c53-149">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="f5c53-149">Next step</span></span>

<span data-ttu-id="f5c53-150">[Deploy (развертывание](deploy-microsoft-365-enterprise.md) ) Microsoft 365 корпоративный в Организации.</span><span class="sxs-lookup"><span data-stu-id="f5c53-150">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5c53-151">См. также</span><span class="sxs-lookup"><span data-stu-id="f5c53-151">See also</span></span>

<span data-ttu-id="f5c53-152">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="f5c53-152">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
