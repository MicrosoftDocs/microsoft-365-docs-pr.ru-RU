---
title: Аналитика поток почты в Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Администраторы могут узнать о кодах ошибок, связанных с доставкой сообщений с помощью соединителей в Office 365 (также известной как логика обработки почтового процесса).
ms.openlocfilehash: d49937afb379b43821d905001e8aee21ca86eb52
ms.sourcegitcommit: b91d75d2631166ddd158d26a0a476e26391a58ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "37886862"
---
# <a name="mail-flow-intelligence-in-office-365"></a><span data-ttu-id="bd4ea-103">Логика потока обработки почты в Office 365</span><span class="sxs-lookup"><span data-stu-id="bd4ea-103">Mail flow intelligence in Office 365</span></span>

<span data-ttu-id="bd4ea-104">Как правило, для маршрутизации сообщений электронной почты из организации Office 365 в локальную среду электронной почты используется соединитель.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-104">Typically, you use a connector to route email messages from your Office 365 organization to your on-premises email environment.</span></span> <span data-ttu-id="bd4ea-105">Соединитель также можно использовать для маршрутизации сообщений из Office 365 в партнерскую организацию.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-105">You might also use a connector to route messages from Office 365 to a partner organization.</span></span> <span data-ttu-id="bd4ea-106">Когда Office 365 не удается доставить сообщение через соединитель, оно помещается в очередь.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-106">When Office 365 can't deliver these messages via the connector, they're queued in Office 365.</span></span> <span data-ttu-id="bd4ea-107">Office 365 продолжит попытки доставки каждого сообщения в течение 24 часов.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-107">Office 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="bd4ea-108">Через 24 часа срок действия сообщения в очереди истечет, и сообщение будет возвращено исходному отправителю в отчете о недоставке (также называемом сообщением о недоставке или сообщении Bounce).</span><span class="sxs-lookup"><span data-stu-id="bd4ea-108">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="bd4ea-109">Office 365 генерирует ошибку, когда сообщение не удается доставить с помощью соединителя.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-109">Office 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="bd4ea-110">Наиболее распространенные ошибки и их решения описаны в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-110">The most common errors and their solutions are described in this topic.</span></span> <span data-ttu-id="bd4ea-111">Коллективно, ошибки очереди и уведомления о недоставленных сообщениях, отправляемых через соединители, называются _логикой обработки почтового процесса_.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-111">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="bd4ea-112">Код ошибки: 450 4.4.312 Сбой запроса DNS</span><span class="sxs-lookup"><span data-stu-id="bd4ea-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="bd4ea-113">Как правило, эта ошибка означает, что Office 365 пытается подключиться к промежуточному узлу, указанному в соединителе, но DNS-запрос на поиск IP-адресов промежуточного узла окончился неудачей.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-113">Typically, this error means Office 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="bd4ea-114">Возможные причины этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="bd4ea-114">The possible causes for this error are:</span></span>

- <span data-ttu-id="bd4ea-115">Проблема со службой размещения DNS домена (компанией, которая обслуживает полномочные серверы доменных имен для вашего домена).</span><span class="sxs-lookup"><span data-stu-id="bd4ea-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="bd4ea-116">Срок действия домена недавно истек, поэтому запись MX невозможно восстановить.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="bd4ea-117">Запись MX домена была недавно изменена, а информация о нем на DNS-серверах Office 365 остается прежней.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-117">Your domain's MX record has recently changed, and the Office 365 DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="bd4ea-118">Как исправить ошибку с кодом 450 4.4.312?</span><span class="sxs-lookup"><span data-stu-id="bd4ea-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="bd4ea-119">Работа со службой хостинга DNS для определения и устранения проблемы с доменом.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="bd4ea-120">Если ошибка связана с вашей партнерской организацией (например, сторонним поставщиком облачных служб), обратитесь к своему партнеру, чтобы устранить эту проблему.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="bd4ea-121">Код ошибки: 450 4.4.315 Время ожидания подключения истекло</span><span class="sxs-lookup"><span data-stu-id="bd4ea-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="bd4ea-122">Как правило, это означает, что Office 365 не удается подключиться к конечному серверу электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-122">Typically, this means Office 365 can't connect to the destination email server.</span></span> <span data-ttu-id="bd4ea-123">Описание проблемы см. в сведениях об ошибке.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-123">The error details will explain the problem.</span></span> <span data-ttu-id="bd4ea-124">Пример:</span><span class="sxs-lookup"><span data-stu-id="bd4ea-124">For example:</span></span>

