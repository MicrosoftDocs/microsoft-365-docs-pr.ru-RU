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
description: Используйте редактор взаимодействий, чтобы изменить текст и переменные поля слияния при форматировании контента.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0cb415da9aa09452176bd8aa9be4575cfc827582
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034481"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="75059-103">Использование редактора взаимодействия</span><span class="sxs-lookup"><span data-stu-id="75059-103">Use the communications editor</span></span>

<span data-ttu-id="75059-104">При определении контента портала, уведомления о юридических удержаниях, а также связанных напоминаний и укрупнений можно использовать редактор взаимодействий для форматирования и динамического настройки контента.</span><span class="sxs-lookup"><span data-stu-id="75059-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can leverage the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="75059-105">Редактор форматированного текста</span><span class="sxs-lookup"><span data-stu-id="75059-105">Rich text editor</span></span> 

<span data-ttu-id="75059-106">Редактор взаимодействий позволяет пользователю настраивать текст с помощью параметров редактора.</span><span class="sxs-lookup"><span data-stu-id="75059-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="75059-107">Например, пользователи могут изменять типы шрифтов, создавать маркированные списки, выделять содержимое и многое другое.</span><span class="sxs-lookup"><span data-stu-id="75059-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span> 

## <a name="merge-field-variables"></a><span data-ttu-id="75059-108">Переменные поля слияния</span><span class="sxs-lookup"><span data-stu-id="75059-108">Merge field variables</span></span>

<span data-ttu-id="75059-109">Вы можете использовать переменные слияния электронной почты из редактора взаимодействия для встраивания настраиваемых атрибутов хранитель в основной текст общения.</span><span class="sxs-lookup"><span data-stu-id="75059-109">You can leverage email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="75059-110">При отправке в Хранитель поле слияния будет заполнено соответствующим полем.</span><span class="sxs-lookup"><span data-stu-id="75059-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="75059-111">Например, при отправке в Хранитель John Smith поле слияния [хранитель name] будет преобразовано соответствующим именем.</span><span class="sxs-lookup"><span data-stu-id="75059-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span> 

<span data-ttu-id="75059-112">Вы можете использовать поля слияния электронной почты, щелкнув значки **поля слияния** в верхней части элемента управления Rich Text Editor.</span><span class="sxs-lookup"><span data-stu-id="75059-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="75059-113">Заполнитель будет добавлен в соответствии с расположением курсора пользователя.</span><span class="sxs-lookup"><span data-stu-id="75059-113">The placeholder will be added based off the location of the users' cursor.</span></span> 

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="75059-114">Список переменных поля слияния</span><span class="sxs-lookup"><span data-stu-id="75059-114">List of merge field variables</span></span>

| <span data-ttu-id="75059-115">Имя поля</span><span class="sxs-lookup"><span data-stu-id="75059-115">Field name</span></span>                  | <span data-ttu-id="75059-116">Сведения о поле</span><span class="sxs-lookup"><span data-stu-id="75059-116">Field details</span></span> | 
| :------------------- | :------------------- |
| <span data-ttu-id="75059-117">"Display Name" (Отображаемое имя);</span><span class="sxs-lookup"><span data-stu-id="75059-117">Display Name</span></span>  | <span data-ttu-id="75059-118">Имя и фамилия хранитель.</span><span class="sxs-lookup"><span data-stu-id="75059-118">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="75059-119">Ссылка подтверждения</span><span class="sxs-lookup"><span data-stu-id="75059-119">Acknowledgement Link</span></span> | <span data-ttu-id="75059-120">Настраиваемая ссылка для записи подтверждения каждого хранитель.</span><span class="sxs-lookup"><span data-stu-id="75059-120">A customized link to record each custodian's acknowledgement.</span></span>|                 |
| <span data-ttu-id="75059-121">Ссылка на портал</span><span class="sxs-lookup"><span data-stu-id="75059-121">Portal Link</span></span>     | <span data-ttu-id="75059-122">Настраиваемая ссылка на портал соответствия требованиям для хранитель.</span><span class="sxs-lookup"><span data-stu-id="75059-122">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="75059-123">Выдача директора</span><span class="sxs-lookup"><span data-stu-id="75059-123">Issuing Officer</span></span>                   | <span data-ttu-id="75059-124">Адрес электронной почты указанного директора поставщика.</span><span class="sxs-lookup"><span data-stu-id="75059-124">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="75059-125">Дата выпуска</span><span class="sxs-lookup"><span data-stu-id="75059-125">Issuing Date</span></span>                   | <span data-ttu-id="75059-126">Дата выпуска уведомления (UTC).</span><span class="sxs-lookup"><span data-stu-id="75059-126">The date that the notice was issued (UTC).</span></span>              |
