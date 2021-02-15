---
title: Изолированная команда для совершенно секретного проекта корпорации Contoso
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/14/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: Сводка. Сведения о том, как в компании Contoso использовали команду с изоляцией безопасности для совершенно секретного проекта для разработки нового набора продуктов и служб.
ms.openlocfilehash: b8794502afcb77a8e597a1b05dfc92acd093f23a
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656073"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="674d6-103">Изолированная команда для совершенно секретного проекта корпорации Contoso</span><span class="sxs-lookup"><span data-stu-id="674d6-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="674d6-104">После того как исполнительный директор компании Contoso упростил разработку нового набора продуктов и услуг, которые могут увеличить прибыль contoso в течение следующих пяти лет, в два раза.</span><span class="sxs-lookup"><span data-stu-id="674d6-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="674d6-105">Проект верхнего секрета для разработки плана для бизнеса, проектирования и рынка назывался **Project 2X,** и были набраы ключевые сотрудники в компании.</span><span class="sxs-lookup"><span data-stu-id="674d6-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="674d6-106">Сроки для исследований и разработок были строгими, поэтому совместная работа должна быть эффективной и обеспечивать безопасные собрания, текущие беседы и хранение файлов.</span><span class="sxs-lookup"><span data-stu-id="674d6-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="674d6-107">Конечными результатами для Project 2X стали бизнес-планы, спецификации продуктов и инженеров, а также маркетинговые материалы и расписания в виде файлов Word, Excel и PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="674d6-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="674d6-108">Из-за их конфиденциальности доступ к этим файлам был:</span><span class="sxs-lookup"><span data-stu-id="674d6-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="674d6-109">Ограничено участниками группы Project 2X и старшим руководством.</span><span class="sxs-lookup"><span data-stu-id="674d6-109">Restricted to Project 2X team members and senior leadership.</span></span>
- <span data-ttu-id="674d6-110">Зашифровано и защищено разрешениями, чтобы разрешить доступ только участникам группы Project 2X и старшему руководству, даже если файлы были распределены за пределы защищенных папок.</span><span class="sxs-lookup"><span data-stu-id="674d6-110">Encrypted and protected with permissions to allow access only to Project 2X team members and senior leadership, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="674d6-111">ИТ-персонал компании Contoso использовал команду [с изоляцией безопасности](secure-teams-security-isolation.md) для Project 2X и указанными здесь действиями.</span><span class="sxs-lookup"><span data-stu-id="674d6-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="674d6-112">Шаг 1. Создана частная команда</span><span class="sxs-lookup"><span data-stu-id="674d6-112">Step 1: Created a private team</span></span>