- <span data-ttu-id="bd4ea-125">Ваш локальный сервер электронной почты не работает.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="bd4ea-126">Ошибка в настройках промежуточного узла соединителя, поэтому Office 365 пытается подключиться к неправильному IP-адресу.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-126">There's an error in the connector's smart host settings, so Office 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="bd4ea-127">Как исправить ошибку с кодом 450 4.4.315?</span><span class="sxs-lookup"><span data-stu-id="bd4ea-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="bd4ea-128">Выясните, какой из этих пунктов относится к вам, и внесите необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-128">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="bd4ea-129">Например, если почтовые потоки работают правильно, а параметры соединителей не были изменены, необходимо проверить локальную среду электронной почты, чтобы проверить, не работает ли сервер, или были ли какие-либо изменения в сетевой инфраструктуре (например, Вы изменили поставщика услуг Интернета, поэтому у вас есть разные IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-129">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="bd4ea-130">Если ошибка связана с вашей партнерской организацией (например, сторонним поставщиком облачных служб), обратитесь к своему партнеру, чтобы устранить эту проблему.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="bd4ea-131">Код ошибки: 450 4.4.316 В подключении отказано</span><span class="sxs-lookup"><span data-stu-id="bd4ea-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="bd4ea-132">Как правило, эта ошибка означает, что в Office 365 возникла ошибка подключения при попытке подключения к конечному серверу электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-132">Typically, this error means Office 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="bd4ea-133">Вероятно, эта ошибка произошла из-за того, что ваш брандмауэр блокирует подключения с IP-адресов Office 365.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-133">A likely cause for this error is your firewall is blocking connections from Office 365 IP addresses.</span></span> <span data-ttu-id="bd4ea-134">Эта ошибка может быть вызвана тем, что вы полностью перенесли локальную почтовую систему в Office 365 и закрываете локальную почтовую среду.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-134">Or, this error might be by design if you've completely migrated your on-premises email system to Office 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="bd4ea-135">Как исправить ошибку с кодом 450 4.4.316?</span><span class="sxs-lookup"><span data-stu-id="bd4ea-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="bd4ea-136">Если у вас есть почтовые ящики в локальной среде, необходимо изменить параметры брандмауэра, чтобы разрешить подключения с IP-адресов Office 365 через TCP-порт 25 к локальным почтовым серверам.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-136">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Office 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="bd4ea-137">Список IP-адресов Office 365 можно найти в разделе URL-адреса [и диапазоны IP-адресов office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx).</span><span class="sxs-lookup"><span data-stu-id="bd4ea-137">For a list of the Office 365 IP addresses, see [Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx).</span></span>

- <span data-ttu-id="bd4ea-p108">Если больше не нужна доставка сообщений в локальную среду, нажмите кнопку **Исправить** в оповещении, чтобы служба Office 365 могла немедленно отклонять сообщения, для которых указаны недействительные получатели. Это уменьшит риск превышения квоты организации относительно недействительных получателей. Такое превышение влияет на нормальную доставку сообщений. Вы также можете вручную устранить проблему, следуя приведенными ниже инструкциям.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-p108">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Office 365 can immediately reject the messages with invalid recipients. This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery. Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="bd4ea-141">В [центре администрирования Exchange](https://docs.microsoft.com/Exchange/exchange-admin-center) в Office 365 отключите или удалите соединитель, который доставляет электронную почту из Office 365 в локальную почтовую среду:</span><span class="sxs-lookup"><span data-stu-id="bd4ea-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) in Office 365, disable or delete the connector that delivers email from Office 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="bd4ea-142">В центре администрирования Exchange перейдите в раздел **соединители** **поток** \> обработки почты.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="bd4ea-143">Выберите соединитель со значением " **от** " **Office 365** и укажите значение в поле " **Кому** " **почтового сервера организации** и выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="bd4ea-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="bd4ea-144">Удаление соединителя путем нажатия кнопки " **Удалить** ![значок удаления"](../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="bd4ea-144">Delete the connector by clicking **Delete** ![Remove icon](../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="bd4ea-145">Отключите соединитель, нажав кнопку **изменить** ![значок](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) редактирования и сняв флажок **включить**.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-145">Disable the connector by clicking **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and unchecking **Turn it on**.</span></span>

  - <span data-ttu-id="bd4ea-146">Изменение обслуживаемого домена в Office 365, связанного с локальной средой электронной почты, от **внутренней ретрансляции** к **удостоверяющему**.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-146">Change the accepted domain in Office 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="bd4ea-147">Инструкции см в разделе [Manage обслуживаемые домены в Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=785428).</span><span class="sxs-lookup"><span data-stu-id="bd4ea-147">For instructions, see [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=785428).</span></span>

  <span data-ttu-id="bd4ea-148">**Примечание**. как правило, для вступления в силу этих изменений требуется от 30 минут до одного часа.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-148">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="bd4ea-149">Через один час убедитесь, что сообщение об ошибке больше не отображается.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-149">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="bd4ea-150">Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных услуг), свяжитесь с ней, чтобы решить проблему.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="bd4ea-151">Код ошибки: 450 4.4.317 Не удается подключиться к удаленному серверу</span><span class="sxs-lookup"><span data-stu-id="bd4ea-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="bd4ea-152">Как правило, эта ошибка означает, что Office 365 подключен к конечному серверу электронной почты, но сервер ответил на немедленную ошибку или не соответствует требованиям к подключению.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-152">Typically, this error means Office 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="bd4ea-153">Описание проблемы см. в сведениях об ошибке.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-153">The error details will explain the problem.</span></span> <span data-ttu-id="bd4ea-154">Пример:</span><span class="sxs-lookup"><span data-stu-id="bd4ea-154">For example:</span></span>

