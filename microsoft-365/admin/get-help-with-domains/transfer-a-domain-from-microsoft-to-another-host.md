---
title: Перенос домена из Майкрософт на другой узел
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'В этой статье приведены инструкции по переносу домена из Майкрософт в другой регистратор. '
ms.openlocfilehash: 1fb1fa50bd919bddb620a39d9edb46abb6710ba4
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645279"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a><span data-ttu-id="b55b1-103">Перенос домена из Майкрософт на другой узел</span><span class="sxs-lookup"><span data-stu-id="b55b1-103">Transfer a domain from Microsoft to another host</span></span>

<span data-ttu-id="b55b1-104">Вы не можете перенести домен Microsoft 365 в другой регистратор в течение 60 дней после приобретения домена от Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b55b1-104">You can't transfer a Microsoft 365 domain to another registrar for 60 days after you purchase the domain from Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="b55b1-105">Запрос _Whois_   показывает приобретенного регистратора доменных имен Майкрософт в качестве подстановочных доменов LLC.</span><span class="sxs-lookup"><span data-stu-id="b55b1-105">A _Whois_ query shows a Microsoft purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="b55b1-106">Тем не менее, обращение к корпорации Майкрософт следует учитывать в приобретенном домене Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b55b1-106">However, only Microsoft should be contacted regarding your Microsoft 365 purchased domain.</span></span>

<span data-ttu-id="b55b1-107">Выполните указанные ниже действия, чтобы получить код в Microsoft 365, а затем перейдите на другой веб-сайт регистратора доменных имен, чтобы настроить передачу имени домена новому регистратору.</span><span class="sxs-lookup"><span data-stu-id="b55b1-107">Follow these steps to get a code at Microsoft 365, and then go to the other domain registrar website to set up transferring your domain name to the new registrar.</span></span>

## <a name="transfer-a-domain"></a><span data-ttu-id="b55b1-108">Передача домена</span><span class="sxs-lookup"><span data-stu-id="b55b1-108">Transfer a domain</span></span>

1. <span data-ttu-id="b55b1-109">В центре администрирования перейдите в раздел  **Settings**   >  **домены**параметров.</span><span class="sxs-lookup"><span data-stu-id="b55b1-109">In the admin center, go to  **Settings** > **Domains**.</span></span>

2. <span data-ttu-id="b55b1-110">На странице **Domains (домены** ) выберите домен Microsoft 365, который требуется передать другому регистратору доменных имен, а затем выберите пункт **проверить работоспособность**.</span><span class="sxs-lookup"><span data-stu-id="b55b1-110">On the **Domains** page, select the Microsoft 365 domain that you want to transfer to another domain registrar, and then select **Check health**.</span></span>

3. <span data-ttu-id="b55b1-111">В верхней части страницы выберите пункт **передать домен**.</span><span class="sxs-lookup"><span data-stu-id="b55b1-111">At the top of the page, select **Transfer domain**.</span></span>

4. <span data-ttu-id="b55b1-112">На странице **Выбор места для переноса домена** выберите **другой регистратор**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b55b1-112">On the **Choose where to transfer your domain** page, select **A different registrar**, and then click **Next**.</span></span>

5. <span data-ttu-id="b55b1-113">На странице " **разблокировка передачи домена** " выберите команду \*\*разблокировать передачу для <_домене_ > \*\*, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b55b1-113">On the **Unlock domain transfer** page, select **Unlock transfer for <_your domain_>**, and then select **Next**.</span></span>

6. <span data-ttu-id="b55b1-114">Проверьте контактную информацию о передаче домена, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b55b1-114">Check your domain transfer contact information, and then select **Next**.</span></span>

7. <span data-ttu-id="b55b1-115">Скопируйте код авторизации и подождите около 30 минут, пока состояние передачи домена изменится на " **разблокировано для переноса** " на вкладке " **Регистрация** ", прежде чем переходить к дальнейшим действиям.</span><span class="sxs-lookup"><span data-stu-id="b55b1-115">Copy the authorization code and wait about 30 minutes for your domain transfer status to change to **Unlocked for transfer** on the **Registration** tab before you proceed with next steps.</span></span>

