---
title: Перенос домена из Майкрософт на другой узел
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
ms.openlocfilehash: c5c1e98ed14c3ac975e55aadbff65e52165a6f8b
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289175"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a><span data-ttu-id="7e259-103">Перенос домена из Майкрософт на другой узел</span><span class="sxs-lookup"><span data-stu-id="7e259-103">Transfer a domain from Microsoft to another host</span></span>

<span data-ttu-id="7e259-104">Вы не можете перенести домен Microsoft 365 в другой регистратор в течение 60 дней после приобретения домена от Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7e259-104">You can't transfer a Microsoft 365 domain to another registrar for 60 days after you purchase the domain from Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="7e259-105">Запрос _Whois_   показывает приобретенного регистратора доменных имен Майкрософт в качестве подстановочных доменов LLC.</span><span class="sxs-lookup"><span data-stu-id="7e259-105">A _Whois_ query shows a Microsoft purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="7e259-106">Тем не менее, обращение к корпорации Майкрософт следует учитывать в приобретенном домене Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e259-106">However, only Microsoft should be contacted regarding your Microsoft 365 purchased domain.</span></span>

<span data-ttu-id="7e259-107">Выполните указанные ниже действия, чтобы получить код в Microsoft 365, а затем перейдите на другой веб-сайт регистратора доменных имен, чтобы настроить передачу имени домена новому регистратору.</span><span class="sxs-lookup"><span data-stu-id="7e259-107">Follow these steps to get a code at Microsoft 365, and then go to the other domain registrar website to set up transferring your domain name to the new registrar.</span></span>

## <a name="transfer-a-domain"></a><span data-ttu-id="7e259-108">Передача домена</span><span class="sxs-lookup"><span data-stu-id="7e259-108">Transfer a domain</span></span>

1. <span data-ttu-id="7e259-109">В центре администрирования перейдите в раздел  **Settings**   >  **домены**параметров.</span><span class="sxs-lookup"><span data-stu-id="7e259-109">In the admin center, go to  **Settings** > **Domains**.</span></span>

2. <span data-ttu-id="7e259-110">На странице **Domains (домены** ) выберите домен Microsoft 365, который требуется передать другому регистратору доменных имен, а затем выберите пункт **проверить работоспособность**.</span><span class="sxs-lookup"><span data-stu-id="7e259-110">On the **Domains** page, select the Microsoft 365 domain that you want to transfer to another domain registrar, and then select **Check health**.</span></span>

3. <span data-ttu-id="7e259-111">В верхней части страницы выберите пункт **передать домен**.</span><span class="sxs-lookup"><span data-stu-id="7e259-111">At the top of the page, select **Transfer domain**.</span></span>

4. <span data-ttu-id="7e259-112">На странице **Выбор места для переноса домена** выберите **другой регистратор**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7e259-112">On the **Choose where to transfer your domain** page, select **A different registrar**, and then click **Next**.</span></span>

5. <span data-ttu-id="7e259-113">На странице " **разблокировка передачи домена** " выберите команду \*\*разблокировать передачу для <_домене_ > \*\*, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7e259-113">On the **Unlock domain transfer** page, select **Unlock transfer for <_your domain_>**, and then select **Next**.</span></span>

6. <span data-ttu-id="7e259-114">Проверьте контактную информацию о передаче домена, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7e259-114">Check your domain transfer contact information, and then select **Next**.</span></span>

7. <span data-ttu-id="7e259-115">Скопируйте код авторизации и подождите около 30 минут, пока состояние передачи домена изменится на " **разблокировано для переноса** " на вкладке " **Регистрация** ", прежде чем переходить к дальнейшим действиям.</span><span class="sxs-lookup"><span data-stu-id="7e259-115">Copy the authorization code and wait about 30 minutes for your domain transfer status to change to **Unlocked for transfer** on the **Registration** tab before you proceed with next steps.</span></span>

8. <span data-ttu-id="7e259-116">Перейдите на веб-сайт регистратора доменных имен, который будет использоваться для управления доменным именем.</span><span class="sxs-lookup"><span data-stu-id="7e259-116">Go to the website of the domain registrar you want to manage your domain name going forward.</span></span> <span data-ttu-id="7e259-117">Следуйте указаниям по переносу домена (Поиск справки на веб-сайте).</span><span class="sxs-lookup"><span data-stu-id="7e259-117">Follow directions for transferring a domain (search for help on their website).</span></span>

<span data-ttu-id="7e259-118">Вкладку **Регистрация** кода авторизации можно найти на странице  **Domains (домены** ) в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e259-118">You can find the authorization code **Registration** tab on the  **Domains** page in Microsoft 365.</span></span>

9. <span data-ttu-id="7e259-119">После завершения переноса вы обновите свой домен в новом регистраторе доменных имен.</span><span class="sxs-lookup"><span data-stu-id="7e259-119">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>

10. <span data-ttu-id="7e259-120">Чтобы завершить процесс, вернитесь на страницу **домены** в центре администрирования, а затем выберите пункт  **полная передача домена**.</span><span class="sxs-lookup"><span data-stu-id="7e259-120">To finish the process, go back to the **Domains** page in the admin center, and then select  **Complete domain transfer**.</span></span>

> [!NOTE]
> <span data-ttu-id="7e259-121">Приобретенные домены Microsoft 365 не подходят для серверов доменных имен и не переносят домен между организациями Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e259-121">Microsoft 365 purchased domains are not eligible for nameserver changes or transferring the domain between Microsoft 365 organizations.</span></span> <span data-ttu-id="7e259-122">Если это необходимо, необходимо передать регистрацию домена другому регистратору.</span><span class="sxs-lookup"><span data-stu-id="7e259-122">If either of these are required, the domain registration must be transferred to another registrar.</span></span>
