---
title: Сведения о политике защиты от потери данных по умолчанию в Microsoft Teams (предварительная версия)
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
ms.openlocfilehash: c6b7413fdd4017fe1211e804c00a2e9c0684468d
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149122"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a><span data-ttu-id="4507e-103">Сведения о политике защиты от потери данных по умолчанию в Microsoft Teams (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="4507e-103">Learn about the default data loss prevention policy in Microsoft Teams (preview)</span></span>

<span data-ttu-id="4507e-104">[Возможности предотвращения](dlp-learn-about-dlp.md) потери данных были расширены для Microsoft Teams сообщений чата и каналов, включая сообщения частных каналов.</span><span class="sxs-lookup"><span data-stu-id="4507e-104">[Data loss prevention](dlp-learn-about-dlp.md) capabilities have been extended to include Microsoft Teams chat and channel messages, including private channel messages.</span></span> <span data-ttu-id="4507e-105">В рамках этого выпуска мы создали политику DLP по умолчанию для Microsoft Teams для первых клиентов центра соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="4507e-105">As a part of this release, we created a default DLP policy for Microsoft Teams for first-time customers to Compliance center.</span></span>

## <a name="applies-to"></a><span data-ttu-id="4507e-106">Область применения</span><span class="sxs-lookup"><span data-stu-id="4507e-106">Applies to</span></span>

<span data-ttu-id="4507e-107">Любой клиент, который имеет одну или несколько лицензий ниже и имеет активных Teams пользователей</span><span class="sxs-lookup"><span data-stu-id="4507e-107">Any tenant who is licensed with one or more of the below licenses and have active Teams users</span></span>
 
- <span data-ttu-id="4507e-108">ME5,</span><span class="sxs-lookup"><span data-stu-id="4507e-108">ME5,</span></span> 
- <span data-ttu-id="4507e-109">MA5,</span><span class="sxs-lookup"><span data-stu-id="4507e-109">MA5,</span></span> 
- <span data-ttu-id="4507e-110">Соответствие требованиям E5/A5,</span><span class="sxs-lookup"><span data-stu-id="4507e-110">E5/A5 Compliance,</span></span> 
- <span data-ttu-id="4507e-111">IP+G,</span><span class="sxs-lookup"><span data-stu-id="4507e-111">IP+G,</span></span> 
- <span data-ttu-id="4507e-112">OE5,</span><span class="sxs-lookup"><span data-stu-id="4507e-112">OE5,</span></span> 
- <span data-ttu-id="4507e-113">O365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="4507e-113">O365 Advanced Compliance</span></span> 
- <span data-ttu-id="4507e-114">EMS E5</span><span class="sxs-lookup"><span data-stu-id="4507e-114">EMS E5</span></span>


## <a name="what-does-the-default-policy-do"></a><span data-ttu-id="4507e-115">Что делает политика по умолчанию?</span><span class="sxs-lookup"><span data-stu-id="4507e-115">What does the default policy do?</span></span>

<span data-ttu-id="4507e-116">Политика DLP по умолчанию для Teams отслеживает все номера кредитных карт, общие внутри организации и внешне.</span><span class="sxs-lookup"><span data-stu-id="4507e-116">The default DLP policy for Teams tracks all the credit card numbers shared internally and externally to the organization.</span></span> <span data-ttu-id="4507e-117">Эта политика по умолчанию для всех пользователей клиента.</span><span class="sxs-lookup"><span data-stu-id="4507e-117">This policy is on by default for all users of the tenant.</span></span> <span data-ttu-id="4507e-118">Он не создает никаких советов по политике для конечных пользователей, но создает событие Оповещения, а также вызывает сообщение с низкой степенью серьезности администратору (добавлено в политику).</span><span class="sxs-lookup"><span data-stu-id="4507e-118">It does not generate any policy tips for end users but does generate an Alert event and also triggers a low severity email to the admin (added in the policy).</span></span> <span data-ttu-id="4507e-119">Администратор может просматривать действия и изменять сведения о политиках, входя в центр соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="4507e-119">Administrator can view the activities and edit the policies details by logging into the Compliance center.</span></span>

<span data-ttu-id="4507e-120">Администраторы могут просматривать эту политику на странице [>](https://compliance.microsoft.com/compliancesettings) политики защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="4507e-120">Admins can view this policy in the [Compliance center](https://compliance.microsoft.com/compliancesettings) > Data Loss prevention policies page.</span></span>


> [!div class="mx-imgBorder"]
> <span data-ttu-id="4507e-121">![политика Teams DLP](../media/default-teams-dlp-policy.png)</span><span class="sxs-lookup"><span data-stu-id="4507e-121">![default Teams DLP policy](../media/default-teams-dlp-policy.png)</span></span>

## <a name="edit-or-delete-the-default-policy"></a><span data-ttu-id="4507e-122">Изменение или удаление политики по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4507e-122">Edit or delete the default policy</span></span>

<span data-ttu-id="4507e-123">Чтобы [изменить политику по умолчанию для улучшения](create-test-tune-dlp-policy.md#tune-a-dlp-policy)производительности или удалить ее, просто используйте учетную запись с разрешениями управления соответствием требованиям **DLP.**</span><span class="sxs-lookup"><span data-stu-id="4507e-123">To [edit the default policy for better performance or to delete it](create-test-tune-dlp-policy.md#tune-a-dlp-policy), just use an account with **DLP Compliance Management** permissions.</span></span> <span data-ttu-id="4507e-124">Дополнительные сведения см. в ["Разрешениях".](create-test-tune-dlp-policy.md#permissions)</span><span class="sxs-lookup"><span data-stu-id="4507e-124">For more information, see, [Permissions](create-test-tune-dlp-policy.md#permissions).</span></span>

