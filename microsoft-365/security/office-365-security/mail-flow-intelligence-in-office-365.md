---
title: Аналитика почтового процесса
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
description: Администраторы могут узнать о кодах ошибок, связанных с доставкой сообщений с помощью соединителей (также называемых логикой обработки почтового процесса).
ms.openlocfilehash: e8427f3e0341ccb381121b6cdc83d20727713d4c
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307921"
---
# <a name="mail-flow-intelligence-in-eop"></a><span data-ttu-id="c1ac4-103">Логика обмена корреспонденцией почты в EOP</span><span class="sxs-lookup"><span data-stu-id="c1ac4-103">Mail flow intelligence in EOP</span></span>

<span data-ttu-id="c1ac4-104">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или автономной службе Exchange Online Protection (EOP) без почтовых ящиков Exchange Online, обычно используется соединитель для маршрутизации сообщений электронной почты из EOP в локальную среду электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you typically use a connector to route email messages from EOP to your on-premises email environment.</span></span> <span data-ttu-id="c1ac4-105">Вы также можете использовать соединитель для маршрутизации сообщений от Microsoft 365 к партнерской организации.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-105">You might also use a connector to route messages from Microsoft 365 to a partner organization.</span></span> <span data-ttu-id="c1ac4-106">Когда Microsoft 365 не может доставить эти сообщения через соединитель, они помещаются в очередь в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-106">When Microsoft 365 can't deliver these messages via the connector, they're queued in Microsoft 365.</span></span> <span data-ttu-id="c1ac4-107">Microsoft 365 продолжит повторять доставку для каждого сообщения в течение 24 часов.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-107">Microsoft 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="c1ac4-108">Через 24 часа срок действия сообщения в очереди истечет, и сообщение будет возвращено исходному отправителю в отчете о недоставке (также называемом сообщением о недоставке или сообщении Bounce).</span><span class="sxs-lookup"><span data-stu-id="c1ac4-108">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="c1ac4-109">Microsoft 365 создает сообщение об ошибке, если сообщение не может быть доставлено с помощью соединителя.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-109">Microsoft 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="c1ac4-110">Наиболее распространенные ошибки и их решения описаны в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-110">The most common errors and their solutions are described in this topic.</span></span> <span data-ttu-id="c1ac4-111">Коллективно, ошибки очереди и уведомления о недоставленных сообщениях, отправляемых через соединители, называются _логикой обработки почтового процесса_.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-111">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="c1ac4-112">Код ошибки: 450 4.4.312 Сбой запроса DNS</span><span class="sxs-lookup"><span data-stu-id="c1ac4-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="c1ac4-113">Как правило, эта ошибка означает, что Microsoft 365 пытался подключиться к промежуточному узлу, указанному в соединителе, но DNS-запрос на поиск IP-адресов промежуточного узла окончился неудачей.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-113">Typically, this error means Microsoft 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="c1ac4-114">Возможные причины этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="c1ac4-114">The possible causes for this error are:</span></span>

- <span data-ttu-id="c1ac4-115">Проблема со службой размещения DNS домена (компанией, которая обслуживает полномочные серверы доменных имен для вашего домена).</span><span class="sxs-lookup"><span data-stu-id="c1ac4-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="c1ac4-116">Срок действия домена недавно истек, поэтому запись MX невозможно восстановить.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="c1ac4-117">Запись MX вашего домена была недавно изменена, а DNS-серверы по-прежнему сохранили кэшированные данные DNS для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-117">Your domain's MX record has recently changed, and the DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="c1ac4-118">Как исправить ошибку с кодом 450 4.4.312?</span><span class="sxs-lookup"><span data-stu-id="c1ac4-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="c1ac4-119">Работа со службой хостинга DNS для определения и устранения проблемы с доменом.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="c1ac4-120">Если ошибка связана с вашей партнерской организацией (например, сторонним поставщиком облачных служб), обратитесь к своему партнеру, чтобы устранить эту проблему.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="c1ac4-121">Код ошибки: 450 4.4.315 Время ожидания подключения истекло</span><span class="sxs-lookup"><span data-stu-id="c1ac4-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="c1ac4-122">Как правило, это означает, что Microsoft 365 не может подключиться к конечному серверу электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-122">Typically, this means Microsoft 365 can't connect to the destination email server.</span></span> <span data-ttu-id="c1ac4-123">Описание проблемы см. в сведениях об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-123">The error details will explain the problem.</span></span> <span data-ttu-id="c1ac4-124">Например:</span><span class="sxs-lookup"><span data-stu-id="c1ac4-124">For example:</span></span>

