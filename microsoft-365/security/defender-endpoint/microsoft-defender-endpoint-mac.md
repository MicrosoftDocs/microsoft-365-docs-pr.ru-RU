---
title: Microsoft Defender для конечной точки на Mac
ms.reviewer: ''
description: Узнайте, как установить, настроить, обновить и использовать Microsoft Defender для конечной точки на Mac.
keywords: Microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamf, macos, big sur, catalina, mojave, mde for mac
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 406a0e699ea563670f41355d122aa54ba8667a0e
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687749"
---
# <a name="microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="44d7f-104">Microsoft Defender для конечной точки на Mac</span><span class="sxs-lookup"><span data-stu-id="44d7f-104">Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="44d7f-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="44d7f-105">**Applies to:**</span></span>
- [<span data-ttu-id="44d7f-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="44d7f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="44d7f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="44d7f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="44d7f-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="44d7f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="44d7f-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="44d7f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="44d7f-110">В этом разделе описывается установка, настройка, обновление и использование Defender для конечной точки на Mac.</span><span class="sxs-lookup"><span data-stu-id="44d7f-110">This topic describes how to install, configure, update, and use Defender for Endpoint on Mac.</span></span>

> [!CAUTION]
> <span data-ttu-id="44d7f-111">Запуск других сторонних продуктов защиты конечной точки наряду с Microsoft Defender для конечной точки на Mac может привести к проблемам с производительностью и непредсказуемым побочным эффектам.</span><span class="sxs-lookup"><span data-stu-id="44d7f-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint on Mac is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="44d7f-112">Если защита конечной точки не microsoft является абсолютным требованием в вашей среде, вы можете безопасно использовать функции Defender для конечной точки на Mac EDR после настройки функции антивируса для запуска в пассивном [режиме.](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="44d7f-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint on Mac EDR functionality after configuring the antivirus functionality to run in [Passive mode](mac-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="whats-new-in-the-latest-release"></a><span data-ttu-id="44d7f-113">Новые возможности последнего выпуска</span><span class="sxs-lookup"><span data-stu-id="44d7f-113">What’s new in the latest release</span></span>

[<span data-ttu-id="44d7f-114">Новые возможности Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="44d7f-114">What's new in Microsoft Defender for Endpoint</span></span>](whats-new-in-microsoft-defender-atp.md)

[<span data-ttu-id="44d7f-115">Новые возможности в Microsoft Defender для конечной точки на Mac</span><span class="sxs-lookup"><span data-stu-id="44d7f-115">What's new in Microsoft Defender for Endpoint on Mac</span></span>](mac-whatsnew.md)

> [!TIP]
> <span data-ttu-id="44d7f-116">Если у вас есть какие-либо отзывы, которые вы хотели бы поделиться, отправьте его, открыв Microsoft Defender для конечной точки на Mac на устройстве и навигации, чтобы **помочь**  >  **отправить обратную связь**.</span><span class="sxs-lookup"><span data-stu-id="44d7f-116">If you have any feedback that you would like to share, submit it by opening Microsoft Defender for Endpoint on Mac on your device and navigating to **Help** > **Send feedback**.</span></span>

<span data-ttu-id="44d7f-117">Чтобы получить последние функции, в том числе возможности предварительного просмотра (например, обнаружение конечных точек и ответы для устройств Mac), настройте устройство macOS под управлением Microsoft Defender для endpoint как устройство "Insider".</span><span class="sxs-lookup"><span data-stu-id="44d7f-117">To get the latest features, including preview capabilities (such as endpoint detection and response for your Mac devices), configure your macOS device running Microsoft Defender for Endpoint to be an "Insider" device.</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="44d7f-118">Установка Microsoft Defender для конечной точки на Mac</span><span class="sxs-lookup"><span data-stu-id="44d7f-118">How to install Microsoft Defender for Endpoint on Mac</span></span>

### <a name="prerequisites"></a><span data-ttu-id="44d7f-119">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="44d7f-119">Prerequisites</span></span>

- <span data-ttu-id="44d7f-120">Подписка на конечную точку Defender и доступ к порталу Центра безопасности Защитника Майкрософт</span><span class="sxs-lookup"><span data-stu-id="44d7f-120">A Defender for Endpoint subscription and access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="44d7f-121">Опыт начального уровня в скриптах macOS и BASH</span><span class="sxs-lookup"><span data-stu-id="44d7f-121">Beginner-level experience in macOS and BASH scripting</span></span>
- <span data-ttu-id="44d7f-122">Административные привилегии на устройстве (в случае ручного развертывания)</span><span class="sxs-lookup"><span data-stu-id="44d7f-122">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="44d7f-123">Инструкции по установке</span><span class="sxs-lookup"><span data-stu-id="44d7f-123">Installation instructions</span></span>

<span data-ttu-id="44d7f-124">Существует несколько методов и средств развертывания, которые можно использовать для установки и настройки Defender для конечной точки на Mac.</span><span class="sxs-lookup"><span data-stu-id="44d7f-124">There are several methods and deployment tools that you can use to install and configure Defender for Endpoint on Mac.</span></span>

- <span data-ttu-id="44d7f-125">Средства управления сторонними средствами управления:</span><span class="sxs-lookup"><span data-stu-id="44d7f-125">Third-party management tools:</span></span>
    - [<span data-ttu-id="44d7f-126">Развертывание на основе Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="44d7f-126">Microsoft Intune-based deployment</span></span>](mac-install-with-intune.md)
    - [<span data-ttu-id="44d7f-127">Развертывание на основе JAMF</span><span class="sxs-lookup"><span data-stu-id="44d7f-127">JAMF-based deployment</span></span>](mac-install-with-jamf.md)
    - [<span data-ttu-id="44d7f-128">Другие продукты MDM</span><span class="sxs-lookup"><span data-stu-id="44d7f-128">Other MDM products</span></span>](mac-install-with-other-mdm.md)

- <span data-ttu-id="44d7f-129">Средство командной строки:</span><span class="sxs-lookup"><span data-stu-id="44d7f-129">Command-line tool:</span></span>
    - [<span data-ttu-id="44d7f-130">Ручное развертывание</span><span class="sxs-lookup"><span data-stu-id="44d7f-130">Manual deployment</span></span>](mac-install-manually.md)

### <a name="system-requirements"></a><span data-ttu-id="44d7f-131">Требования к системе</span><span class="sxs-lookup"><span data-stu-id="44d7f-131">System requirements</span></span>

<span data-ttu-id="44d7f-132">Поддерживаются три последних основных выпуска macOS.</span><span class="sxs-lookup"><span data-stu-id="44d7f-132">The three most recent major releases of macOS are supported.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44d7f-133">В macOS 11 (Big Sur) Microsoft Defender для конечной точки требует дополнительных профилей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="44d7f-133">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="44d7f-134">Если вы существующий клиент, обновляющийся из более ранних версий macOS, не забудьте развернуть дополнительные профили конфигурации, перечисленные в новых профилях конфигурации для [macOS Catalina](mac-sysext-policies.md)и более новых версиях macOS.</span><span class="sxs-lookup"><span data-stu-id="44d7f-134">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [New configuration profiles for macOS Catalina and newer versions of macOS](mac-sysext-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44d7f-135">Поддержка macOS 10.13 (High Sierra) прекращена с 15 февраля 2021 г.</span><span class="sxs-lookup"><span data-stu-id="44d7f-135">Support for macOS 10.13 (High Sierra) has been discontinued as of February 15th, 2021.</span></span>

- <span data-ttu-id="44d7f-136">11 (Big Sur), 10.15 (Каталина), 10.14 (Mojave)</span><span class="sxs-lookup"><span data-stu-id="44d7f-136">11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave)</span></span>
- <span data-ttu-id="44d7f-137">Пространство диска: 1 ГБ</span><span class="sxs-lookup"><span data-stu-id="44d7f-137">Disk space: 1GB</span></span>

<span data-ttu-id="44d7f-138">Бета-версии macOS не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="44d7f-138">Beta versions of macOS are not supported.</span></span>

<span data-ttu-id="44d7f-139">После включения службы может потребоваться настроить сеть или брандмауэр, чтобы разрешить исходящие подключения между ней и конечными точками.</span><span class="sxs-lookup"><span data-stu-id="44d7f-139">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="44d7f-140">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="44d7f-140">Licensing requirements</span></span>

<span data-ttu-id="44d7f-141">Microsoft Defender для конечной точки на Mac требует одно из следующих предложений по лицензированию объемов Microsoft:</span><span class="sxs-lookup"><span data-stu-id="44d7f-141">Microsoft Defender for Endpoint on Mac requires one of the following Microsoft Volume Licensing offers:</span></span>

- <span data-ttu-id="44d7f-142">Microsoft 365 E5 (M365 E5)</span><span class="sxs-lookup"><span data-stu-id="44d7f-142">Microsoft 365 E5 (M365 E5)</span></span>
- <span data-ttu-id="44d7f-143">Безопасность Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="44d7f-143">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="44d7f-144">Microsoft 365 A5 (M365 A5)</span><span class="sxs-lookup"><span data-stu-id="44d7f-144">Microsoft 365 A5 (M365 A5)</span></span>

> [!NOTE]
> <span data-ttu-id="44d7f-145">Лицензированные пользователи могут использовать Microsoft Defender для конечной точки на пяти одновременном устройстве.</span><span class="sxs-lookup"><span data-stu-id="44d7f-145">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="44d7f-146">Microsoft Defender для конечной точки также доступен для покупки у поставщика облачных решений (CSP).</span><span class="sxs-lookup"><span data-stu-id="44d7f-146">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span> <span data-ttu-id="44d7f-147">При покупке через CSP не требуется перечисление предложений microsoft Volume Licensing.</span><span class="sxs-lookup"><span data-stu-id="44d7f-147">When purchased via a CSP, it does not require Microsoft Volume Licensing offers listed.</span></span>

### <a name="network-connections"></a><span data-ttu-id="44d7f-148">Сетевые соединения.</span><span class="sxs-lookup"><span data-stu-id="44d7f-148">Network connections</span></span>

<span data-ttu-id="44d7f-149">В следующей загружаемой таблице перечислены службы и связанные с ними URL-адреса, к которые должна подключаться ваша сеть.</span><span class="sxs-lookup"><span data-stu-id="44d7f-149">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="44d7f-150">Необходимо убедиться, что нет правил фильтрации брандмауэра или сети, которые бы  отказывали в доступе к этим URL-адресам, или вам может потребоваться создать правило разрешить специально для них.</span><span class="sxs-lookup"><span data-stu-id="44d7f-150">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>



|<span data-ttu-id="44d7f-151">**Таблица списка доменов**</span><span class="sxs-lookup"><span data-stu-id="44d7f-151">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="44d7f-152">**Description**</span><span class="sxs-lookup"><span data-stu-id="44d7f-152">**Description**</span></span>|
|:-----|:-----|
|![Изображение пальца для таблицы URL-адресов Microsoft Defender для конечных точек](images/mdatp-urls.png)<br/>  | <span data-ttu-id="44d7f-154">Таблица определенных DNS-записей для расположения служб, географических местоположений и ОС.</span><span class="sxs-lookup"><span data-stu-id="44d7f-154">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br><span data-ttu-id="44d7f-155">Скачайте таблицу здесь: [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).</span><span class="sxs-lookup"><span data-stu-id="44d7f-155">Download the spreadsheet here: [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).</span></span>

<span data-ttu-id="44d7f-156">Microsoft Defender для конечной точки может открыть прокси-сервер с помощью следующих методов обнаружения:</span><span class="sxs-lookup"><span data-stu-id="44d7f-156">Microsoft Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="44d7f-157">Прокси-автоконфиг (PAC)</span><span class="sxs-lookup"><span data-stu-id="44d7f-157">Proxy autoconfig (PAC)</span></span>
- <span data-ttu-id="44d7f-158">Протокол автообнаружия веб-прокси (WPAD)</span><span class="sxs-lookup"><span data-stu-id="44d7f-158">Web Proxy Autodiscovery Protocol (WPAD)</span></span>
- <span data-ttu-id="44d7f-159">Ручная статическая конфигурация прокси</span><span class="sxs-lookup"><span data-stu-id="44d7f-159">Manual static proxy configuration</span></span>

<span data-ttu-id="44d7f-160">Если прокси-сервер или брандмауэр блокирует анонимный трафик, убедитесь, что анонимный трафик разрешен в указанных ранее URL-адресах.</span><span class="sxs-lookup"><span data-stu-id="44d7f-160">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span>

> [!WARNING]
> <span data-ttu-id="44d7f-161">Прокси-прокси с проверкой подлинности не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="44d7f-161">Authenticated proxies are not supported.</span></span> <span data-ttu-id="44d7f-162">Убедитесь, что используется только PAC, WPAD или статический прокси.</span><span class="sxs-lookup"><span data-stu-id="44d7f-162">Ensure that only PAC, WPAD, or a static proxy is being used.</span></span>
>
> <span data-ttu-id="44d7f-163">Проверка SSL и перехват прокси также не поддерживаются по соображениям безопасности.</span><span class="sxs-lookup"><span data-stu-id="44d7f-163">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="44d7f-164">Настройте исключение для проверки SSL и прокси-сервера, чтобы напрямую передавать данные из Microsoft Defender для конечной точки на macOS в соответствующие URL-адреса без перехвата.</span><span class="sxs-lookup"><span data-stu-id="44d7f-164">Configure an exception for SSL inspection and your proxy server to directly pass through data from Microsoft Defender for Endpoint on macOS to the relevant URLs without interception.</span></span> <span data-ttu-id="44d7f-165">Добавление сертификата перехвата в глобальный магазин не позволяет перехватывать.</span><span class="sxs-lookup"><span data-stu-id="44d7f-165">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="44d7f-166">Чтобы проверить, не заблокировано ли подключение, откройте [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) и [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) в браузере.</span><span class="sxs-lookup"><span data-stu-id="44d7f-166">To test that a connection is not blocked, open [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) and [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) in a browser.</span></span>

<span data-ttu-id="44d7f-167">Если вы предпочитаете командную строку, вы также можете проверить подключение, задав следующую команду в терминале:</span><span class="sxs-lookup"><span data-stu-id="44d7f-167">If you prefer the command line, you can also check the connection by running the following command in Terminal:</span></span>

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="44d7f-168">Выход из этой команды должен быть похож на следующие:</span><span class="sxs-lookup"><span data-stu-id="44d7f-168">The output from this command should be similar to the following:</span></span>

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> <span data-ttu-id="44d7f-169">Рекомендуется поддерживать [включенную](https://support.apple.com/en-us/HT204899) защиту целостности системы (SIP) на клиентских устройствах.</span><span class="sxs-lookup"><span data-stu-id="44d7f-169">We recommend that you keep [System Integrity Protection](https://support.apple.com/en-us/HT204899) (SIP) enabled on client devices.</span></span> <span data-ttu-id="44d7f-170">SIP — это встроенная функция безопасности macOS, которая предотвращает низкоуровневые взломы ОС и включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="44d7f-170">SIP is a built-in macOS security feature that prevents low-level tampering with the OS, and is enabled by default.</span></span>

<span data-ttu-id="44d7f-171">После установки Microsoft Defender для конечной точки подключение можно проверить, заверив следующую команду в терминале:</span><span class="sxs-lookup"><span data-stu-id="44d7f-171">Once Microsoft Defender for Endpoint is installed, connectivity can be validated by running the following command in Terminal:</span></span>
```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="44d7f-172">Обновление Microsoft Defender для конечной точки на Mac</span><span class="sxs-lookup"><span data-stu-id="44d7f-172">How to update Microsoft Defender for Endpoint on Mac</span></span>

<span data-ttu-id="44d7f-173">Корпорация Майкрософт регулярно публикует обновления программного обеспечения для повышения производительности, безопасности и предоставления новых функций.</span><span class="sxs-lookup"><span data-stu-id="44d7f-173">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="44d7f-174">Для обновления Microsoft Defender для конечной точки на Mac используется программа с именем Microsoft AutoUpdate (MAU).</span><span class="sxs-lookup"><span data-stu-id="44d7f-174">To update Microsoft Defender for Endpoint on Mac, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="44d7f-175">Дополнительные новости см. в дополнительных подробной информации о развертывании обновлений [для Microsoft Defender для конечной точки на Mac.](mac-updates.md)</span><span class="sxs-lookup"><span data-stu-id="44d7f-175">To learn more, see [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="44d7f-176">Настройка Microsoft Defender для конечной точки на Mac</span><span class="sxs-lookup"><span data-stu-id="44d7f-176">How to configure Microsoft Defender for Endpoint on Mac</span></span>

<span data-ttu-id="44d7f-177">Инструкции по настройке продукта в корпоративных средах доступны в наборе предпочтений [Для Microsoft Defender для конечной](mac-preferences.md)точки на Mac .</span><span class="sxs-lookup"><span data-stu-id="44d7f-177">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint on Mac](mac-preferences.md).</span></span>

## <a name="macos-kernel-and-system-extensions"></a><span data-ttu-id="44d7f-178">ядра macOS и расширения системы</span><span class="sxs-lookup"><span data-stu-id="44d7f-178">macOS kernel and system extensions</span></span>

<span data-ttu-id="44d7f-179">В соответствии с эволюцией macOS мы готовим обновление Microsoft Defender для конечной точки на Mac, которое использует расширения системы вместо расширений ядра.</span><span class="sxs-lookup"><span data-stu-id="44d7f-179">In alignment with macOS evolution, we are preparing a Microsoft Defender for Endpoint on Mac update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="44d7f-180">Соответствующие сведения см. [в материале "Что нового в Microsoft Defender для конечной точки на Mac".](mac-whatsnew.md)</span><span class="sxs-lookup"><span data-stu-id="44d7f-180">For relevant details, see [What's new in Microsoft Defender for Endpoint on Mac](mac-whatsnew.md).</span></span>

## <a name="resources"></a><span data-ttu-id="44d7f-181">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="44d7f-181">Resources</span></span>

- <span data-ttu-id="44d7f-182">Дополнительные сведения о журнале, uninstalling или других темах см. в [разделе Ресурсы для Microsoft Defender для конечной](mac-resources.md)точки на Mac.</span><span class="sxs-lookup"><span data-stu-id="44d7f-182">For more information about logging, uninstalling, or other topics, see [Resources for Microsoft Defender for Endpoint on Mac](mac-resources.md).</span></span>

- <span data-ttu-id="44d7f-183">[Конфиденциальность для Microsoft Defender для конечной точки на Mac](mac-privacy.md).</span><span class="sxs-lookup"><span data-stu-id="44d7f-183">[Privacy for Microsoft Defender for Endpoint on Mac](mac-privacy.md).</span></span>
