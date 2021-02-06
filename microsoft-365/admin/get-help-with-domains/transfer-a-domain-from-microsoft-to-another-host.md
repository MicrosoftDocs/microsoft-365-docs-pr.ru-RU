---
title: Перенос домена из Майкрософт на другой сайт
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'Здесь вы найдете действия по переносу домена из Майкрософт другому регистратору. '
ms.openlocfilehash: f34e9733ab53c8bdc6f4432c96e6232ecc26ee06
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126351"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a><span data-ttu-id="53e1f-103">Перенос домена из Майкрософт на другой сайт</span><span class="sxs-lookup"><span data-stu-id="53e1f-103">Transfer a domain from Microsoft to another host</span></span>

<span data-ttu-id="53e1f-104">Вы не можете передать домен Microsoft 365 другому регистратору в течение 60 дней после приобретения домена у корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="53e1f-104">You can't transfer a Microsoft 365 domain to another registrar for 60 days after you purchase the domain from Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="53e1f-105">Запрос _Whois_ показывает приобретенного регистратора доменов Майкрософт как   Wild West Domains LLC.</span><span class="sxs-lookup"><span data-stu-id="53e1f-105">A _Whois_ query shows a Microsoft purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="53e1f-106">Однако в отношении вашего приобретенного домена Microsoft 365 следует связаться только с корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="53e1f-106">However, only Microsoft should be contacted regarding your Microsoft 365 purchased domain.</span></span>

<span data-ttu-id="53e1f-107">Выполните следующие действия, чтобы получить код в Microsoft 365, а затем перейдите на другой веб-сайт регистратора доменных имен, чтобы настроить передачу доменного имени новому регистратору.</span><span class="sxs-lookup"><span data-stu-id="53e1f-107">Follow these steps to get a code at Microsoft 365, and then go to the other domain registrar website to set up transferring your domain name to the new registrar.</span></span>

## <a name="transfer-a-domain"></a><span data-ttu-id="53e1f-108">Передача домена</span><span class="sxs-lookup"><span data-stu-id="53e1f-108">Transfer a domain</span></span>

1. <span data-ttu-id="53e1f-109">В Центре администрирования перейдите к   \*\*\*\*   >  **доменам параметров.**</span><span class="sxs-lookup"><span data-stu-id="53e1f-109">In the admin center, go to   **Settings** > **Domains**.</span></span>

2. <span data-ttu-id="53e1f-110">На странице **"Домены"** выберите домен Microsoft 365, который нужно передать другому регистратору доменных имен, а затем выберите "Проверить **состояние".**</span><span class="sxs-lookup"><span data-stu-id="53e1f-110">On the **Domains** page, select the Microsoft 365 domain that you want to transfer to another domain registrar, and then select **Check health**.</span></span>

3. <span data-ttu-id="53e1f-111">В верхней части страницы выберите **"Перенос домена".**</span><span class="sxs-lookup"><span data-stu-id="53e1f-111">At the top of the page, select **Transfer domain**.</span></span>

4. <span data-ttu-id="53e1f-112">На странице **"Выбор места** переноса домена" выберите другого **регистратора** и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="53e1f-112">On the **Choose where to transfer your domain** page, select **A different registrar**, and then click **Next**.</span></span>

5. <span data-ttu-id="53e1f-113">На странице **"Разблокировка передачи** домена" **>** выберите разблокировку для <домена, а затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="53e1f-113">On the **Unlock domain transfer** page, select **Unlock transfer for <_your domain_>**, and then select **Next**.</span></span>

6. <span data-ttu-id="53e1f-114">Проверьте контактные данные о передаче домена и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="53e1f-114">Check your domain transfer contact information, and then select **Next**.</span></span>

7. <span data-ttu-id="53e1f-115">Скопируйте код авторизации и подождите около 30 минут, пока состояние передачи домена изменится на **"Разблокировано** для передачи" на вкладке **"Регистрация",** прежде чем приступить к следующим шагам.</span><span class="sxs-lookup"><span data-stu-id="53e1f-115">Copy the authorization code and wait about 30 minutes for your domain transfer status to change to **Unlocked for transfer** on the **Registration** tab before you proceed with next steps.</span></span>

