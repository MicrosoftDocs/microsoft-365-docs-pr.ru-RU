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
description: Сводка. Как Contoso использовала команду с изолированностью безопасности для совершенно секретного проекта для разработки нового набора продуктов и служб.
ms.openlocfilehash: d5ab2808251ff6a53f8975ea868431691d3301e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051010"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="c47e0-103">Изолированная команда для совершенно секретного проекта корпорации Contoso</span><span class="sxs-lookup"><span data-stu-id="c47e0-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="c47e0-104">После этого генеральный директор Contoso распорядился разработать новый набор продуктов и служб, который мог бы удвоить прибыль Contoso в течение следующих пяти лет.</span><span class="sxs-lookup"><span data-stu-id="c47e0-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="c47e0-105">Совершенно секретный проект по разработке бизнес-, инженерных и рыночных планов был назван **Project 2X,** и были набрано ключевые сотрудники по всей компании.</span><span class="sxs-lookup"><span data-stu-id="c47e0-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="c47e0-106">Сроки для исследований и разработок были сжатыми, что означало, что совместная работа должна быть эффективной и обеспечивать безопасные собрания, текущие беседы и хранение файлов.</span><span class="sxs-lookup"><span data-stu-id="c47e0-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="c47e0-107">Конечными результатами для Project 2X стали бизнес-планы, спецификации продукта и инженерии, а также маркетинговые материалы и расписания в виде файлов Word, Excel и PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="c47e0-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="c47e0-108">В связи с их конфиденциальным характером доступ к этим файлам был:</span><span class="sxs-lookup"><span data-stu-id="c47e0-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="c47e0-109">Ограничивается членами команды Project 2X и высшим руководством.</span><span class="sxs-lookup"><span data-stu-id="c47e0-109">Restricted to Project 2X team members and senior leadership.</span></span>
- <span data-ttu-id="c47e0-110">Зашифровано и защищено разрешениями, позволяющими получать доступ только к членам команды Project 2X и старшему руководству, даже если файлы распространялись за пределами защищенных папок.</span><span class="sxs-lookup"><span data-stu-id="c47e0-110">Encrypted and protected with permissions to allow access only to Project 2X team members and senior leadership, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="c47e0-111">ИТ-сотрудники Contoso использовали [команду с](secure-teams-security-isolation.md) изолированностью безопасности для Project 2X и эти действия.</span><span class="sxs-lookup"><span data-stu-id="c47e0-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="c47e0-112">Шаг 1. Созданная частная команда</span><span class="sxs-lookup"><span data-stu-id="c47e0-112">Step 1: Created a private team</span></span>

