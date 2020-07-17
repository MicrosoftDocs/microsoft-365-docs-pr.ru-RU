---
title: Применение меток к персональным данным
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Узнайте, как использовать ярлыки Office как часть вашего плана защиты Общего Регламента Защиты Данных (GDPR).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a7bea2abeaec7a858b3cfc693603c46c0f2a416a
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126820"
---
# <a name="apply-labels-to-personal-data"></a><span data-ttu-id="071fa-103">Применение меток к персональным данным</span><span class="sxs-lookup"><span data-stu-id="071fa-103">Apply labels to personal data</span></span>

 <span data-ttu-id="071fa-104">Указания в этой статье помогут вам, если вы используете метки классификации для защиты данных в соответствии с регламентом GDPR.</span><span class="sxs-lookup"><span data-stu-id="071fa-104">Use this topic if you're using classification labels as part of your GDPR protection plan.</span></span> 

<span data-ttu-id="071fa-105">Если вы используете метки для защиты персональных данных в Microsoft 365, корпорация Майкрософт рекомендует начать работу с [метками хранения](retention.md#retention-labels).</span><span class="sxs-lookup"><span data-stu-id="071fa-105">If you're using labels for protection of personal data in Microsoft 365, Microsoft recommends you start with [retention labels](retention.md#retention-labels).</span></span> <span data-ttu-id="071fa-106">С помощью меток хранения вы можете:</span><span class="sxs-lookup"><span data-stu-id="071fa-106">With retention labels, you can:</span></span>
- <span data-ttu-id="071fa-107">Использовать расширенное управление данными, чтобы автоматически применять метки в зависимости от типов конфиденциальной информации или других условий.</span><span class="sxs-lookup"><span data-stu-id="071fa-107">Use Advanced Data Governance to automatically apply labels based on sensitive information types or other criteria.</span></span>
- <span data-ttu-id="071fa-108">Применять защиту, используя метки хранения с защитой от потери данных.</span><span class="sxs-lookup"><span data-stu-id="071fa-108">Use retention labels with data loss prevention to apply protection.</span></span> 
- <span data-ttu-id="071fa-109">Использовать метки с функциями обнаружения электронных данных и поиска контента.</span><span class="sxs-lookup"><span data-stu-id="071fa-109">Use labels with eDiscovery and Content Search.</span></span> 

<span data-ttu-id="071fa-110">Cloud App Security сейчас не поддерживает метки хранения, но вы можете использовать типы конфиденциальной информации Microsoft 365 с Cloud App Security для отслеживания персональных данных, которые хранятся в других приложениях SaaS.</span><span class="sxs-lookup"><span data-stu-id="071fa-110">Cloud App Security doesn't currently support retention labels, but you can use Microsoft 365 sensitive information types with Cloud App Security to monitor personal data that resides in other SaaS apps.</span></span>

<span data-ttu-id="071fa-111">В настоящее время [метки конфиденциальности](sensitivity-labels.md) рекомендуется использовать для применения меток к файлам в локальной среде, других облачных службах и поставщиках,</span><span class="sxs-lookup"><span data-stu-id="071fa-111">[Sensitivity labels](sensitivity-labels.md) are currently recommended for applying labels to files on premises and in other cloud services and providers.</span></span> <span data-ttu-id="071fa-112">Их также рекомендуется использовать для файлов в Microsoft 365, требующих защиты данных с помощью шифрования Azure Information Protection. Например, такие файлы могут содержать коммерческую тайну.</span><span class="sxs-lookup"><span data-stu-id="071fa-112">These are also recommended for files in Microsoft 365 that require Azure Information Protection encryption for data protection, such as trade secret files.</span></span>

<span data-ttu-id="071fa-113">Сейчас Azure Information Protection не рекомендуется использовать для шифрования файлов Microsoft 365 с данными, на которые распространяется регламент GDPR.</span><span class="sxs-lookup"><span data-stu-id="071fa-113">At this time, using Azure Information Protection to apply encryption is not recommended for files in Microsoft 365 with data that is subject to the GDPR.</span></span> <span data-ttu-id="071fa-114">Службы Microsoft 365 в настоящее время не могут считывать файлы, зашифрованные с использованием AIP,</span><span class="sxs-lookup"><span data-stu-id="071fa-114">Microsoft 365 services currently cannot read into AIP-encrypted files.</span></span> <span data-ttu-id="071fa-115">поэтому не могут находить конфиденциальные данные в этих файлах.</span><span class="sxs-lookup"><span data-stu-id="071fa-115">Therefore, the service can't find sensitive data in these files.</span></span>

<span data-ttu-id="071fa-116">К почте в Exchange Online можно применять метки хранения. Кроме того, их можно использовать при защите от потери данных в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="071fa-116">Retention labels can be applied to mail in Exchange Online and these labels work with Microsoft 365 data loss prevention.</span></span> 

![Метки Microsoft 365 и Azure Information Protection](../media/Apply-labels-to-personal-data-in-Office-365-image1.png)


<span data-ttu-id="071fa-118">На этом рисунке:</span><span class="sxs-lookup"><span data-stu-id="071fa-118">In the illustration:</span></span>

-   <span data-ttu-id="071fa-119">Используйте метки хранения для персональных данных, строго регулируемых файлов и файлов с коммерческими тайнами в SharePoint Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="071fa-119">Use retention labels for personal data and for highly regulated and trade secret files in SharePoint Online and OneDrive for Business.</span></span>
-   <span data-ttu-id="071fa-120">Типы конфиденциальной информации Microsoft 365 можно использовать в Microsoft 365 и с Cloud App Security для отслеживания персональных данных, хранящихся в других приложениях SaaS.</span><span class="sxs-lookup"><span data-stu-id="071fa-120">Microsoft 365 sensitive information types can be used within Microsoft 365 and with Cloud App Security to monitor personal data that resides in other SaaS apps.</span></span>
-   <span data-ttu-id="071fa-121">Используйте метки конфиденциальности для строго регулируемых файлов и файлов с коммерческими тайнами, электронной почты Exchange Online, файлов в других службах SaaS, файлов в локальных центрах обработки данных и других облачных службах.</span><span class="sxs-lookup"><span data-stu-id="071fa-121">Use sensitivity labels for highly regulated and trade secret files, Exchange Online email, files in other SaaS services, files in on-premises datacenters, and files in other cloud providers.</span></span>


## <a name="use-retention-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a><span data-ttu-id="071fa-122">Использование меток хранения и типов конфиденциальной информации в Microsoft 365 для защиты данных</span><span class="sxs-lookup"><span data-stu-id="071fa-122">Use retention labels and sensitive information types across Microsoft 365 for information protection</span></span>

<span data-ttu-id="071fa-123">На рисунке ниже показано, как метки хранения и типы конфиденциальной информации можно использовать в политиках в отношении меток, политиках защиты от потери данных и политиках Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="071fa-123">The following illustration shows how retention labels and sensitive information types can be used in label policies, data loss prevention policies, and with Cloud App Security policies.</span></span>

![Метки и типы конфиденциальной информации Office](../media/Apply-labels-to-personal-data-in-Office-365-image2.png)

<span data-ttu-id="071fa-125">Для работы специальных возможностей примеры на рисунке также приведены в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="071fa-125">For accessibility, the following table provides the same examples in the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="071fa-126"><strong>Элементы классификации</strong></span><span class="sxs-lookup"><span data-stu-id="071fa-126"><strong>Classification elements</strong></span></span></th>
<th align="left"><span data-ttu-id="071fa-127"><strong>Политики в отношении меток — 2 примера</strong></span><span class="sxs-lookup"><span data-stu-id="071fa-127"><strong>Label policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="071fa-128"><strong>Политики защиты от потери данных — 2 примера</strong></span><span class="sxs-lookup"><span data-stu-id="071fa-128"><strong>Data loss prevention policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="071fa-129"><strong>Политики Cloud App Security для всех приложений SaaS — 1 пример</strong></span><span class="sxs-lookup"><span data-stu-id="071fa-129"><strong>Cloud App Security policies for all SaaS apps — 1 example</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="071fa-130">Метки хранения.</span><span class="sxs-lookup"><span data-stu-id="071fa-130">Retention labels.</span></span> <span data-ttu-id="071fa-131">Примеры: "Персональные", "Общедоступные", "Данные клиента", "Данные о персонале" "Конфиденциально", "Строго конфиденциально"</span><span class="sxs-lookup"><span data-stu-id="071fa-131">Examples: Personal, Public, Customer data, HR data, Confidential, Highly confidential</span></span></td>
<td align="left"><p><span data-ttu-id="071fa-p105">Автоматически применять эту метку...</span><span class="sxs-lookup"><span data-stu-id="071fa-p105">Auto apply this label . . .</span></span></p>
<p><span data-ttu-id="071fa-135">Данные клиента</span><span class="sxs-lookup"><span data-stu-id="071fa-135">Customer data</span></span></p>
<p><span data-ttu-id="071fa-p106">...к документам, которые соответствуют этим типам конфиденциальной информации...</span><span class="sxs-lookup"><span data-stu-id="071fa-p106">. . . to documents that match these sensitive information types . . .</span></span></p>
<p><span data-ttu-id="071fa-142">&lt;список примеров типов конфиденциальной информации&gt;</span><span class="sxs-lookup"><span data-stu-id="071fa-142">&lt;list of example sensitive information types&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="071fa-p107">Применять эту защиту...</span><span class="sxs-lookup"><span data-stu-id="071fa-p107">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="071fa-146">&lt;определение защиты&gt;</span><span class="sxs-lookup"><span data-stu-id="071fa-146">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="071fa-p108">...к документам с этой меткой...</span><span class="sxs-lookup"><span data-stu-id="071fa-p108">. . . to documents with this label . . .</span></span></p>
<p><span data-ttu-id="071fa-153">Данные клиента</span><span class="sxs-lookup"><span data-stu-id="071fa-153">Customer data</span></span></p></td>
<td align="left"><p><span data-ttu-id="071fa-p109">Оповещать, когда к файлам с этими атрибутами...</span><span class="sxs-lookup"><span data-stu-id="071fa-p109">Alert when files with these attributes . . .</span></span></p>
<p><span data-ttu-id="071fa-157">Выберите один или несколько атрибутов: предопределенный атрибут PII, тип конфиденциальной информации Microsoft 365, метка конфиденциальности (AIP), настраиваемое выражение</span><span class="sxs-lookup"><span data-stu-id="071fa-157">Choose one or more attributes: predefined PII attribute, Microsoft 365 sensitive information type, sensitivity label (AIP), custom expression</span></span></p>
<p><span data-ttu-id="071fa-158">.</span><span class="sxs-lookup"><span data-stu-id="071fa-158">.</span></span> <span data-ttu-id="071fa-159">.</span><span class="sxs-lookup"><span data-stu-id="071fa-159">.</span></span> <span data-ttu-id="071fa-160">.</span><span class="sxs-lookup"><span data-stu-id="071fa-160">.</span></span> <span data-ttu-id="071fa-161">в любом санкционированном приложении SaaS предоставляется общий доступ за пределами организации</span><span class="sxs-lookup"><span data-stu-id="071fa-161">in any sanctioned SaaS app are shared outside the organization</span></span></p><p><span data-ttu-id="071fa-162">Примечание. Метки хранения сейчас не поддерживаются в Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="071fa-162">Note: Retention labels are currently not supported in Cloud App Security.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="071fa-p111">Типы конфиденциальной информации. Примеры: "Внутренний идентификационный номер гражданина Бельгии", "Номер кредитной карты", "Номер идентификационной карты гражданина Хорватии", "Национальный идентификационный номер гражданина Финляндии"</span><span class="sxs-lookup"><span data-stu-id="071fa-p111">Sensitive information types. Examples: Belgium National Number, Credit Card Number, Croatia Identity Cart Number, Finland National ID</span></span></td>
<td align="left"><p><span data-ttu-id="071fa-p112">Публиковать эти метки для пользователей, чтобы вручную применять...</span><span class="sxs-lookup"><span data-stu-id="071fa-p112">Publish these labels for users to manually apply . . .</span></span></p>
<p><span data-ttu-id="071fa-168">&lt;выберите метки&gt;</span><span class="sxs-lookup"><span data-stu-id="071fa-168">&lt;select labels&gt;</span></span></p>
<p><span data-ttu-id="071fa-p113">...к этим расположениям...</span><span class="sxs-lookup"><span data-stu-id="071fa-p113">. . . to these locations . . .</span></span></p>
<p><span data-ttu-id="071fa-175">&lt;все расположения или выберите расположения&gt;</span><span class="sxs-lookup"><span data-stu-id="071fa-175">&lt;all locations or choose specific locations&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="071fa-p114">Применять эту защиту...</span><span class="sxs-lookup"><span data-stu-id="071fa-p114">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="071fa-179">&lt;определение защиты&gt;</span><span class="sxs-lookup"><span data-stu-id="071fa-179">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="071fa-p115">...к документам, которые соответствуют этим типам конфиденциальной информации&gt;</span><span class="sxs-lookup"><span data-stu-id="071fa-p115">. . . to documents that match these sensitive information types&gt;</span></span></p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a><span data-ttu-id="071fa-184">Определение приоритетных политик автоматического применения меток</span><span class="sxs-lookup"><span data-stu-id="071fa-184">Prioritize auto-apply label policies</span></span>

<span data-ttu-id="071fa-p116">Корпорация Майкрософт рекомендует автоматически применять метки к персональным данным, на которые распространяется регламент GDPR, используя типы конфиденциальной информации, подобранные для вашей среды. Важно хорошо правильно разработать и проверить политики автоматического применения меток, чтобы они правильно работали.</span><span class="sxs-lookup"><span data-stu-id="071fa-p116">For personal data that is subject to GDPR, Microsoft recommends auto-applying labels by using the sensitive information types you curated for your environment. It is important that auto-apply label policies are well designed and tested to ensure the intended behavior occurs.</span></span>

<span data-ttu-id="071fa-p117">На результаты влияет порядок создания политик автоматического применения, а также то, применяют ли эти метки пользователи. Поэтому крайне важно тщательно спланировать развертывание. Вот что нужно знать.</span><span class="sxs-lookup"><span data-stu-id="071fa-p117">The order that auto-apply policies are created and whether users are also applying these labels affect the result. So, it's important to carefully plan the roll-out. Here's what you need to know.</span></span>

### <a name="one-label-at-a-time"></a><span data-ttu-id="071fa-189">По одной метке</span><span class="sxs-lookup"><span data-stu-id="071fa-189">One label at a time</span></span>

<span data-ttu-id="071fa-190">Документу можно назначить только одну метку.</span><span class="sxs-lookup"><span data-stu-id="071fa-190">You can only assign one label to a document.</span></span>

### <a name="older-auto-apply-policies-win"></a><span data-ttu-id="071fa-191">Установка приоритета для политик автоматического применения более ранних версий</span><span class="sxs-lookup"><span data-stu-id="071fa-191">Older auto-apply policies win</span></span>

<span data-ttu-id="071fa-p118">Если имеется несколько правил назначения автоматической метки, а содержимое соответствует условиям всех этих правил, будет назначена метка для самого старого правила. По этой причине очень важно тщательно спланировать применение политик в отношении меток, прежде чем их настраивать. Если организации необходимо изменить приоритет политик в отношении меток, их потребуется удалить и заново создать.</span><span class="sxs-lookup"><span data-stu-id="071fa-p118">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned. For this reason, it's important to plan the label policies carefully before configuring them. If an organization requires a change to the priority of the label policies, they'll need to delete and recreate them.</span></span>

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a><span data-ttu-id="071fa-195">Метки, вручную примененные пользователем, имеют приоритет над автоматическими метками</span><span class="sxs-lookup"><span data-stu-id="071fa-195">Manual user-applied labels trump auto-applied labels</span></span>

<span data-ttu-id="071fa-p119">Метки, вручную примененные пользователем, имеют приоритет над автоматическими метками. Политики автоматического применения не могут заменить метку, которую уже применил пользователь. Пользователи могут заменять автоматические метки.</span><span class="sxs-lookup"><span data-stu-id="071fa-p119">Manual user applied labels trump auto-applied labels. Auto-apply policies can't replace a label that is already applied by a user. Users can replace labels that are auto-applied.</span></span>

### <a name="auto-assigned-labels-can-be-updated"></a><span data-ttu-id="071fa-199">Возможность обновления автоматически назначаемых меток</span><span class="sxs-lookup"><span data-stu-id="071fa-199">Auto-assigned labels can be updated</span></span>

<span data-ttu-id="071fa-200">Автоматически назначаемые метки можно обновлять с помощью новых политик в отношении меток или путем обновления существующих политик.</span><span class="sxs-lookup"><span data-stu-id="071fa-200">Auto-assigned labels can be updated by either newer label policies or by updates to existing policies.</span></span>

<span data-ttu-id="071fa-201">Убедитесь, что ваш план по внедрению меток предусматривает следующее:</span><span class="sxs-lookup"><span data-stu-id="071fa-201">Be sure your plan for implementing labels includes:</span></span>

- <span data-ttu-id="071fa-202">Определение приоритетного порядка создания политик автоматического применения.</span><span class="sxs-lookup"><span data-stu-id="071fa-202">Prioritizing the order that auto-apply policies are created.</span></span>

- <span data-ttu-id="071fa-p120">Наличие достаточного времени для автоматического применения меток перед их развертыванием для применения пользователями вручную. Применение меток ко всему содержимому, которое соответствует условиям, может занять до семи дней.</span><span class="sxs-lookup"><span data-stu-id="071fa-p120">Allowing enough time for labels to be automatically applied before rolling these out for users to manually apply. It can take up to seven days for the labels to be applied to all content that matches the conditions.</span></span>

### <a name="example-priority-for-creating-the-auto-apply-policies"></a><span data-ttu-id="071fa-205">Пример установки приоритета для создания политик автоматического применения</span><span class="sxs-lookup"><span data-stu-id="071fa-205">Example priority for creating the auto-apply policies</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="071fa-206"><strong>Метки</strong></span><span class="sxs-lookup"><span data-stu-id="071fa-206"><strong>Labels</strong></span></span></th>
<th align="left"><span data-ttu-id="071fa-207"><strong>Приоритетный порядок создания политик автоматического применения</strong></span><span class="sxs-lookup"><span data-stu-id="071fa-207"><strong>Priority order to create auto-apply policies</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="071fa-208">Отдел кадров — данные о сотрудниках</span><span class="sxs-lookup"><span data-stu-id="071fa-208">Human Resources — Employee Data</span></span></td>
<td align="left"><span data-ttu-id="071fa-209">1</span><span class="sxs-lookup"><span data-stu-id="071fa-209">1</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="071fa-210">Данные клиента</span><span class="sxs-lookup"><span data-stu-id="071fa-210">Customer Data</span></span></td>
<td align="left"><span data-ttu-id="071fa-211">2</span><span class="sxs-lookup"><span data-stu-id="071fa-211">2</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="071fa-212">Строго конфиденциально</span><span class="sxs-lookup"><span data-stu-id="071fa-212">Highly Confidential</span></span></td>
<td align="left"><span data-ttu-id="071fa-213">3</span><span class="sxs-lookup"><span data-stu-id="071fa-213">3</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="071fa-214">Отдел кадров — данные о зарплате</span><span class="sxs-lookup"><span data-stu-id="071fa-214">Human Resources — Salary Data</span></span></td>
<td align="left"><span data-ttu-id="071fa-215">4</span><span class="sxs-lookup"><span data-stu-id="071fa-215">4</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="071fa-216">Конфиденциально</span><span class="sxs-lookup"><span data-stu-id="071fa-216">Confidential</span></span></td>
<td align="left"><span data-ttu-id="071fa-217">5</span><span class="sxs-lookup"><span data-stu-id="071fa-217">5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="071fa-218">Общедоступные</span><span class="sxs-lookup"><span data-stu-id="071fa-218">Public</span></span></td>
<td align="left"><span data-ttu-id="071fa-219">6</span><span class="sxs-lookup"><span data-stu-id="071fa-219">6</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="071fa-220">Персональные</span><span class="sxs-lookup"><span data-stu-id="071fa-220">Personal</span></span></td>
<td align="left"><span data-ttu-id="071fa-221">Без политики автоматического применения</span><span class="sxs-lookup"><span data-stu-id="071fa-221">No auto-apply policy</span></span></td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a><span data-ttu-id="071fa-222">Создание меток и политик их автоматического применения</span><span class="sxs-lookup"><span data-stu-id="071fa-222">Create labels and auto-apply label policies</span></span>

<span data-ttu-id="071fa-223">Метки и политики создаются в Центре безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="071fa-223">Create labels and policies in the security center or the compliance center.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="071fa-224"><strong>Шаг</strong></span><span class="sxs-lookup"><span data-stu-id="071fa-224"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="071fa-225"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="071fa-225"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="071fa-226">Предоставление разрешений ответственным за обеспечение соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="071fa-226">Give permissions to members of your compliance team.</span></span></p></td>
<td align="left"><p><span data-ttu-id="071fa-p121">Ответственным за обеспечение соответствия требованиям лицам, которые будут создавать метки, необходимы разрешения на использование Центра безопасности и/или Центра соответствия требованиям. Перейдите в раздел "Разрешения" в Центре безопасности или Центра соответствия требованиям и внесите изменения в список участников группы "Администратор соответствия требованиям".</span><span class="sxs-lookup"><span data-stu-id="071fa-p121">Members of your compliance team who will create labels need permissions to use the security center and/or the compliance center. Go to Permissions in the security center or the compliance center and modify the members of the Compliance Administrator group.</span></span></p>
<p><span data-ttu-id="071fa-229">См. статью <a href="https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center">Предоставление пользователям доступа к Центру безопасности и/или Центру соответствия требованиям</a>.</span><span class="sxs-lookup"><span data-stu-id="071fa-229">See <a href="https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center">Give users access to the security center and/or the compliance center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="071fa-230">Создание меток хранения.</span><span class="sxs-lookup"><span data-stu-id="071fa-230">Create retention labels.</span></span></p></td>
<td align="left"><span data-ttu-id="071fa-231">Перейдите в раздел классификаций в Центре безопасности или Центре соответствия требованиям, выберите "Метки хранения" и создайте метки для вашей среды.</span><span class="sxs-lookup"><span data-stu-id="071fa-231">Go to Classifications in the Security center or the Compliance center, choose Retention labels, and create the labels for your environment.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="071fa-232">Создание политик автоматического применения меток</span><span class="sxs-lookup"><span data-stu-id="071fa-232">Create auto-apply policies for labels.</span></span></p></td>
<td align="left"><span data-ttu-id="071fa-p122">Перейдите в раздел классификаций в Центре безопасности или Центре соответствия требованиям, выберите пункт "Политики меток" и создайте политики для автоматического применения меток (обязательно в порядке приоритета).</span><span class="sxs-lookup"><span data-stu-id="071fa-p122">Go to Classification in security center or the compliance center, choose Label policies, and create the policies for auto-applying labels. Be sure to create these policies in the prioritized order.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="071fa-235">Ни рисунке ниже показано, как создать автоматическую метку "Данные клиента".</span><span class="sxs-lookup"><span data-stu-id="071fa-235">The following illustration shows how to create an auto-apply label for the Customer data label.</span></span>

![Создание и применение метки для данных клиента](../media/Apply-labels-to-personal-data-in-Office-365-image3.png)

<span data-ttu-id="071fa-237">На этом рисунке:</span><span class="sxs-lookup"><span data-stu-id="071fa-237">In the illustration:</span></span>

- <span data-ttu-id="071fa-238">Создается метка "Данные клиента".</span><span class="sxs-lookup"><span data-stu-id="071fa-238">The "Customer data" label is created.</span></span>

- <span data-ttu-id="071fa-239">Перечисляются типы конфиденциальной информации для соблюдения регламента GDPR: "Внутренний идентификационный номер гражданина Бельгии", "Номер кредитной карты", "Номер идентификационной карты гражданина Хорватии", "Национальный идентификационный номер гражданина Финляндии".</span><span class="sxs-lookup"><span data-stu-id="071fa-239">The desired sensitive information types for GDPR are listed: Belgium National Number, Credit Card Number, Croatia Identity Card Number, Finland National ID.</span></span>

- <span data-ttu-id="071fa-240">Создается политика автоматического применения, которая назначает метку "Данные клиента" всем файлам, включающим один из типов конфиденциальной информации, добавленных в политику.</span><span class="sxs-lookup"><span data-stu-id="071fa-240">Create an auto-apply policy assigns the label "Customer data" to any file that includes one of the sensitive information types that you add to the policy.</span></span>
