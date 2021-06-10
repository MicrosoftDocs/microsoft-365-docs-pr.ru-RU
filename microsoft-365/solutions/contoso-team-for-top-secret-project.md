---
title: Изолированная команда для совершенно секретного проекта корпорации Contoso
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
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
ms.openlocfilehash: 751bf3972d148219a6cc341067c0bf34cd581447
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2021
ms.locfileid: "52029020"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="11c90-103">Изолированная команда для совершенно секретного проекта корпорации Contoso</span><span class="sxs-lookup"><span data-stu-id="11c90-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="11c90-104">После этого генеральный директор Contoso распорядился разработать новый набор продуктов и служб, который мог бы удвоить прибыль Contoso в течение следующих пяти лет.</span><span class="sxs-lookup"><span data-stu-id="11c90-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="11c90-105">Совершенно секретный проект по разработке бизнес-, инженерных и рыночных планов был Project **2X,** и были набрано ключевые сотрудники в компании.</span><span class="sxs-lookup"><span data-stu-id="11c90-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="11c90-106">Сроки для исследований и разработок были сжатыми, что означало, что совместная работа должна быть эффективной и обеспечивать безопасные собрания, текущие беседы и хранение файлов.</span><span class="sxs-lookup"><span data-stu-id="11c90-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="11c90-107">В результате для Project 2X были бизнес-планы, спецификации продукта и инженерии, а также маркетинговые материалы и расписания в виде файлов Word, Excel и PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="11c90-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="11c90-108">В связи с их конфиденциальным характером доступ к этим файлам был:</span><span class="sxs-lookup"><span data-stu-id="11c90-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="11c90-109">Ограничивается Project 2X членов команды и высшего руководства.</span><span class="sxs-lookup"><span data-stu-id="11c90-109">Restricted to Project 2X team members and senior leadership.</span></span>
- <span data-ttu-id="11c90-110">Шифруется и защищено разрешениями, чтобы разрешить доступ только Project 2X членам команды и старшему руководству, даже если файлы распространялись за пределами их защищенных папок.</span><span class="sxs-lookup"><span data-stu-id="11c90-110">Encrypted and protected with permissions to allow access only to Project 2X team members and senior leadership, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="11c90-111">ИТ-сотрудники Contoso использовали команду [с](secure-teams-security-isolation.md) изолированностью безопасности для Project 2X и этих действий.</span><span class="sxs-lookup"><span data-stu-id="11c90-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="11c90-112">Шаг 1. Созданная частная команда</span><span class="sxs-lookup"><span data-stu-id="11c90-112">Step 1: Created a private team</span></span>

