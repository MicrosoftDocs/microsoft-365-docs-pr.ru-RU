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
ms.openlocfilehash: 841c5197addff704016e344ba7ae44355c872f72
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47817112"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="57b81-103">Объявление элементов записями с использованием меток хранения</span><span class="sxs-lookup"><span data-stu-id="57b81-103">Declare records by using retention labels</span></span>

><span data-ttu-id="57b81-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="57b81-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="57b81-105">Чтобы объявить документы и письма в качестве записей, используйте [метки хранения](retention.md#retention-labels), помечающие элементы как записи.</span><span class="sxs-lookup"><span data-stu-id="57b81-105">To declare documents and emails as a record, you use [retention labels](retention.md#retention-labels) that mark items as a record.</span></span> <span data-ttu-id="57b81-106">Вы можете либо опубликовать эти метки, чтобы пользователи и администраторы могли вручную применить их к содержимому, либо автоматически применить эти метки к содержимому, которое вы хотите пометить как запись.</span><span class="sxs-lookup"><span data-stu-id="57b81-106">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="57b81-107">Настройка меток хранения для объявления элементов записями</span><span class="sxs-lookup"><span data-stu-id="57b81-107">Configuring retention labels to declare records</span></span>

<span data-ttu-id="57b81-108">Когда вы создаете или настраиваете метку хранения, выберите вариант пометки элементов как записей.</span><span class="sxs-lookup"><span data-stu-id="57b81-108">When you create or configure a retention label, select the option to mark items as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="57b81-109">Параметр пометки содержимого как запись недоступен при создании или настройки метки хранения из раздела **Управление информацией** в Центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="57b81-109">The option to mark the content as a record is not available when you create or configure retention labels from **Information Governance** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="57b81-110">Вместо этого необходимо использовать раздел**Управление записями**.</span><span class="sxs-lookup"><span data-stu-id="57b81-110">Instead, you must use **Records Management**.</span></span>

<span data-ttu-id="57b81-111">Создание метки хранения, помечающей содержимое как запись:</span><span class="sxs-lookup"><span data-stu-id="57b81-111">To create a new retention label that marks the content as a record:</span></span>

1. <span data-ttu-id="57b81-112">В [Центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com), перейти в раздел **Управление записями** \> **План хранения**.</span><span class="sxs-lookup"><span data-stu-id="57b81-112">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="57b81-113">На странице **План хранения** выберите **Создать метку**.</span><span class="sxs-lookup"><span data-stu-id="57b81-113">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="57b81-114">На странице **Определение параметров хранения** в мастере выберите параметр, чтобы пометить элементы как записи:</span><span class="sxs-lookup"><span data-stu-id="57b81-114">On the **Define retention settings** page in the wizard, choose the option to mark items as records:</span></span>
    
   ![Выбор параметра хранения для пометки элементов как записей](../media/recordversioning6.png)

3. <span data-ttu-id="57b81-116">При необходимости можно применить метку хранения к документам SharePoint или OneDrive и электронным письмам Exchange.</span><span class="sxs-lookup"><span data-stu-id="57b81-116">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="57b81-117">Для получения инструкций:</span><span class="sxs-lookup"><span data-stu-id="57b81-117">For instructions:</span></span>
    
    - [<span data-ttu-id="57b81-118">Создание меток хранения и их применение в приложениях</span><span class="sxs-lookup"><span data-stu-id="57b81-118">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="57b81-119">Автоматическое применение метки хранения к контенту</span><span class="sxs-lookup"><span data-stu-id="57b81-119">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="57b81-120">Применение сконфигурированной метки хранения к содержимому</span><span class="sxs-lookup"><span data-stu-id="57b81-120">Applying the configured retention label to content</span></span>

<span data-ttu-id="57b81-121">Когда метки хранения, помечающие содержимое как запись, становятся доступны для пользователей для применения их в приложениях:</span><span class="sxs-lookup"><span data-stu-id="57b81-121">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="57b81-122">Любой пользователь в Exchange, имеющий доступ к почтовому ящику с возможностью ввода текста, может применить метку хранения.</span><span class="sxs-lookup"><span data-stu-id="57b81-122">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="57b81-123">Применить метки в SharePoint и OneDrive может любой пользователь, который (на уровне разрешения "Участие") входит в группу "Участники", используемую по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="57b81-123">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="57b81-124">Пример документа, помеченного как запись, с помощью метки хранения:</span><span class="sxs-lookup"><span data-stu-id="57b81-124">Example of a document marked as record by using a retention label:</span></span>

![Область сведений о документе, отмеченном как запись](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="57b81-126">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="57b81-126">Next steps</span></span>

<span data-ttu-id="57b81-127">Список сценариев, поддерживаемых службой управления записей, см. в разделе [Обычные сценарии для управления записями](get-started-with-records-management.md#common-scenarios-for-records-management).</span><span class="sxs-lookup"><span data-stu-id="57b81-127">For a list of scenarios supported by records management, see [Common scenarios for records management](get-started-with-records-management.md#common-scenarios-for-records-management).</span></span>
