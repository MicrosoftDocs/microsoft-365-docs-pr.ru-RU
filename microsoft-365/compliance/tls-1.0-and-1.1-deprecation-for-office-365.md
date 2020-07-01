---
title: Устаревшие протоколы TLS 1,0 и 1,1 для Office 365
description: Описываются устаревшие протоколы TLS 1,0 и 1,1 для Office 365.
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: v-six
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 611b6970c3ecb95f4cdf046b96a5e3aa9155391d
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "44937347"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a><span data-ttu-id="42bc3-103">Устаревшие протоколы TLS 1,0 и 1,1 для Office 365</span><span class="sxs-lookup"><span data-stu-id="42bc3-103">TLS 1.0 and 1.1 deprecation for Office 365</span></span>

<span data-ttu-id="42bc3-104">На 31 октября 2018 протоколы TLS 1,0 и 1,1 не рекомендуются для службы Office 365.</span><span class="sxs-lookup"><span data-stu-id="42bc3-104">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Office 365 service.</span></span> <span data-ttu-id="42bc3-105">Ожидаемый результат для конечных пользователей должен быть минимальным.</span><span class="sxs-lookup"><span data-stu-id="42bc3-105">The effect for end-users is expected to be minimal.</span></span> <span data-ttu-id="42bc3-106">Это изменение было общедоступно в течение двух лет с первым общедоступным объявлением, выполненным в декабре 2017.</span><span class="sxs-lookup"><span data-stu-id="42bc3-106">This change was publicized for almost two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="42bc3-107">Эта статья предназначена только для того, чтобы охватить локального клиента Office 365 по отношению к службе Office 365, но также можно применить к локальным проблемам TLS при работе с Office и Office Online Server/Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="42bc3-107">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

## <a name="office-and-tls-overview"></a><span data-ttu-id="42bc3-108">Обзор Office и TLS</span><span class="sxs-lookup"><span data-stu-id="42bc3-108">Office and TLS overview</span></span>

<span data-ttu-id="42bc3-109">Клиент Office использует веб-службу Windows (WINHTTP) для отправки и получения трафика через протоколы TLS.</span><span class="sxs-lookup"><span data-stu-id="42bc3-109">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="42bc3-110">Клиент Office может использовать TLS 1,2, если веб-служба локального компьютера может использовать TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="42bc3-110">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="42bc3-111">Все клиенты Office могут использовать протоколы TLS, так как протоколы TLS и SSL являются частью операционной системы, а не только для клиента Office.</span><span class="sxs-lookup"><span data-stu-id="42bc3-111">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="42bc3-112">В Windows 8 и более поздних версиях</span><span class="sxs-lookup"><span data-stu-id="42bc3-112">On Windows 8 and later versions</span></span>

<span data-ttu-id="42bc3-113">По умолчанию протоколы TLS 1,2 и 1,1 доступны, если ни одно сетевое устройство не настроено для отклонения трафика TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="42bc3-113">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="42bc3-114">В Windows 7</span><span class="sxs-lookup"><span data-stu-id="42bc3-114">On Windows 7</span></span>