<span data-ttu-id="11c90-113">Во-первых, чтобы защитить доступ к основному сайту SharePoint для группы, ИТ-администраторы Contoso настроили рекомендуемые политики SharePoint [доступа.](../security/office-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="11c90-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="11c90-114">Затем ИТ-администратор Contoso создал новую частную команду с именем Project 2X и добавил учетные записи пользователей Project 2X в качестве членов.</span><span class="sxs-lookup"><span data-stu-id="11c90-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span> <span data-ttu-id="11c90-115">Они также настраивали команду так, чтобы только Project 2X-команд могли создавать частные каналы.</span><span class="sxs-lookup"><span data-stu-id="11c90-115">They also configured the team so that only Project 2X team owners can create private channels.</span></span>

<span data-ttu-id="11c90-116">Сведения о конфигурации см. в [материале Create a private team.](secure-teams-security-isolation.md#create-a-private-team)</span><span class="sxs-lookup"><span data-stu-id="11c90-116">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="11c90-117">Шаг 2. Создан метка конфиденциальности для Project 2X</span><span class="sxs-lookup"><span data-stu-id="11c90-117">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="11c90-118">Администраторы Contoso создали новую метку конфиденциальности с именем **Project 2X,** которая:</span><span class="sxs-lookup"><span data-stu-id="11c90-118">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="11c90-119">Включено шифрование.</span><span class="sxs-lookup"><span data-stu-id="11c90-119">Enabled encryption.</span></span>
- <span data-ttu-id="11c90-120">Разрешено Co-Author разрешений для Project 2X Microsoft 365 группы.</span><span class="sxs-lookup"><span data-stu-id="11c90-120">Allowed Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="11c90-121">Разрешенные разрешения просмотра для группы старших руководителей.</span><span class="sxs-lookup"><span data-stu-id="11c90-121">Allowed Viewer permissions for the Senior Leadership group.</span></span>
- <span data-ttu-id="11c90-122">Заблокирован доступ к неугодным устройствам.</span><span class="sxs-lookup"><span data-stu-id="11c90-122">Blocked access to unmanaged devices.</span></span>

<span data-ttu-id="11c90-123">Файлы в **разделе Документы** в основном сайте Project 2X SharePoint защищены:</span><span class="sxs-lookup"><span data-stu-id="11c90-123">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="11c90-124">Разрешения сайта, которые позволяют только полные разрешения членам группы Project 2X Microsoft 365 и читать разрешения группе старшего руководства.</span><span class="sxs-lookup"><span data-stu-id="11c90-124">The site permissions, which only allow full permissions to members of the Project 2X Microsoft 365 group and read permissions to the Senior Leadership group.</span></span>
- <span data-ttu-id="11c90-125">Метка Project 2X с шифрованием и разрешениями, которые перемещаются с файлом при перемещении или копировании с сайта.</span><span class="sxs-lookup"><span data-stu-id="11c90-125">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="11c90-126">Сведения о конфигурации см. в [материале Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="11c90-126">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="11c90-127">Шаг 3. Настройка SharePoint сайта</span><span class="sxs-lookup"><span data-stu-id="11c90-127">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="11c90-128">Во-первых, чтобы защитить доступ к основному сайту SharePoint для группы, ИТ-администраторы Contoso настроили рекомендуемые политики SharePoint [доступа.](../security/office-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="11c90-128">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="11c90-129">Затем они настроили дополнительные параметры разрешений для сайта:</span><span class="sxs-lookup"><span data-stu-id="11c90-129">Next, they configured additional permission settings for the site:</span></span>

- <span data-ttu-id="11c90-130">Чтобы Project участникам группы 2X не удалось делиться доступом к сайту.</span><span class="sxs-lookup"><span data-stu-id="11c90-130">To prevent Project 2X group members from sharing access to the site.</span></span> <span data-ttu-id="11c90-131">Сведения о конфигурации см. [в SharePoint параметров для группы с изолированностью безопасности.](secure-teams-security-isolation.md#sharepoint-settings)</span><span class="sxs-lookup"><span data-stu-id="11c90-131">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>
- <span data-ttu-id="11c90-132">Для получения разрешений на чтение для группы старших руководителей.</span><span class="sxs-lookup"><span data-stu-id="11c90-132">For Read permissions for the Senior Leadership group.</span></span>

<span data-ttu-id="11c90-133">Далее они настроили дополнительные параметры разрешений для сайта, чтобы Project участникам группы 2X доступ к сайту.</span><span class="sxs-lookup"><span data-stu-id="11c90-133">Next, they configured additional permission settings for the site to prevent Project 2X group members from sharing access to the site.</span></span> 

<span data-ttu-id="11c90-134">По мере создания частных каналов Project 2X владелец группы отключил общий доступ к гостю и установил ссылку на общий доступ по умолчанию к значению **Specific people.**</span><span class="sxs-lookup"><span data-stu-id="11c90-134">As private channels for the Project 2X were created, the group owner disabled guest sharing and set the default sharing link to the **Specific people** value.</span></span>

<span data-ttu-id="11c90-135">Вот итоговая конфигурация команды Project 2X с изолированностью безопасности.</span><span class="sxs-lookup"><span data-stu-id="11c90-135">Here is the resulting configuration of the Project 2X team with security isolation.</span></span>

![В результате конфигурация команды Project 2X](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="11c90-137">Шаг 4. Обучение Project членов команды 2X</span><span class="sxs-lookup"><span data-stu-id="11c90-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="11c90-138">Сотрудники службы безопасности Contoso обучили членов Project 2X в обязательный курс, который прошел через них:</span><span class="sxs-lookup"><span data-stu-id="11c90-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="11c90-139">Доступ к новой команде Project 2X, использование собраний и чатов и совместное использование файлов группы.</span><span class="sxs-lookup"><span data-stu-id="11c90-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="11c90-140">Создание новых файлов в команде и отправка новых файлов, созданных локально.</span><span class="sxs-lookup"><span data-stu-id="11c90-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="11c90-141">Как маркировать файлы меткой Project 2X.</span><span class="sxs-lookup"><span data-stu-id="11c90-141">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="11c90-142">Демонстрация того, как метка Project 2X защищает файл, даже если он покидает команду.</span><span class="sxs-lookup"><span data-stu-id="11c90-142">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="11c90-143">Конечным результатом стала безопасная среда, в которой Project 2X сотрудничали в безопасной среде для чатов, собраний и файлов.</span><span class="sxs-lookup"><span data-stu-id="11c90-143">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="11c90-144">Вот пример файла, хранимого в основном сайте Project 2X с присвоенным меткой чувствительности Project 2X.</span><span class="sxs-lookup"><span data-stu-id="11c90-144">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![Пример файла, хранимого в основном сайте Project 2X](../media/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="11c90-146">В нескольких случаях члены Project 2X скачали файлы, защищенные меткой 2X Project 2X, на локальный диск для автономной работы.</span><span class="sxs-lookup"><span data-stu-id="11c90-146">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> 

<span data-ttu-id="11c90-147">Однако после запроса учетных данных при их открытии они осознали свою ошибку и удалили их.</span><span class="sxs-lookup"><span data-stu-id="11c90-147">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="11c90-148">Из-за среды совместной Teams и функций безопасности Microsoft 365, сведения о Project 2X хранятся в секрете на протяжении всего проекта.</span><span class="sxs-lookup"><span data-stu-id="11c90-148">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="11c90-149">Contoso объявила о своих планах и в настоящее время развертывает новые продукты и услуги на радость своих клиентов и инвесторов и огорчение своих конкурентов.</span><span class="sxs-lookup"><span data-stu-id="11c90-149">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="11c90-150">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="11c90-150">Next step</span></span>

<span data-ttu-id="11c90-151">[Развертывание группы с изолированностью безопасности](secure-teams-security-isolation.md) в организации.</span><span class="sxs-lookup"><span data-stu-id="11c90-151">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