<span data-ttu-id="674d6-113">Во-первых, чтобы защитить доступ группы к основному сайту SharePoint, ИТ-администраторы Contoso настроили рекомендуемые политики [доступа SharePoint.](../security/office-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="674d6-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="674d6-114">Затем ИТ-администратор Contoso создал частную команду с именем Project 2X и добавил учетные записи сотрудников Project 2X в качестве участников.</span><span class="sxs-lookup"><span data-stu-id="674d6-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span> <span data-ttu-id="674d6-115">Они также настроили команду так, чтобы только владельцы команды Project 2X могли создавать частные каналы.</span><span class="sxs-lookup"><span data-stu-id="674d6-115">They also configured the team so that only Project 2X team owners can create private channels.</span></span>

<span data-ttu-id="674d6-116">Дополнительные сведения о конфигурации см. в сведениях [о создании закрытой команды.](secure-teams-security-isolation.md#create-a-private-team)</span><span class="sxs-lookup"><span data-stu-id="674d6-116">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="674d6-117">Шаг 2. Создана метка конфиденциальности для группы Project 2X</span><span class="sxs-lookup"><span data-stu-id="674d6-117">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="674d6-118">Администраторы Contoso создали новую метку конфиденциальности **с именем Project 2X,** которая:</span><span class="sxs-lookup"><span data-stu-id="674d6-118">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="674d6-119">Включенное шифрование.</span><span class="sxs-lookup"><span data-stu-id="674d6-119">Enabled encryption.</span></span>
- <span data-ttu-id="674d6-120">Разрешено Co-Author разрешений для группы Project 2X Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="674d6-120">Allowed Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="674d6-121">Разрешения "Просмотр" для группы "Старшие руководители".</span><span class="sxs-lookup"><span data-stu-id="674d6-121">Allowed Viewer permissions for the Senior Leadership group.</span></span>
- <span data-ttu-id="674d6-122">Заблокирован доступ к неугодным устройствам.</span><span class="sxs-lookup"><span data-stu-id="674d6-122">Blocked access to unmanaged devices.</span></span>

<span data-ttu-id="674d6-123">Файлы в **разделе "Документы"** на основном сайте SharePoint Project 2X защищены с помощью:</span><span class="sxs-lookup"><span data-stu-id="674d6-123">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="674d6-124">Разрешения сайта, которые позволяют только полные разрешения участникам группы Project 2X Microsoft 365 и разрешения на чтение для группы старших руководителей.</span><span class="sxs-lookup"><span data-stu-id="674d6-124">The site permissions, which only allow full permissions to members of the Project 2X Microsoft 365 group and read permissions to the Senior Leadership group.</span></span>
- <span data-ttu-id="674d6-125">Метка конфиденциальности Project 2X с шифрованием и разрешениями, которые перемещаются вместе с файлом, если он перемещен или скопирован с сайта.</span><span class="sxs-lookup"><span data-stu-id="674d6-125">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="674d6-126">Дополнительные сведения о конфигурации см. в под [названием "Создание метки конфиденциальности".](secure-teams-security-isolation.md#create-a-sensitivity-label)</span><span class="sxs-lookup"><span data-stu-id="674d6-126">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="674d6-127">Шаг 3. Настройка сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="674d6-127">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="674d6-128">Во-первых, чтобы защитить доступ группы к основному сайту SharePoint, ИТ-администраторы Contoso настроили рекомендуемые политики [доступа SharePoint.](../security/office-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="674d6-128">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="674d6-129">Затем они настроили дополнительные параметры разрешений для сайта:</span><span class="sxs-lookup"><span data-stu-id="674d6-129">Next, they configured additional permission settings for the site:</span></span>

- <span data-ttu-id="674d6-130">Чтобы запретить участникам группы Project 2X доступ к сайту.</span><span class="sxs-lookup"><span data-stu-id="674d6-130">To prevent Project 2X group members from sharing access to the site.</span></span> <span data-ttu-id="674d6-131">Подробные сведения о конфигурации см. в [параметрах SharePoint для команды с изоляцией системы безопасности.](secure-teams-security-isolation.md#sharepoint-settings)</span><span class="sxs-lookup"><span data-stu-id="674d6-131">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>
- <span data-ttu-id="674d6-132">Для разрешений на чтение для группы старших руководителей.</span><span class="sxs-lookup"><span data-stu-id="674d6-132">For Read permissions for the Senior Leadership group.</span></span>

<span data-ttu-id="674d6-133">Затем они настроили дополнительные параметры разрешений для сайта, чтобы запретить участникам группы Project 2X доступ к сайту.</span><span class="sxs-lookup"><span data-stu-id="674d6-133">Next, they configured additional permission settings for the site to prevent Project 2X group members from sharing access to the site.</span></span> 

<span data-ttu-id="674d6-134">Когда были созданы частные каналы для Project 2X, владелец группы отключил гостевой общий доступ и установил для ссылки для общего доступа по умолчанию значение **"Конкретные люди".**</span><span class="sxs-lookup"><span data-stu-id="674d6-134">As private channels for the Project 2X were created, the group owner disabled guest sharing and set the default sharing link to the **Specific people** value.</span></span>

<span data-ttu-id="674d6-135">Ниже приводится итоговая конфигурация команды Project 2X с изоляцией системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="674d6-135">Here is the resulting configuration of the Project 2X team with security isolation.</span></span>

![Итоговая конфигурация команды Project 2X](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="674d6-137">Шаг 4. Обученные участники группы Project 2X</span><span class="sxs-lookup"><span data-stu-id="674d6-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="674d6-138">Сотрудники службы безопасности Contoso прошли обязательный курс обучения участников группы Project 2X, который прошел их пошаговые процедуры:</span><span class="sxs-lookup"><span data-stu-id="674d6-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="674d6-139">Как получить доступ к новой команде Project 2X, использовать собрания и чаты, а также как совместно работать с файлами команды.</span><span class="sxs-lookup"><span data-stu-id="674d6-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="674d6-140">Создание новых файлов в команде и отправка новых файлов, созданных локально.</span><span class="sxs-lookup"><span data-stu-id="674d6-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="674d6-141">Как пометить файлы меткой конфиденциальности Project 2X.</span><span class="sxs-lookup"><span data-stu-id="674d6-141">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="674d6-142">Демонстрация того, как метка Project 2X защищает файл, даже когда он покидает команду.</span><span class="sxs-lookup"><span data-stu-id="674d6-142">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="674d6-143">В результате была защищенная среда, в которой участники группы Project 2X совместно участвовали в безопасной среде для чатов, собраний и файлов.</span><span class="sxs-lookup"><span data-stu-id="674d6-143">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="674d6-144">Вот пример файла, хранимого на основном сайте Project 2X с назначенной меткой конфиденциальности Project 2X.</span><span class="sxs-lookup"><span data-stu-id="674d6-144">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![Пример файла, хранимого на основном сайте Project 2X](../media/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="674d6-146">В нескольких случаях участники группы Project 2X скачали файлы, защищенные меткой Project 2X, на локальный диск для автономной работы.</span><span class="sxs-lookup"><span data-stu-id="674d6-146">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> 

<span data-ttu-id="674d6-147">Однако после запроса учетных данных при их открытии они поняли свою ошибку и удалили их.</span><span class="sxs-lookup"><span data-stu-id="674d6-147">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="674d6-148">Из-за среды совместной работы Teams и функций безопасности Microsoft 365 сведения о Project 2X хранились в секрете на протяжении всего проекта.</span><span class="sxs-lookup"><span data-stu-id="674d6-148">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="674d6-149">Компания Contoso объявляла о своих планах и в настоящее время развертывает новые продукты и службы, чтобы почаховать клиентов и инвестиций, а также отчаить конкурентов.</span><span class="sxs-lookup"><span data-stu-id="674d6-149">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="674d6-150">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="674d6-150">Next step</span></span>

<span data-ttu-id="674d6-151">[Развертывание команды с изоляцией безопасности](secure-teams-security-isolation.md) в организации.</span><span class="sxs-lookup"><span data-stu-id="674d6-151">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

