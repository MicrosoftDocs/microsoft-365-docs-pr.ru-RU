---
title: Логика потока обработки почты
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Администраторы могут узнать коды ошибок, связанные с доставкой сообщений, с помощью соединителей (также называемой анализом потока обработки почты).
ms.openlocfilehash: b345b52f572efca2aca1fde6ba720d733e521cc4
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827717"
---
# <a name="mail-flow-intelligence-in-eop"></a><span data-ttu-id="78149-103">Логика обмена корреспонденцией почты в EOP</span><span class="sxs-lookup"><span data-stu-id="78149-103">Mail flow intelligence in EOP</span></span>

<span data-ttu-id="78149-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online, как правило, соединитель используется для маршрутизации сообщений из EOP в локальную среду электронной почты.</span><span class="sxs-lookup"><span data-stu-id="78149-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you typically use a connector to route email messages from EOP to your on-premises email environment.</span></span> <span data-ttu-id="78149-105">Вы также можете использовать соединитель для маршрутизации сообщений из Microsoft 365 в партнерскую организацию.</span><span class="sxs-lookup"><span data-stu-id="78149-105">You might also use a connector to route messages from Microsoft 365 to a partner organization.</span></span> <span data-ttu-id="78149-106">Если Microsoft 365 не удается доставить сообщение через соединитель, они добавляются в очередь в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78149-106">When Microsoft 365 can't deliver these messages via the connector, they're queued in Microsoft 365.</span></span> <span data-ttu-id="78149-107">Microsoft 365 продолжает попытки доставить каждое сообщение в течение 24 часов.</span><span class="sxs-lookup"><span data-stu-id="78149-107">Microsoft 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="78149-108">После 24 часов срок действия сообщения в очереди истечет, а сообщение будет возвращено исходному отправителю в отчете о недоставке.</span><span class="sxs-lookup"><span data-stu-id="78149-108">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="78149-109">Microsoft 365 генерирует ошибку, когда сообщение не удается доставить с помощью соединителя.</span><span class="sxs-lookup"><span data-stu-id="78149-109">Microsoft 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="78149-110">Наиболее распространенные ошибки и их решения описаны в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="78149-110">The most common errors and their solutions are described in this topic.</span></span> <span data-ttu-id="78149-111">Помещение в очередь недоставленных сообщений, отправленных через соединители, и ошибки уведомлений о них называют _логикой потока обработки почты._</span><span class="sxs-lookup"><span data-stu-id="78149-111">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="78149-112">Код ошибки: 450 4.4.312 Сбой запроса DNS</span><span class="sxs-lookup"><span data-stu-id="78149-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="78149-113">Как правило, эта ошибка означает, что Microsoft 365 пытался подключиться к промежуточному узлу, указанному в соединителе, но поиск IP-адресов промежуточного узла выполнить не удалось.</span><span class="sxs-lookup"><span data-stu-id="78149-113">Typically, this error means Microsoft 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="78149-114">Возможные причины этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="78149-114">The possible causes for this error are:</span></span>

- <span data-ttu-id="78149-115">Проблема со службой размещения DNS домена (компанией, которая обслуживает полномочные серверы доменных имен для вашего домена).</span><span class="sxs-lookup"><span data-stu-id="78149-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="78149-116">Срок действия домена недавно истек, поэтому запись MX невозможно восстановить.</span><span class="sxs-lookup"><span data-stu-id="78149-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="78149-117">Запись MX домена была недавно изменена, а информация о нем на DNS-серверах остается прежней.</span><span class="sxs-lookup"><span data-stu-id="78149-117">Your domain's MX record has recently changed, and the DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="78149-118">Как исправить ошибку 450 4.4.312?</span><span class="sxs-lookup"><span data-stu-id="78149-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="78149-119">Определите и устраните проблему с доменом вместе со службой размещения DNS.</span><span class="sxs-lookup"><span data-stu-id="78149-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="78149-120">Если ошибка возникла в партнерской организации (например, сторонним поставщиком облачных услуг), обратитесь к партнеру за исправлением проблемы.</span><span class="sxs-lookup"><span data-stu-id="78149-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="78149-121">Код ошибки: 450 4.4.315 Время ожидания подключения истекло</span><span class="sxs-lookup"><span data-stu-id="78149-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="78149-122">Как правило, это означает, что Microsoft 365 не может подключиться к конечному почтовому серверу.</span><span class="sxs-lookup"><span data-stu-id="78149-122">Typically, this means Microsoft 365 can't connect to the destination email server.</span></span> <span data-ttu-id="78149-123">Описание проблемы см. в сведениях об ошибке.</span><span class="sxs-lookup"><span data-stu-id="78149-123">The error details will explain the problem.</span></span> <span data-ttu-id="78149-124">Например:</span><span class="sxs-lookup"><span data-stu-id="78149-124">For example:</span></span>

