---
title: Предварительная версия функций защиты от угроз Майкрософт
description: Сведения о новых возможностях Microsoft 365 Security
keywords: Предварительная версия, новая, m365 безопасность, безопасность, 365, возможности
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b0703aa14bee3d14d1c3ff4fe46ea9d72de73ce2
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515871"
---
# <a name="microsoft-threat-protection-preview-features"></a><span data-ttu-id="f026d-104">Функции предварительной версии Microsoft Threat protection</span><span class="sxs-lookup"><span data-stu-id="f026d-104">Microsoft Threat Protection preview features</span></span>

<span data-ttu-id="f026d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f026d-105">**Applies to:**</span></span>
- <span data-ttu-id="f026d-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="f026d-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="f026d-107">Служба Microsoft Threat Protection постоянно обновляется с добавлением новых функций и возможностей.</span><span class="sxs-lookup"><span data-stu-id="f026d-107">The Microsoft Threat Protection service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="f026d-108">Узнайте о новых возможностях в выпуске ознакомительной версии Microsoft Threat Protection, а также в первую очередь для последующей работы, включив ознакомительную версию.</span><span class="sxs-lookup"><span data-stu-id="f026d-108">Learn about new features in the Microsoft Threat Protection preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="f026d-109">Дополнительные сведения о новых возможностях, которые обычно доступны, см. в статье [Новые возможности системы защиты от угроз (Майкрософт)](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="f026d-109">For more information on new capabilities that are generally available, see [What's new in Microsoft Threat Protection](whats-new.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="f026d-110">Включение предварительных функций</span><span class="sxs-lookup"><span data-stu-id="f026d-110">Turn on preview features</span></span>
<span data-ttu-id="f026d-111">Вы получите доступ к будущим функциям, которые помогут вам повысить эффективность работы, прежде чем они будут доступны.</span><span class="sxs-lookup"><span data-stu-id="f026d-111">You'll have access to upcoming features which you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="f026d-112">Включите параметр Предварительный просмотр, чтобы попытаться выполнить будущие функции.</span><span class="sxs-lookup"><span data-stu-id="f026d-112">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="f026d-113">В области навигации выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="f026d-113">In the navigation pane, select **Settings**.</span></span>

2. <span data-ttu-id="f026d-114">Выберите **Защита от угроз Майкрософт**.</span><span class="sxs-lookup"><span data-stu-id="f026d-114">Select **Microsoft Threat Protection**.</span></span>


3. <span data-ttu-id="f026d-115">Нажмите кнопку **Предварительный просмотр компонентов**  >  , чтобы**включить предварительные функции**.</span><span class="sxs-lookup"><span data-stu-id="f026d-115">Select **Preview features** > **Turn on preview features**.</span></span> 

3. <span data-ttu-id="f026d-116">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f026d-116">Select **Save**.</span></span>

<span data-ttu-id="f026d-117">Вы узнаете, что функции предварительного просмотра включены, когда вы видите флажок **включить предварительный просмотр компонентов** .</span><span class="sxs-lookup"><span data-stu-id="f026d-117">You'll know you have preview features turned on when you see that the **Turn on preview features** check box is selected.</span></span> 

## <a name="preview-features"></a><span data-ttu-id="f026d-118">Предварительные функции</span><span class="sxs-lookup"><span data-stu-id="f026d-118">Preview features</span></span>
<span data-ttu-id="f026d-119">В настоящее время доступны следующие функции и расширения для предварительной версии:</span><span class="sxs-lookup"><span data-stu-id="f026d-119">The following features and enhancements are currently available on preview:</span></span>

- <span data-ttu-id="f026d-120">**[Таблицы удостоверений и приложений](advanced-hunting-schema-tables.md)** — получение представления о событиях проверки подлинности, запросах Active Directory и действиях, связанных с приложениями, с таблицами [идентитилогоневентс](advanced-hunting-identitylogonevents-table.md), [идентитикуеревентс](advanced-hunting-identityqueryevents-table.md)и [аппфиливентс](advanced-hunting-appfileevents-table.md) в схеме расширенного поискового запроса.</span><span class="sxs-lookup"><span data-stu-id="f026d-120">**[Identity and app tables](advanced-hunting-schema-tables.md)** — get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>

- <span data-ttu-id="f026d-121">**[Таблица емаилпостделиверевентс](advanced-hunting-emailpostdeliveryevents-table.md)** — эта таблица используется для создания [расширенных](advanced-hunting-overview.md) запросов поиска, которые проверяют действия, выполненные на сообщениях после их доставки в почтовые ящики получателей.</span><span class="sxs-lookup"><span data-stu-id="f026d-121">**[EmailPostDeliveryEvents table](advanced-hunting-emailpostdeliveryevents-table.md)** — use this table to create [advanced hunting](advanced-hunting-overview.md) queries that check for actions taken on emails after they have been delivered to recipient mailboxes.</span></span>

- <span data-ttu-id="f026d-122">**[Функция филепрофиле ()](advanced-hunting-fileprofile-function.md)** — используется в [расширенных](advanced-hunting-overview.md) запросах на поиск для включения исчерпывающей информации о файле.</span><span class="sxs-lookup"><span data-stu-id="f026d-122">**[FileProfile() function](advanced-hunting-fileprofile-function.md)** — use in your [advanced hunting](advanced-hunting-overview.md) queries to incorporate comprehensive file information.</span></span>
