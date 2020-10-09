---
title: Изолированная группа для верхнего уровня секретного проекта корпорации Contoso
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
description: Сводка. сведения о том, как компания Contoso использовала группу с изоляцией безопасности для проекта верхнего уровня, чтобы разработать новый набор продуктов и служб.
ms.openlocfilehash: 16d10f5d6e5b5939172c02746c9324eb20b6987e
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399493"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="6dda8-103">Изолированная группа для верхнего уровня секретного проекта корпорации Contoso</span><span class="sxs-lookup"><span data-stu-id="6dda8-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="6dda8-104">После того, как руководитель организации находится за пределами, Генеральный директор Contoso упорядочивает разработку нового набора продуктов и услуг, которые могут вдвое прибыли от компании Contoso в течение следующих пяти лет.</span><span class="sxs-lookup"><span data-stu-id="6dda8-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="6dda8-105">Проект верхнего уровня для разработки бизнес-, инженерного и маркетингового плана назывался **Project 2x** и основные сотрудники компании.</span><span class="sxs-lookup"><span data-stu-id="6dda8-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="6dda8-106">Временные шкалы для исследования и разработки были тесно выполнены, поэтому совместная работа должна быть эффективной и обеспечивать безопасное собрание, текущие беседы и хранение файлов.</span><span class="sxs-lookup"><span data-stu-id="6dda8-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="6dda8-107">Конечные результаты для проекта 2X: бизнес-планы, спецификации продуктов и технических материалов, а также маркетинговые материалы и расписания в виде файлов Word, Excel и PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="6dda8-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="6dda8-108">Из-за конфиденциальной природы доступ к этим файлам имел следующий вид:</span><span class="sxs-lookup"><span data-stu-id="6dda8-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="6dda8-109">Ограничивается членами группы в Project 2X и высшим лидером.</span><span class="sxs-lookup"><span data-stu-id="6dda8-109">Restricted to Project 2X team members and senior leadership.</span></span>
- <span data-ttu-id="6dda8-110">Зашифровать и защитить с помощью разрешений, чтобы предоставить доступ только членам группы в Project 2X и высшему руководству, даже если файлы были распределены за пререшениями защищенных папок.</span><span class="sxs-lookup"><span data-stu-id="6dda8-110">Encrypted and protected with permissions to allow access only to Project 2X team members and senior leadership, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="6dda8-111">Сотрудники ИТ Contoso использовали [команду с изоляцией безопасности](secure-teams-security-isolation.md) для Project 2x и следующими действиями.</span><span class="sxs-lookup"><span data-stu-id="6dda8-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="6dda8-112">Шаг 1: создание частной команды</span><span class="sxs-lookup"><span data-stu-id="6dda8-112">Step 1: Created a private team</span></span>

