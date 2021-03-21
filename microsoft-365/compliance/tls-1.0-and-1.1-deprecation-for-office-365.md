---
title: Отключение TLS 1.0 и 1.1 для Microsoft 365
description: Описывает Амортизации и отключения TLS 1.0 и 1.1 для Microsoft 365.
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
ms.openlocfilehash: 3d44e178d351942b4a178ddc1954ddd839665639
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919305"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a><span data-ttu-id="2e710-103">Отключение TLS 1.0 и 1.1 для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2e710-103">Disabling TLS 1.0 and 1.1 for Microsoft 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e710-104">Мы временно прекратили отключение TLS 1.0 и 1.1 для коммерческих клиентов из-за COVID-19.</span><span class="sxs-lookup"><span data-stu-id="2e710-104">We temporarily halted disablement of TLS 1.0 and 1.1 for commercial customers due to COVID-19.</span></span> <span data-ttu-id="2e710-105">По мере корректировки цепочек поставок и открытия некоторых стран 15 октября 2020 г. мы перезапустили запуск TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="2e710-105">As supply chains have adjusted and certain countries open back up, we restarted the TLS 1.2 enforcement rollout on October 15, 2020.</span></span> <span data-ttu-id="2e710-106">Выкатка будет продолжена в течение следующих недель и месяцев.</span><span class="sxs-lookup"><span data-stu-id="2e710-106">Rollout will continue over the following weeks and months.</span></span>

<span data-ttu-id="2e710-107">С 31 октября 2018 г. для службы Microsoft 365 отстает протоколы безопасности транспортных слоев (TLS) 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="2e710-107">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Microsoft 365 service.</span></span> <span data-ttu-id="2e710-108">Эффект для конечных пользователей минимальный.</span><span class="sxs-lookup"><span data-stu-id="2e710-108">The effect for end-users is minimal.</span></span> <span data-ttu-id="2e710-109">Это изменение было опубликовано более двух лет, с первым публичным объявлением, сделанным в декабре 2017 г.</span><span class="sxs-lookup"><span data-stu-id="2e710-109">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="2e710-110">Эта статья предназначена только для покрытия локального клиента Office 365 по отношению к службе Office 365, но также может применяться к локальным TLS-вопросам с веб-приложениями Office и Office Online Server/Office.</span><span class="sxs-lookup"><span data-stu-id="2e710-110">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

