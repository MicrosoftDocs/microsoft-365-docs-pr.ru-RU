---
title: Изолированная группа для верхнего уровня секретного проекта корпорации Contoso
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: Сводка. сведения о том, как компания Contoso использовала группу с изоляцией безопасности для проекта верхнего уровня, чтобы разработать новый набор продуктов и служб.
ms.openlocfilehash: 2da51890001a2890b2d65bc6b71537b51c335eb4
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/01/2020
ms.locfileid: "44003215"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="79592-103">Изолированная группа для верхнего уровня секретного проекта корпорации Contoso</span><span class="sxs-lookup"><span data-stu-id="79592-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="79592-104">После того, как руководитель организации находится за пределами, Генеральный директор Contoso упорядочивает разработку нового набора продуктов и услуг, которые могут вдвое прибыли от компании Contoso в течение следующих пяти лет.</span><span class="sxs-lookup"><span data-stu-id="79592-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="79592-105">Проект верхнего уровня для разработки бизнес-, инженерного и маркетингового плана назывался **Project 2x** и основные сотрудники компании.</span><span class="sxs-lookup"><span data-stu-id="79592-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="79592-106">Временные шкалы для исследования и разработки были тесно выполнены, поэтому совместная работа должна быть эффективной и обеспечивать безопасное собрание, текущие беседы и хранение файлов.</span><span class="sxs-lookup"><span data-stu-id="79592-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="79592-107">Конечные результаты для проекта 2X: бизнес-планы, спецификации продуктов и технических материалов, а также маркетинговые материалы и расписания в виде файлов Word, Excel и PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="79592-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="79592-108">Из-за конфиденциальной природы доступ к этим файлам имел следующий вид:</span><span class="sxs-lookup"><span data-stu-id="79592-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="79592-109">Ограничено членами группы "проект 2X".</span><span class="sxs-lookup"><span data-stu-id="79592-109">Restricted to Project 2X team members.</span></span>
- <span data-ttu-id="79592-110">Шифруются и защищаются с помощью разрешений, чтобы предоставить доступ только участникам группы в Project 2X, даже если файлы были распределены за прев них папки.</span><span class="sxs-lookup"><span data-stu-id="79592-110">Encrypted and protected with permissions to allow access only to Project 2X team members, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="79592-111">Сотрудники ИТ Contoso использовали [команду с изоляцией безопасности](secure-teams-security-isolation.md) для Project 2x и следующими действиями.</span><span class="sxs-lookup"><span data-stu-id="79592-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="79592-112">Шаг 1: создание частной команды</span><span class="sxs-lookup"><span data-stu-id="79592-112">Step 1: Created a private team</span></span>

