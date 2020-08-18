---
title: Объявление элементов записями с использованием меток хранения
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Объявление элементов записями с использованием меток хранения.
ms.openlocfilehash: d637817e8d1bcc8c72bfe011dfd288ac4e2d0298
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778519"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="4cd91-103">Объявление элементов записями с использованием меток хранения</span><span class="sxs-lookup"><span data-stu-id="4cd91-103">Declare records by using retention labels</span></span>

><span data-ttu-id="4cd91-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="4cd91-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="4cd91-105">Чтобы объявить элементы в качестве записей, используйте [метки хранения](retention.md#retention-labels), помечающие содержимое как запись.</span><span class="sxs-lookup"><span data-stu-id="4cd91-105">To declare items as a record, you use [retention labels](retention.md#retention-labels) that mark the content as a record.</span></span> <span data-ttu-id="4cd91-106">Вы можете либо опубликовать эти метки, чтобы пользователи и администраторы могли вручную применить их к содержимому, либо автоматически применить эти метки к содержимому, которое вы хотите пометить как запись.</span><span class="sxs-lookup"><span data-stu-id="4cd91-106">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="4cd91-107">Настройка меток хранения для объявления элементов записями</span><span class="sxs-lookup"><span data-stu-id="4cd91-107">Configuring retention labels to declare records</span></span>

<span data-ttu-id="4cd91-108">Когда вы создаете или настраиваете метку хранения, выберите вариант пометки содержимого как записи.</span><span class="sxs-lookup"><span data-stu-id="4cd91-108">When you create or configure a retention label, select the option to mark the content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="4cd91-109">Параметр пометки содержимого как запись недоступен при создании или настройки метки хранения из раздела **Управление информацией** в Центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4cd91-109">The option to mark the content as a record is not available when you create or configure retention labels from **Information Governance** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="4cd91-110">Вместо этого необходимо использовать раздел**Управление записями**.</span><span class="sxs-lookup"><span data-stu-id="4cd91-110">Instead, you must use **Records Management**.</span></span>

<span data-ttu-id="4cd91-111">Создание метки хранения, помечающей содержимое как запись:</span><span class="sxs-lookup"><span data-stu-id="4cd91-111">To create a new retention label that marks the content as a record:</span></span>

1. <span data-ttu-id="4cd91-112">В [Центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com), перейти в раздел **Управление записями** \> **План хранения**.</span><span class="sxs-lookup"><span data-stu-id="4cd91-112">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="4cd91-113">На странице **План хранения** выберите **Создать метку**.</span><span class="sxs-lookup"><span data-stu-id="4cd91-113">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="4cd91-114">На странице мастера**Параметры метки** выберите параметр для классификации содержимого как записи.</span><span class="sxs-lookup"><span data-stu-id="4cd91-114">On the **Label settings** page in the wizard, choose the option to classify content as a record.</span></span>
    
   ![Нажмите "Использовать метку", чтобы обозначить содержимое как "Запись" с помощью флажка.](../media/recordversioning6.png)

3. <span data-ttu-id="4cd91-116">При необходимости можно применить метку хранения к документам SharePoint или OneDrive и электронным письмам Exchange.</span><span class="sxs-lookup"><span data-stu-id="4cd91-116">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="4cd91-117">Для получения инструкций:</span><span class="sxs-lookup"><span data-stu-id="4cd91-117">For instructions:</span></span>
    
    - [<span data-ttu-id="4cd91-118">Создание меток хранения и их применение в приложениях</span><span class="sxs-lookup"><span data-stu-id="4cd91-118">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="4cd91-119">Автоматическое применение метки хранения к контенту</span><span class="sxs-lookup"><span data-stu-id="4cd91-119">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="4cd91-120">Применение сконфигурированной метки хранения к содержимому</span><span class="sxs-lookup"><span data-stu-id="4cd91-120">Applying the configured retention label to content</span></span>

<span data-ttu-id="4cd91-121">Когда метки хранения, помечающие содержимое как запись, становятся доступны для пользователей для применения их в приложениях:</span><span class="sxs-lookup"><span data-stu-id="4cd91-121">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="4cd91-122">Любой пользователь в Exchange, имеющий доступ к почтовому ящику с возможностью ввода текста, может применить метку хранения.</span><span class="sxs-lookup"><span data-stu-id="4cd91-122">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="4cd91-123">Применить метки в SharePoint и OneDrive может любой пользователь, который (на уровне разрешения "Участие") входит в группу "Участники", используемую по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4cd91-123">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="4cd91-124">Пример документа, помеченного как запись, с помощью метки хранения:</span><span class="sxs-lookup"><span data-stu-id="4cd91-124">Example of a document marked as record by using a retention label:</span></span>

![Область сведений о документе, отмеченном как запись](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="4cd91-126">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="4cd91-126">Next steps</span></span>

<span data-ttu-id="4cd91-127">Список сценариев, поддерживаемых службой управления записей, см. в разделе [Обычные сценарии для управления записями](get-started-with-records-management.md#common-scenarios-for-records-management).</span><span class="sxs-lookup"><span data-stu-id="4cd91-127">For a list of scenarios supported by records management, see [Common scenarios for records management](get-started-with-records-management.md#common-scenarios-for-records-management).</span></span>