- <span data-ttu-id="bd4ea-155">Конечный сервер электронной почты выдал сообщение об ошибке "Служба недоступна", которая указывает на то, что сервер не может поддерживать связь с Office 365.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Office 365.</span></span>

- <span data-ttu-id="bd4ea-156">Для соединителя настроено требование TLS, но конечный сервер электронной почты не поддерживает TLS.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="bd4ea-157">Как исправить ошибку с кодом 450 4.4.317?</span><span class="sxs-lookup"><span data-stu-id="bd4ea-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="bd4ea-158">Проверьте параметры TLS и сертификаты на локальных почтовых серверах и параметры TLS на соединителе.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="bd4ea-159">Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных услуг), свяжитесь с ней, чтобы решить проблему.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="bd4ea-160">Код ошибки: 450 4.4.318 Соединение было внезапно прервано</span><span class="sxs-lookup"><span data-stu-id="bd4ea-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="bd4ea-161">Как правило, эта ошибка означает, что в Office 365 возникают проблемы связи с локальной средой электронной почты, поэтому подключение было разорвано.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-161">Typically, this error means Office 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="bd4ea-162">Возможные причины этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="bd4ea-162">The possible causes for this error are:</span></span>

- <span data-ttu-id="bd4ea-163">Брандмауэр использует правила проверки пакетов SMTP, и эти правила работают неправильно.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="bd4ea-164">Локальный сервер электронной почты работает неправильно (например, служба зависает или недостаточными системными ресурсами), что приводит к превышению времени ожидания сервера и закрытию подключения к Office 365.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Office 365.</span></span>

- <span data-ttu-id="bd4ea-165">Проблемы с сетью между локальной средой и Office 365.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-165">There are network issues between your on-premises environment and Office 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="bd4ea-166">Как исправить ошибку с кодом 450 4.4.318?</span><span class="sxs-lookup"><span data-stu-id="bd4ea-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="bd4ea-167">Выясните, какой из этих пунктов относится к вам, и внесите необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="bd4ea-168">Если проблема возникает из-за проблем с сетью между локальной средой и Office 365, обратитесь к команде сети, чтобы устранить эту проблему.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-168">If the problem is caused by network issues between your on-premises environment and Office 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="bd4ea-169">Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных услуг), свяжитесь с ней, чтобы решить проблему.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="bd4ea-170">Код ошибки: 450 4.7.320 Не удалось проверить сертификат</span><span class="sxs-lookup"><span data-stu-id="bd4ea-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="bd4ea-171">Как правило, эта ошибка означает, что в Office 365 возникла ошибка при попытке проверить сертификат конечного сервера электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-171">Typically, this error means Office 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="bd4ea-172">Описание см. в сведениях об ошибке.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-172">The error details will explain the error.</span></span> <span data-ttu-id="bd4ea-173">Например:</span><span class="sxs-lookup"><span data-stu-id="bd4ea-173">For example:</span></span>

- <span data-ttu-id="bd4ea-174">Срок действия сертификата истек</span><span class="sxs-lookup"><span data-stu-id="bd4ea-174">Certificate expired</span></span>

- <span data-ttu-id="bd4ea-175">Субъект сертификата не совпадает с именем узла</span><span class="sxs-lookup"><span data-stu-id="bd4ea-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="bd4ea-176">Сертификат больше не действителен</span><span class="sxs-lookup"><span data-stu-id="bd4ea-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="bd4ea-177">Как исправить ошибку с кодом 450 4.7.320?</span><span class="sxs-lookup"><span data-stu-id="bd4ea-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="bd4ea-178">Исправьте сертификат или параметры на соединителе, чтобы можно было доставить сообщения в очереди в Office 365.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-178">Fix the certificate or the settings on the connector so that queued messages in Office 365 can be delivered.</span></span>

- <span data-ttu-id="bd4ea-179">Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных служб), свяжитесь с ней, чтобы решить проблему.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="bd4ea-180">Коды других ошибок</span><span class="sxs-lookup"><span data-stu-id="bd4ea-180">Other error codes</span></span>

<span data-ttu-id="bd4ea-181">Office 365 не удается доставить сообщения на локальный или партнерский сервер электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-181">Office 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="bd4ea-182">Используйте информацию **Конечный сервер** в сообщении об ошибке, чтобы устранить проблему в своей среде, или измените соединитель, если ошибка связана с конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-182">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="bd4ea-183">Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных услуг), свяжитесь с ней, чтобы решить проблему.</span><span class="sxs-lookup"><span data-stu-id="bd4ea-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
