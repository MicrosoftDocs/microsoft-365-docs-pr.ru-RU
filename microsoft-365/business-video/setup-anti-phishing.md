---
title: Настройка защиты от фишинга
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
ms.openlocfilehash: 32494eda4496d99e5e5f4def213ba7876f6c3183
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580418"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="a1043-103">Настройка защиты от фишинга</span><span class="sxs-lookup"><span data-stu-id="a1043-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="a1043-104">Фишинг — это вредоносная атака, при которой сообщение электронной почты выглядит так, как будто оно было отправлено из знакомого источника, но оно пытается собрать личные данные.</span><span class="sxs-lookup"><span data-stu-id="a1043-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="a1043-105">По умолчанию Microsoft 365 включает некоторые средства защиты от фишинга, но эту защиту можно повысить за счет уточнения параметров.</span><span class="sxs-lookup"><span data-stu-id="a1043-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="a1043-106">Давайте посмотрим.</span><span class="sxs-lookup"><span data-stu-id="a1043-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="a1043-107">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="a1043-107">Try it!</span></span>

1. <span data-ttu-id="a1043-108">В центре администрирования выберите безопасность, управление [https://admin.microsoft.com](https://admin.microsoft.com) угрозами , **политика**, **затем ATP anti-phishing**.  </span><span class="sxs-lookup"><span data-stu-id="a1043-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="a1043-109">Выберите **политику по умолчанию** для ее уточнения.</span><span class="sxs-lookup"><span data-stu-id="a1043-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="a1043-110">В разделе **Impersonation** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a1043-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="a1043-111">Перейдите **к добавлению доменов,** чтобы защитить и выбрать тоггл, чтобы автоматически включить домены, которые у вас есть.</span><span class="sxs-lookup"><span data-stu-id="a1043-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="a1043-112">Перейдите **к действиям,** откройте drop-down **Если** электронная почта отправляется безымяенным пользователем, и выберите нужное действие.</span><span class="sxs-lookup"><span data-stu-id="a1043-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="a1043-113">Откройте drop-down **Если электронная почта** отправляется с помощью обезличенных доменов и выберите нужное действие.</span><span class="sxs-lookup"><span data-stu-id="a1043-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="a1043-114">Выберите **Подсказки по безопасности для обезличения.**</span><span class="sxs-lookup"><span data-stu-id="a1043-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="a1043-115">Выберите, следует ли предоставлять пользователям советы, если система обнаруживает обезличенных пользователей, домены или необычные символы.</span><span class="sxs-lookup"><span data-stu-id="a1043-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="a1043-116">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a1043-116">Select **Save**.</span></span>
1. <span data-ttu-id="a1043-117">Выберите **разведданные почтовых ящиков** и убедитесь, что он включен.</span><span class="sxs-lookup"><span data-stu-id="a1043-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="a1043-118">Это позволяет вашей электронной почте более эффективно использовать шаблоны использования.</span><span class="sxs-lookup"><span data-stu-id="a1043-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="a1043-119">Выберите **Добавление надежных отправителей и доменов.**</span><span class="sxs-lookup"><span data-stu-id="a1043-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="a1043-120">Здесь можно добавить адреса электронной почты или домены, которые не следует классифицировать как обезличенные.</span><span class="sxs-lookup"><span data-stu-id="a1043-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="a1043-121">Выберите **Обзор параметров,** убедитесь, что все правильно, выберите **Сохранить**, а затем **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="a1043-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="a1043-122">Теперь ваша организация лучше защищена от фишинговых угроз.</span><span class="sxs-lookup"><span data-stu-id="a1043-122">Your organization now has better protection from phishing threats.</span></span>