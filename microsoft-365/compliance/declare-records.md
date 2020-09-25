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
ms.openlocfilehash: 490f81ba9c1d2d291539107650ec3c3f5938eba8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198928"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="f90e9-103">Объявление элементов записями с использованием меток хранения</span><span class="sxs-lookup"><span data-stu-id="f90e9-103">Declare records by using retention labels</span></span>

><span data-ttu-id="f90e9-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="f90e9-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="f90e9-105">Для объявления документов и писем [записями](records-management.md#records) используются [метки хранения](retention.md#retention-labels), помечающие контент как **запись** или как **нормативную запись**.</span><span class="sxs-lookup"><span data-stu-id="f90e9-105">To declare documents and emails as [records](records-management.md#records), you use [retention labels](retention.md#retention-labels) that mark the content as a **record** or a **regulatory record**.</span></span>

> [!NOTE]
> <span data-ttu-id="f90e9-106">В настоящий момент работа с нормативными записями возможна в предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="f90e9-106">Regulatory records are currently in preview.</span></span>

<span data-ttu-id="f90e9-107">Если вы не знаете, какой вариант нужно выбрать (запись или нормативную запись), см. статью [Сравнение ограничений на разрешенные или блокируемые действия](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span><span class="sxs-lookup"><span data-stu-id="f90e9-107">If you're not sure whether to use a record or a regulatory record, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span> <span data-ttu-id="f90e9-108">Если вам нужно использовать нормативные записи, нужно сначала запустить команду PowerShell, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="f90e9-108">If you need to use regulatory records, you must first run a PowerShell command, as described in the next section.</span></span>

<span data-ttu-id="f90e9-109">После этого вы можете либо опубликовать эти метки в политике меток хранения, чтобы пользователи и администраторы могли вручную применить их к содержимому, либо (в случае меток, помечающих элементы как записи, но не как нормативные записи) автоматически применить их к содержимому, которое вы хотите пометить как запись.</span><span class="sxs-lookup"><span data-stu-id="f90e9-109">You can then either publish those labels in a retention label policy so that users and administrators can apply them to content, or for labels that mark items as records (but not regulatory records), auto-apply those labels to content that you want to declare a record.</span></span>

## <a name="how-to-display-the-option-to-mark-content-as-a-regulatory-record"></a><span data-ttu-id="f90e9-110">Как отобразить параметр для пометки содержимого в качестве нормативной записи</span><span class="sxs-lookup"><span data-stu-id="f90e9-110">How to display the option to mark content as a regulatory record</span></span>

>[!NOTE] 
> <span data-ttu-id="f90e9-111">Изложенная ниже процедура относится к подлежащим аудиту действиям и вносит элемент **Разрешен вариант использования меток хранения для нормативных записей** в раздел журнала аудита [Действия, относящиеся к политикам хранения и меткам хранения](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities).</span><span class="sxs-lookup"><span data-stu-id="f90e9-111">The following procedure is an auditable action, logging **Enabled regulatory record option for retention labels** in the [Retention policy and retention label activities](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities) section of the audit log.</span></span>

<span data-ttu-id="f90e9-112">По умолчанию параметр меток хранения для пометки содержимого как нормативных записей не отображается в мастере меток хранения.</span><span class="sxs-lookup"><span data-stu-id="f90e9-112">By default, the retention label option to mark content as a regulatory record isn't displayed in the retention label wizard.</span></span> <span data-ttu-id="f90e9-113">Чтобы отобразить этот параметр, нужно сначала запустить команду PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f90e9-113">To display this option, you must first run a PowerShell command:</span></span>

1. <span data-ttu-id="f90e9-114">[Подключение к Powershell Центра безопасности и соответствия требованиям Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="f90e9-114">[Connect to the Office 365 Security & Compliance Center Powershell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="f90e9-115">Запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="f90e9-115">Run the following cmdlet:</span></span>
    
    ```powershell
    Set-RegulatoryComplianceUI -Enabled $true
    ````
    <span data-ttu-id="f90e9-116">Этот параметр вводится немедленно без запроса подтверждения.</span><span class="sxs-lookup"><span data-stu-id="f90e9-116">There is no prompt to confirm and the setting takes effect immediately.</span></span>

<span data-ttu-id="f90e9-117">Если вы передумали и больше не хотите, чтобы этот параметр отображался в мастере меток хранения, вы можете снова скрыть его, запустив тот же командлет со значением **false**: `Set-RegulatoryComplianceUI -Enabled $false`</span><span class="sxs-lookup"><span data-stu-id="f90e9-117">If you change your mind about seeing this option in the retention label wizard, you can hide it again by running the same cmdlet with the **false** value: `Set-RegulatoryComplianceUI -Enabled $false`</span></span> 

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="f90e9-118">Настройка меток хранения для объявления элементов записями</span><span class="sxs-lookup"><span data-stu-id="f90e9-118">Configuring retention labels to declare records</span></span>

<span data-ttu-id="f90e9-119">При создании или изменении метки хранения из решения **Управление записями** в Центре соответствия требованиям Microsoft 365 вы можете пометить элементы как записи.</span><span class="sxs-lookup"><span data-stu-id="f90e9-119">When you create or edit a retention label from the **Records Management** solution in the Microsoft 365 compliance center, you have the option to mark items as a record.</span></span> <span data-ttu-id="f90e9-120">Если вы запустили команду PowerShell из предыдущего раздела, то можете также пометить элементы как нормативные записи.</span><span class="sxs-lookup"><span data-stu-id="f90e9-120">If you ran the PowerShell command from the previous section, you can alternatively mark items as a regulatory record.</span></span>

<span data-ttu-id="f90e9-121">Пример.</span><span class="sxs-lookup"><span data-stu-id="f90e9-121">For example:</span></span>

![Настройка метки хранения для пометки содержимого как записи или нормативной записи](../media/recordversioning6.png)

<span data-ttu-id="f90e9-123">При необходимости можно применить эту метку хранения к документам SharePoint или OneDrive и сообщениям электронной почты Exchange.</span><span class="sxs-lookup"><span data-stu-id="f90e9-123">Using this retention label, you can now apply it to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> 

<span data-ttu-id="f90e9-124">Полный набор инструкций см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="f90e9-124">For full instructions:</span></span>

- [<span data-ttu-id="f90e9-125">Создание меток хранения и их применение в приложениях</span><span class="sxs-lookup"><span data-stu-id="f90e9-125">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)

- <span data-ttu-id="f90e9-126">[Автоматическое применение метки хранения к содержимому](apply-retention-labels-automatically.md) (не поддерживается для нормативных записей)</span><span class="sxs-lookup"><span data-stu-id="f90e9-126">[Apply a retention label to content automatically](apply-retention-labels-automatically.md) (not supported for regulatory records)</span></span>


## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="f90e9-127">Применение настроенной метки хранения к содержимому</span><span class="sxs-lookup"><span data-stu-id="f90e9-127">Applying the configured retention label to content</span></span>

<span data-ttu-id="f90e9-128">Доступность меток хранения, помечающих элементы в качестве записи или нормативной записи, пользователям для применения в приложениях:</span><span class="sxs-lookup"><span data-stu-id="f90e9-128">When retention labels that mark items as a record or regulatory record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="f90e9-129">Любой пользователь в Exchange, имеющий доступ к почтовому ящику с возможностью ввода текста, может применить метку хранения.</span><span class="sxs-lookup"><span data-stu-id="f90e9-129">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="f90e9-130">Применить метки в SharePoint и OneDrive может любой пользователь, который (на уровне разрешения "Участие") входит в группу "Участники", используемую по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f90e9-130">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="f90e9-131">Пример документа, помеченного как запись, с помощью метки хранения:</span><span class="sxs-lookup"><span data-stu-id="f90e9-131">Example of a document marked as record by using a retention label:</span></span>

![Область сведений о документе, отмеченном как запись](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="f90e9-133">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="f90e9-133">Next steps</span></span>

<span data-ttu-id="f90e9-134">Список сценариев, поддерживаемых службой управления записей, см. в разделе [Обычные сценарии для управления записями](get-started-with-records-management.md#common-scenarios-for-records-management).</span><span class="sxs-lookup"><span data-stu-id="f90e9-134">For a list of scenarios supported by records management, see [Common scenarios for records management](get-started-with-records-management.md#common-scenarios-for-records-management).</span></span>
