---
title: Использование редактора взаимодействия
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Используйте редактор коммуникаций для изменения текста и объединения переменных поля при форматирование содержимого.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6dcfb58dff3a3acf99340895872bb2da9795d9c8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769164"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="3dcb7-103">Использование редактора взаимодействия</span><span class="sxs-lookup"><span data-stu-id="3dcb7-103">Use the communications editor</span></span>

<span data-ttu-id="3dcb7-104">При определении содержимого портала, уведомлений об удержании по юридическим вопросам и связанных напоминаний и эскалаций можно использовать редактор сообщений для форматации и динамической настройки контента.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can use the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="3dcb7-105">Редактор RICH TEXT</span><span class="sxs-lookup"><span data-stu-id="3dcb7-105">Rich text editor</span></span>

<span data-ttu-id="3dcb7-106">Редактор сообщений позволяет пользователю настраивать текст с помощью параметров редактора.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="3dcb7-107">Например, пользователи могут изменять типы шрифтов, создавать маркеры списков, выделять содержимое и многие другие.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span>

## <a name="merge-field-variables"></a><span data-ttu-id="3dcb7-108">Объединение переменных полей</span><span class="sxs-lookup"><span data-stu-id="3dcb7-108">Merge field variables</span></span>

<span data-ttu-id="3dcb7-109">Вы можете использовать переменные объединения электронной почты из редактора сообщений, чтобы встраить настраиваемые атрибуты хранителя в текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-109">You can use email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="3dcb7-110">При отправлении хранителя в поле объединения будет заполнено соответствующее поле.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="3dcb7-111">Например, при отправлении хранителя Ивану Иванову поле объединения [Имя хранителя] будет переведено с соответствующим именем.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span>

<span data-ttu-id="3dcb7-112">Вы можете использовать поля слияния электронной почты, выбрав **значки** полей объединения в верхней части редактора хвойного текста.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="3dcb7-113">Этот замессатор будет добавлен в зависимости от расположения курсора пользователя.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-113">The placeholder will be added based off the location of the users' cursor.</span></span>

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="3dcb7-114">Список переменных поля объединения</span><span class="sxs-lookup"><span data-stu-id="3dcb7-114">List of merge field variables</span></span>

| <span data-ttu-id="3dcb7-115">Имя поля</span><span class="sxs-lookup"><span data-stu-id="3dcb7-115">Field name</span></span>                  | <span data-ttu-id="3dcb7-116">Сведения о поле</span><span class="sxs-lookup"><span data-stu-id="3dcb7-116">Field details</span></span> |
| :------------------- | :------------------- |
| <span data-ttu-id="3dcb7-117">"Display Name" (Отображаемое имя);</span><span class="sxs-lookup"><span data-stu-id="3dcb7-117">Display Name</span></span>  | <span data-ttu-id="3dcb7-118">Имя и фамилия хранителя.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-118">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="3dcb7-119">Ссылка подтверждения</span><span class="sxs-lookup"><span data-stu-id="3dcb7-119">Acknowledgment Link</span></span> | <span data-ttu-id="3dcb7-120">Настраиваемая ссылка для записи подтверждения каждого хранителя.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-120">A customized link to record each custodian's acknowledgment.</span></span>|                 |
| <span data-ttu-id="3dcb7-121">Ссылка на портал</span><span class="sxs-lookup"><span data-stu-id="3dcb7-121">Portal Link</span></span>     | <span data-ttu-id="3dcb7-122">Настраиваемая ссылка для портала соответствия требованиям хранителя.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-122">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="3dcb7-123">Сотрудник по выдаче</span><span class="sxs-lookup"><span data-stu-id="3dcb7-123">Issuing Officer</span></span>                   | <span data-ttu-id="3dcb7-124">Адрес электронной почты указанного сотрудника, выдав его.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-124">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="3dcb7-125">Дата выдачи</span><span class="sxs-lookup"><span data-stu-id="3dcb7-125">Issuing Date</span></span>                   | <span data-ttu-id="3dcb7-126">Дата выдачи уведомления (UTC).</span><span class="sxs-lookup"><span data-stu-id="3dcb7-126">The date that the notice was issued (UTC).</span></span>              |
|||