- <span data-ttu-id="78149-125">Локальный почтовый сервер не доступен.</span><span class="sxs-lookup"><span data-stu-id="78149-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="78149-126">Ошибка в параметрах промежуточного узла соединителя, поэтому Microsoft 365 пытается подключиться к некорректный IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="78149-126">There's an error in the connector's smart host settings, so Microsoft 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="78149-127">Как исправить ошибку 450 4.4.315?</span><span class="sxs-lookup"><span data-stu-id="78149-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="78149-128">Выясните, какой из этих пунктов относится к вам, и внесите необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="78149-128">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="78149-129">Например, если поток обработки почты работал правильно и вы не изменяли параметры соединителя, проверьте локальную почтовую среду, чтобы узнать, не отключен ли сервер и не было ли изменений в сетевой инфраструктуре (например, изменился интернет-провайдер, поэтому теперь у вас другие IP-адреса).</span><span class="sxs-lookup"><span data-stu-id="78149-129">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="78149-130">Если ошибка возникла в партнерской организации (например, сторонним поставщиком облачных услуг), обратитесь к партнеру за исправлением проблемы.</span><span class="sxs-lookup"><span data-stu-id="78149-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="78149-131">Код ошибки: 450 4.4.316 В подключении отказано</span><span class="sxs-lookup"><span data-stu-id="78149-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="78149-132">Как правило, эта ошибка означает, что при попытке подключения к целевому почтовому серверу произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="78149-132">Typically, this error means Microsoft 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="78149-133">Вероятно, эта ошибка вызвана тем, что ваш брандмауэр блокирует подключения с IP-адресов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78149-133">A likely cause for this error is your firewall is blocking connections from Microsoft 365 IP addresses.</span></span> <span data-ttu-id="78149-134">Эта ошибка касается того, что если вы полностью перенесли локальную систему электронной почты в Microsoft 365 и завершили работу локальной почтовой среды.</span><span class="sxs-lookup"><span data-stu-id="78149-134">Or, this error might be by design if you've completely migrated your on-premises email system to Microsoft 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="78149-135">Как исправить ошибку 450 4.4.316?</span><span class="sxs-lookup"><span data-stu-id="78149-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="78149-136">Если в локальной среде есть почтовые ящики, измените настройки брандмауэра, чтобы разрешать подключения к локальным почтовым серверам с IP-адресов Microsoft 365 на TCP-порту 25.</span><span class="sxs-lookup"><span data-stu-id="78149-136">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Microsoft 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="78149-137">Список IP-адресов Microsoft 365 см. в статье ["URL-адреса и диапазоны IP-адресов Microsoft 365".](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="78149-137">For a list of the Microsoft 365 IP addresses, see [Microsoft 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

- <span data-ttu-id="78149-138">Если вам больше не требуется доставить сообщения в локальную среду, щелкните **"Исправить" теперь** в оповещении, чтобы Microsoft 365 мог сразу отклонить сообщения с недопустимыми получателями.</span><span class="sxs-lookup"><span data-stu-id="78149-138">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Microsoft 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="78149-139">Это снижает риск превышения квоты организации для недопустимых получателей, что может повлиять на обычную доставку сообщений.</span><span class="sxs-lookup"><span data-stu-id="78149-139">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="78149-140">Или вы можете воспорить следующие инструкции, чтобы устранить проблему вручную:</span><span class="sxs-lookup"><span data-stu-id="78149-140">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="78149-141">В [Центре администрирования Exchange отключите](https://docs.microsoft.com/Exchange/exchange-admin-center)соединитель, который доставляет электронную почту из Microsoft 365, в локальную среду электронной почты:</span><span class="sxs-lookup"><span data-stu-id="78149-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center), disable or delete the connector that delivers email from Microsoft 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="78149-142">В Центре администрирования Exchange перейдите к **соединителям** \> **потока обработки почты.**</span><span class="sxs-lookup"><span data-stu-id="78149-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="78149-143">Выберите соединитель со **значением "От"** **Office 365,** значением в поле **"Кому"** почтового сервера вашей **организации** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="78149-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="78149-144">Delete the connector by clicking the **Delete** ![ Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="78149-144">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="78149-145">Отключите соединитель, нажав **значок** ![ ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) правки и **снимите его.**</span><span class="sxs-lookup"><span data-stu-id="78149-145">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and clearing **Turn it on**.</span></span>

  - <span data-ttu-id="78149-146">Измените обслуживаемый домен в Microsoft 365, который связан с локальной почтовой средой, с **внутренней ретрансляции** на **уполномоченный.**</span><span class="sxs-lookup"><span data-stu-id="78149-146">Change the accepted domain in Microsoft 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="78149-147">Инструкции см. в статье Управление [обслуживаемыми доменами в Exchange Online.](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="78149-147">For instructions, see [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="78149-148">**Примечание. Обычно**изменения вступили в силу от 30 минут до 1 часа.</span><span class="sxs-lookup"><span data-stu-id="78149-148">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="78149-149">Через час проверьте, больше ли вы не видеть ошибку.</span><span class="sxs-lookup"><span data-stu-id="78149-149">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="78149-150">Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных служб), свяжитесь с ней, чтобы решить проблему.</span><span class="sxs-lookup"><span data-stu-id="78149-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="78149-151">Код ошибки: 450 4.4.317 Не удается подключиться к удаленному серверу</span><span class="sxs-lookup"><span data-stu-id="78149-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="78149-152">Как правило, эта ошибка означает, что Microsoft 365 подсоединен к целевому почтовому серверу, но ответ сервера содержит ошибку или он не соответствует требованиям для подключения.</span><span class="sxs-lookup"><span data-stu-id="78149-152">Typically, this error means Microsoft 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="78149-153">Описание проблемы см. в сведениях об ошибке.</span><span class="sxs-lookup"><span data-stu-id="78149-153">The error details will explain the problem.</span></span> <span data-ttu-id="78149-154">Например:</span><span class="sxs-lookup"><span data-stu-id="78149-154">For example:</span></span>

- <span data-ttu-id="78149-155">Ответ целевого почтового сервера с сообщением об ошибке "Служба недоступна", что означает, что сервер не может поддерживать связь с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78149-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Microsoft 365.</span></span>

- <span data-ttu-id="78149-156">Соединитель настроен так, чтобы он требоходил протокол TLS, но конечный почтовый сервер не поддерживает TLS.</span><span class="sxs-lookup"><span data-stu-id="78149-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="78149-157">Как исправить ошибку 450 4.4.317?</span><span class="sxs-lookup"><span data-stu-id="78149-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="78149-158">Проверьте настройки TLS и сертификаты на локальных почтовых серверах и параметры TLS на соединителе.</span><span class="sxs-lookup"><span data-stu-id="78149-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="78149-159">Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных услуг), свяжитесь с ней, чтобы решить проблему.</span><span class="sxs-lookup"><span data-stu-id="78149-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="78149-160">Код ошибки: 450 4.4.318 Соединение было внезапно прервано</span><span class="sxs-lookup"><span data-stu-id="78149-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="78149-161">Как правило, эта ошибка означает, что у Microsoft 365 возникли проблемы со связью с локальной почтовой средой, поэтому соединение было разорвано.</span><span class="sxs-lookup"><span data-stu-id="78149-161">Typically, this error means Microsoft 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="78149-162">Возможные причины этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="78149-162">The possible causes for this error are:</span></span>

- <span data-ttu-id="78149-163">Брандмауэр использует правила проверки пакетов SMTP, и эти правила работают неправильно.</span><span class="sxs-lookup"><span data-stu-id="78149-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="78149-164">Локальный почтовый сервер не работает правильно (например, зависания служб, сбои или низкие системные ресурсы), из-за чего время ожидания истекает и сервер закрывает подключение к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78149-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Microsoft 365.</span></span>

- <span data-ttu-id="78149-165">Проблемы с сетью между локальной средой и Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78149-165">There are network issues between your on-premises environment and Microsoft 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="78149-166">Как исправить ошибку 450 4.4.318?</span><span class="sxs-lookup"><span data-stu-id="78149-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="78149-167">Выясните, какой из этих пунктов относится к вам, и внесите необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="78149-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="78149-168">Если проблема вызвана проблемами с сетью между локальной средой и Microsoft 365, обратитесь к службе поддержки сети для ее устранения.</span><span class="sxs-lookup"><span data-stu-id="78149-168">If the problem is caused by network issues between your on-premises environment and Microsoft 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="78149-169">Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных услуг), свяжитесь с ней, чтобы решить проблему.</span><span class="sxs-lookup"><span data-stu-id="78149-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="78149-170">Код ошибки: 450 4.7.320 Не удалось проверить сертификат</span><span class="sxs-lookup"><span data-stu-id="78149-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="78149-171">Как правило, эта ошибка означает, что при попытке проверить сертификат целевого почтового сервера произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="78149-171">Typically, this error means Microsoft 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="78149-172">Описание см. в сведениях об ошибке.</span><span class="sxs-lookup"><span data-stu-id="78149-172">The error details will explain the error.</span></span> <span data-ttu-id="78149-173">Например:</span><span class="sxs-lookup"><span data-stu-id="78149-173">For example:</span></span>

- <span data-ttu-id="78149-174">Срок действия сертификата истек</span><span class="sxs-lookup"><span data-stu-id="78149-174">Certificate expired</span></span>

- <span data-ttu-id="78149-175">Субъект сертификата не совпадает с именем узла</span><span class="sxs-lookup"><span data-stu-id="78149-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="78149-176">Сертификат больше не действителен</span><span class="sxs-lookup"><span data-stu-id="78149-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="78149-177">Как исправить ошибку 450 4.7.320?</span><span class="sxs-lookup"><span data-stu-id="78149-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="78149-178">Исправьте сертификат или настройки соединителя, чтобы можно было доставить сообщения в очереди Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78149-178">Fix the certificate or the settings on the connector so that queued messages in Microsoft 365 can be delivered.</span></span>

- <span data-ttu-id="78149-179">Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных служб), свяжитесь с ней, чтобы решить проблему.</span><span class="sxs-lookup"><span data-stu-id="78149-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="78149-180">Коды других ошибок</span><span class="sxs-lookup"><span data-stu-id="78149-180">Other error codes</span></span>

<span data-ttu-id="78149-181">Microsoft 365 не удается доставить сообщения на локальный или партнерский почтовый сервер.</span><span class="sxs-lookup"><span data-stu-id="78149-181">Microsoft 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="78149-182">Используйте информацию **Конечный сервер** в сообщении об ошибке, чтобы устранить проблему в своей среде, или измените соединитель, если ошибка связана с конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="78149-182">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="78149-183">Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных услуг), свяжитесь с ней, чтобы решить проблему.</span><span class="sxs-lookup"><span data-stu-id="78149-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
