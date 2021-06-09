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
description: При форматирование контента используйте редактор коммуникаций для изменения текстовых переменных и объединения переменных поля.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6dcfb58dff3a3acf99340895872bb2da9795d9c8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769164"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="f23cf-103">Использование редактора взаимодействия</span><span class="sxs-lookup"><span data-stu-id="f23cf-103">Use the communications editor</span></span>

<span data-ttu-id="f23cf-104">Определяя содержимое контента портала, уведомлений о удержании и связанных с ними напоминаний и эскалаций, вы можете использовать редактор коммуникаций для формата и динамической настройки контента.</span><span class="sxs-lookup"><span data-stu-id="f23cf-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can use the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="f23cf-105">Богатый текстовый редактор</span><span class="sxs-lookup"><span data-stu-id="f23cf-105">Rich text editor</span></span>

<span data-ttu-id="f23cf-106">Редактор сообщений позволяет пользователю настраивать текст с помощью параметров редактора.</span><span class="sxs-lookup"><span data-stu-id="f23cf-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="f23cf-107">Например, пользователи могут изменять типы шрифтов, создавать списки с пулями, выделить контент и другие.</span><span class="sxs-lookup"><span data-stu-id="f23cf-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span>

## <a name="merge-field-variables"></a><span data-ttu-id="f23cf-108">Переменные поля слияния</span><span class="sxs-lookup"><span data-stu-id="f23cf-108">Merge field variables</span></span>

<span data-ttu-id="f23cf-109">Для встраиваемых настраиваемых атрибутов хранителя в текст сообщения можно использовать переменные слияния электронной почты из редактора коммуникаций.</span><span class="sxs-lookup"><span data-stu-id="f23cf-109">You can use email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="f23cf-110">При отправлении в хранителя поле слияния заполняется соответствующим полем.</span><span class="sxs-lookup"><span data-stu-id="f23cf-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="f23cf-111">Например, при отправлении хранителя Джону Смиту поле слияния [Имя хранителя] будет переведено с соответствующим именем.</span><span class="sxs-lookup"><span data-stu-id="f23cf-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span>

<span data-ttu-id="f23cf-112">Поля слияния электронной почты можно использовать, выбрав значки **поля Merge** в верхней части управления редактором с богатым текстом.</span><span class="sxs-lookup"><span data-stu-id="f23cf-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="f23cf-113">Местообладатель будет добавлен в зависимости от расположения курсора пользователя.</span><span class="sxs-lookup"><span data-stu-id="f23cf-113">The placeholder will be added based off the location of the users' cursor.</span></span>

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="f23cf-114">Список переменных полей слияния</span><span class="sxs-lookup"><span data-stu-id="f23cf-114">List of merge field variables</span></span>

| <span data-ttu-id="f23cf-115">Имя поля</span><span class="sxs-lookup"><span data-stu-id="f23cf-115">Field name</span></span>                  | <span data-ttu-id="f23cf-116">Сведения о поле</span><span class="sxs-lookup"><span data-stu-id="f23cf-116">Field details</span></span> |
| :------------------- | :------------------- |
| <span data-ttu-id="f23cf-117">"Display Name" (Отображаемое имя);</span><span class="sxs-lookup"><span data-stu-id="f23cf-117">Display Name</span></span>  | <span data-ttu-id="f23cf-118">Имя и фамилия хранителя.</span><span class="sxs-lookup"><span data-stu-id="f23cf-118">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="f23cf-119">Связь с подтверждением</span><span class="sxs-lookup"><span data-stu-id="f23cf-119">Acknowledgment Link</span></span> | <span data-ttu-id="f23cf-120">Настраиваемая ссылка для записи подтверждения каждого хранителя.</span><span class="sxs-lookup"><span data-stu-id="f23cf-120">A customized link to record each custodian's acknowledgment.</span></span>|                 |
| <span data-ttu-id="f23cf-121">Ссылка портала</span><span class="sxs-lookup"><span data-stu-id="f23cf-121">Portal Link</span></span>     | <span data-ttu-id="f23cf-122">Настраиваемая ссылка для портала соответствия требованиям хранителя.</span><span class="sxs-lookup"><span data-stu-id="f23cf-122">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="f23cf-123">Сотрудник по выдаче</span><span class="sxs-lookup"><span data-stu-id="f23cf-123">Issuing Officer</span></span>                   | <span data-ttu-id="f23cf-124">Адрес электронной почты указанного сотрудника по выдаче.</span><span class="sxs-lookup"><span data-stu-id="f23cf-124">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="f23cf-125">Дата выпуска</span><span class="sxs-lookup"><span data-stu-id="f23cf-125">Issuing Date</span></span>                   | <span data-ttu-id="f23cf-126">Дата выпуска уведомления (UTC).</span><span class="sxs-lookup"><span data-stu-id="f23cf-126">The date that the notice was issued (UTC).</span></span>              |
|||
