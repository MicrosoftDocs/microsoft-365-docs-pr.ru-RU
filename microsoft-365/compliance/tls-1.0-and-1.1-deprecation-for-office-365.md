---
title: Прекращение поддержки протоколов TLS 1.0 и 1.1 в Office 365
description: Описываются устаревшие протоколы TLS 1,0 и 1,1 для Office 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: shmehta
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: ab3685883ac08522ab9ea1ee0cf194ba263d9166
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681693"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a><span data-ttu-id="fb52a-103">Прекращение поддержки протоколов TLS 1.0 и 1.1 в Office 365</span><span class="sxs-lookup"><span data-stu-id="fb52a-103">TLS 1.0 and 1.1 deprecation for Office 365</span></span>
> [!IMPORTANT]
> <span data-ttu-id="fb52a-104">Мы временно приостановили принудительное применение протокола TLS 1,0 и 1,1 для коммерческих клиентов из-за ковид-19, но в связи с тем, что цепочки поставки настроены, а некоторые страны открывают резервную копию, мы переустанавливая принудительное применение протокола TLS для начала работы с 15 октября, 2020 и up будут продолжаться на следующих неделях и месяцах.</span><span class="sxs-lookup"><span data-stu-id="fb52a-104">We temporarily halted deprecation enforcement of TLS 1.0 and 1.1 for commercial customers due to covid-19, but as supply chains have adjusted and certain countries open back up, we are resetting the TLS enforcement to begin Oct 15, 2020 and rollout will continue over the following weeks and months.</span></span> 

<span data-ttu-id="fb52a-105">На 31 октября 2018 протоколы TLS 1,0 и 1,1 не рекомендуются для службы Office 365.</span><span class="sxs-lookup"><span data-stu-id="fb52a-105">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Office 365 service.</span></span> <span data-ttu-id="fb52a-106">Ожидаемый результат для конечных пользователей должен быть минимальным.</span><span class="sxs-lookup"><span data-stu-id="fb52a-106">The effect for end-users is expected to be minimal.</span></span> <span data-ttu-id="fb52a-107">Это изменение было общедоступно за два года с первым общедоступным объявлением, выполненным в декабре 2017.</span><span class="sxs-lookup"><span data-stu-id="fb52a-107">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="fb52a-108">Эта статья предназначена только для того, чтобы охватить локального клиента Office 365 по отношению к службе Office 365, но также можно применить к локальным проблемам TLS при работе с Office и Office Online Server/Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="fb52a-108">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

## <a name="office-and-tls-overview"></a><span data-ttu-id="fb52a-109">Обзор Office и TLS</span><span class="sxs-lookup"><span data-stu-id="fb52a-109">Office and TLS overview</span></span>

<span data-ttu-id="fb52a-110">Клиент Office использует веб-службу Windows (WINHTTP) для отправки и получения трафика через протоколы TLS.</span><span class="sxs-lookup"><span data-stu-id="fb52a-110">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="fb52a-111">Клиент Office может использовать TLS 1,2, если веб-служба локального компьютера может использовать TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="fb52a-111">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="fb52a-112">Все клиенты Office могут использовать протоколы TLS, так как протоколы TLS и SSL являются частью операционной системы, а не только для клиента Office.</span><span class="sxs-lookup"><span data-stu-id="fb52a-112">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="fb52a-113">В Windows 8 и более поздних версиях</span><span class="sxs-lookup"><span data-stu-id="fb52a-113">On Windows 8 and later versions</span></span>

<span data-ttu-id="fb52a-114">По умолчанию протоколы TLS 1,2 и 1,1 доступны, если ни одно сетевое устройство не настроено для отклонения трафика TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="fb52a-114">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="fb52a-115">В Windows 7</span><span class="sxs-lookup"><span data-stu-id="fb52a-115">On Windows 7</span></span>

