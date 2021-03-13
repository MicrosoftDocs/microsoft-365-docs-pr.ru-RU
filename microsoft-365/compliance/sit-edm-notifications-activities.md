---
title: Создание уведомлений для действий точного соответствия данных (предварительная версия)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Узнайте, как создавать уведомления для действий точного соответствия данных.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a537cffe253fa20cf6838ddf3fd9a51ec440fe76
ms.sourcegitcommit: 89095172c9c4793d56645b4c885ac8e30936bd0a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/13/2021
ms.locfileid: "50766701"
---
# <a name="create-notifications-for-exact-data-match-activities-preview"></a><span data-ttu-id="7445a-103">Создание уведомлений для действий точного соответствия данных (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="7445a-103">Create notifications for exact data match activities (preview)</span></span>

<span data-ttu-id="7445a-104">Когда вы создаете [пользовательские типы конфиденциальной информации с точным соответствием данных (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md), в [журнале аудита](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log) создается несколько действий.</span><span class="sxs-lookup"><span data-stu-id="7445a-104">When you [create custom sensitive information types with exact data match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) there are a number of activities that are created in the [audit log](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span> <span data-ttu-id="7445a-105">Вы можете использовать командлет [New-ProtectionAlert](https://docs.microsoft.com/powershell/module/exchange/new-protectionalert?view=exchange-ps) в PowerShell, чтобы создать уведомления, которые будут оповещать вас о таких действиях:</span><span class="sxs-lookup"><span data-stu-id="7445a-105">You can use the [New-ProtectionAlert](https://docs.microsoft.com/powershell/module/exchange/new-protectionalert?view=exchange-ps) PowerShell cmdlet to create notifications that let you know when these activities occur:</span></span>

- <span data-ttu-id="7445a-106">CreateSchema</span><span class="sxs-lookup"><span data-stu-id="7445a-106">CreateSchema</span></span>
- <span data-ttu-id="7445a-107">EditSchema</span><span class="sxs-lookup"><span data-stu-id="7445a-107">EditSchema</span></span>
- <span data-ttu-id="7445a-108">RemoveSchema</span><span class="sxs-lookup"><span data-stu-id="7445a-108">RemoveSchema</span></span>
- <span data-ttu-id="7445a-109">UploadDataFailed</span><span class="sxs-lookup"><span data-stu-id="7445a-109">UploadDataFailed</span></span>
- <span data-ttu-id="7445a-110">UploadDataCompleted</span><span class="sxs-lookup"><span data-stu-id="7445a-110">UploadDataCompleted</span></span>

> [!NOTE]
> <span data-ttu-id="7445a-111">Возможность создания уведомлений о действиях EDM доступна только для глобального облака и облака GCC.</span><span class="sxs-lookup"><span data-stu-id="7445a-111">The ability to create notifications for EDM activities is only available for the World Wide and GCC clouds only.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="7445a-112">Необходимые условия</span><span class="sxs-lookup"><span data-stu-id="7445a-112">Pre-requisites</span></span>

<span data-ttu-id="7445a-113">Требуется использовать одну из следующих учетных записей:</span><span class="sxs-lookup"><span data-stu-id="7445a-113">The account you use must be one of the following:</span></span>

- <span data-ttu-id="7445a-114">глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="7445a-114">a global admin</span></span>
- <span data-ttu-id="7445a-115">администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="7445a-115">compliance administrator</span></span>
- <span data-ttu-id="7445a-116">администратор службы Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7445a-116">Exchange Online administrator</span></span>

<span data-ttu-id="7445a-117">Дополнительные сведения о разрешениях DLP см. в разделе [Разрешения](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="7445a-117">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="7445a-118">Классификация на основе EDM включена в следующие подписки:</span><span class="sxs-lookup"><span data-stu-id="7445a-118">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="7445a-119">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="7445a-119">Office 365 E5</span></span>
- <span data-ttu-id="7445a-120">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="7445a-120">Microsoft 365 E5</span></span>
- <span data-ttu-id="7445a-121">Соответствие требованиям Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="7445a-121">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="7445a-122">Защита информации и управление данными в Microsoft E5/A5</span><span class="sxs-lookup"><span data-stu-id="7445a-122">Microsoft E5/A5 Information Protection and Governance</span></span>

<span data-ttu-id="7445a-123">Дополнительные сведения о лицензировании DLP см. в статье [Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span><span class="sxs-lookup"><span data-stu-id="7445a-123">To learn more about DLP licensing, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span></span>

## <a name="configure-notifications-for-edm-activities"></a><span data-ttu-id="7445a-124">Настройка уведомлений для действий EDM</span><span class="sxs-lookup"><span data-stu-id="7445a-124">Configure notifications for EDM activities</span></span>

1. <span data-ttu-id="7445a-125">Подключитесь к [интерфейсу PowerShell Центра безопасности и соответствия требованиям](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="7445a-125">Connect to the [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)</span></span> 

2. <span data-ttu-id="7445a-126">Запустите командлет `New-ProtectionAlert`, используя действие, для которого нужно создать уведомление.</span><span class="sxs-lookup"><span data-stu-id="7445a-126">Run the `New-ProtectionAlert` cmdlet using the activity that you want to create the notification for.</span></span>  <span data-ttu-id="7445a-127">Например, если вы хотите получать уведомление при выполнении действия **UploadDataCompleted**, запустите</span><span class="sxs-lookup"><span data-stu-id="7445a-127">For example, if you want to be notified when the **UploadDataCompleted** action occured, run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

<span data-ttu-id="7445a-128">для **UploadDataFailed** можно запустить</span><span class="sxs-lookup"><span data-stu-id="7445a-128">for the **UploadDataFailed** you can run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a><span data-ttu-id="7445a-129">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="7445a-129">Related articles</span></span>

- [<span data-ttu-id="7445a-130">Создание пользовательских типов конфиденциальной информации с точным соответствием данных</span><span class="sxs-lookup"><span data-stu-id="7445a-130">Create custom sensitive information types with exact data match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="7445a-131">New-ProtectionAlert</span><span class="sxs-lookup"><span data-stu-id="7445a-131">New-ProtectionAlert</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-protectionalert?view=exchange-ps) 