<span data-ttu-id="42bc3-115">Протоколы TLS 1,1 и 1,2 недоступны без обновления [KB 3140245](https://support.microsoft.com/help/3140245) .</span><span class="sxs-lookup"><span data-stu-id="42bc3-115">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="42bc3-116">Обновление устраняет эту ошибку и добавляет следующий подраздел реестра:</span><span class="sxs-lookup"><span data-stu-id="42bc3-116">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="42bc3-117">Пользователи Windows 7, у которых нет этого обновления, подвержены воздействию 31 октября 2018 г.</span><span class="sxs-lookup"><span data-stu-id="42bc3-117">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="42bc3-118">[Статья базы знаний 3140245](https://support.microsoft.com/help/3140245) содержит сведения о том, как изменить параметры WinHTTP для включения протоколов TLS.</span><span class="sxs-lookup"><span data-stu-id="42bc3-118">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="42bc3-119">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="42bc3-119">More information</span></span>

<span data-ttu-id="42bc3-120">Значение раздела реестра **DefaultSecureProtocols** , описанное в статье базы знаний, определяет, какие сетевые протоколы можно использовать:</span><span class="sxs-lookup"><span data-stu-id="42bc3-120">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="42bc3-121">Значение DefaultSecureProtocols</span><span class="sxs-lookup"><span data-stu-id="42bc3-121">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="42bc3-122">Протокол включен</span><span class="sxs-lookup"><span data-stu-id="42bc3-122">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="42bc3-123">0x00000008</span><span class="sxs-lookup"><span data-stu-id="42bc3-123">0x00000008</span></span>|<span data-ttu-id="42bc3-124">Включить протокол SSL 2.0 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="42bc3-124">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="42bc3-125">0x00000020</span><span class="sxs-lookup"><span data-stu-id="42bc3-125">0x00000020</span></span>|<span data-ttu-id="42bc3-126">Включить протокол SSL 3.0 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="42bc3-126">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="42bc3-127">0x00000080</span><span class="sxs-lookup"><span data-stu-id="42bc3-127">0x00000080</span></span>|<span data-ttu-id="42bc3-128">Включить протокол TLS 1.0 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="42bc3-128">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="42bc3-129">0x00000200</span><span class="sxs-lookup"><span data-stu-id="42bc3-129">0x00000200</span></span>|<span data-ttu-id="42bc3-130">Включить протокол TLS 1.1 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="42bc3-130">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="42bc3-131">0x00000800</span><span class="sxs-lookup"><span data-stu-id="42bc3-131">0x00000800</span></span>|<span data-ttu-id="42bc3-132">Включить протокол TLS 1.2 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="42bc3-132">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="42bc3-133">Разделы реестра для клиентов Office и TLS</span><span class="sxs-lookup"><span data-stu-id="42bc3-133">Office clients and TLS registry keys</span></span>

<span data-ttu-id="42bc3-134">Вы можете обратиться к статье [KB 4057306, которая готовится к обязательному использованию протокола TLS 1,2 в Office 365](https://support.microsoft.com/help/4057306).</span><span class="sxs-lookup"><span data-stu-id="42bc3-134">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="42bc3-135">Это общая статья для ИТ-администраторов, и она является официальной документацией по изменению TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="42bc3-135">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="42bc3-136">В следующей таблице приведены значения соответствующих разделов реестра в клиентах Office 365 после 31 октября 2018 г.</span><span class="sxs-lookup"><span data-stu-id="42bc3-136">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="42bc3-137">Включенные протоколы для службы Office 365 после 31 октября 2018 г.</span><span class="sxs-lookup"><span data-stu-id="42bc3-137">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="42bc3-138">Шестнадцатеричное значение</span><span class="sxs-lookup"><span data-stu-id="42bc3-138">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="42bc3-139">TLS 1,0 + 1,1 + 1,2</span><span class="sxs-lookup"><span data-stu-id="42bc3-139">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="42bc3-140">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="42bc3-140">0x00000A80</span></span>|
|<span data-ttu-id="42bc3-141">TLS 1,1 + 1,2</span><span class="sxs-lookup"><span data-stu-id="42bc3-141">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="42bc3-142">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="42bc3-142">0x00000A00</span></span>|
|<span data-ttu-id="42bc3-143">TLS 1,0 + 1,2</span><span class="sxs-lookup"><span data-stu-id="42bc3-143">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="42bc3-144">0x00000880</span><span class="sxs-lookup"><span data-stu-id="42bc3-144">0x00000880</span></span>|
|<span data-ttu-id="42bc3-145">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="42bc3-145">TLS 1.2</span></span>|<span data-ttu-id="42bc3-146">0x00000800</span><span class="sxs-lookup"><span data-stu-id="42bc3-146">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="42bc3-147">Мы не рекомендуем использовать протоколы SSL 2,0 и 3,0, которые также можно установить с помощью ключа **DefaultSecureProtocols** .</span><span class="sxs-lookup"><span data-stu-id="42bc3-147">We don't recommend that you use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="42bc3-148">Протоколы SSL 2,0 и 3,0 считаются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="42bc3-148">SSL 2.0 and 3.0 are considered deprecated protocols.</span></span> <span data-ttu-id="42bc3-149">Рекомендуется прекратить использование SSL 2,0 и SSL 3,0, хотя решение для этого в конечном итоге зависит от того, что соответствует требованиям к продукту.</span><span class="sxs-lookup"><span data-stu-id="42bc3-149">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="42bc3-150">Дополнительные сведения об уязвимостях SSL 3,0 см. в статье [KB 3009008](https://support.microsoft.com/help/3009008).</span><span class="sxs-lookup"><span data-stu-id="42bc3-150">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="42bc3-151">Вы можете использовать калькулятор Windows по умолчанию в режиме программиста для настройки одинаковых значений разделов реестра.</span><span class="sxs-lookup"><span data-stu-id="42bc3-151">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="42bc3-152">Для получения дополнительных сведений ознакомьтесь [с обновлением KB 3140245, чтобы включить протоколы tls 1,1 и tls 1,2 в качестве протоколов безопасности по умолчанию в WinHTTP в Windows](https://support.microsoft.com/help/3140245).</span><span class="sxs-lookup"><span data-stu-id="42bc3-152">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="42bc3-153">Независимо от того, установлено ли обновление для Windows 7 ([KB 3140245](https://support.microsoft.com/help/3140245)), подраздел реестра DefaultSecureProtocols отсутствует и должен быть добавлен вручную или через объект групповой политики (GPO).</span><span class="sxs-lookup"><span data-stu-id="42bc3-153">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="42bc3-154">То есть, если вам не нужно настраивать защищенные протоколы или запрещены, этот ключ не требуется.</span><span class="sxs-lookup"><span data-stu-id="42bc3-154">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="42bc3-155">Вам потребуется только обновление Windows 7 с пакетом обновления 1 (SP1) ([KB 3140245](https://support.microsoft.com/help/3140245)).</span><span class="sxs-lookup"><span data-stu-id="42bc3-155">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>
