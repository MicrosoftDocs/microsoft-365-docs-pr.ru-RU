---
title: Настройка защиты от фишинга
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Узнайте, как настроить защиту от фишинга.
ms.openlocfilehash: f3a1399c8a6a51c7b14af7ffea8fbaea39cd1541
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702891"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="73bc0-103">Настройка защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="73bc0-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="73bc0-104">Фишинг — это вредоносная атака, при которой сообщение электронной почты выглядит так, будто оно было отправлено из знакомого источника, но оно пытается получить вашу личную информацию.</span><span class="sxs-lookup"><span data-stu-id="73bc0-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="73bc0-105">По умолчанию Microsoft 365 включает некоторые средства защиты от фишинга, но вы можете повысить эту защиту, уточнив параметры.</span><span class="sxs-lookup"><span data-stu-id="73bc0-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="73bc0-106">Давайте рассмотрим.</span><span class="sxs-lookup"><span data-stu-id="73bc0-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="73bc0-107">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="73bc0-107">Try it!</span></span>

1. <span data-ttu-id="73bc0-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com) , select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="73bc0-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="73bc0-109">Выберите **политику по умолчанию,** чтобы уточнить ее.</span><span class="sxs-lookup"><span data-stu-id="73bc0-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="73bc0-110">В разделе **"Под вопросом"** выберите "Изменить". </span><span class="sxs-lookup"><span data-stu-id="73bc0-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="73bc0-111">Перейдите **в список "Добавить домены",** чтобы защитить домены, и выберите его, чтобы автоматически включить собственные домены.</span><span class="sxs-lookup"><span data-stu-id="73bc0-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="73bc0-112">Перейдите **в "Действия",** откройте drop-down, если сообщение отправлено ненастоящем пользователем, и выберите нужное действие. </span><span class="sxs-lookup"><span data-stu-id="73bc0-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="73bc0-113">Откройте drop-down, **если сообщение отправлено** с помощью ненастоящем домене и выберите нужное действие.</span><span class="sxs-lookup"><span data-stu-id="73bc0-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="73bc0-114">Select **Turn on impersonation safety tips**.</span><span class="sxs-lookup"><span data-stu-id="73bc0-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="73bc0-115">Выберите, следует ли предоставлять пользователям советы, когда система обнаруживает нестандартных пользователей, домены или необычные символы.</span><span class="sxs-lookup"><span data-stu-id="73bc0-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="73bc0-116">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="73bc0-116">Select **Save**.</span></span>
1. <span data-ttu-id="73bc0-117">Выберите **"Аналитика почтовых** ящиков" и убедитесь, что она включена.</span><span class="sxs-lookup"><span data-stu-id="73bc0-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="73bc0-118">Это позволяет более эффективно использовать электронную почту, изучив шаблоны использования.</span><span class="sxs-lookup"><span data-stu-id="73bc0-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="73bc0-119">Choose **Add trusted senders and domains**.</span><span class="sxs-lookup"><span data-stu-id="73bc0-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="73bc0-120">Здесь вы можете добавить адреса электронной почты или домены, которые не следует классифицировать как подмайные.</span><span class="sxs-lookup"><span data-stu-id="73bc0-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="73bc0-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span><span class="sxs-lookup"><span data-stu-id="73bc0-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="73bc0-122">Теперь ваша организация лучше защищена от фишинговых угроз.</span><span class="sxs-lookup"><span data-stu-id="73bc0-122">Your organization now has better protection from phishing threats.</span></span>