<span data-ttu-id="79592-113">Во-первых, чтобы защитить доступ к базовому сайту SharePoint для группы, ИТ-администраторы Contoso настроили [Рекомендуемые политики доступа к SharePoint](../enterprise/sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="79592-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="79592-114">Затем администратор Contoso создал новую частную группу с именем Project 2X и добавила учетные записи пользователей в качестве участников Project 2X.</span><span class="sxs-lookup"><span data-stu-id="79592-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span>

<span data-ttu-id="79592-115">Сведения о конфигурации можно найти в статье [Создание частной команды](secure-teams-security-isolation.md#create-a-private-team).</span><span class="sxs-lookup"><span data-stu-id="79592-115">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="79592-116">Шаг 2: создание метки чувствительности для группы проекта 2X</span><span class="sxs-lookup"><span data-stu-id="79592-116">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="79592-117">Администраторы Contoso создали новую метку чувствительности с именем **Project 2x** , которая:</span><span class="sxs-lookup"><span data-stu-id="79592-117">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="79592-118">Требует шифрования.</span><span class="sxs-lookup"><span data-stu-id="79592-118">Requires encryption.</span></span>
- <span data-ttu-id="79592-119">Разрешает разрешения совместного редактирования для группы Microsoft 365 в проекте 2X.</span><span class="sxs-lookup"><span data-stu-id="79592-119">Allows Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>

<span data-ttu-id="79592-120">Файлы в разделе **документы** базового сайта SharePoint на 2x защищены:</span><span class="sxs-lookup"><span data-stu-id="79592-120">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="79592-121">Разрешения сайта, которые разрешают доступ только к участникам группы Microsoft 365 в проекте 2X.</span><span class="sxs-lookup"><span data-stu-id="79592-121">The site permissions, which only allow access to members of the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="79592-122">Метка "чувствительность к проекту 2X" с шифрованием и разрешениями, которые передаются вместе с файлом, если он перемещается или копируется с сайта.</span><span class="sxs-lookup"><span data-stu-id="79592-122">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="79592-123">Сведения о конфигурации приведены в разделе [Создание метки конфиденциальности](secure-teams-security-isolation.md#create-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="79592-123">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="79592-124">Шаг 3: Настройка базового сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="79592-124">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="79592-125">Во-первых, чтобы защитить доступ к базовому сайту SharePoint для группы, ИТ-администраторы Contoso настроили [Рекомендуемые политики доступа к SharePoint](../enterprise/sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="79592-125">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="79592-126">Затем они настроили дополнительные параметры разрешений для сайта, чтобы предотвратить общий доступ к сайту с помощью Project 2X.</span><span class="sxs-lookup"><span data-stu-id="79592-126">Next, they configured additional permission settings for the site to prevent Project 2X from sharing access to the site.</span></span> <span data-ttu-id="79592-127">Сведения о конфигурации представлены в разделе [Параметры SharePoint для группы с изоляцией безопасности](secure-teams-security-isolation.md#sharepoint-settings).</span><span class="sxs-lookup"><span data-stu-id="79592-127">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>

<span data-ttu-id="79592-128">Ниже показана итоговая конфигурация команды Project 2X.</span><span class="sxs-lookup"><span data-stu-id="79592-128">Here is the resulting configuration of the Project 2X team.</span></span>

![Итоговая конфигурация команды Project 2X](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="79592-130">Шаг 4: квалифицированные участники группы для Project 2X</span><span class="sxs-lookup"><span data-stu-id="79592-130">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="79592-131">Сотрудники отдела безопасности Contoso обучены членам группы "проект 2" в обязательном курсе, в котором их пошагово пройдет следующим образом:</span><span class="sxs-lookup"><span data-stu-id="79592-131">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="79592-132">Как получить доступ к новой команде Project 2X, использовать собрания и беседы, а также как совместно работать с файлами группы.</span><span class="sxs-lookup"><span data-stu-id="79592-132">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="79592-133">Создание новых файлов в команде и отправка новых файлов, созданных локально.</span><span class="sxs-lookup"><span data-stu-id="79592-133">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="79592-134">Демонстрация того, как политика DLP блокирует доступ к файлам извне.</span><span class="sxs-lookup"><span data-stu-id="79592-134">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="79592-135">Пометка файлов с помощью метки чувствительности к проекту 2X.</span><span class="sxs-lookup"><span data-stu-id="79592-135">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="79592-136">Демонстрация того, как подпись проекта 2X защищает файл, даже если он покидает команду.</span><span class="sxs-lookup"><span data-stu-id="79592-136">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="79592-137">Конечный результат — это безопасная среда, в которой участники группы Project 2X совместно работают в безопасной среде для чатов, собраний и файлов.</span><span class="sxs-lookup"><span data-stu-id="79592-137">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="79592-138">Ниже приведен пример файла, хранящегося на базовом сайте с проектом 2X с назначенной меткой конфиденциальности для проекта 2X.</span><span class="sxs-lookup"><span data-stu-id="79592-138">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![Пример файла, хранящегося на сайте базового проекта 2X](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="79592-140">В нескольких экземплярах участники группы Project 2X загрузили файлы, защищенные меткой проекта 2X, на локальный диск для работы в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="79592-140">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> <span data-ttu-id="79592-141">Однако после того как вы запрашиваете учетные данные при их открытии, они выдавали свои ошибки и удалили их.</span><span class="sxs-lookup"><span data-stu-id="79592-141">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="79592-142">Из-за среды совместной работы Teams и функций безопасности Microsoft 365 сведения о проекте 2X хранятся в секрете в течение проекта.</span><span class="sxs-lookup"><span data-stu-id="79592-142">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="79592-143">Компания Contoso объявила о своих планах и в процессе развертывания новых продуктов и служб в сведения своих клиентов и инвесторов и Чагрин конкурентов.</span><span class="sxs-lookup"><span data-stu-id="79592-143">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="79592-144">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="79592-144">Next step</span></span>

<span data-ttu-id="79592-145">[Развертывание группы с изоляцией безопасности](secure-teams-security-isolation.md) в Организации.</span><span class="sxs-lookup"><span data-stu-id="79592-145">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

