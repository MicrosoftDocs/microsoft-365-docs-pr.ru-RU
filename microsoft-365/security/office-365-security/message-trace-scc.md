---
title: Трассировка сообщений на Microsoft 365 Defender портале
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут использовать ссылку трассировки сообщений на портале Microsoft 365 Defender, чтобы узнать, что произошло с сообщениями.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7b6f7b12086e46c6ad93b60e8c510ea533815a1
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108131"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="7a687-103">Трассировка сообщений на Microsoft 365 Defender портале</span><span class="sxs-lookup"><span data-stu-id="7a687-103">Message trace in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7a687-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="7a687-104">**Applies to**</span></span>
- [<span data-ttu-id="7a687-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7a687-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7a687-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="7a687-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="7a687-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7a687-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="7a687-108">Трассировка сообщений на портале Microsoft 365 Defender сообщений электронной почты во время их перемещения по Exchange Online организации.</span><span class="sxs-lookup"><span data-stu-id="7a687-108">Message trace in the Microsoft 365 Defender portal follows email messages as they travel through your Exchange Online organization.</span></span> <span data-ttu-id="7a687-109">Вы можете определить, было ли сообщение получено, отклонено, отложено или доставлено службой.</span><span class="sxs-lookup"><span data-stu-id="7a687-109">You can determine if a message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="7a687-110">В нем также показано, какие действия были приняты в сообщении до его окончательного состояния.</span><span class="sxs-lookup"><span data-stu-id="7a687-110">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="7a687-111">Вы можете использовать сведения из трассировки сообщений, чтобы эффективно отвечать на вопросы пользователей о том, что произошло с сообщениями, устранять проблемы с потоком почты и проверять изменения политики.</span><span class="sxs-lookup"><span data-stu-id="7a687-111">You can use the information from message trace to efficiently answer user questions about what happened to messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

> [!NOTE]
> <span data-ttu-id="7a687-112">Трассировка сообщений на Microsoft 365 Defender портале — это просто пропуск трассировки сообщения в центре Exchange администрирования.</span><span class="sxs-lookup"><span data-stu-id="7a687-112">Message trace in the Microsoft 365 Defender portal is just a pass through to Message trace in the Exchange admin center.</span></span> <span data-ttu-id="7a687-113">Дополнительные сведения см. в сообщении в [центре администрирования Exchange.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)</span><span class="sxs-lookup"><span data-stu-id="7a687-113">For more information, see [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7a687-114">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="7a687-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7a687-115">Для использования трассировки сообщений  необходимо быть  членом групп  ролей в области управления **организацией,** управления соответствием требованиям или службы поддержки в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7a687-115">You need to be a member of the **Organization Management**, **Compliance Management** or **Help Desk** role groups in **Exchange Online** to use message trace.</span></span> <span data-ttu-id="7a687-116">Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="7a687-116">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="7a687-117">**Примечание.** Членство в соответствующей Azure Active Directory роли в Центр администрирования Microsoft 365 предоставляет пользователям необходимые  разрешения и разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7a687-117">**Notes**: Membership in the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="7a687-118">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="7a687-118">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="7a687-119">Максимальное количество сообщений, отображаемых в результатах трассировки сообщений, зависит от выбранного типа отчета (подробнее см. раздел [Выберите](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) тип отчета).</span><span class="sxs-lookup"><span data-stu-id="7a687-119">The maximum number of messages that are displayed in the results of a message trace depends on the report type you selected (see the [Choose report type](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) section for details).</span></span> <span data-ttu-id="7a687-120">Комлет [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) в Exchange Online PowerShell или автономный EOP PowerShell возвращает все сообщения в результатах.</span><span class="sxs-lookup"><span data-stu-id="7a687-120">The [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) cmdlet in Exchange Online PowerShell or standalone EOP PowerShell returns all messages in the results.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="7a687-121">Трассировка открытого сообщения</span><span class="sxs-lookup"><span data-stu-id="7a687-121">Open message trace</span></span>

<span data-ttu-id="7a687-122">На портале Microsoft 365 Defender () перейдите к электронной почте <https://security.microsoft.com> **&** \> **совместной Exchange сообщений**.</span><span class="sxs-lookup"><span data-stu-id="7a687-122">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration** \> **Exchange message trace**.</span></span> <span data-ttu-id="7a687-123">Или, чтобы перейти непосредственно на страницу трассировки сообщений, используйте <https://admin.exchange.microsoft.com/#/messagetrace> .</span><span class="sxs-lookup"><span data-stu-id="7a687-123">Or, to go directly to the message trace page, use <https://admin.exchange.microsoft.com/#/messagetrace>.</span></span>

<span data-ttu-id="7a687-124">На этом этапе откроется трассировка сообщений в EAC.</span><span class="sxs-lookup"><span data-stu-id="7a687-124">At this point, message trace in the EAC opens.</span></span> <span data-ttu-id="7a687-125">Дополнительные сведения см. в сообщении в [центре администрирования Exchange.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)</span><span class="sxs-lookup"><span data-stu-id="7a687-125">For more information, see [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span></span>