<span data-ttu-id="fb52a-116">Протоколы TLS 1,1 и 1,2 недоступны без обновления [KB 3140245](https://support.microsoft.com/help/3140245) .</span><span class="sxs-lookup"><span data-stu-id="fb52a-116">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="fb52a-117">Обновление устраняет эту ошибку и добавляет следующий подраздел реестра:</span><span class="sxs-lookup"><span data-stu-id="fb52a-117">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="fb52a-118">Пользователи Windows 7, у которых нет этого обновления, подвержены воздействию 31 октября 2018 г.</span><span class="sxs-lookup"><span data-stu-id="fb52a-118">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="fb52a-119">[Статья базы знаний 3140245](https://support.microsoft.com/help/3140245) содержит сведения о том, как изменить параметры WinHTTP для включения протоколов TLS.</span><span class="sxs-lookup"><span data-stu-id="fb52a-119">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="fb52a-120">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="fb52a-120">More information</span></span>

<span data-ttu-id="fb52a-121">Значение раздела реестра **DefaultSecureProtocols** , описанное в статье базы знаний, определяет, какие сетевые протоколы можно использовать:</span><span class="sxs-lookup"><span data-stu-id="fb52a-121">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="fb52a-122">Значение DefaultSecureProtocols</span><span class="sxs-lookup"><span data-stu-id="fb52a-122">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="fb52a-123">Протокол включен</span><span class="sxs-lookup"><span data-stu-id="fb52a-123">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="fb52a-124">0x00000008</span><span class="sxs-lookup"><span data-stu-id="fb52a-124">0x00000008</span></span>|<span data-ttu-id="fb52a-125">Включить протокол SSL 2.0 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb52a-125">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="fb52a-126">0x00000020</span><span class="sxs-lookup"><span data-stu-id="fb52a-126">0x00000020</span></span>|<span data-ttu-id="fb52a-127">Включить протокол SSL 3.0 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb52a-127">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="fb52a-128">0x00000080</span><span class="sxs-lookup"><span data-stu-id="fb52a-128">0x00000080</span></span>|<span data-ttu-id="fb52a-129">Включить протокол TLS 1.0 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb52a-129">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="fb52a-130">0x00000200</span><span class="sxs-lookup"><span data-stu-id="fb52a-130">0x00000200</span></span>|<span data-ttu-id="fb52a-131">Включить протокол TLS 1.1 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb52a-131">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="fb52a-132">0x00000800</span><span class="sxs-lookup"><span data-stu-id="fb52a-132">0x00000800</span></span>|<span data-ttu-id="fb52a-133">Включить протокол TLS 1.2 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb52a-133">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="fb52a-134">Разделы реестра для клиентов Office и TLS</span><span class="sxs-lookup"><span data-stu-id="fb52a-134">Office clients and TLS registry keys</span></span>

<span data-ttu-id="fb52a-135">Вы можете обратиться к статье [KB 4057306, которая готовится к обязательному использованию протокола TLS 1,2 в Office 365](https://support.microsoft.com/help/4057306).</span><span class="sxs-lookup"><span data-stu-id="fb52a-135">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="fb52a-136">Это общая статья для ИТ-администраторов, и она является официальной документацией по изменению TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="fb52a-136">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="fb52a-137">В следующей таблице приведены значения соответствующих разделов реестра в клиентах Office 365 после 31 октября 2018 г.</span><span class="sxs-lookup"><span data-stu-id="fb52a-137">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="fb52a-138">Включенные протоколы для службы Office 365 после 31 октября 2018 г.</span><span class="sxs-lookup"><span data-stu-id="fb52a-138">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="fb52a-139">Шестнадцатеричное значение</span><span class="sxs-lookup"><span data-stu-id="fb52a-139">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="fb52a-140">TLS 1,0 + 1,1 + 1,2</span><span class="sxs-lookup"><span data-stu-id="fb52a-140">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="fb52a-141">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="fb52a-141">0x00000A80</span></span>|
|<span data-ttu-id="fb52a-142">TLS 1,1 + 1,2</span><span class="sxs-lookup"><span data-stu-id="fb52a-142">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="fb52a-143">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="fb52a-143">0x00000A00</span></span>|
|<span data-ttu-id="fb52a-144">TLS 1,0 + 1,2</span><span class="sxs-lookup"><span data-stu-id="fb52a-144">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="fb52a-145">0x00000880</span><span class="sxs-lookup"><span data-stu-id="fb52a-145">0x00000880</span></span>|
|<span data-ttu-id="fb52a-146">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="fb52a-146">TLS 1.2</span></span>|<span data-ttu-id="fb52a-147">0x00000800</span><span class="sxs-lookup"><span data-stu-id="fb52a-147">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="fb52a-148">Мы не рекомендуем использовать протоколы SSL 2,0 и 3,0, которые также можно установить с помощью ключа **DefaultSecureProtocols** .</span><span class="sxs-lookup"><span data-stu-id="fb52a-148">We don't recommend that you use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="fb52a-149">Протоколы SSL 2,0 и 3,0 считаются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="fb52a-149">SSL 2.0 and 3.0 are considered deprecated protocols.</span></span> <span data-ttu-id="fb52a-150">Рекомендуется прекратить использование SSL 2,0 и SSL 3,0, хотя решение для этого в конечном итоге зависит от того, что соответствует требованиям к продукту.</span><span class="sxs-lookup"><span data-stu-id="fb52a-150">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="fb52a-151">Дополнительные сведения об уязвимостях SSL 3,0 см. в статье [KB 3009008](https://support.microsoft.com/help/3009008).</span><span class="sxs-lookup"><span data-stu-id="fb52a-151">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="fb52a-152">Вы можете использовать калькулятор Windows по умолчанию в режиме программиста для настройки одинаковых значений разделов реестра.</span><span class="sxs-lookup"><span data-stu-id="fb52a-152">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="fb52a-153">Для получения дополнительных сведений ознакомьтесь [с обновлением KB 3140245, чтобы включить протоколы tls 1,1 и tls 1,2 в качестве протоколов безопасности по умолчанию в WinHTTP в Windows](https://support.microsoft.com/help/3140245).</span><span class="sxs-lookup"><span data-stu-id="fb52a-153">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="fb52a-154">Независимо от того, установлено ли обновление для Windows 7 ([KB 3140245](https://support.microsoft.com/help/3140245)), подраздел реестра DefaultSecureProtocols отсутствует и должен быть добавлен вручную или через объект групповой политики (GPO).</span><span class="sxs-lookup"><span data-stu-id="fb52a-154">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="fb52a-155">То есть, если вам не нужно настраивать защищенные протоколы или запрещены, этот ключ не требуется.</span><span class="sxs-lookup"><span data-stu-id="fb52a-155">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="fb52a-156">Вам потребуется только обновление Windows 7 с пакетом обновления 1 (SP1) ([KB 3140245](https://support.microsoft.com/help/3140245)).</span><span class="sxs-lookup"><span data-stu-id="fb52a-156">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>
