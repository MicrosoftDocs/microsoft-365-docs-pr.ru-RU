---
title: Отключение TLS 1.0 и 1.1 для Microsoft 365
description: Описывается отключение и отключение TLS 1.0 и 1.1 для Microsoft 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: fasqiu
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 669ab53739bfd108bdbe9077762272e6a4901865
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233101"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a><span data-ttu-id="420f0-103">Отключение TLS 1.0 и 1.1 для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="420f0-103">Disabling TLS 1.0 and 1.1 for Microsoft 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="420f0-104">Мы временно остановили отключение TLS 1.0 и 1.1 для коммерческих клиентов из-за COVID-19.</span><span class="sxs-lookup"><span data-stu-id="420f0-104">We temporarily halted disablement of TLS 1.0 and 1.1 for commercial customers due to COVID-19.</span></span> <span data-ttu-id="420f0-105">По мере того как цепочки поставок скорректированы и некоторые страны открывают их, 15 октября 2020 г. мы перезапустили обязательное исполнение TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="420f0-105">As supply chains have adjusted and certain countries open back up, we restarted the TLS 1.2 enforcement rollout on October 15, 2020.</span></span> <span data-ttu-id="420f0-106">Выкат будет продолжен в течение следующих недель и месяцев.</span><span class="sxs-lookup"><span data-stu-id="420f0-106">Rollout will continue over the following weeks and months.</span></span>

<span data-ttu-id="420f0-107">С 31 октября 2018 г. протоколы TLS 1.0 и 1.1 являются неподготовленными для службы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="420f0-107">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Microsoft 365 service.</span></span> <span data-ttu-id="420f0-108">Эффект для конечных пользователей минимальный.</span><span class="sxs-lookup"><span data-stu-id="420f0-108">The effect for end-users is minimal.</span></span> <span data-ttu-id="420f0-109">Это изменение было опубликовано в течение двух лет с первым общедоступным объявлением, сделанным в декабре 2017 г.</span><span class="sxs-lookup"><span data-stu-id="420f0-109">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="420f0-110">Эта статья предназначена только для локального клиента Office 365 относительно службы Office 365, но также может применяться к локальным вопросам TLS в Office и Office Online Server/Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="420f0-110">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

