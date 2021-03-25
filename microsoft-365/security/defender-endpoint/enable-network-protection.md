---
title: Включаем защиту сети
description: Включить защиту сети с помощью групповой политики, PowerShell или диспетчера управления и конфигурации мобильных устройств.
keywords: Защита ANetwork, эксплойтов, вредоносный веб-сайт, IP, домен, домены, включить, включить
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 84a0e94b653eb426fab14d9c55ba8d29df388fe5
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164773"
---
# <a name="turn-on-network-protection"></a><span data-ttu-id="59560-104">Включаем защиту сети</span><span class="sxs-lookup"><span data-stu-id="59560-104">Turn on network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="59560-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="59560-105">**Applies to:**</span></span>
- [<span data-ttu-id="59560-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="59560-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="59560-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59560-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="59560-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="59560-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="59560-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="59560-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="59560-110">[Защита сети](network-protection.md) помогает предотвратить использование сотрудниками любого приложения для доступа к опасным доменам, в которые могут быть организованы фишинговые атаки, эксплойты и другой вредоносный контент в Интернете.</span><span class="sxs-lookup"><span data-stu-id="59560-110">[Network protection](network-protection.md) helps to prevent employees from using any application to access dangerous domains that may host phishing scams, exploits, and other malicious content on the internet.</span></span> <span data-ttu-id="59560-111">Вы можете [проверить защиту сети](evaluate-network-protection.md) в тестовой среде, чтобы просмотреть, какие приложения будут заблокированы, прежде чем включить ее.</span><span class="sxs-lookup"><span data-stu-id="59560-111">You can [audit network protection](evaluate-network-protection.md) in a test environment to view which apps would be blocked before you enable it.</span></span>

[<span data-ttu-id="59560-112">Дополнительные информацию о параметрах конфигурации фильтрации сети</span><span class="sxs-lookup"><span data-stu-id="59560-112">Learn more about network filtering configuration options</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a><span data-ttu-id="59560-113">Проверьте, включена ли защита сети</span><span class="sxs-lookup"><span data-stu-id="59560-113">Check if network protection is enabled</span></span>

<span data-ttu-id="59560-114">Проверьте, включена ли защита сети на локальном устройстве с помощью редактора реестра.</span><span class="sxs-lookup"><span data-stu-id="59560-114">Check if network protection has been enabled on a local device by using Registry editor.</span></span>

1. <span data-ttu-id="59560-115">Выберите **кнопку Начните** в панели задач и введите **regedit** для открытия редактора реестра</span><span class="sxs-lookup"><span data-stu-id="59560-115">Select the **Start** button in the task bar and type **regedit** to open Registry editor</span></span>
1. <span data-ttu-id="59560-116">Выберите **HKEY_LOCAL_MACHINE** из бокового меню</span><span class="sxs-lookup"><span data-stu-id="59560-116">Choose **HKEY_LOCAL_MACHINE** from the side menu</span></span>
1. <span data-ttu-id="59560-117">Перейдите через вложенные меню к политикам программного обеспечения Microsoft  >    >    >  **Защитник Windows**  >  **Защитник Windows Защита сети guard**  >  </span><span class="sxs-lookup"><span data-stu-id="59560-117">Navigate through the nested menus to **SOFTWARE** > **Policies** > **Microsoft** > **Windows Defender** > **Windows Defender Exploit Guard** > **Network Protection**</span></span>
1. <span data-ttu-id="59560-118">Выберите **EnableNetworkProtection,** чтобы увидеть текущее состояние сетевой защиты на устройстве</span><span class="sxs-lookup"><span data-stu-id="59560-118">Select **EnableNetworkProtection** to see the current state of network protection on the device</span></span>

    * <span data-ttu-id="59560-119">0 или **off**</span><span class="sxs-lookup"><span data-stu-id="59560-119">0, or **Off**</span></span>
    * <span data-ttu-id="59560-120">1 или **On**</span><span class="sxs-lookup"><span data-stu-id="59560-120">1, or **On**</span></span>
    * <span data-ttu-id="59560-121">2 или **режим аудита**</span><span class="sxs-lookup"><span data-stu-id="59560-121">2, or **Audit** mode</span></span>
    
    ![networkprotection](https://user-images.githubusercontent.com/3296790/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.PNG)

## <a name="enable-network-protection"></a><span data-ttu-id="59560-123">Включить защиту сети</span><span class="sxs-lookup"><span data-stu-id="59560-123">Enable network protection</span></span>

<span data-ttu-id="59560-124">Включить защиту сети с помощью любого из этих методов:</span><span class="sxs-lookup"><span data-stu-id="59560-124">Enable network protection by using any of these methods:</span></span>

* [<span data-ttu-id="59560-125">PowerShell</span><span class="sxs-lookup"><span data-stu-id="59560-125">PowerShell</span></span>](#powershell)
* [<span data-ttu-id="59560-126">Управление мобильными устройствами (MDM)</span><span class="sxs-lookup"><span data-stu-id="59560-126">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="59560-127">Microsoft Endpoint Manager / Intune</span><span class="sxs-lookup"><span data-stu-id="59560-127">Microsoft Endpoint Manager / Intune</span></span>](#microsoft-endpoint-manager-formerly-intune)
* [<span data-ttu-id="59560-128">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="59560-128">Group Policy</span></span>](#group-policy)

### <a name="powershell"></a><span data-ttu-id="59560-129">PowerShell</span><span class="sxs-lookup"><span data-stu-id="59560-129">PowerShell</span></span>

1. <span data-ttu-id="59560-130">Введите **powershell** в меню Пуск, щелкните правой кнопкой мыши **Windows PowerShell** выберите **Выполнить в качестве администратора**</span><span class="sxs-lookup"><span data-stu-id="59560-130">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="59560-131">Введите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="59560-131">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. <span data-ttu-id="59560-132">Необязательный вариант: включить функцию в режиме аудита с помощью следующего cmdlet:</span><span class="sxs-lookup"><span data-stu-id="59560-132">Optional: Enable the feature in audit mode using the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    <span data-ttu-id="59560-133">Используйте `Disabled` вместо или для `AuditMode` `Enabled` отключения функции.</span><span class="sxs-lookup"><span data-stu-id="59560-133">Use `Disabled` instead of `AuditMode` or `Enabled` to turn off the feature.</span></span>

### <a name="mobile-device-management-mdm"></a><span data-ttu-id="59560-134">Управление мобильными устройствами (MDM)</span><span class="sxs-lookup"><span data-stu-id="59560-134">Mobile device management (MDM)</span></span>

<span data-ttu-id="59560-135">Используйте [поставщик услуг конфигурации ./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) (CSP), чтобы включить или отключить защиту сети или включить режим аудита.</span><span class="sxs-lookup"><span data-stu-id="59560-135">Use the [./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) configuration service provider (CSP) to enable or disable network protection or enable audit mode.</span></span>

### <a name="microsoft-endpoint-manager-formerly-intune"></a><span data-ttu-id="59560-136">Microsoft Endpoint Manager (ранее Intune)</span><span class="sxs-lookup"><span data-stu-id="59560-136">Microsoft Endpoint Manager (formerly Intune)</span></span>

1. <span data-ttu-id="59560-137">Вход в центр администрирования microsoft Endpoint Manager (https://endpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="59560-137">Sign into the Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com)</span></span>

2. <span data-ttu-id="59560-138">Создание или изменение профиля конфигурации [защиты конечной точки](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-configure)</span><span class="sxs-lookup"><span data-stu-id="59560-138">Create or edit an [endpoint protection configuration profile](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-configure)</span></span>

3. <span data-ttu-id="59560-139">В статье "Параметры конфигурации" в потоке профилей перейдите в **microsoft Defender Exploit Guard Network**  >  **filtering Network** protection  >    >  **Enable** or **Audit only**</span><span class="sxs-lookup"><span data-stu-id="59560-139">Under "Configuration Settings" in the profile flow, go to **Microsoft Defender Exploit Guard** > **Network filtering** > **Network protection** > **Enable** or **Audit only**</span></span>

### <a name="group-policy"></a><span data-ttu-id="59560-140">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="59560-140">Group Policy</span></span>

<span data-ttu-id="59560-141">Используйте следующую процедуру, чтобы включить защиту сети на компьютерах с доменом или на автономных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="59560-141">Use the following procedure to enable network protection on domain-joined computers or on a standalone computer.</span></span>

1. <span data-ttu-id="59560-142">На автономных компьютерах перейдите в **Начните,** а затем введите и выберите **групповую политику редактирования.**</span><span class="sxs-lookup"><span data-stu-id="59560-142">On a standalone computer, go to **Start** and then type and select **Edit group policy**.</span></span>

    <span data-ttu-id="59560-143">*-Or-*</span><span class="sxs-lookup"><span data-stu-id="59560-143">*-Or-*</span></span>

    <span data-ttu-id="59560-144">На компьютере управления групповой политикой, примыкаемом к домену, откройте консоль управления групповой политикой [правой](https://technet.microsoft.com/library/cc731212.aspx)кнопкой мыши объект групповой политики, который необходимо настроить, и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="59560-144">On a domain-joined Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="59560-145">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и выберите **административные шаблоны.**</span><span class="sxs-lookup"><span data-stu-id="59560-145">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="59560-146">Расширь дерево до **компонентов Антивирус** Microsoft Defender  >  **Microsoft Defender** Защитник Windows защита сети exploit  >    >  **Guard.**</span><span class="sxs-lookup"><span data-stu-id="59560-146">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Network protection**.</span></span>

> [!NOTE]
> <span data-ttu-id="59560-147">В старых версиях Windows путь групповой политики может говорить "Защитник Windows антивирус", а не "Антивирус Microsoft Defender".</span><span class="sxs-lookup"><span data-stu-id="59560-147">On older versions of Windows, the group policy path may say "Windows Defender Antivirus" instead of "Microsoft Defender Antivirus."</span></span>

4. <span data-ttu-id="59560-148">Дважды щелкните кнопку **Запретить пользователям и приложениям доступ** к опасным настройкам веб-сайтов и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="59560-148">Double-click the **Prevent users and apps from accessing dangerous websites** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="59560-149">В разделе Параметры необходимо указать один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="59560-149">In the options section, you must specify one of the following options:</span></span>
    * <span data-ttu-id="59560-150">**Block** . Пользователи не могут получить доступ к вредоносным IP-адресам и доменам</span><span class="sxs-lookup"><span data-stu-id="59560-150">**Block** - Users can't access malicious IP addresses and domains</span></span>
    * <span data-ttu-id="59560-151">**Отключение (по умолчанию)** — функция защиты сети не будет работать.</span><span class="sxs-lookup"><span data-stu-id="59560-151">**Disable (Default)** - The Network protection feature won't work.</span></span> <span data-ttu-id="59560-152">Пользователям не будет заблокирован доступ к вредоносным доменам</span><span class="sxs-lookup"><span data-stu-id="59560-152">Users won't be blocked from accessing malicious domains</span></span>
    * <span data-ttu-id="59560-153">**Режим аудита** . Если пользователь посещает вредоносный IP-адрес или домен, событие будет записано в журнале событий Windows.</span><span class="sxs-lookup"><span data-stu-id="59560-153">**Audit Mode** - If a user visits a malicious IP address or domain, an event will be recorded in the Windows event log.</span></span> <span data-ttu-id="59560-154">Однако пользователю не будет заблокировано посещение адреса.</span><span class="sxs-lookup"><span data-stu-id="59560-154">However, the user won't be blocked from visiting the address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="59560-155">Чтобы полностью включить защиту сети, необходимо настроить  параметр Групповой политики для включения, а также выбрать **Блок** в выпадаемом меню параметров.</span><span class="sxs-lookup"><span data-stu-id="59560-155">To fully enable network protection, you must set the Group Policy option to **Enabled** and also select **Block** in the options drop-down menu.</span></span>

<span data-ttu-id="59560-156">Подтверждение того, что защита сети включена на локальном компьютере с помощью редактора реестра:</span><span class="sxs-lookup"><span data-stu-id="59560-156">Confirm network protection is enabled on a local computer by using Registry editor:</span></span>

1. <span data-ttu-id="59560-157">Выберите **regedit Начните и** введите, чтобы открыть **редактор реестра.** </span><span class="sxs-lookup"><span data-stu-id="59560-157">Select **Start** and type **regedit** to open **Registry Editor**.</span></span>

2. <span data-ttu-id="59560-158">Перейдите **кHKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Windows Defender Exploit Guard\Network Protection**</span><span class="sxs-lookup"><span data-stu-id="59560-158">Navigate to **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Windows Defender Exploit Guard\Network Protection**</span></span>

3. <span data-ttu-id="59560-159">Выберите **EnableNetworkProtection** и подтвердите значение:</span><span class="sxs-lookup"><span data-stu-id="59560-159">Select **EnableNetworkProtection** and confirm the value:</span></span>
   * <span data-ttu-id="59560-160">0=Off</span><span class="sxs-lookup"><span data-stu-id="59560-160">0=Off</span></span>
   * <span data-ttu-id="59560-161">1=On</span><span class="sxs-lookup"><span data-stu-id="59560-161">1=On</span></span>
   * <span data-ttu-id="59560-162">2=Audit</span><span class="sxs-lookup"><span data-stu-id="59560-162">2=Audit</span></span>

## <a name="see-also"></a><span data-ttu-id="59560-163">См. также</span><span class="sxs-lookup"><span data-stu-id="59560-163">See also</span></span>

* [<span data-ttu-id="59560-164">Защита сети</span><span class="sxs-lookup"><span data-stu-id="59560-164">Network protection</span></span>](network-protection.md)
* [<span data-ttu-id="59560-165">Оценка защиты сети</span><span class="sxs-lookup"><span data-stu-id="59560-165">Evaluate network protection</span></span>](evaluate-network-protection.md)
* [<span data-ttu-id="59560-166">Защита сети от неполадок</span><span class="sxs-lookup"><span data-stu-id="59560-166">Troubleshoot network protection</span></span>](troubleshoot-np.md)