<span data-ttu-id="2e710-111">Для SharePoint и OneDrive необходимо обновить и настроить .NET для поддержки TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="2e710-111">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="2e710-112">Сведения см. [в том, как включить TLS 1.2 для клиентов.](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="2e710-112">For information, see [How to enable TLS 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="office-365-and-tls-overview"></a><span data-ttu-id="2e710-113">Обзор Office 365 и TLS</span><span class="sxs-lookup"><span data-stu-id="2e710-113">Office 365 and TLS overview</span></span>

<span data-ttu-id="2e710-114">Клиент Office использует веб-службу Windows (WINHTTP) для отправки и получения трафика по протоколам TLS.</span><span class="sxs-lookup"><span data-stu-id="2e710-114">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="2e710-115">Клиент Office может использовать TLS 1.2, если веб-служба локального компьютера может использовать TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="2e710-115">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="2e710-116">Все клиенты Office могут использовать TLS-протоколы, так как TLS и SSL-протоколы являются частью операционной системы и не являются специфическими для клиента Office.</span><span class="sxs-lookup"><span data-stu-id="2e710-116">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="2e710-117">В Windows 8 и более поздних версиях</span><span class="sxs-lookup"><span data-stu-id="2e710-117">On Windows 8 and later versions</span></span>

<span data-ttu-id="2e710-118">По умолчанию протоколы TLS 1.2 и 1.1 доступны, если не настроены сетевые устройства для отказа от трафика TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="2e710-118">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="2e710-119">В Windows 7</span><span class="sxs-lookup"><span data-stu-id="2e710-119">On Windows 7</span></span>

<span data-ttu-id="2e710-120">Протоколы TLS 1.1 и 1.2 недоступны без обновления [KB 3140245.](https://support.microsoft.com/help/3140245)</span><span class="sxs-lookup"><span data-stu-id="2e710-120">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="2e710-121">Обновление решает эту проблему и добавляет следующий под ключ реестра:</span><span class="sxs-lookup"><span data-stu-id="2e710-121">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="2e710-122">С 31 октября 2018 г. затронуты пользователи Windows 7, которые не имеют этого обновления.</span><span class="sxs-lookup"><span data-stu-id="2e710-122">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="2e710-123">[В KB 3140245](https://support.microsoft.com/help/3140245) есть сведения о том, как изменить параметры WINHTTP, чтобы включить протоколы TLS.</span><span class="sxs-lookup"><span data-stu-id="2e710-123">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="2e710-124">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="2e710-124">More information</span></span>

<span data-ttu-id="2e710-125">Значение ключа реестра **DefaultSecureProtocols,** описываемого в статье KB, определяет, какие сетевые протоколы можно использовать:</span><span class="sxs-lookup"><span data-stu-id="2e710-125">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="2e710-126">Значение DefaultSecureProtocols</span><span class="sxs-lookup"><span data-stu-id="2e710-126">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="2e710-127">Включен протокол</span><span class="sxs-lookup"><span data-stu-id="2e710-127">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="2e710-128">0x00000008</span><span class="sxs-lookup"><span data-stu-id="2e710-128">0x00000008</span></span>|<span data-ttu-id="2e710-129">Включить протокол SSL 2.0 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="2e710-129">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="2e710-130">0x00000020</span><span class="sxs-lookup"><span data-stu-id="2e710-130">0x00000020</span></span>|<span data-ttu-id="2e710-131">Включить протокол SSL 3.0 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="2e710-131">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="2e710-132">0x00000080</span><span class="sxs-lookup"><span data-stu-id="2e710-132">0x00000080</span></span>|<span data-ttu-id="2e710-133">Включить протокол TLS 1.0 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="2e710-133">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="2e710-134">0x00000200</span><span class="sxs-lookup"><span data-stu-id="2e710-134">0x00000200</span></span>|<span data-ttu-id="2e710-135">Включить протокол TLS 1.1 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="2e710-135">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="2e710-136">0x00000800</span><span class="sxs-lookup"><span data-stu-id="2e710-136">0x00000800</span></span>|<span data-ttu-id="2e710-137">Включить протокол TLS 1.2 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="2e710-137">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="2e710-138">Клиенты Office и ключи реестра TLS</span><span class="sxs-lookup"><span data-stu-id="2e710-138">Office clients and TLS registry keys</span></span>

<span data-ttu-id="2e710-139">Вы можете обратиться к [KB 4057306 Подготовка](https://support.microsoft.com/help/4057306)к обязательному использованию TLS 1.2 в Office 365 .</span><span class="sxs-lookup"><span data-stu-id="2e710-139">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="2e710-140">Это общая статья для ИТ-администраторов и это официальная документация об изменении TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="2e710-140">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="2e710-141">В следующей таблице показаны соответствующие ключевые значения реестра для клиентов Office 365 после 31 октября 2018 г.</span><span class="sxs-lookup"><span data-stu-id="2e710-141">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="2e710-142">Включенные протоколы для службы Office 365 после 31 октября 2018 г.</span><span class="sxs-lookup"><span data-stu-id="2e710-142">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="2e710-143">Hexadecimal value</span><span class="sxs-lookup"><span data-stu-id="2e710-143">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="2e710-144">TLS 1.0 + 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="2e710-144">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="2e710-145">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="2e710-145">0x00000A80</span></span>|
|<span data-ttu-id="2e710-146">TLS 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="2e710-146">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="2e710-147">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="2e710-147">0x00000A00</span></span>|
|<span data-ttu-id="2e710-148">TLS 1.0 + 1.2</span><span class="sxs-lookup"><span data-stu-id="2e710-148">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="2e710-149">0x00000880</span><span class="sxs-lookup"><span data-stu-id="2e710-149">0x00000880</span></span>|
|<span data-ttu-id="2e710-150">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="2e710-150">TLS 1.2</span></span>|<span data-ttu-id="2e710-151">0x00000800</span><span class="sxs-lookup"><span data-stu-id="2e710-151">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="2e710-152">Не используйте протоколы SSL 2.0 и 3.0, которые также можно установить с помощью **ключа DefaultSecureProtocols.**</span><span class="sxs-lookup"><span data-stu-id="2e710-152">Don't use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="2e710-153">Протоколы SSL 2.0 и 3.0 считаются устаревшими и небезопасными.</span><span class="sxs-lookup"><span data-stu-id="2e710-153">SSL 2.0 and 3.0 are considered outdated and insecure protocols.</span></span> <span data-ttu-id="2e710-154">Лучше всего прекратить использование SSL 2.0 и SSL 3.0, хотя решение об этом в конечном счете зависит от того, что наилучшим образом соответствует вашим потребностям продукта.</span><span class="sxs-lookup"><span data-stu-id="2e710-154">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="2e710-155">Дополнительные сведения об уязвимостях SSL 3.0 можно найти в [KB 3009008.](https://support.microsoft.com/help/3009008)</span><span class="sxs-lookup"><span data-stu-id="2e710-155">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="2e710-156">Вы можете использовать калькулятор Windows по умолчанию в режиме Программист, чтобы настроить те же ключевые значения реестра ссылок.</span><span class="sxs-lookup"><span data-stu-id="2e710-156">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="2e710-157">Дополнительные сведения см. в обновлении [KB 3140245, чтобы включить TLS 1.1 и TLS 1.2](https://support.microsoft.com/help/3140245)в качестве безопасных протоколов по умолчанию в WinHTTP в Windows .</span><span class="sxs-lookup"><span data-stu-id="2e710-157">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="2e710-158">Независимо от того, установлено или нет обновление Windows[7 (KB 3140245),](https://support.microsoft.com/help/3140245)под ключ реестра DefaultSecureProtocols не присутствует и должен быть добавлен вручную или через объект групповой политики (GPO).</span><span class="sxs-lookup"><span data-stu-id="2e710-158">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="2e710-159">То есть, если вам не придется настраивать, какие безопасные протоколы включены или ограничены, этот ключ не требуется.</span><span class="sxs-lookup"><span data-stu-id="2e710-159">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="2e710-160">Требуется только обновление Windows 7 SP1[(KB 3140245).](https://support.microsoft.com/help/3140245)</span><span class="sxs-lookup"><span data-stu-id="2e710-160">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a><span data-ttu-id="2e710-161">Обновление и настройка платформа .NET Framework для поддержки TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="2e710-161">Update and configure the .NET Framework to support TLS 1.2</span></span>

<span data-ttu-id="2e710-162">Чтобы использовать TLS 1.2, необходимо обновить приложения, вызываемые API Microsoft 365 по TLS 1.0 или TLS 1.1.</span><span class="sxs-lookup"><span data-stu-id="2e710-162">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="2e710-163">.NET 4.5 по умолчанию для TLS 1.1.</span><span class="sxs-lookup"><span data-stu-id="2e710-163">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="2e710-164">Чтобы обновить конфигурацию .NET, см. в руб. Как включить безопасность транспортного слоя [(TLS) 1.2 для клиентов.](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="2e710-164">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="more-information"></a><span data-ttu-id="2e710-165">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="2e710-165">More information</span></span>

<span data-ttu-id="2e710-166">Дополнительные сведения см. в статью Подготовка к обязательному использованию [TLS 1.2 в Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="2e710-166">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>