---
title: Использование локального сканера для защиты от потери данных Microsoft 365 (предварительная версия)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Узнайте, как использовать локальный сканер для защиты от потери данных Microsoft 365 для сканирования неактивных данных и реализации защитных мер на локальных файловых ресурсах и в локальных папках и библиотеках документов SharePoint.
ms.openlocfilehash: 34be93f5c9980a7f8ea8ad31b708af14a8725f73
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/03/2021
ms.locfileid: "50417394"
---
# <a name="use-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="aeb9a-103">Использование локального сканера для защиты от потери данных Microsoft 365 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="aeb9a-103">Use the Microsoft 365 data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="aeb9a-104">Чтобы помочь вам ознакомиться с локальными возможностями защиты от потери данных, а также с использованием этих возможностей в политиках защиты от потери данных, мы составили для вас несколько сценариев.</span><span class="sxs-lookup"><span data-stu-id="aeb9a-104">To help familiarize you with DLP on-premises features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aeb9a-105">Эти сценарии локальной защиты от потери данных — не официальные процедуры для создания и настройки политик защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="aeb9a-105">These DLP on-premises scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="aeb9a-106">Если вам нужно использовать политики защиты от потери данных в общих ситуациях, прочитайте эти статьи:</span><span class="sxs-lookup"><span data-stu-id="aeb9a-106">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>- [<span data-ttu-id="aeb9a-107">Общие сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="aeb9a-107">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
>- [<span data-ttu-id="aeb9a-108">Начало работы со стандартной политикой защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="aeb9a-108">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="aeb9a-109">Создание политики защиты от потери данных на основе шаблона</span><span class="sxs-lookup"><span data-stu-id="aeb9a-109">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="aeb9a-110">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="aeb9a-110">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-discover-files-matching-dlp-rules"></a><span data-ttu-id="aeb9a-111">Сценарий: обнаружение файлов, соответствующих правилам защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="aeb9a-111">Scenario: Discover files matching DLP rules</span></span>

<span data-ttu-id="aeb9a-112">Данные с локального сканера защиты от потери данных используются в нескольких областях</span><span class="sxs-lookup"><span data-stu-id="aeb9a-112">Data from DLP on-premises scanner surfaces in several areas</span></span>

#### <a name="activity-explorer"></a><span data-ttu-id="aeb9a-113">Обозреватель действий</span><span class="sxs-lookup"><span data-stu-id="aeb9a-113">Activity explorer</span></span>

 <span data-ttu-id="aeb9a-114">Локальная защита от потери данных (Майкрософт) обнаруживает соответствия правил защиты от потери данных и сообщает о них в [Обозреватель действий](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer).</span><span class="sxs-lookup"><span data-stu-id="aeb9a-114">Microsoft DLP for on-premises detects DLP rule matches and reports them to [Activity Explorer](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer).</span></span> 
 
#### <a name="microsoft-365-audit-log"></a><span data-ttu-id="aeb9a-115">Журнал аудита Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aeb9a-115">Microsoft 365 Audit log</span></span>

<span data-ttu-id="aeb9a-116">В общедоступной предварительной версии соответствия правил защиты от потери данных доступны в пользовательском интерфейсе журнала аудита, см. [Поиск журнала аудита в Центре соответствия требованиям](search-the-audit-log-in-security-and-compliance.md) или с помощью командлета [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aeb9a-116">During the public preview the DLP rule matches are available in Audit log UI, see [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md)  or accessible by [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell.</span></span>

#### <a name="aip"></a><span data-ttu-id="aeb9a-117">AIP</span><span class="sxs-lookup"><span data-stu-id="aeb9a-117">AIP</span></span>

<span data-ttu-id="aeb9a-118">Данные обнаружения доступны в локальном отчете в формате csv, который хранится по адресу:</span><span class="sxs-lookup"><span data-stu-id="aeb9a-118">Discovery data is available in a local report in csv format which is stored under:</span></span>

<span data-ttu-id="aeb9a-119">**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.</span><span class="sxs-lookup"><span data-stu-id="aeb9a-119">**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.</span></span>

 <span data-ttu-id="aeb9a-120">Выполните поиск следующих столбцов:</span><span class="sxs-lookup"><span data-stu-id="aeb9a-120">Look for the following columns:</span></span>
- <span data-ttu-id="aeb9a-121">Режим DLP</span><span class="sxs-lookup"><span data-stu-id="aeb9a-121">DLP Mode</span></span>
- <span data-ttu-id="aeb9a-122">Статус DLP</span><span class="sxs-lookup"><span data-stu-id="aeb9a-122">DLP Status</span></span>
- <span data-ttu-id="aeb9a-123">Комментарий DLP</span><span class="sxs-lookup"><span data-stu-id="aeb9a-123">DLP Comment</span></span>
- <span data-ttu-id="aeb9a-124">Имя правила DLP, действия DLP</span><span class="sxs-lookup"><span data-stu-id="aeb9a-124">DLP Rule Name DLP Actions</span></span>
- <span data-ttu-id="aeb9a-125">Владелец</span><span class="sxs-lookup"><span data-stu-id="aeb9a-125">Owner</span></span>
- <span data-ttu-id="aeb9a-126">Текущие разрешения NTFS (SDDL)</span><span class="sxs-lookup"><span data-stu-id="aeb9a-126">Current NTFS Permissions (SDDL)</span></span>
- <span data-ttu-id="aeb9a-127">Примененные разрешения NTFS (SDDL)</span><span class="sxs-lookup"><span data-stu-id="aeb9a-127">Applied NTFS Permissions (SDDL)</span></span>
- <span data-ttu-id="aeb9a-128">Тип разрешений NTFS</span><span class="sxs-lookup"><span data-stu-id="aeb9a-128">NTFS permissions type</span></span>
 
### <a name="scenario-enforce-dlp-rule"></a><span data-ttu-id="aeb9a-129">Сценарий: принудительное применение правила защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="aeb9a-129">Scenario: Enforce DLP rule</span></span> 

<span data-ttu-id="aeb9a-130">Если вы хотите принудительно применить правила защиты от потери данных к отсканированным файлам, то такое принудительное применение должно быть включено как для задания сканирования содержимого в AIP, так и на уровне политики в защите от потери данных.</span><span class="sxs-lookup"><span data-stu-id="aeb9a-130">If you want to enforce DLP rules on the scanned files, enforcement must be enabled on both the content scan job in AIP and at the policy level in DLP.</span></span>


#### <a name="configure-dlp-to-enforce-policy-actions"></a><span data-ttu-id="aeb9a-131">Настройка защиты от потери данных для принудительного применения действий политики</span><span class="sxs-lookup"><span data-stu-id="aeb9a-131">Configure DLP to enforce policy actions</span></span>

1. <span data-ttu-id="aeb9a-132">Откройте страницу [Защита от потери данных](https://compliance.microsoft.com/datalossprevention?viewid=policies) и выберите политику защиты от потери данных, направленную на репозитории локального расположения, которые вы настроили в AIP.</span><span class="sxs-lookup"><span data-stu-id="aeb9a-132">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) and select the DLP policy that is targeted to the on-premises location repositories you have configured in AIP.</span></span> 
2. <span data-ttu-id="aeb9a-133">Изменение политики</span><span class="sxs-lookup"><span data-stu-id="aeb9a-133">Edit the policy.</span></span>
3. <span data-ttu-id="aeb9a-134">На странице **Проверка или включение политики** выберите пункт **Да, включить сейчас**.</span><span class="sxs-lookup"><span data-stu-id="aeb9a-134">On the **Test or turn on the policy** page, select **Yes, turn it on right away**.</span></span> 

## <a name="see-also"></a><span data-ttu-id="aeb9a-135">См. также</span><span class="sxs-lookup"><span data-stu-id="aeb9a-135">See also</span></span>

- [<span data-ttu-id="aeb9a-136">Сведения о локальном сканере защиты от потери данных (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="aeb9a-136">Learn about DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="aeb9a-137">Начало работы с локальным сканером для защиты от потери данных (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="aeb9a-137">Get started with  DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-get-started.md)
- [<span data-ttu-id="aeb9a-138">Общие сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="aeb9a-138">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="aeb9a-139">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="aeb9a-139">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="aeb9a-140">Начало работы с обозревателем действий</span><span class="sxs-lookup"><span data-stu-id="aeb9a-140">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)