---
title: Сведения о политике предотвращения потери данных по умолчанию в Microsoft Teams (предварительный просмотр)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Сведения о политике предотвращения потери данных по умолчанию в Microsoft Teams
ms.openlocfilehash: 3992daf9431dbd87ed5e947a1e5a2b0acd20edce
ms.sourcegitcommit: 450661071e44854f0a0a92af648f76d907767b71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2021
ms.locfileid: "50826250"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a><span data-ttu-id="b58cf-103">Сведения о политике предотвращения потери данных по умолчанию в Microsoft Teams (предварительный просмотр)</span><span class="sxs-lookup"><span data-stu-id="b58cf-103">Learn about the default data loss prevention policy in Microsoft Teams (preview)</span></span>

<span data-ttu-id="b58cf-104">[Возможности по предотвращению](data-loss-prevention-policies.md) потери данных (DLP) расширены, включив сообщения чатов и каналов Microsoft Teams, включая сообщения частных каналов.</span><span class="sxs-lookup"><span data-stu-id="b58cf-104">[Data loss prevention](data-loss-prevention-policies.md) (DLP) capabilities have been extended to include Microsoft Teams chat and channel messages, including private channel messages.</span></span> <span data-ttu-id="b58cf-105">В рамках этого выпуска мы создали политику DLP по умолчанию для первых клиентов центра соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="b58cf-105">As a part of this release, we created a default DLP policy for first-time customers to Compliance center.</span></span>

## <a name="applies-to"></a><span data-ttu-id="b58cf-106">Область применения</span><span class="sxs-lookup"><span data-stu-id="b58cf-106">Applies to</span></span>

<span data-ttu-id="b58cf-107">Любой клиент, который имеет лицензию с одной или более ниже лицензий и имеет активных пользователей Teams</span><span class="sxs-lookup"><span data-stu-id="b58cf-107">Any tenant who is licensed with one or more of the below licenses and have active Teams users</span></span>
 
- <span data-ttu-id="b58cf-108">ME5,</span><span class="sxs-lookup"><span data-stu-id="b58cf-108">ME5,</span></span> 
- <span data-ttu-id="b58cf-109">MA5,</span><span class="sxs-lookup"><span data-stu-id="b58cf-109">MA5,</span></span> 
- <span data-ttu-id="b58cf-110">Соответствие требованиям E5/A5,</span><span class="sxs-lookup"><span data-stu-id="b58cf-110">E5/A5 Compliance,</span></span> 
- <span data-ttu-id="b58cf-111">IP+G,</span><span class="sxs-lookup"><span data-stu-id="b58cf-111">IP+G,</span></span> 
- <span data-ttu-id="b58cf-112">OE5,</span><span class="sxs-lookup"><span data-stu-id="b58cf-112">OE5,</span></span> 
- <span data-ttu-id="b58cf-113">O365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="b58cf-113">O365 Advanced Compliance</span></span> 
- <span data-ttu-id="b58cf-114">EMS E5</span><span class="sxs-lookup"><span data-stu-id="b58cf-114">EMS E5</span></span>


## <a name="what-does-the-default-policy-do"></a><span data-ttu-id="b58cf-115">Что делает политика по умолчанию?</span><span class="sxs-lookup"><span data-stu-id="b58cf-115">What does the default policy do?</span></span>

<span data-ttu-id="b58cf-116">Политика DLP по умолчанию отслеживает все номера кредитных карт, общие внутри организации и внешне.</span><span class="sxs-lookup"><span data-stu-id="b58cf-116">The default DLP policy tracks all the credit card numbers shared internally and externally to the organization.</span></span> <span data-ttu-id="b58cf-117">Эта политика по умолчанию для всех пользователей клиента.</span><span class="sxs-lookup"><span data-stu-id="b58cf-117">This policy is on by default for all users of the tenant.</span></span> <span data-ttu-id="b58cf-118">Он не создает никаких советов по политике для конечных пользователей, но создает событие Оповещения, а также вызывает сообщение с низкой степенью серьезности администратору (добавлено в политику).</span><span class="sxs-lookup"><span data-stu-id="b58cf-118">It does not generate any policy tips for end users but does generate an Alert event and also triggers a low severity email to the admin (added in the policy).</span></span> <span data-ttu-id="b58cf-119">Администратор может просматривать действия и изменять сведения о политиках, входя в центр соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="b58cf-119">Administrator can view the activities and edit the policies details by logging into the Compliance center.</span></span>

<span data-ttu-id="b58cf-120">Администраторы могут просматривать эту политику на странице [>](https://compliance.microsoft.com/compliancesettings) политики защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="b58cf-120">Admins can view this policy in the [Compliance center](https://compliance.microsoft.com/compliancesettings) > Data Loss prevention policies page.</span></span>


> [!div class="mx-imgBorder"]
> <span data-ttu-id="b58cf-121">![Политика DLP команд по умолчанию](../media/default-teams-dlp-policy.png)</span><span class="sxs-lookup"><span data-stu-id="b58cf-121">![default Teams DLP policy](../media/default-teams-dlp-policy.png)</span></span>

## <a name="edit-or-delete-the-default-policy"></a><span data-ttu-id="b58cf-122">Изменение или удаление политики по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b58cf-122">Edit or delete the default policy</span></span>

<span data-ttu-id="b58cf-123">Чтобы [изменить политику по умолчанию для улучшения](create-test-tune-dlp-policy.md#tune-a-dlp-policy)производительности или удалить ее, просто используйте учетную запись с разрешениями управления соответствием требованиям **DLP.**</span><span class="sxs-lookup"><span data-stu-id="b58cf-123">To [edit the default policy for better performance or to delete it](create-test-tune-dlp-policy.md#tune-a-dlp-policy), just use an account with **DLP Compliance Management** permissions.</span></span> <span data-ttu-id="b58cf-124">Дополнительные сведения см. в ["Разрешениях".](create-test-tune-dlp-policy.md#permissions)</span><span class="sxs-lookup"><span data-stu-id="b58cf-124">For more information, see, [Permissions](create-test-tune-dlp-policy.md#permissions).</span></span>