8. <span data-ttu-id="53e1f-116">Перейдите на веб-сайт регистратора доменных имен, который будет управлять доменным именем в будущем.</span><span class="sxs-lookup"><span data-stu-id="53e1f-116">Go to the website of the domain registrar you want to manage your domain name going forward.</span></span> <span data-ttu-id="53e1f-117">Следуйте указаниям по переносу домена (выполните поиск справки на веб-сайте).</span><span class="sxs-lookup"><span data-stu-id="53e1f-117">Follow directions for transferring a domain (search for help on their website).</span></span> <span data-ttu-id="53e1f-118">Обычно это означает оплату платы за передачу и предоставление Authcode новому регистратору, чтобы он инициирует передачу данных.</span><span class="sxs-lookup"><span data-stu-id="53e1f-118">This usually means paying transfer fees and giving the Authcode to the new registrar so they can initiate the transfer.</span></span> <span data-ttu-id="53e1f-119">Корпорация Майкрософт напишите вам по электронной почте, чтобы подтвердить, что мы получили запрос на передачу данных, и домен будет передаваться в течение 5 дней.</span><span class="sxs-lookup"><span data-stu-id="53e1f-119">Microsoft will email you to confirm we’ve received the transfer request, and the domain will transfer within 5 days.</span></span>

    <span data-ttu-id="53e1f-120">Вкладку "Регистрация **кода** авторизации" можно найти на странице  **"Домены"** в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="53e1f-120">You can find the authorization code **Registration** tab on the  **Domains** page in Microsoft 365.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="53e1f-121">Для доменов .uk требуется другая процедура.</span><span class="sxs-lookup"><span data-stu-id="53e1f-121">.uk domains require a different procedure.</span></span> <span data-ttu-id="53e1f-122">Обратитесь в службу поддержки Майкрософт и запросите **изменение тега IPS** в соответствие с регистратором, который будет управлять доменом в будущем.</span><span class="sxs-lookup"><span data-stu-id="53e1f-122">Contact Microsoft Support and request an **IPS Tag change** to match the registrar you want to manage your domain going forward.</span></span> <span data-ttu-id="53e1f-123">После изменения тега домен немедленно передается новому регистратору.</span><span class="sxs-lookup"><span data-stu-id="53e1f-123">Once the tag changes, the domain immediately transfers to the new registrar.</span></span> <span data-ttu-id="53e1f-124">После этого вам потребуется поработать с новым регистратором, чтобы завершить передачу данных, в связи с чем, скорее всего, вы будете платить за передачу данных и добавить перенесенный домен в свою учетную запись с помощью нового регистратора.</span><span class="sxs-lookup"><span data-stu-id="53e1f-124">You will then need to work with the new registrar to complete the transfer, likely paying transfer fees and adding the transferred domain to your account with your new registrar.</span></span>

9. <span data-ttu-id="53e1f-125">После завершения переноса вы обновите свой домен у нового регистратора доменных имен.</span><span class="sxs-lookup"><span data-stu-id="53e1f-125">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>

10. <span data-ttu-id="53e1f-126">Чтобы завершить процесс, перейдите  на страницу "Домены" в Центре администрирования и выберите "Полная передача  **домена".**</span><span class="sxs-lookup"><span data-stu-id="53e1f-126">To finish the process, go back to the **Domains** page in the admin center, and then select  **Complete domain transfer**.</span></span> <span data-ttu-id="53e1f-127">Это пометит домен как больше не приобретенный у Microsoft 365 и отключит подписку на домен.</span><span class="sxs-lookup"><span data-stu-id="53e1f-127">This will mark the domain as no longer purchased from Microsoft 365, and will disable the domain subscription.</span></span> <span data-ttu-id="53e1f-128">Он не удаляет домен из клиента и не влияет на существующих пользователей и почтовые ящики в домене.</span><span class="sxs-lookup"><span data-stu-id="53e1f-128">It will not remove the domain from the tenant, and will not affect existing users and mailboxes on the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="53e1f-129">Приобретенные домены Microsoft 365 не имеют права на изменение доменных имен или передачу домена между организациями Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="53e1f-129">Microsoft 365 purchased domains are not eligible for nameserver changes or transferring the domain between Microsoft 365 organizations.</span></span> <span data-ttu-id="53e1f-130">Если это необходимо, регистрация домена должна быть передана другому регистратору.</span><span class="sxs-lookup"><span data-stu-id="53e1f-130">If either of these are required, the domain registration must be transferred to another registrar.</span></span>
