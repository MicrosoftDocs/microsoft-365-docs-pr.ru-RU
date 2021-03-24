---
title: Аналитика потока почты
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Администраторы могут узнать о кодах ошибок, связанных с доставкой сообщений с помощью соединители (также известный как разведданные потока почты).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2cb52e5865415440b3b2924a3ebcc96a7f8e17e5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071365"
---
# <a name="mail-flow-intelligence-in-eop"></a><span data-ttu-id="37f5a-103">Аналитика потока обработки почты в EOP</span><span class="sxs-lookup"><span data-stu-id="37f5a-103">Mail flow intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="37f5a-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="37f5a-104">**Applies to**</span></span>
- [<span data-ttu-id="37f5a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="37f5a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="37f5a-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="37f5a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="37f5a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37f5a-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="37f5a-108">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online обычно используется соединитель для маршрутов сообщений электронной почты из EOP в локальной среде электронной почты.</span><span class="sxs-lookup"><span data-stu-id="37f5a-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you typically use a connector to route email messages from EOP to your on-premises email environment.</span></span> <span data-ttu-id="37f5a-109">Можно также использовать соединители для маршрутизации сообщений из Microsoft 365 в организацию-партнер.</span><span class="sxs-lookup"><span data-stu-id="37f5a-109">You might also use a connector to route messages from Microsoft 365 to a partner organization.</span></span> <span data-ttu-id="37f5a-110">Когда Microsoft 365 не может доставить эти сообщения через соединители, они стоят в очереди в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="37f5a-110">When Microsoft 365 can't deliver these messages via the connector, they're queued in Microsoft 365.</span></span> <span data-ttu-id="37f5a-111">Microsoft 365 будет продолжать повторно отправлять каждое сообщение в течение 24 часов.</span><span class="sxs-lookup"><span data-stu-id="37f5a-111">Microsoft 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="37f5a-112">По истечении 24 часов срок ожидания сообщения истекает, и сообщение будет возвращено исходному отправителю в отчете о невывозе (также известном как сообщение NDR или отказов).</span><span class="sxs-lookup"><span data-stu-id="37f5a-112">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="37f5a-113">Microsoft 365 создает ошибку, когда сообщение не может быть доставлено с помощью соединиттеля.</span><span class="sxs-lookup"><span data-stu-id="37f5a-113">Microsoft 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="37f5a-114">Наиболее распространенные ошибки и их решения описаны в этой статье.</span><span class="sxs-lookup"><span data-stu-id="37f5a-114">The most common errors and their solutions are described in this article.</span></span> <span data-ttu-id="37f5a-115">В совокупности ошибки в очередях и уведомлениях для неразличимых сообщений, отправленных через соединители, называются _разведданными потока почты._</span><span class="sxs-lookup"><span data-stu-id="37f5a-115">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="37f5a-116">Код ошибки: 450 4.4.312 Сбой запроса DNS</span><span class="sxs-lookup"><span data-stu-id="37f5a-116">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="37f5a-117">Как правило, эта ошибка означает, что Microsoft 365 попыталась подключиться к смарт-хосту, указанному в соединителе, но запрос DNS для поиска IP-адресов смарт-хоста не удалось.</span><span class="sxs-lookup"><span data-stu-id="37f5a-117">Typically, this error means Microsoft 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="37f5a-118">Возможные причины этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="37f5a-118">The possible causes for this error are:</span></span>

- <span data-ttu-id="37f5a-119">Проблема со службой размещения DNS домена (компанией, которая обслуживает полномочные серверы доменных имен для вашего домена).</span><span class="sxs-lookup"><span data-stu-id="37f5a-119">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="37f5a-120">Срок действия домена недавно истек, поэтому запись MX невозможно восстановить.</span><span class="sxs-lookup"><span data-stu-id="37f5a-120">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="37f5a-121">Запись MX вашего домена недавно изменилась, и DNS-серверы до сих пор кэшировали данные DNS для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="37f5a-121">Your domain's MX record has recently changed, and the DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="37f5a-122">Как исправить код ошибки 450 4.4.312?</span><span class="sxs-lookup"><span data-stu-id="37f5a-122">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="37f5a-123">Работайте со службой размещения DNS для выявления и устранения проблемы с доменом.</span><span class="sxs-lookup"><span data-stu-id="37f5a-123">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="37f5a-124">Если ошибка произошла из организации-партнера (например, поставщика облачных служб третьей стороны), обратитесь к партнеру, чтобы устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="37f5a-124">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="37f5a-125">Код ошибки: 450 4.4.315 Время ожидания подключения истекло</span><span class="sxs-lookup"><span data-stu-id="37f5a-125">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="37f5a-126">Как правило, это означает, что Microsoft 365 не может подключиться к почтовому серверу назначения.</span><span class="sxs-lookup"><span data-stu-id="37f5a-126">Typically, this means Microsoft 365 can't connect to the destination email server.</span></span> <span data-ttu-id="37f5a-127">Описание проблемы см. в сведениях об ошибке.</span><span class="sxs-lookup"><span data-stu-id="37f5a-127">The error details will explain the problem.</span></span> <span data-ttu-id="37f5a-128">Например:</span><span class="sxs-lookup"><span data-stu-id="37f5a-128">For example:</span></span>

- <span data-ttu-id="37f5a-129">На локальном сервере электронной почты не будет.</span><span class="sxs-lookup"><span data-stu-id="37f5a-129">Your on-premises email server is down.</span></span>

- <span data-ttu-id="37f5a-130">В настройках смарт-хостов соединительная система имеет ошибку, поэтому Microsoft 365 пытается подключиться к неправильному IP-адресу.</span><span class="sxs-lookup"><span data-stu-id="37f5a-130">There's an error in the connector's smart host settings, so Microsoft 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="37f5a-131">Как исправить код ошибки 450 4.4.315?</span><span class="sxs-lookup"><span data-stu-id="37f5a-131">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="37f5a-132">Выясните, какой из этих пунктов относится к вам, и внесите необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="37f5a-132">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="37f5a-133">Например, если поток почты работает правильно и параметры соединителю не изменены, необходимо проверить локальное окружение электронной почты, чтобы узнать, не работает ли сервер или произошли ли какие-либо изменения в сетевой инфраструктуре (например, вы изменили поставщиков услуг Интернета, поэтому теперь у вас есть разные IP-адреса).</span><span class="sxs-lookup"><span data-stu-id="37f5a-133">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="37f5a-134">Если ошибка произошла из организации-партнера (например, поставщика облачных служб третьей стороны), обратитесь к партнеру, чтобы устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="37f5a-134">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="37f5a-135">Код ошибки: 450 4.4.316 В подключении отказано</span><span class="sxs-lookup"><span data-stu-id="37f5a-135">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="37f5a-136">Как правило, эта ошибка означает, что при подключении к почтовому серверу назначения в Microsoft 365 произошла ошибка подключения.</span><span class="sxs-lookup"><span data-stu-id="37f5a-136">Typically, this error means Microsoft 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="37f5a-137">Вероятной причиной этой ошибки является блокировка брандмауэром подключений с IP-адресов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="37f5a-137">A likely cause for this error is your firewall is blocking connections from Microsoft 365 IP addresses.</span></span> <span data-ttu-id="37f5a-138">Или эта ошибка может быть по ошибке, если вы полностью перенаселили локальной системы электронной почты в Microsoft 365 и закрыть локальной среде электронной почты.</span><span class="sxs-lookup"><span data-stu-id="37f5a-138">Or, this error might be by design if you've completely migrated your on-premises email system to Microsoft 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="37f5a-139">Как исправить код ошибки 450 4.4.316?</span><span class="sxs-lookup"><span data-stu-id="37f5a-139">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="37f5a-140">Если в локальной среде есть почтовые ящики, необходимо изменить параметры брандмауэра, чтобы разрешить подключение с IP-адресов Microsoft 365 в порту TCP 25 на локальном сервере электронной почты.</span><span class="sxs-lookup"><span data-stu-id="37f5a-140">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Microsoft 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="37f5a-141">Список IP-адресов Microsoft 365 см. в списке URL-адресов [Microsoft 365 и диапазонов IP-адресов.](../../enterprise/urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="37f5a-141">For a list of the Microsoft 365 IP addresses, see [Microsoft 365 URLs and IP address ranges](../../enterprise/urls-and-ip-address-ranges.md).</span></span>

- <span data-ttu-id="37f5a-142">Если больше не следует отправлять сообщения в локальной среде, щелкните **Исправление** в оповещении, чтобы Microsoft 365 немедленно отклонить сообщения с недействительными получателями.</span><span class="sxs-lookup"><span data-stu-id="37f5a-142">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Microsoft 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="37f5a-143">Это снизит риск превышения квоты организации для недействительных получателей, что может повлиять на нормальную доставку сообщений.</span><span class="sxs-lookup"><span data-stu-id="37f5a-143">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="37f5a-144">Чтобы вручную устранить проблему, можно использовать следующие инструкции.</span><span class="sxs-lookup"><span data-stu-id="37f5a-144">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="37f5a-145">В центре [администрирования Exchange (EAC)](/Exchange/exchange-admin-center)отключите или удалите соединитель, который доставляет электронную почту из Microsoft 365 в локальной среде электронной почты:</span><span class="sxs-lookup"><span data-stu-id="37f5a-145">In the [Exchange admin center (EAC)](/Exchange/exchange-admin-center), disable or delete the connector that delivers email from Microsoft 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="37f5a-146">В EAC перейдите к **соединитетелям потока** \> **почты.**</span><span class="sxs-lookup"><span data-stu-id="37f5a-146">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="37f5a-147">Выберите соединитектор **с** значением **Office 365** и сервером электронной почты Вашей организации **и** сделайте один из следующих действий: </span><span class="sxs-lookup"><span data-stu-id="37f5a-147">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="37f5a-148">Удаление соединитетеля, щелкнув **значок Delete** ![ Remove Remove](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="37f5a-148">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="37f5a-149">Отключайте соединители, щелкнув значок **Edit** ![ Edit и ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) включив его. </span><span class="sxs-lookup"><span data-stu-id="37f5a-149">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and clearing **Turn it on**.</span></span>

  - <span data-ttu-id="37f5a-150">Измените принятый домен в Microsoft 365, связанный с локальной средой электронной почты, с внутреннего **ретрансляции** на **авторитетный.**</span><span class="sxs-lookup"><span data-stu-id="37f5a-150">Change the accepted domain in Microsoft 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="37f5a-151">Инструкции см. в [рублях Управление принятыми доменами в Exchange Online.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="37f5a-151">For instructions, see [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="37f5a-152">**Примечание.** Как правило, эти изменения вступает в силу от 30 минут до одного часа.</span><span class="sxs-lookup"><span data-stu-id="37f5a-152">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="37f5a-153">Через час убедитесь, что ошибка больше не будет допущена.</span><span class="sxs-lookup"><span data-stu-id="37f5a-153">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="37f5a-154">Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных служб), свяжитесь с ней, чтобы решить проблему.</span><span class="sxs-lookup"><span data-stu-id="37f5a-154">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="37f5a-155">Код ошибки: 450 4.4.317 Не удается подключиться к удаленному серверу</span><span class="sxs-lookup"><span data-stu-id="37f5a-155">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="37f5a-156">Как правило, эта ошибка означает, что Microsoft 365 подключен к почтовому серверу назначения, но сервер ответил немедленной ошибкой или не отвечает требованиям к подключению.</span><span class="sxs-lookup"><span data-stu-id="37f5a-156">Typically, this error means Microsoft 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="37f5a-157">Описание проблемы см. в сведениях об ошибке.</span><span class="sxs-lookup"><span data-stu-id="37f5a-157">The error details will explain the problem.</span></span> <span data-ttu-id="37f5a-158">Например:</span><span class="sxs-lookup"><span data-stu-id="37f5a-158">For example:</span></span>

- <span data-ttu-id="37f5a-159">Сервер электронной почты назначения ответил ошибкой "Служба недоступна", что указывает на то, что сервер не может поддерживать связь с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="37f5a-159">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Microsoft 365.</span></span>

- <span data-ttu-id="37f5a-160">Соединитель настроен для TLS, но сервер электронной почты назначения не поддерживает TLS.</span><span class="sxs-lookup"><span data-stu-id="37f5a-160">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="37f5a-161">Как исправить код ошибки 450 4.4.317?</span><span class="sxs-lookup"><span data-stu-id="37f5a-161">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="37f5a-162">Проверьте параметры TLS и сертификаты на локальном сервере электронной почты и параметры TLS на соединителенном.</span><span class="sxs-lookup"><span data-stu-id="37f5a-162">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="37f5a-163">Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных услуг), свяжитесь с ней, чтобы решить проблему.</span><span class="sxs-lookup"><span data-stu-id="37f5a-163">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="37f5a-164">Код ошибки: 450 4.4.318 Соединение было внезапно прервано</span><span class="sxs-lookup"><span data-stu-id="37f5a-164">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="37f5a-165">Как правило, эта ошибка означает, что Microsoft 365 с трудом общается с локальной средой электронной почты, поэтому подключение было отброшено.</span><span class="sxs-lookup"><span data-stu-id="37f5a-165">Typically, this error means Microsoft 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="37f5a-166">Возможные причины этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="37f5a-166">The possible causes for this error are:</span></span>

- <span data-ttu-id="37f5a-167">Брандмауэр использует правила проверки пакетов SMTP, и эти правила работают неправильно.</span><span class="sxs-lookup"><span data-stu-id="37f5a-167">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="37f5a-168">Локальное сервер электронной почты не работает правильно (например, служба зависает, сбои или низкий уровень системных ресурсов), что приводит к тому, что сервер будет отсутвлять время и закрывать подключение к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="37f5a-168">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Microsoft 365.</span></span>

- <span data-ttu-id="37f5a-169">Между локальной средой и Microsoft 365 существуют проблемы с сетью.</span><span class="sxs-lookup"><span data-stu-id="37f5a-169">There are network issues between your on-premises environment and Microsoft 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="37f5a-170">Как исправить код ошибки 450 4.4.318?</span><span class="sxs-lookup"><span data-stu-id="37f5a-170">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="37f5a-171">Выясните, какой из этих пунктов относится к вам, и внесите необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="37f5a-171">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="37f5a-172">Если проблема вызвана сетевыми неполадками между локальной средой и Microsoft 365, свяжитесь с сетевой командой, чтобы устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="37f5a-172">If the problem is caused by network issues between your on-premises environment and Microsoft 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="37f5a-173">Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных услуг), свяжитесь с ней, чтобы решить проблему.</span><span class="sxs-lookup"><span data-stu-id="37f5a-173">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="37f5a-174">Код ошибки: 450 4.7.320 Не удалось проверить сертификат</span><span class="sxs-lookup"><span data-stu-id="37f5a-174">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="37f5a-175">Как правило, эта ошибка означает, что в Microsoft 365 произошла ошибка при проверке сертификата почтового сервера назначения.</span><span class="sxs-lookup"><span data-stu-id="37f5a-175">Typically, this error means Microsoft 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="37f5a-176">Описание см. в сведениях об ошибке.</span><span class="sxs-lookup"><span data-stu-id="37f5a-176">The error details will explain the error.</span></span> <span data-ttu-id="37f5a-177">Например:</span><span class="sxs-lookup"><span data-stu-id="37f5a-177">For example:</span></span>

- <span data-ttu-id="37f5a-178">Срок действия сертификата истек</span><span class="sxs-lookup"><span data-stu-id="37f5a-178">Certificate expired</span></span>

- <span data-ttu-id="37f5a-179">Субъект сертификата не совпадает с именем узла</span><span class="sxs-lookup"><span data-stu-id="37f5a-179">Certificate subject mismatch</span></span>

- <span data-ttu-id="37f5a-180">Сертификат больше не действителен</span><span class="sxs-lookup"><span data-stu-id="37f5a-180">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="37f5a-181">Как исправить код ошибки 450 4.7.320?</span><span class="sxs-lookup"><span data-stu-id="37f5a-181">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="37f5a-182">Исправление сертификата или параметров на соединители, чтобы можно было доставить в очереди сообщения в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="37f5a-182">Fix the certificate or the settings on the connector so that queued messages in Microsoft 365 can be delivered.</span></span>

- <span data-ttu-id="37f5a-183">Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных служб), свяжитесь с ней, чтобы решить проблему.</span><span class="sxs-lookup"><span data-stu-id="37f5a-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="37f5a-184">Коды других ошибок</span><span class="sxs-lookup"><span data-stu-id="37f5a-184">Other error codes</span></span>

<span data-ttu-id="37f5a-185">Microsoft 365 затрудняет доставку сообщений на локальном сервере или сервере электронной почты партнера.</span><span class="sxs-lookup"><span data-stu-id="37f5a-185">Microsoft 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="37f5a-186">Используйте информацию **Конечный сервер** в сообщении об ошибке, чтобы устранить проблему в своей среде, или измените соединитель, если ошибка связана с конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="37f5a-186">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="37f5a-187">Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных услуг), свяжитесь с ней, чтобы решить проблему.</span><span class="sxs-lookup"><span data-stu-id="37f5a-187">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>