<span data-ttu-id="420f0-111">Для SharePoint и OneDrive необходимо обновить и настроить .NET для поддержки TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="420f0-111">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="420f0-112">Сведения см. в [том, как включить TLS 1.2 на клиентах.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="420f0-112">For information, see [How to enable TLS 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="office-365-and-tls-overview"></a><span data-ttu-id="420f0-113">Обзор Office 365 и TLS</span><span class="sxs-lookup"><span data-stu-id="420f0-113">Office 365 and TLS overview</span></span>

<span data-ttu-id="420f0-114">Клиент Office использует веб-службу Windows (WINHTTP) для отправки и получения трафика по протоколам TLS.</span><span class="sxs-lookup"><span data-stu-id="420f0-114">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="420f0-115">Клиент Office может использовать TLS 1.2, если веб-служба локального компьютера может использовать TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="420f0-115">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="420f0-116">Все клиенты Office могут использовать протоколы TLS, так как протоколы TLS и SSL являются частью операционной системы и не являются специфическими для клиента Office.</span><span class="sxs-lookup"><span data-stu-id="420f0-116">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="420f0-117">В Windows 8 и более поздних версиях</span><span class="sxs-lookup"><span data-stu-id="420f0-117">On Windows 8 and later versions</span></span>

<span data-ttu-id="420f0-118">По умолчанию протоколы TLS 1.2 и 1.1 доступны, если сетевые устройства не настроены на отклонение трафика TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="420f0-118">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="420f0-119">В Windows 7</span><span class="sxs-lookup"><span data-stu-id="420f0-119">On Windows 7</span></span>

<span data-ttu-id="420f0-120">Протоколы TLS 1.1 и 1.2 недоступны без обновления [KB 3140245.](https://support.microsoft.com/help/3140245)</span><span class="sxs-lookup"><span data-stu-id="420f0-120">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="420f0-121">Обновление решает эту проблему и добавляет следующий под ключ реестра:</span><span class="sxs-lookup"><span data-stu-id="420f0-121">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="420f0-122">С 31 октября 2018 г. затронут пользователи Windows 7, у которых нет этого обновления.</span><span class="sxs-lookup"><span data-stu-id="420f0-122">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="420f0-123">[В KB 3140245](https://support.microsoft.com/help/3140245) есть сведения об изменении параметров WINHTTP, чтобы включить протоколы TLS.</span><span class="sxs-lookup"><span data-stu-id="420f0-123">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="420f0-124">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="420f0-124">More information</span></span>

<span data-ttu-id="420f0-125">Значение ключа реестра **DefaultSecureProtocols,** описанного в статье КБ, определяет, какие сетевые протоколы можно использовать:</span><span class="sxs-lookup"><span data-stu-id="420f0-125">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="420f0-126">Значение DefaultSecureProtocols</span><span class="sxs-lookup"><span data-stu-id="420f0-126">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="420f0-127">Протокол включен</span><span class="sxs-lookup"><span data-stu-id="420f0-127">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="420f0-128">0x00000008</span><span class="sxs-lookup"><span data-stu-id="420f0-128">0x00000008</span></span>|<span data-ttu-id="420f0-129">Включить протокол SSL 2.0 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="420f0-129">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="420f0-130">0x00000020</span><span class="sxs-lookup"><span data-stu-id="420f0-130">0x00000020</span></span>|<span data-ttu-id="420f0-131">Включить протокол SSL 3.0 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="420f0-131">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="420f0-132">0x00000080</span><span class="sxs-lookup"><span data-stu-id="420f0-132">0x00000080</span></span>|<span data-ttu-id="420f0-133">Включить протокол TLS 1.0 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="420f0-133">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="420f0-134">0x00000200</span><span class="sxs-lookup"><span data-stu-id="420f0-134">0x00000200</span></span>|<span data-ttu-id="420f0-135">Включить протокол TLS 1.1 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="420f0-135">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="420f0-136">0x00000800</span><span class="sxs-lookup"><span data-stu-id="420f0-136">0x00000800</span></span>|<span data-ttu-id="420f0-137">Включить протокол TLS 1.2 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="420f0-137">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="420f0-138">Клиенты Office и ключи реестра TLS</span><span class="sxs-lookup"><span data-stu-id="420f0-138">Office clients and TLS registry keys</span></span>

<span data-ttu-id="420f0-139">Вы можете обратиться к [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span><span class="sxs-lookup"><span data-stu-id="420f0-139">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="420f0-140">Это общая статья для ИТ-администраторов и ее официальной документации об изменении TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="420f0-140">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="420f0-141">В следующей таблице показаны соответствующие значения ключей реестра в клиентах Office 365 после 31 октября 2018 г.</span><span class="sxs-lookup"><span data-stu-id="420f0-141">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="420f0-142">Включенные протоколы для службы Office 365 после 31 октября 2018 г.</span><span class="sxs-lookup"><span data-stu-id="420f0-142">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="420f0-143">Hexadecimal value</span><span class="sxs-lookup"><span data-stu-id="420f0-143">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="420f0-144">TLS 1.0 + 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="420f0-144">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="420f0-145">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="420f0-145">0x00000A80</span></span>|
|<span data-ttu-id="420f0-146">TLS 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="420f0-146">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="420f0-147">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="420f0-147">0x00000A00</span></span>|
|<span data-ttu-id="420f0-148">TLS 1.0 + 1.2</span><span class="sxs-lookup"><span data-stu-id="420f0-148">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="420f0-149">0x00000880</span><span class="sxs-lookup"><span data-stu-id="420f0-149">0x00000880</span></span>|
|<span data-ttu-id="420f0-150">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="420f0-150">TLS 1.2</span></span>|<span data-ttu-id="420f0-151">0x00000800</span><span class="sxs-lookup"><span data-stu-id="420f0-151">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="420f0-152">Не используйте протоколы SSL 2.0 и 3.0, которые также можно настроить с помощью ключа **DefaultSecureProtocols.**</span><span class="sxs-lookup"><span data-stu-id="420f0-152">Don't use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="420f0-153">Протоколы SSL 2.0 и 3.0 считаются устаревшими и небезопасными протоколами.</span><span class="sxs-lookup"><span data-stu-id="420f0-153">SSL 2.0 and 3.0 are considered outdated and insecure protocols.</span></span> <span data-ttu-id="420f0-154">Лучше всего прекратить использование SSL 2.0 и SSL 3.0, хотя решение об этом в конечном итоге зависит от того, что лучше всего соответствует потребностям вашего продукта.</span><span class="sxs-lookup"><span data-stu-id="420f0-154">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="420f0-155">Дополнительные сведения об уязвимостях SSL 3.0 можно найти в [KB 3009008.](https://support.microsoft.com/help/3009008)</span><span class="sxs-lookup"><span data-stu-id="420f0-155">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="420f0-156">Вы можете использовать калькулятор Windows по умолчанию в режиме программиста, чтобы настроить одинаковые значения эталонного ключа реестра.</span><span class="sxs-lookup"><span data-stu-id="420f0-156">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="420f0-157">Дополнительные сведения см. в обновлении [KB 3140245, чтобы включить протоколы TLS 1.1 и TLS 1.2](https://support.microsoft.com/help/3140245)в качестве протоколов безопасности по умолчанию в WinHTTP в Windows.</span><span class="sxs-lookup"><span data-stu-id="420f0-157">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="420f0-158">Независимо от того, установлено ли обновление Windows[7 (KB 3140245),](https://support.microsoft.com/help/3140245)подразрядный ключ реестра DefaultSecureProtocols не существует и должен быть добавлен вручную или с помощью объекта групповой политики (GPO).</span><span class="sxs-lookup"><span data-stu-id="420f0-158">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="420f0-159">То есть, если вам не нужно настраивать протоколы безопасности, которые включены или ограничены, этот ключ не требуется.</span><span class="sxs-lookup"><span data-stu-id="420f0-159">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="420f0-160">Вам потребуется только обновление Windows 7 с sp1[(KB 3140245).](https://support.microsoft.com/help/3140245)</span><span class="sxs-lookup"><span data-stu-id="420f0-160">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a><span data-ttu-id="420f0-161">Обновление и настройка .NET Framework для поддержки TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="420f0-161">Update and configure the .NET Framework to support TLS 1.2</span></span>

<span data-ttu-id="420f0-162">Вам потребуется обновить приложения, которые звонят API Microsoft 365 по TLS 1.0 или TLS 1.1, чтобы использовать TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="420f0-162">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="420f0-163">.NET 4.5 по умолчанию TLS 1.1.</span><span class="sxs-lookup"><span data-stu-id="420f0-163">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="420f0-164">Чтобы обновить конфигурацию .NET, узнайте, как включить [TLS 1.2 на клиентах.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="420f0-164">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="more-information"></a><span data-ttu-id="420f0-165">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="420f0-165">More information</span></span>

<span data-ttu-id="420f0-166">Дополнительные сведения см. в подготовии к обязательному использованию [TLS 1.2 в Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="420f0-166">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>
