---
title: Развертывание с другой системой управления мобильными устройствами (MDM) для Microsoft Defender для конечной точки для Mac
description: Установите Microsoft Defender для конечной точки для Mac на другие решения управления.
keywords: Microsoft, defender, atp, mac, installation, deploy, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e929c17ada761a334700f6e66d2921483686834b
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861567"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="f2dca-104">Развертывание с другой системой управления мобильными устройствами (MDM) для Microsoft Defender для конечной точки на macOS</span><span class="sxs-lookup"><span data-stu-id="f2dca-104">Deployment with a different Mobile Device Management (MDM) system for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f2dca-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f2dca-105">**Applies to:**</span></span>
- [<span data-ttu-id="f2dca-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f2dca-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f2dca-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2dca-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f2dca-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="f2dca-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f2dca-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="f2dca-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="f2dca-110">Необходимые условия и требования к системе</span><span class="sxs-lookup"><span data-stu-id="f2dca-110">Prerequisites and system requirements</span></span>

<span data-ttu-id="f2dca-111">Перед началом работы см. в главной странице [Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md) на странице macOS описание необходимых условий и системных требований к текущей версии программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="f2dca-111">Before you get started, see [the main Microsoft Defender for Endpoint on macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>


## <a name="approach"></a><span data-ttu-id="f2dca-112">Способ</span><span class="sxs-lookup"><span data-stu-id="f2dca-112">Approach</span></span>

> [!CAUTION]

> <span data-ttu-id="f2dca-113">В настоящее время Корпорация Майкрософт официально поддерживает только Intune и JAMF для развертывания и управления Microsoft Defender для конечной точки на macOS.</span><span class="sxs-lookup"><span data-stu-id="f2dca-113">Currently, Microsoft officially supports only Intune and JAMF for the deployment and management of Microsoft Defender for Endpoint on macOS.</span></span> <span data-ttu-id="f2dca-114">Корпорация Майкрософт не предоставляет никаких гарантий, экспресс-или подразумеваемых, в отношении сведений, предоставленных ниже.</span><span class="sxs-lookup"><span data-stu-id="f2dca-114">Microsoft makes no warranties, express or implied, with respect to the information provided below.</span></span>

<span data-ttu-id="f2dca-115">Если в организации используется решение управления мобильными устройствами (MDM), которое не поддерживается официально, это не означает, что вы не можете развернуть или запустить Microsoft Defender для конечной точки на macOS.</span><span class="sxs-lookup"><span data-stu-id="f2dca-115">If your organization uses a Mobile Device Management (MDM) solution that is not officially supported, this does not mean you are unable to deploy or run Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="f2dca-116">Microsoft Defender для конечной точки на macOS не зависит от каких-либо компонентов, определенных для поставщика.</span><span class="sxs-lookup"><span data-stu-id="f2dca-116">Microsoft Defender for Endpoint on macOS does not depend on any vendor-specific features.</span></span> <span data-ttu-id="f2dca-117">Его можно использовать с любым решением MDM, которое поддерживает следующие функции:</span><span class="sxs-lookup"><span data-stu-id="f2dca-117">It can be used with any MDM solution that supports the following features:</span></span>

- <span data-ttu-id="f2dca-118">Развертывание macOS .pkg на управляемых устройствах.</span><span class="sxs-lookup"><span data-stu-id="f2dca-118">Deploy a macOS .pkg to managed devices.</span></span>
- <span data-ttu-id="f2dca-119">Развертывание профилей конфигурации системы macOS на управляемых устройствах.</span><span class="sxs-lookup"><span data-stu-id="f2dca-119">Deploy macOS system configuration profiles to managed devices.</span></span>
- <span data-ttu-id="f2dca-120">Запустите произвольный настраиваемый администратором инструмент или скрипт на управляемых устройствах.</span><span class="sxs-lookup"><span data-stu-id="f2dca-120">Run an arbitrary admin-configured tool/script on managed devices.</span></span>

<span data-ttu-id="f2dca-121">Большинство современных решений MDM включают эти функции, однако они могут называть их по-другому.</span><span class="sxs-lookup"><span data-stu-id="f2dca-121">Most modern MDM solutions include these features, however, they may call them differently.</span></span>

<span data-ttu-id="f2dca-122">Однако можно развернуть Defender без последнего требования из предыдущего списка:</span><span class="sxs-lookup"><span data-stu-id="f2dca-122">You can deploy Defender without the last requirement from the preceding list, however:</span></span>

- <span data-ttu-id="f2dca-123">Вы не сможете централизованно собирать состояние</span><span class="sxs-lookup"><span data-stu-id="f2dca-123">You will not be able to collect status in a centralized way</span></span>
- <span data-ttu-id="f2dca-124">Если вы решите удалить Defender, вам потребуется войти на клиентские устройства локально в качестве администратора</span><span class="sxs-lookup"><span data-stu-id="f2dca-124">If you decide to uninstall Defender, you will need to log on to the client device locally as an administrator</span></span>

## <a name="deployment"></a><span data-ttu-id="f2dca-125">Развертывание</span><span class="sxs-lookup"><span data-stu-id="f2dca-125">Deployment</span></span>

<span data-ttu-id="f2dca-126">Большинство решений MDM используют ту же модель для управления устройствами macOS с аналогичной терминологией.</span><span class="sxs-lookup"><span data-stu-id="f2dca-126">Most MDM solutions use the same model for managing macOS devices, with similar terminology.</span></span> <span data-ttu-id="f2dca-127">Используйте [развертывание на основе JAMF в](mac-install-with-jamf.md) качестве шаблона.</span><span class="sxs-lookup"><span data-stu-id="f2dca-127">Use [JAMF-based deployment](mac-install-with-jamf.md) as a template.</span></span>

### <a name="package"></a><span data-ttu-id="f2dca-128">Пакет</span><span class="sxs-lookup"><span data-stu-id="f2dca-128">Package</span></span>

<span data-ttu-id="f2dca-129">Настройка развертывания [необходимого](mac-install-with-jamf.md)пакета приложений с пакетом установки (wdav.pkg), загруженным из Центра безопасности [Microsoft Defender.](mac-install-with-jamf.md)</span><span class="sxs-lookup"><span data-stu-id="f2dca-129">Configure deployment of a [required application package](mac-install-with-jamf.md), with the installation package (wdav.pkg) downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>

<span data-ttu-id="f2dca-130">Чтобы развернуть пакет на предприятии, используйте инструкции, связанные с решением MDM.</span><span class="sxs-lookup"><span data-stu-id="f2dca-130">In order to deploy the package to your enterprise, use the instructions associated with your MDM solution.</span></span>

### <a name="license-settings"></a><span data-ttu-id="f2dca-131">Параметры лицензии</span><span class="sxs-lookup"><span data-stu-id="f2dca-131">License settings</span></span>

<span data-ttu-id="f2dca-132">Настройка [профиля конфигурации системы.](mac-install-with-jamf.md)</span><span class="sxs-lookup"><span data-stu-id="f2dca-132">Set up [a system configuration profile](mac-install-with-jamf.md).</span></span> 

<span data-ttu-id="f2dca-133">Решение MDM может называться как "Пользовательский профиль параметров", так как Microsoft Defender для конечной точки на macOS не является частью macOS.</span><span class="sxs-lookup"><span data-stu-id="f2dca-133">Your MDM solution may call it something like "Custom Settings Profile", as Microsoft Defender for Endpoint on macOS is not part of macOS.</span></span>

<span data-ttu-id="f2dca-134">Используйте список свойств jamf/WindowsDefenderATPOnboarding.plist, который можно извлечь из бортового пакета, загруженного из Центра безопасности [Microsoft Defender.](mac-install-with-jamf.md)</span><span class="sxs-lookup"><span data-stu-id="f2dca-134">Use the property list, jamf/WindowsDefenderATPOnboarding.plist, which can be extracted from an onboarding package downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>
<span data-ttu-id="f2dca-135">Система может поддерживать произвольный список свойств в формате XML.</span><span class="sxs-lookup"><span data-stu-id="f2dca-135">Your system may support an arbitrary property list in XML format.</span></span> <span data-ttu-id="f2dca-136">В этом случае можно загрузить файл jamf/WindowsDefenderATPOnboarding.plist.</span><span class="sxs-lookup"><span data-stu-id="f2dca-136">You can upload the jamf/WindowsDefenderATPOnboarding.plist file as-is in that case.</span></span>
<span data-ttu-id="f2dca-137">Кроме того, может потребоваться сначала преобразовать список свойств в другой формат.</span><span class="sxs-lookup"><span data-stu-id="f2dca-137">Alternatively, it may require you to convert the property list to a different format first.</span></span>

<span data-ttu-id="f2dca-138">Как правило, пользовательский профиль имеет атрибут ID, name или domain.</span><span class="sxs-lookup"><span data-stu-id="f2dca-138">Typically, your custom profile has an ID, name, or domain attribute.</span></span> <span data-ttu-id="f2dca-139">Для этого значения необходимо использовать именно "com.microsoft.wdav.atp".</span><span class="sxs-lookup"><span data-stu-id="f2dca-139">You must use exactly "com.microsoft.wdav.atp" for this value.</span></span>
<span data-ttu-id="f2dca-140">MDM использует его для развертывания файла параметров **в /Library/Managed Preferences/com.microsoft.wdav.atp.plist** на клиентском устройстве, а Defender использует этот файл для загрузки данных на борту.</span><span class="sxs-lookup"><span data-stu-id="f2dca-140">MDM uses it to deploy the settings file to **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** on a client device, and Defender uses this file for loading the onboarding information.</span></span>

### <a name="kernel-extension-policy"></a><span data-ttu-id="f2dca-141">Политика расширения ядра</span><span class="sxs-lookup"><span data-stu-id="f2dca-141">Kernel extension policy</span></span>

<span data-ttu-id="f2dca-142">Настройка политики расширения KEXT или ядра.</span><span class="sxs-lookup"><span data-stu-id="f2dca-142">Set up a KEXT or kernel extension policy.</span></span> <span data-ttu-id="f2dca-143">Используйте идентификатор **группы UBF8T346G9,** чтобы разрешить расширения ядра, предоставляемые Корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f2dca-143">Use team identifier **UBF8T346G9** to allow kernel extensions provided by Microsoft.</span></span>

> [!CAUTION]
> <span data-ttu-id="f2dca-144">Если среда состоит из устройств Apple Silicon (M1), эти машины не должны получать профили конфигурации с политиками KEXT.</span><span class="sxs-lookup"><span data-stu-id="f2dca-144">If your environment consists of Apple Silicon (M1) devices, these machines should not receive configuration profiles with KEXT policies.</span></span>
> <span data-ttu-id="f2dca-145">Apple не поддерживает KEXT на этих машинах, развертывание такого профиля может быть неудачным на машинах M1.</span><span class="sxs-lookup"><span data-stu-id="f2dca-145">Apple does not support KEXT on these machines, deployment of such profile would fail on M1 machines.</span></span>

### <a name="system-extension-policy"></a><span data-ttu-id="f2dca-146">Политика расширения системы</span><span class="sxs-lookup"><span data-stu-id="f2dca-146">System extension policy</span></span>

<span data-ttu-id="f2dca-147">Настройка политики расширения системы.</span><span class="sxs-lookup"><span data-stu-id="f2dca-147">Set up a system extension policy.</span></span> <span data-ttu-id="f2dca-148">Используйте идентификатор **группы UBF8T346G9** и утвердите следующие идентификаторы пакета:</span><span class="sxs-lookup"><span data-stu-id="f2dca-148">Use team identifier **UBF8T346G9** and approve the following bundle identifiers:</span></span>

- <span data-ttu-id="f2dca-149">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="f2dca-149">com.microsoft.wdav.epsext</span></span>
- <span data-ttu-id="f2dca-150">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="f2dca-150">com.microsoft.wdav.netext</span></span>

### <a name="full-disk-access-policy"></a><span data-ttu-id="f2dca-151">Политика полного доступа к дискам</span><span class="sxs-lookup"><span data-stu-id="f2dca-151">Full disk access policy</span></span>

<span data-ttu-id="f2dca-152">Предоставление полного доступа на диск к следующим компонентам:</span><span class="sxs-lookup"><span data-stu-id="f2dca-152">Grant Full Disk Access to the following components:</span></span>

- <span data-ttu-id="f2dca-153">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f2dca-153">Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="f2dca-154">Идентификатор: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="f2dca-154">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="f2dca-155">Тип идентификатора: идентификатор пакета</span><span class="sxs-lookup"><span data-stu-id="f2dca-155">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="f2dca-156">Требование кода: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="f2dca-156">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

- <span data-ttu-id="f2dca-157">Microsoft Defender для расширения безопасности конечных точек</span><span class="sxs-lookup"><span data-stu-id="f2dca-157">Microsoft Defender for Endpoint Security Extension</span></span>
    - <span data-ttu-id="f2dca-158">Идентификатор: `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="f2dca-158">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="f2dca-159">Тип идентификатора: идентификатор пакета</span><span class="sxs-lookup"><span data-stu-id="f2dca-159">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="f2dca-160">Требование кода: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="f2dca-160">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

### <a name="network-extension-policy"></a><span data-ttu-id="f2dca-161">Политика расширения сети</span><span class="sxs-lookup"><span data-stu-id="f2dca-161">Network extension policy</span></span>

<span data-ttu-id="f2dca-162">В рамках возможностей обнаружения конечных точек и ответов Microsoft Defender for Endpoint на macOS проверяет трафик розетки и передает эти сведения на портал Центра безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="f2dca-162">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="f2dca-163">Следующая политика позволяет сетевому расширению выполнять эту функцию.</span><span class="sxs-lookup"><span data-stu-id="f2dca-163">The following policy allows the network extension to perform this functionality.</span></span>

- <span data-ttu-id="f2dca-164">Тип фильтра: плагин</span><span class="sxs-lookup"><span data-stu-id="f2dca-164">Filter type: Plugin</span></span>
- <span data-ttu-id="f2dca-165">Идентификатор пакета плагинов: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="f2dca-165">Plugin bundle identifier: `com.microsoft.wdav`</span></span>
- <span data-ttu-id="f2dca-166">Идентификатор пакета поставщиков данных фильтрации: `com.microsoft.wdav.netext`</span><span class="sxs-lookup"><span data-stu-id="f2dca-166">Filter data provider bundle identifier: `com.microsoft.wdav.netext`</span></span>
- <span data-ttu-id="f2dca-167">Требование поставщика фильтрации данных: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="f2dca-167">Filter data provider designated requirement: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
- <span data-ttu-id="f2dca-168">Фильтровать розетки: `true`</span><span class="sxs-lookup"><span data-stu-id="f2dca-168">Filter sockets: `true`</span></span>

## <a name="check-installation-status"></a><span data-ttu-id="f2dca-169">Проверка состояния установки</span><span class="sxs-lookup"><span data-stu-id="f2dca-169">Check installation status</span></span>

<span data-ttu-id="f2dca-170">Запустите [Microsoft Defender для конечной точки](mac-install-with-jamf.md) на клиентских устройствах, чтобы проверить состояние бортового устройства.</span><span class="sxs-lookup"><span data-stu-id="f2dca-170">Run [Microsoft Defender for Endpoint](mac-install-with-jamf.md) on a client device to check the onboarding status.</span></span>
