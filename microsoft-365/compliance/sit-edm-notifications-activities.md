---
title: Создание уведомлений для действий точного соответствия данных
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
ms.openlocfilehash: 263dc319d7e7d3ee5f12ebe374e8f5bd44c4cc8c
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341680"
---
# <a name="create-notifications-for-exact-data-match-activities"></a><span data-ttu-id="bb88c-103">Создание уведомлений для действий точного соответствия данных</span><span class="sxs-lookup"><span data-stu-id="bb88c-103">Create notifications for exact data match activities</span></span>

<span data-ttu-id="bb88c-104">Когда вы создаете [пользовательские типы конфиденциальной информации с точным соответствием данных (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md), в [журнале аудита](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log) создается несколько действий.</span><span class="sxs-lookup"><span data-stu-id="bb88c-104">When you [create custom sensitive information types with exact data match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) there are a number of activities that are created in the [audit log](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log).</span></span> <span data-ttu-id="bb88c-105">Вы можете использовать командлет [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) в PowerShell, чтобы создать уведомления, которые будут оповещать вас о таких действиях:</span><span class="sxs-lookup"><span data-stu-id="bb88c-105">You can use the [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) PowerShell cmdlet to create notifications that let you know when these activities occur:</span></span>

- <span data-ttu-id="bb88c-106">CreateSchema</span><span class="sxs-lookup"><span data-stu-id="bb88c-106">CreateSchema</span></span>
- <span data-ttu-id="bb88c-107">EditSchema</span><span class="sxs-lookup"><span data-stu-id="bb88c-107">EditSchema</span></span>
- <span data-ttu-id="bb88c-108">RemoveSchema</span><span class="sxs-lookup"><span data-stu-id="bb88c-108">RemoveSchema</span></span>
- <span data-ttu-id="bb88c-109">UploadDataFailed</span><span class="sxs-lookup"><span data-stu-id="bb88c-109">UploadDataFailed</span></span>
- <span data-ttu-id="bb88c-110">UploadDataCompleted</span><span class="sxs-lookup"><span data-stu-id="bb88c-110">UploadDataCompleted</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="bb88c-111">Необходимые условия</span><span class="sxs-lookup"><span data-stu-id="bb88c-111">Pre-requisites</span></span>

<span data-ttu-id="bb88c-112">Требуется использовать одну из следующих учетных записей:</span><span class="sxs-lookup"><span data-stu-id="bb88c-112">The account you use must be one of the following:</span></span>

- <span data-ttu-id="bb88c-113">глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="bb88c-113">a global admin</span></span>
- <span data-ttu-id="bb88c-114">администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="bb88c-114">compliance administrator</span></span>
- <span data-ttu-id="bb88c-115">администратор службы Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bb88c-115">Exchange Online administrator</span></span>

<span data-ttu-id="bb88c-116">Дополнительные сведения о разрешениях DLP см. в разделе [Разрешения](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="bb88c-116">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="bb88c-117">Классификация на основе EDM включена в следующие подписки:</span><span class="sxs-lookup"><span data-stu-id="bb88c-117">EDM-based classification is included in these subscriptions:</span></span>

- <span data-ttu-id="bb88c-118">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="bb88c-118">Office 365 E5</span></span>
- <span data-ttu-id="bb88c-119">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="bb88c-119">Microsoft 365 E5</span></span>
- <span data-ttu-id="bb88c-120">Соответствие требованиям Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="bb88c-120">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="bb88c-121">Защита информации и управление данными в Microsoft E5/A5</span><span class="sxs-lookup"><span data-stu-id="bb88c-121">Microsoft E5/A5 Information Protection and Governance</span></span>

<span data-ttu-id="bb88c-122">Дополнительные сведения о лицензировании DLP см. в статье [Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span><span class="sxs-lookup"><span data-stu-id="bb88c-122">To learn more about DLP licensing, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span>

## <a name="configure-notifications-for-edm-activities"></a><span data-ttu-id="bb88c-123">Настройка уведомлений для действий EDM</span><span class="sxs-lookup"><span data-stu-id="bb88c-123">Configure notifications for EDM activities</span></span>

1. <span data-ttu-id="bb88c-124">Подключитесь к [интерфейсу PowerShell Центра безопасности и соответствия требованиям](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="bb88c-124">Connect to the [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="bb88c-125">Запустите командлет `New-ProtectionAlert`, используя действие, для которого нужно создать уведомление.</span><span class="sxs-lookup"><span data-stu-id="bb88c-125">Run the `New-ProtectionAlert` cmdlet using the activity that you want to create the notification for.</span></span>  <span data-ttu-id="bb88c-126">Например, если вы хотите получать уведомление при выполнении действия **UploadDataCompleted**, запустите:</span><span class="sxs-lookup"><span data-stu-id="bb88c-126">For example, if you want to be notified when the **UploadDataCompleted** action occurred, run:</span></span>

    ```powershell
    New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <address to send notification to> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
    ```
    
    <span data-ttu-id="bb88c-127">для **UploadDataFailed** можно запустить:</span><span class="sxs-lookup"><span data-stu-id="bb88c-127">for the **UploadDataFailed** you can run:</span></span>
    
    ```powershell
    New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <SMTP address to send notification to> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
    ```

## <a name="related-articles"></a><span data-ttu-id="bb88c-128">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="bb88c-128">Related articles</span></span>

- [<span data-ttu-id="bb88c-129">Создание пользовательских типов конфиденциальной информации с точным соответствием данных</span><span class="sxs-lookup"><span data-stu-id="bb88c-129">Create custom sensitive information types with exact data match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="bb88c-130">New-ProtectionAlert</span><span class="sxs-lookup"><span data-stu-id="bb88c-130">New-ProtectionAlert</span></span>](/powershell/module/exchange/new-protectionalert)