- <span data-ttu-id="c1ac4-125">Ваш локальный сервер электронной почты не работает.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="c1ac4-126">Произошла ошибка в параметрах промежуточного узла соединителя, поэтому Microsoft 365 пытается подключиться к неправильному IP-адресу.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-126">There's an error in the connector's smart host settings, so Microsoft 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="c1ac4-127">Как исправить ошибку с кодом 450 4.4.315?</span><span class="sxs-lookup"><span data-stu-id="c1ac4-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="c1ac4-128">Выясните, какой из этих пунктов относится к вам, и внесите необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-128">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="c1ac4-129">Например, если почтовые потоки работают правильно, а параметры соединителя не были изменены, необходимо проверить локальную среду электронной почты, чтобы проверить, не работает ли сервер, или если вы изменили сетевую инфраструктуру (например, вы изменили поставщика услуг Интернета).</span><span class="sxs-lookup"><span data-stu-id="c1ac4-129">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="c1ac4-130">Если ошибка связана с вашей партнерской организацией (например, сторонним поставщиком облачных служб), обратитесь к своему партнеру, чтобы устранить эту проблему.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="c1ac4-131">Код ошибки: 450 4.4.316 В подключении отказано</span><span class="sxs-lookup"><span data-stu-id="c1ac4-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="c1ac4-132">Как правило, эта ошибка означает, что при попытке подключения к конечному серверу электронной почты в Microsoft 365 возникла ошибка подключения.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-132">Typically, this error means Microsoft 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="c1ac4-133">Вероятно, эта ошибка вызвана тем, что ваш брандмауэр блокирует подключения к IP-адресам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-133">A likely cause for this error is your firewall is blocking connections from Microsoft 365 IP addresses.</span></span> <span data-ttu-id="c1ac4-134">Эта ошибка может быть вызвана тем, что вы полностью перенесли локальную почтовую систему в Microsoft 365 и закрываете локальную почтовую среду.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-134">Or, this error might be by design if you've completely migrated your on-premises email system to Microsoft 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="c1ac4-135">Как исправить ошибку с кодом 450 4.4.316?</span><span class="sxs-lookup"><span data-stu-id="c1ac4-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="c1ac4-136">Если у вас есть почтовые ящики в локальной среде, необходимо изменить параметры брандмауэра, чтобы разрешить подключения с IP-адресов Microsoft 365 через TCP-порт 25 к локальным почтовым серверам.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-136">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Microsoft 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="c1ac4-137">Список IP-адресов Microsoft 365 можно найти в разделе URL-адреса [и диапазоны IP-адресов microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="c1ac4-137">For a list of the Microsoft 365 IP addresses, see [Microsoft 365 URLs and IP address ranges](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span></span>