8. <span data-ttu-id="b55b1-116">Перейдите на веб-сайт регистратора доменных имен, который будет использоваться для управления доменным именем.</span><span class="sxs-lookup"><span data-stu-id="b55b1-116">Go to the website of the domain registrar you want to manage your domain name going forward.</span></span> <span data-ttu-id="b55b1-117">Следуйте указаниям по переносу домена (Поиск справки на веб-сайте).</span><span class="sxs-lookup"><span data-stu-id="b55b1-117">Follow directions for transferring a domain (search for help on their website).</span></span> <span data-ttu-id="b55b1-118">Обычно это означает оплату передачи и предоставление Аускоде новому регистратору, чтобы они могли начать передачу.</span><span class="sxs-lookup"><span data-stu-id="b55b1-118">This usually means paying transfer fees and giving the Authcode to the new registrar so they can initiate the transfer.</span></span> <span data-ttu-id="b55b1-119">Корпорация Майкрософт будет по электронной почте подтвердить, что мы получили запрос на перемещение, а домен будет переноситься в течение 5 дней.</span><span class="sxs-lookup"><span data-stu-id="b55b1-119">Microsoft will email you to confirm we’ve received the transfer request, and the domain will transfer within 5 days.</span></span>

    <span data-ttu-id="b55b1-120">Вкладку **Регистрация** кода авторизации можно найти на странице  **Domains (домены** ) в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b55b1-120">You can find the authorization code **Registration** tab on the  **Domains** page in Microsoft 365.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="b55b1-121">для доменов Великобритании требуется другая процедура.</span><span class="sxs-lookup"><span data-stu-id="b55b1-121">.uk domains require a different procedure.</span></span> <span data-ttu-id="b55b1-122">Обратитесь в службу поддержки Майкрософт и запросите **метку IP-адресов** , чтобы найти регистратор, который будет использоваться для управления доменом.</span><span class="sxs-lookup"><span data-stu-id="b55b1-122">Contact Microsoft Support and request an **IPS Tag change** to match the registrar you want to manage your domain going forward.</span></span> <span data-ttu-id="b55b1-123">После изменения тега домен немедленно переносится на новый регистратор.</span><span class="sxs-lookup"><span data-stu-id="b55b1-123">Once the tag changes, the domain immediately transfers to the new registrar.</span></span> <span data-ttu-id="b55b1-124">Затем необходимо будет работать с новым регистратором, чтобы завершить передачу, вероятность оплаты передачи и добавление перенесенного домена в свою учетную запись с новым регистратором.</span><span class="sxs-lookup"><span data-stu-id="b55b1-124">You will then need to work with the new registrar to complete the transfer, likely paying transfer fees and adding the transferred domain to your account with your new registrar.</span></span>

9. <span data-ttu-id="b55b1-125">После завершения переноса вы обновите свой домен в новом регистраторе доменных имен.</span><span class="sxs-lookup"><span data-stu-id="b55b1-125">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>

10. <span data-ttu-id="b55b1-126">Чтобы завершить процесс, вернитесь на страницу **домены** в центре администрирования, а затем выберите пункт  **полная передача домена**.</span><span class="sxs-lookup"><span data-stu-id="b55b1-126">To finish the process, go back to the **Domains** page in the admin center, and then select  **Complete domain transfer**.</span></span> <span data-ttu-id="b55b1-127">После этого домен будет отмечен как не приобретенный в Microsoft 365, и будет отключена подписка на домен.</span><span class="sxs-lookup"><span data-stu-id="b55b1-127">This will mark the domain as no longer purchased from Microsoft 365, and will disable the domain subscription.</span></span> <span data-ttu-id="b55b1-128">Он не удалит домен из клиента и не повлияет на существующих пользователей и почтовые ящики в домене.</span><span class="sxs-lookup"><span data-stu-id="b55b1-128">It will not remove the domain from the tenant, and will not affect existing users and mailboxes on the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="b55b1-129">Приобретенные домены Microsoft 365 не подходят для серверов доменных имен и не переносят домен между организациями Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b55b1-129">Microsoft 365 purchased domains are not eligible for nameserver changes or transferring the domain between Microsoft 365 organizations.</span></span> <span data-ttu-id="b55b1-130">Если это необходимо, необходимо передать регистрацию домена другому регистратору.</span><span class="sxs-lookup"><span data-stu-id="b55b1-130">If either of these are required, the domain registration must be transferred to another registrar.</span></span>
