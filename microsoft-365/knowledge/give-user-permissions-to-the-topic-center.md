---
title: Предоставление пользователям разрешений для центра справки (Предварительная версия)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Сведения о том, как предоставить пользователям разрешения на выполнение задач в центре разделов
ms.openlocfilehash: 0e4e05d0addfdb754459e67acfdff3f61c7c812e
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537855"
---
# <a name="give-user-permissions-to-the-topic-center-preview"></a><span data-ttu-id="fb7a8-103">Предоставление пользователям разрешений для центра справки (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="fb7a8-103">Give user permissions to the topic center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="fb7a8-104">Содержимое этой статьи предназначено для Кортексного предварительного просмотра Project.</span><span class="sxs-lookup"><span data-stu-id="fb7a8-104">The content in this article is for Project Cortex Private Preview.</span></span> [<span data-ttu-id="fb7a8-105">Узнайте больше о Project Кортекс</span><span class="sxs-lookup"><span data-stu-id="fb7a8-105">Find out more about Project Cortex</span></span>](https://aka.ms/projectcortex) 

<span data-ttu-id="fb7a8-106">Для работы в центре разделов необходимы необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="fb7a8-106">In order to work in the topic center, you need to have the required permissions.</span></span> <span data-ttu-id="fb7a8-107">Администратор может назначать эти разрешения пользователям во время [установки управления знаниями](set-up-knowledge-network.md), а затем добавлять новых пользователей.</span><span class="sxs-lookup"><span data-stu-id="fb7a8-107">Your admin can assign these permissions to users during [knowledge management setup](set-up-knowledge-network.md), or new users can be added afterwards.</span></span>

<span data-ttu-id="fb7a8-108">Пользователям центра разделов могут быть предоставлены два набора разрешений:</span><span class="sxs-lookup"><span data-stu-id="fb7a8-108">Topic center users can be given two sets of permissions:</span></span>

- <span data-ttu-id="fb7a8-109">**Создание и редактирование разделов**: создание новых разделов или обновление содержимого разделов, таких как описание, документы и связанные лица</span><span class="sxs-lookup"><span data-stu-id="fb7a8-109">**Create and edit topics**: Create new topics or update topic content such as the description, documents and associated persons</span></span>
- <span data-ttu-id="fb7a8-110">**Управление разделами**: использование панели управления разделами для просмотра тем в Организации.</span><span class="sxs-lookup"><span data-stu-id="fb7a8-110">**Manage topics**: Use the Topic management dashboard to review topics across the organization.</span></span> <span data-ttu-id="fb7a8-111">Пользователи могут выполнять такие действия, как подтверждение и отклонение неподтвержденных разделов.</span><span class="sxs-lookup"><span data-stu-id="fb7a8-111">Users can perform actions such as confirming and rejecting unconfirmed topics.</span></span>

<span data-ttu-id="fb7a8-112">При необходимости пользователю могут быть предоставлены оба набора разрешений или только один из них.</span><span class="sxs-lookup"><span data-stu-id="fb7a8-112">A user can be given both sets of permissions, or only one if needed.</span></span> 

<span data-ttu-id="fb7a8-113">Если пользователю не предоставлены разрешения во время установки, администратор может сделать это с помощью центра администрирования Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="fb7a8-113">If a user is not given permissions during setup, an admin can do the following give users permissions through the Microsoft 365 admin center:</span></span>

<span data-ttu-id="fb7a8-114">Чтобы предоставить пользователю разрешения на управление разделами:</span><span class="sxs-lookup"><span data-stu-id="fb7a8-114">To give a user permissions to manage topics:</span></span>

1. <span data-ttu-id="fb7a8-115">В центре администрирования Microsoft 365 в области навигации нажмите кнопку **настроить**.</span><span class="sxs-lookup"><span data-stu-id="fb7a8-115">In the Microsoft 365 admin center, in the navigation pane, select **Set up**.</span></span>
2. <span data-ttu-id="fb7a8-116">В разделе " **сведения о организации** " в разделе **подключить пользователей к сведениям**выберите **Просмотр**.</span><span class="sxs-lookup"><span data-stu-id="fb7a8-116">In the **Organizational Knowledge** section, under **Connect people to knowledge**, select **View**.</span></span>
3. <span data-ttu-id="fb7a8-117">На странице **подключить людей к сведениям** выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="fb7a8-117">On the **Connect people to knowledge** page, select **Manage**.</span></span>
4. <span data-ttu-id="fb7a8-118">На странице " **сеть базы знаний** " перейдите на вкладку **разрешения для раздела** .</span><span class="sxs-lookup"><span data-stu-id="fb7a8-118">On the **Knowledge Network** page, select the **Topic permissions** tab.</span></span>
5. <span data-ttu-id="fb7a8-119">На вкладке **разрешения раздела** в разделе **Пользователи, которые могут управлять разделами**выберите **вид**.</span><span class="sxs-lookup"><span data-stu-id="fb7a8-119">On the **Topic permissions** tab, under **Who can manage topics**, select **View**.</span></span>
6.  <span data-ttu-id="fb7a8-120">На странице **Пользователи, которые могут управлять разделами** добавьте пользователя в поле **только выбранные пользователи или группы безопасности** .</span><span class="sxs-lookup"><span data-stu-id="fb7a8-120">On the **Who can manage topics** page, add the user to the **Only selected users or security groups** box.</span></span>
7. <span data-ttu-id="fb7a8-121">После добавления пользователя нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="fb7a8-121">After adding your user, select **Add**.</span></span>
3. <span data-ttu-id="fb7a8-122">В разделе **кто может создавать и редактировать темы**выберите **Просмотр**.</span><span class="sxs-lookup"><span data-stu-id="fb7a8-122">Under the **Who can create and edit topics**, select **View**.</span></span>
4. <span data-ttu-id="fb7a8-123">Добавьте пользователя в поле **только выбранные пользователи или группы безопасности** .</span><span class="sxs-lookup"><span data-stu-id="fb7a8-123">Add the user to the **Only selected users or security groups** box.</span></span>
5. <span data-ttu-id="fb7a8-124">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="fb7a8-124">Select **Add**.</span></span>

<span data-ttu-id="fb7a8-125">Предоставление пользователю разрешений на создание и редактирование разделов:</span><span class="sxs-lookup"><span data-stu-id="fb7a8-125">To give a user permissions to create and edit topics:</span></span>

1. <span data-ttu-id="fb7a8-126">На вкладке **разрешения раздела** в разделе **Пользователи, которые могут создавать и редактировать разделы**выберите **вид**.</span><span class="sxs-lookup"><span data-stu-id="fb7a8-126">On the **Topic permissions** tab, under **Who can create and edit topics**, select **View**.</span></span>
2. <span data-ttu-id="fb7a8-127">Добавьте пользователя в поле **только выбранные пользователи или группы безопасности** .</span><span class="sxs-lookup"><span data-stu-id="fb7a8-127">Add the user to the **Only selected users or security groups** box.</span></span>
3. <span data-ttu-id="fb7a8-128">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="fb7a8-128">Select **Add**.</span></span>



## <a name="see-also"></a><span data-ttu-id="fb7a8-129">См. также</span><span class="sxs-lookup"><span data-stu-id="fb7a8-129">See Also</span></span>
  
[<span data-ttu-id="fb7a8-130">Работать с разделами в центре разделов</span><span class="sxs-lookup"><span data-stu-id="fb7a8-130">Work with topics in the Topic Center</span></span>](work-with-topics.md)