<span data-ttu-id="6dda8-113">Во-первых, чтобы защитить доступ к базовому сайту SharePoint для группы, ИТ-администраторы Contoso настроили [Рекомендуемые политики доступа к SharePoint](../security/office-365-security/sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6dda8-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="6dda8-114">Затем администратор Contoso создал новую частную группу с именем Project 2X и добавила учетные записи пользователей в качестве участников Project 2X.</span><span class="sxs-lookup"><span data-stu-id="6dda8-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span> <span data-ttu-id="6dda8-115">Кроме того, они настроили группу так, что частные каналы могут создавать только владельцы группы по проекту 2X.</span><span class="sxs-lookup"><span data-stu-id="6dda8-115">They also configured the team so that only Project 2X team owners can create private channels.</span></span>

<span data-ttu-id="6dda8-116">Сведения о конфигурации можно найти в статье [Создание частной команды](secure-teams-security-isolation.md#create-a-private-team).</span><span class="sxs-lookup"><span data-stu-id="6dda8-116">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="6dda8-117">Шаг 2: создание метки чувствительности для группы проекта 2X</span><span class="sxs-lookup"><span data-stu-id="6dda8-117">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="6dda8-118">Администраторы Contoso создали новую метку чувствительности с именем **Project 2x** , которая:</span><span class="sxs-lookup"><span data-stu-id="6dda8-118">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="6dda8-119">Включенное шифрование.</span><span class="sxs-lookup"><span data-stu-id="6dda8-119">Enabled encryption.</span></span>
- <span data-ttu-id="6dda8-120">Разрешенные Co-Author разрешения для группы Microsoft 365 Project 2X.</span><span class="sxs-lookup"><span data-stu-id="6dda8-120">Allowed Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="6dda8-121">Разрешенные разрешения средства просмотра для группы высшего руководства.</span><span class="sxs-lookup"><span data-stu-id="6dda8-121">Allowed Viewer permissions for the Senior Leadership group.</span></span>
- <span data-ttu-id="6dda8-122">Заблокирован доступ к неуправляемым устройствам.</span><span class="sxs-lookup"><span data-stu-id="6dda8-122">Blocked access to unmanaged devices.</span></span>

<span data-ttu-id="6dda8-123">Файлы в разделе **документы** базового сайта SharePoint на 2x защищены:</span><span class="sxs-lookup"><span data-stu-id="6dda8-123">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="6dda8-124">Разрешения сайта, которые разрешают только полный доступ к участникам проекта 2X Microsoft 365 и разрешение на чтение для группы высшего руководства.</span><span class="sxs-lookup"><span data-stu-id="6dda8-124">The site permissions, which only allow full permissions to members of the Project 2X Microsoft 365 group and read permissions to the Senior Leadership group.</span></span>
- <span data-ttu-id="6dda8-125">Метка "чувствительность к проекту 2X" с шифрованием и разрешениями, которые передаются вместе с файлом, если он перемещается или копируется с сайта.</span><span class="sxs-lookup"><span data-stu-id="6dda8-125">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="6dda8-126">Сведения о конфигурации приведены в разделе [Создание метки конфиденциальности](secure-teams-security-isolation.md#create-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="6dda8-126">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="6dda8-127">Шаг 3: Настройка базового сайта SharePoint</span><span class="sxs-lookup"><span data-stu-id="6dda8-127">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="6dda8-128">Во-первых, чтобы защитить доступ к базовому сайту SharePoint для группы, ИТ-администраторы Contoso настроили [Рекомендуемые политики доступа к SharePoint](../security/office-365-security/sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6dda8-128">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="6dda8-129">Затем они настроили дополнительные параметры разрешений для сайта:</span><span class="sxs-lookup"><span data-stu-id="6dda8-129">Next, they configured additional permission settings for the site:</span></span>

- <span data-ttu-id="6dda8-130">Чтобы запретить участникам группы Project 2X предоставлять доступ к сайту.</span><span class="sxs-lookup"><span data-stu-id="6dda8-130">To prevent Project 2X group members from sharing access to the site.</span></span> <span data-ttu-id="6dda8-131">Сведения о конфигурации представлены в разделе [Параметры SharePoint для группы с изоляцией безопасности](secure-teams-security-isolation.md#sharepoint-settings).</span><span class="sxs-lookup"><span data-stu-id="6dda8-131">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>
- <span data-ttu-id="6dda8-132">Разрешения на чтение для группы высшего руководства.</span><span class="sxs-lookup"><span data-stu-id="6dda8-132">For Read permissions for the Senior Leadership group.</span></span>

<span data-ttu-id="6dda8-133">Затем они настроили дополнительные параметры разрешений для сайта, чтобы запретить участникам группы Project 2X предоставлять доступ к сайту.</span><span class="sxs-lookup"><span data-stu-id="6dda8-133">Next, they configured additional permission settings for the site to prevent Project 2X group members from sharing access to the site.</span></span> 

<span data-ttu-id="6dda8-134">По мере создания частных каналов для проекта 2X владелец группы отключил общий доступ и присвоить определению по умолчанию ссылку для общего доступа **определенным пользователям** .</span><span class="sxs-lookup"><span data-stu-id="6dda8-134">As private channels for the Project 2X were created, the group owner disabled guest sharing and set the default sharing link to the **Specific people** value.</span></span>

<span data-ttu-id="6dda8-135">Ниже показана итоговая Конфигурация группы проекта 2X с изоляцией безопасности.</span><span class="sxs-lookup"><span data-stu-id="6dda8-135">Here is the resulting configuration of the Project 2X team with security isolation.</span></span>

![Итоговая конфигурация команды Project 2X](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="6dda8-137">Шаг 4: квалифицированные участники группы для Project 2X</span><span class="sxs-lookup"><span data-stu-id="6dda8-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="6dda8-138">Сотрудники отдела безопасности Contoso обучены членам группы "проект 2" в обязательном курсе, в котором их пошагово пройдет следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6dda8-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="6dda8-139">Как получить доступ к новой команде Project 2X, использовать собрания и беседы, а также как совместно работать с файлами группы.</span><span class="sxs-lookup"><span data-stu-id="6dda8-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="6dda8-140">Создание новых файлов в команде и отправка новых файлов, созданных локально.</span><span class="sxs-lookup"><span data-stu-id="6dda8-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="6dda8-141">Пометка файлов с помощью метки чувствительности к проекту 2X.</span><span class="sxs-lookup"><span data-stu-id="6dda8-141">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="6dda8-142">Демонстрация того, как подпись проекта 2X защищает файл, даже если он покидает команду.</span><span class="sxs-lookup"><span data-stu-id="6dda8-142">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="6dda8-143">Конечный результат — это безопасная среда, в которой участники группы Project 2X совместно работают в безопасной среде для чатов, собраний и файлов.</span><span class="sxs-lookup"><span data-stu-id="6dda8-143">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="6dda8-144">Ниже приведен пример файла, хранящегося на базовом сайте с проектом 2X с назначенной меткой конфиденциальности для проекта 2X.</span><span class="sxs-lookup"><span data-stu-id="6dda8-144">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![Пример файла, хранящегося на сайте базового проекта 2X](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="6dda8-146">В нескольких экземплярах участники группы Project 2X загрузили файлы, защищенные меткой проекта 2X, на локальный диск для работы в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="6dda8-146">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> 

<span data-ttu-id="6dda8-147">Однако после того как вы запрашиваете учетные данные при их открытии, они выдавали свои ошибки и удалили их.</span><span class="sxs-lookup"><span data-stu-id="6dda8-147">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="6dda8-148">Из-за среды совместной работы Teams и функций безопасности Microsoft 365 сведения о проекте 2X хранятся в секрете в течение проекта.</span><span class="sxs-lookup"><span data-stu-id="6dda8-148">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="6dda8-149">Компания Contoso объявила о своих планах и в процессе развертывания новых продуктов и служб в сведения своих клиентов и инвесторов и Чагрин конкурентов.</span><span class="sxs-lookup"><span data-stu-id="6dda8-149">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="6dda8-150">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="6dda8-150">Next step</span></span>

<span data-ttu-id="6dda8-151">[Развертывание группы с изоляцией безопасности](secure-teams-security-isolation.md) в Организации.</span><span class="sxs-lookup"><span data-stu-id="6dda8-151">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