<span data-ttu-id="c47e0-113">Во-первых, чтобы защитить доступ к основному сайту SharePoint для группы, ИТ-администраторы Contoso настроили рекомендуемые политики доступа [к SharePoint.](../security/defender-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c47e0-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/defender-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="c47e0-114">Затем ИТ-администратор Contoso создал новую частную команду с именем Project 2X и добавил учетные записи пользователей сотрудников Project 2X в качестве членов.</span><span class="sxs-lookup"><span data-stu-id="c47e0-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span> <span data-ttu-id="c47e0-115">Они также настраивали команду так, чтобы только владельцы команд Project 2X могли создавать частные каналы.</span><span class="sxs-lookup"><span data-stu-id="c47e0-115">They also configured the team so that only Project 2X team owners can create private channels.</span></span>

<span data-ttu-id="c47e0-116">Сведения о конфигурации см. в [материале Create a private team.](secure-teams-security-isolation.md#create-a-private-team)</span><span class="sxs-lookup"><span data-stu-id="c47e0-116">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="c47e0-117">Шаг 2. Создан метка конфиденциальности для группы Project 2X</span><span class="sxs-lookup"><span data-stu-id="c47e0-117">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="c47e0-118">Администраторы Contoso создали новую метку конфиденциальности с именем **Project 2X,** которая:</span><span class="sxs-lookup"><span data-stu-id="c47e0-118">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="c47e0-119">Включено шифрование.</span><span class="sxs-lookup"><span data-stu-id="c47e0-119">Enabled encryption.</span></span>
- <span data-ttu-id="c47e0-120">Разрешено Co-Author разрешений для группы Project 2X Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c47e0-120">Allowed Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="c47e0-121">Разрешенные разрешения просмотра для группы старших руководителей.</span><span class="sxs-lookup"><span data-stu-id="c47e0-121">Allowed Viewer permissions for the Senior Leadership group.</span></span>
- <span data-ttu-id="c47e0-122">Заблокирован доступ к неугодным устройствам.</span><span class="sxs-lookup"><span data-stu-id="c47e0-122">Blocked access to unmanaged devices.</span></span>

<span data-ttu-id="c47e0-123">Файлы в **разделе Документы** на основном сайте Project 2X SharePoint защищены:</span><span class="sxs-lookup"><span data-stu-id="c47e0-123">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="c47e0-124">Разрешения сайта, которые позволяют только полные разрешения членам группы Project 2X Microsoft 365 и читать разрешения группе старшего руководства.</span><span class="sxs-lookup"><span data-stu-id="c47e0-124">The site permissions, which only allow full permissions to members of the Project 2X Microsoft 365 group and read permissions to the Senior Leadership group.</span></span>
- <span data-ttu-id="c47e0-125">Метка чувствительности Project 2X с шифрованием и разрешениями, которые перемещаются вместе с файлом, если он перемещен или скопирован с сайта.</span><span class="sxs-lookup"><span data-stu-id="c47e0-125">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="c47e0-126">Сведения о конфигурации см. в [материале Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="c47e0-126">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="c47e0-127">Шаг 3. Настройка на основном сайте SharePoint</span><span class="sxs-lookup"><span data-stu-id="c47e0-127">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="c47e0-128">Во-первых, чтобы защитить доступ к основному сайту SharePoint для группы, ИТ-администраторы Contoso настроили рекомендуемые политики доступа [к SharePoint.](../security/defender-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c47e0-128">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/defender-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="c47e0-129">Затем они настроили дополнительные параметры разрешений для сайта:</span><span class="sxs-lookup"><span data-stu-id="c47e0-129">Next, they configured additional permission settings for the site:</span></span>

- <span data-ttu-id="c47e0-130">Чтобы запретить участникам группы Project 2X делиться доступом к сайту.</span><span class="sxs-lookup"><span data-stu-id="c47e0-130">To prevent Project 2X group members from sharing access to the site.</span></span> <span data-ttu-id="c47e0-131">Сведения о конфигурации см. в [разделе Параметры SharePoint для группы с изолированностью безопасности.](secure-teams-security-isolation.md#sharepoint-settings)</span><span class="sxs-lookup"><span data-stu-id="c47e0-131">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>
- <span data-ttu-id="c47e0-132">Для получения разрешений на чтение для группы старших руководителей.</span><span class="sxs-lookup"><span data-stu-id="c47e0-132">For Read permissions for the Senior Leadership group.</span></span>

<span data-ttu-id="c47e0-133">Затем они настроили дополнительные параметры разрешений для сайта, чтобы запретить участникам группы Project 2X делиться доступом к сайту.</span><span class="sxs-lookup"><span data-stu-id="c47e0-133">Next, they configured additional permission settings for the site to prevent Project 2X group members from sharing access to the site.</span></span> 

<span data-ttu-id="c47e0-134">По мере создания частных каналов для Project 2X владелец группы отключил общий доступ к гостю и установил ссылку на общий доступ по умолчанию к значению **Specific people.**</span><span class="sxs-lookup"><span data-stu-id="c47e0-134">As private channels for the Project 2X were created, the group owner disabled guest sharing and set the default sharing link to the **Specific people** value.</span></span>

<span data-ttu-id="c47e0-135">Вот итоговая конфигурация команды Project 2X с изолированностью безопасности.</span><span class="sxs-lookup"><span data-stu-id="c47e0-135">Here is the resulting configuration of the Project 2X team with security isolation.</span></span>

![Итоговая конфигурация команды Project 2X](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="c47e0-137">Шаг 4. Обученные участники группы Project 2X</span><span class="sxs-lookup"><span data-stu-id="c47e0-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="c47e0-138">Сотрудники службы безопасности Contoso обучили членов команды Project 2X обязательным курсом, который прошел через них:</span><span class="sxs-lookup"><span data-stu-id="c47e0-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="c47e0-139">Доступ к новой команде Project 2X, использование собраний и чатов и совместное использование файлов группы.</span><span class="sxs-lookup"><span data-stu-id="c47e0-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="c47e0-140">Создание новых файлов в команде и отправка новых файлов, созданных локально.</span><span class="sxs-lookup"><span data-stu-id="c47e0-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="c47e0-141">Метка файлов с меткой чувствительности Project 2X.</span><span class="sxs-lookup"><span data-stu-id="c47e0-141">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="c47e0-142">Демонстрация того, как метка Project 2X защищает файл, даже если он покидает команду.</span><span class="sxs-lookup"><span data-stu-id="c47e0-142">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="c47e0-143">Конечным результатом стала безопасная среда, в которой члены команды Project 2X сотрудничали в безопасной среде для чатов, собраний и файлов.</span><span class="sxs-lookup"><span data-stu-id="c47e0-143">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="c47e0-144">Вот пример файла, хранимого на основном сайте Project 2X с меткой чувствительности Project 2X.</span><span class="sxs-lookup"><span data-stu-id="c47e0-144">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![Пример файла, хранимого в основном сайте Project 2X](../media/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="c47e0-146">В нескольких случаях участники команды Project 2X скачали файлы, защищенные меткой Project 2X, на локальный диск для автономной работы.</span><span class="sxs-lookup"><span data-stu-id="c47e0-146">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> 

<span data-ttu-id="c47e0-147">Однако после запроса учетных данных при их открытии они осознали свою ошибку и удалили их.</span><span class="sxs-lookup"><span data-stu-id="c47e0-147">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="c47e0-148">Из-за среды совместной работы Teams и функций безопасности Microsoft 365 сведения о Project 2X были сохранены в секрете на протяжении всего проекта.</span><span class="sxs-lookup"><span data-stu-id="c47e0-148">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="c47e0-149">Contoso объявила о своих планах и в настоящее время развертывает новые продукты и услуги на радость своих клиентов и инвесторов и огорчение своих конкурентов.</span><span class="sxs-lookup"><span data-stu-id="c47e0-149">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="c47e0-150">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="c47e0-150">Next step</span></span>

<span data-ttu-id="c47e0-151">[Развертывание группы с изолированностью безопасности](secure-teams-security-isolation.md) в организации.</span><span class="sxs-lookup"><span data-stu-id="c47e0-151">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

