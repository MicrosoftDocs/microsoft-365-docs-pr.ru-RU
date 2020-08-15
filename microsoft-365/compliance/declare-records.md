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
ms.openlocfilehash: c8024cf08be2259ffa8b6747bebf4943e11e4d60
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695276"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="a4dcd-103">Объявление элементов записями с использованием меток хранения</span><span class="sxs-lookup"><span data-stu-id="a4dcd-103">Declare records by using retention labels</span></span>

><span data-ttu-id="a4dcd-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="a4dcd-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="a4dcd-105">Чтобы пометить содержимое как запись, используются [метки хранения](retention.md#retention-labels).</span><span class="sxs-lookup"><span data-stu-id="a4dcd-105">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="a4dcd-106">Вы можете либо опубликовать эти метки, чтобы пользователи и администраторы могли вручную применить их к содержимому, либо автоматически применить эти метки к содержимому, которое вы хотите пометить как запись.</span><span class="sxs-lookup"><span data-stu-id="a4dcd-106">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="a4dcd-107">Настройка меток хранения для объявления элементов записями</span><span class="sxs-lookup"><span data-stu-id="a4dcd-107">Configuring retention labels to declare records</span></span>

<span data-ttu-id="a4dcd-108">При создании [метки хранения](retention.md#retention-labels), выберите параметр, чтобы пометить содержимое как запись.</span><span class="sxs-lookup"><span data-stu-id="a4dcd-108">When you create a [retention label](retention.md#retention-labels), select the option to mark the content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="a4dcd-109">Параметр пометки содержимого как запись недоступен при создании или настройки метки хранения из раздела **Управление информацией** в Центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a4dcd-109">The option to mark the content as a record is not available when you create or configure retention labels from **Information Governance** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="a4dcd-110">Вместо этого необходимо использовать раздел**Управление записями**.</span><span class="sxs-lookup"><span data-stu-id="a4dcd-110">Instead, you must use **Records Management**.</span></span>

1. <span data-ttu-id="a4dcd-111">В [Центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com), перейти в раздел **Управление записями** \> **План хранения**.</span><span class="sxs-lookup"><span data-stu-id="a4dcd-111">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="a4dcd-112">На странице **План хранения** выберите **Создать метку**.</span><span class="sxs-lookup"><span data-stu-id="a4dcd-112">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="a4dcd-113">На странице мастера**Параметры метки** выберите параметр для классификации содержимого как записи.</span><span class="sxs-lookup"><span data-stu-id="a4dcd-113">On the **Label settings** page in the wizard, choose the option to classify content as a record.</span></span>
    
   ![Нажмите "Использовать метку", чтобы обозначить содержимое как "Запись" с помощью флажка.](../media/recordversioning6.png)

3. <span data-ttu-id="a4dcd-115">При необходимости можно применить метку хранения к документам SharePoint или OneDrive и электронным письмам Exchange.</span><span class="sxs-lookup"><span data-stu-id="a4dcd-115">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="a4dcd-116">Для получения инструкций:</span><span class="sxs-lookup"><span data-stu-id="a4dcd-116">For instructions:</span></span>
    
    - [<span data-ttu-id="a4dcd-117">Создание меток хранения и их применение в приложениях</span><span class="sxs-lookup"><span data-stu-id="a4dcd-117">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="a4dcd-118">Автоматическое применение метки хранения к контенту</span><span class="sxs-lookup"><span data-stu-id="a4dcd-118">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="a4dcd-119">Применение сконфигурированной метки хранения к содержимому</span><span class="sxs-lookup"><span data-stu-id="a4dcd-119">Applying the configured retention label to content</span></span>

<span data-ttu-id="a4dcd-120">Когда метки хранения, помечающие содержимое как запись, становятся доступны для пользователей для применения их в приложениях:</span><span class="sxs-lookup"><span data-stu-id="a4dcd-120">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="a4dcd-121">Любой пользователь в Exchange, имеющий доступ к почтовому ящику с возможностью ввода текста, может применить метку хранения.</span><span class="sxs-lookup"><span data-stu-id="a4dcd-121">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="a4dcd-122">Применить метки в SharePoint и OneDrive может любой пользователь, который (на уровне разрешения "Участие") входит в группу "Участники", используемую по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a4dcd-122">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="a4dcd-123">Пример документа, помеченного как запись, с помощью метки хранения:</span><span class="sxs-lookup"><span data-stu-id="a4dcd-123">Example of a document marked as record by using a retention label:</span></span>

![Область сведений о документе, отмеченном как запись](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="a4dcd-125">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="a4dcd-125">Next steps</span></span>

<span data-ttu-id="a4dcd-126">Если необходимо обновить документы, являющиеся записями, см. раздел [Использование версий записи для обновления записей, хранящихся в SharePoint или OneDrive](record-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="a4dcd-126">If you need to update documents that are records, see [Use record versioning to update records stored in SharePoint or OneDrive](record-versioning.md).</span></span>

<span data-ttu-id="a4dcd-127">Информацию о ликвидации записей см. в разделе [Ликвидация содержимого](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="a4dcd-127">To learn about the disposition of records, see [Disposing of content](disposition.md).</span></span>