- <span data-ttu-id="c1ac4-138">Если вы не хотите доставлять сообщения в локальную среду, нажмите кнопку **исправить сейчас** в окне оповещение, чтобы Microsoft 365 мог сразу же отклонить сообщения с недопустимыми получателями.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-138">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Microsoft 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="c1ac4-139">Это снизит риск превышения квоты Организации для недопустимых получателей, что может повлиять на обычную доставку сообщений.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-139">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="c1ac4-140">Вы также можете исправить проблему вручную с помощью следующих инструкций:</span><span class="sxs-lookup"><span data-stu-id="c1ac4-140">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="c1ac4-141">В [центре администрирования Exchange](https://docs.microsoft.com/Exchange/exchange-admin-center)отключите или удалите соединитель, который доставляет электронную почту от Microsoft 365 в локальную почтовую среду:</span><span class="sxs-lookup"><span data-stu-id="c1ac4-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center), disable or delete the connector that delivers email from Microsoft 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="c1ac4-142">В центре администрирования Exchange перейдите в **Mail flow** раздел \> **соединители**поток обработки почты.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="c1ac4-143">Выберите соединитель со значением " **от** " **Office 365** и укажите значение в поле " **Кому** " **почтового сервера организации** и выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="c1ac4-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="c1ac4-144">Удаление соединителя путем нажатия кнопки " **Удалить** ![ значок удаления"](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="c1ac4-144">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="c1ac4-145">Отключите соединитель, нажав кнопку **изменить** ![ значок редактирования ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) и сняв флажок **включить**.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-145">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and clearing **Turn it on**.</span></span>

  - <span data-ttu-id="c1ac4-146">Изменение обслуживаемого домена в Microsoft 365, связанного с локальной средой электронной почты, от **внутренней ретрансляции** к **удостоверяющему**.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-146">Change the accepted domain in Microsoft 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="c1ac4-147">Инструкции см в разделе [Manage обслуживаемые домены в Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span><span class="sxs-lookup"><span data-stu-id="c1ac4-147">For instructions, see [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="c1ac4-148">**Примечание**. как правило, для вступления в силу этих изменений требуется от 30 минут до одного часа.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-148">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="c1ac4-149">Через один час убедитесь, что сообщение об ошибке больше не отображается.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-149">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="c1ac4-150">Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных служб), свяжитесь с ней, чтобы решить проблему.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="c1ac4-151">Код ошибки: 450 4.4.317 Не удается подключиться к удаленному серверу</span><span class="sxs-lookup"><span data-stu-id="c1ac4-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="c1ac4-152">Как правило, эта ошибка означает, что Microsoft 365 подключен к конечному серверу электронной почты, но сервер ответил на немедленную ошибку или не соответствует требованиям к подключению.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-152">Typically, this error means Microsoft 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="c1ac4-153">Описание проблемы см. в сведениях об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-153">The error details will explain the problem.</span></span> <span data-ttu-id="c1ac4-154">Например:</span><span class="sxs-lookup"><span data-stu-id="c1ac4-154">For example:</span></span>

- <span data-ttu-id="c1ac4-155">Конечный сервер электронной почты выдал сообщение об ошибке "Служба недоступна", которая указывает на то, что сервер не может поддерживать связь с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Microsoft 365.</span></span>

- <span data-ttu-id="c1ac4-156">Для соединителя настроено требование TLS, но конечный сервер электронной почты не поддерживает TLS.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="c1ac4-157">Как исправить ошибку с кодом 450 4.4.317?</span><span class="sxs-lookup"><span data-stu-id="c1ac4-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="c1ac4-158">Проверьте параметры TLS и сертификаты на локальных почтовых серверах и параметры TLS на соединителе.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="c1ac4-159">Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных услуг), свяжитесь с ней, чтобы решить проблему.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="c1ac4-160">Код ошибки: 450 4.4.318 Соединение было внезапно прервано</span><span class="sxs-lookup"><span data-stu-id="c1ac4-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="c1ac4-161">Как правило, эта ошибка означает, что в Microsoft 365 возникают проблемы связи с локальной средой электронной почты, поэтому подключение было разорвано.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-161">Typically, this error means Microsoft 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="c1ac4-162">Возможные причины этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="c1ac4-162">The possible causes for this error are:</span></span>

- <span data-ttu-id="c1ac4-163">Брандмауэр использует правила проверки пакетов SMTP, и эти правила работают неправильно.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="c1ac4-164">Локальный сервер электронной почты работает неправильно (например, служба зависает или не хватает системных ресурсов), что приводит к превышению времени ожидания сервера и закрытию подключения к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Microsoft 365.</span></span>

- <span data-ttu-id="c1ac4-165">Существуют сетевые проблемы между локальной средой и Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-165">There are network issues between your on-premises environment and Microsoft 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="c1ac4-166">Как исправить ошибку с кодом 450 4.4.318?</span><span class="sxs-lookup"><span data-stu-id="c1ac4-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="c1ac4-167">Выясните, какой из этих пунктов относится к вам, и внесите необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="c1ac4-168">Если проблема возникает из-за проблем с сетью между локальной средой и Microsoft 365, обратитесь в группу сети, чтобы устранить эту проблему.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-168">If the problem is caused by network issues between your on-premises environment and Microsoft 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="c1ac4-169">Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных услуг), свяжитесь с ней, чтобы решить проблему.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="c1ac4-170">Код ошибки: 450 4.7.320 Не удалось проверить сертификат</span><span class="sxs-lookup"><span data-stu-id="c1ac4-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="c1ac4-171">Как правило, эта ошибка означает, что при попытке проверки сертификата конечного сервера электронной почты в Microsoft 365 возникла ошибка.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-171">Typically, this error means Microsoft 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="c1ac4-172">Описание см. в сведениях об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-172">The error details will explain the error.</span></span> <span data-ttu-id="c1ac4-173">Например:</span><span class="sxs-lookup"><span data-stu-id="c1ac4-173">For example:</span></span>

- <span data-ttu-id="c1ac4-174">Срок действия сертификата истек</span><span class="sxs-lookup"><span data-stu-id="c1ac4-174">Certificate expired</span></span>

- <span data-ttu-id="c1ac4-175">Субъект сертификата не совпадает с именем узла</span><span class="sxs-lookup"><span data-stu-id="c1ac4-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="c1ac4-176">Сертификат больше не действителен</span><span class="sxs-lookup"><span data-stu-id="c1ac4-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="c1ac4-177">Как исправить ошибку с кодом 450 4.7.320?</span><span class="sxs-lookup"><span data-stu-id="c1ac4-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="c1ac4-178">Исправьте сертификат или параметры на соединителе таким образом, чтобы сообщения в очереди в Microsoft 365 могли быть доставлены.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-178">Fix the certificate or the settings on the connector so that queued messages in Microsoft 365 can be delivered.</span></span>

- <span data-ttu-id="c1ac4-179">Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных служб), свяжитесь с ней, чтобы решить проблему.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="c1ac4-180">Коды других ошибок</span><span class="sxs-lookup"><span data-stu-id="c1ac4-180">Other error codes</span></span>

<span data-ttu-id="c1ac4-181">Microsoft 365 испытывает трудности при доставке сообщений на локальный или партнерский сервер электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-181">Microsoft 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="c1ac4-182">Используйте информацию **Конечный сервер** в сообщении об ошибке, чтобы устранить проблему в своей среде, или измените соединитель, если ошибка связана с конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-182">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="c1ac4-183">Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных услуг), свяжитесь с ней, чтобы решить проблему.</span><span class="sxs-lookup"><span data-stu-id="c1ac4-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
