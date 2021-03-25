---
title: Управление microsoft Defender для конечной точки с помощью объектов групповой политики
description: Узнайте, как управлять Microsoft Defender для конечной точки с помощью объектов групповой политики
keywords: после переноса, управления, операций, обслуживания, использования, PowerShell, защиты от угроз, atp, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: 6d10bd932d9414f1460076d3fe7ca8dbed8041a6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185663"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a><span data-ttu-id="5d9f2-104">Управление защитником Майкрософт для конечной точки с помощью объектов групповой политики</span><span class="sxs-lookup"><span data-stu-id="5d9f2-104">Manage Microsoft Defender for Endpoint with Group Policy Objects</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5d9f2-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5d9f2-105">**Applies to:**</span></span>
- [<span data-ttu-id="5d9f2-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5d9f2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5d9f2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5d9f2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5d9f2-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="5d9f2-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5d9f2-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="5d9f2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


> [!NOTE]
> <span data-ttu-id="5d9f2-110">Мы рекомендуем использовать [Microsoft Endpoint Manager](https://docs.microsoft.com/mem) для управления функциями защиты от угроз для устройств (также именуемой конечными точками).</span><span class="sxs-lookup"><span data-stu-id="5d9f2-110">We recommend using [Microsoft Endpoint Manager](https://docs.microsoft.com/mem) to manage your organization's threat protection features for devices (also referred to as endpoints).</span></span> <span data-ttu-id="5d9f2-111">Endpoint Manager включает [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) и [Microsoft Endpoint Configuration Manager.](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)</span><span class="sxs-lookup"><span data-stu-id="5d9f2-111">Endpoint Manager includes [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) and [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).</span></span> <span data-ttu-id="5d9f2-112">**[Дополнительные информацию о endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview)**.</span><span class="sxs-lookup"><span data-stu-id="5d9f2-112">**[Learn more about Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview)**.</span></span> 

<span data-ttu-id="5d9f2-113">Объекты групповой политики можно использовать в службах домена Azure Active Directory для управления некоторыми настройками в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="5d9f2-113">You can use Group Policy Objects in Azure Active Directory Domain Services to manage some settings in Microsoft Defender for Endpoint.</span></span>

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a><span data-ttu-id="5d9f2-114">Настройка Microsoft Defender для конечной точки с помощью объектов групповой политики</span><span class="sxs-lookup"><span data-stu-id="5d9f2-114">Configure Microsoft Defender for Endpoint with Group Policy Objects</span></span>

<span data-ttu-id="5d9f2-115">В следующей таблице перечислены различные задачи, которые можно выполнить для настройки Microsoft Defender для конечной точки с объектами групповой политики.</span><span class="sxs-lookup"><span data-stu-id="5d9f2-115">The following table lists various tasks you can perform to configure Microsoft Defender for Endpoint with Group Policy Objects.</span></span>

|<span data-ttu-id="5d9f2-116">Задача</span><span class="sxs-lookup"><span data-stu-id="5d9f2-116">Task</span></span>  |<span data-ttu-id="5d9f2-117">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="5d9f2-117">Resources to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="5d9f2-118">**Управление настройками объектов пользователя и компьютера**</span><span class="sxs-lookup"><span data-stu-id="5d9f2-118">**Manage settings for user and computer objects**</span></span> <br/><br/><span data-ttu-id="5d9f2-119">*Настройка встроенных объектов групповой политики или создание настраиваемых объектов групповой политики и организационных подразделений в соответствии с вашими организационными потребностями.*</span><span class="sxs-lookup"><span data-stu-id="5d9f2-119">*Customize built-in Group Policy Objects, or create custom Group Policy Objects and organizational units to suit your organizational needs.*</span></span>     |[<span data-ttu-id="5d9f2-120">Администрирование групповой политики в управляемом домене Azure Active Directory Domain Services</span><span class="sxs-lookup"><span data-stu-id="5d9f2-120">Administer Group Policy in an Azure Active Directory Domain Services managed domain</span></span>](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)   |
|<span data-ttu-id="5d9f2-121">**Настройка антивируса Microsoft Defender**</span><span class="sxs-lookup"><span data-stu-id="5d9f2-121">**Configure Microsoft Defender Antivirus**</span></span> <br/><br/><span data-ttu-id="5d9f2-122">*Настройка функций антивирусного &, включая параметры политики, исключения, исправление и плановые проверки на устройствах организации (также именуемые конечными точками).*</span><span class="sxs-lookup"><span data-stu-id="5d9f2-122">*Configure antivirus features & capabilities, including policy settings, exclusions, remediation, and scheduled scans on your organization's devices (also referred to as endpoints).*</span></span>   |[<span data-ttu-id="5d9f2-123">Настройка и управление антивирусной программой Microsoft Defender с помощью параметров групповой политики</span><span class="sxs-lookup"><span data-stu-id="5d9f2-123">Use Group Policy settings to configure and manage Microsoft Defender Antivirus</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/>[<span data-ttu-id="5d9f2-124">Использование групповой политики для обеспечения облачной защиты</span><span class="sxs-lookup"><span data-stu-id="5d9f2-124">Use Group Policy to enable cloud-delivered protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)      |
|<span data-ttu-id="5d9f2-125">**Управление правилами уменьшения поверхности атак в организации**</span><span class="sxs-lookup"><span data-stu-id="5d9f2-125">**Manage your organization's attack surface reduction rules**</span></span> <br/><br/><span data-ttu-id="5d9f2-126">*Настройте правила уменьшения поверхности атаки, исключив & папки или добавив настраиваемый текст в уведомления, которые отображаются на устройствах пользователей.*</span><span class="sxs-lookup"><span data-stu-id="5d9f2-126">*Customize your attack surface reduction rules by excluding files & folders, or by adding custom text to notification alerts that appear on users' devices.*</span></span> |[<span data-ttu-id="5d9f2-127">Настройка правил уменьшения поверхности атаки с помощью объектов групповой политики</span><span class="sxs-lookup"><span data-stu-id="5d9f2-127">Customize attack surface reduction rules with Group Policy Objects</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders) |
|<span data-ttu-id="5d9f2-128">**Управление настройками защиты от эксплойтов**</span><span class="sxs-lookup"><span data-stu-id="5d9f2-128">**Manage exploit protection settings**</span></span><br/><br/><span data-ttu-id="5d9f2-129">*Вы можете настроить параметры защиты от эксплойтов, импортировать файл конфигурации и затем использовать групповую политику для развертывания этого файла конфигурации.*</span><span class="sxs-lookup"><span data-stu-id="5d9f2-129">*You can customize your exploit protection settings, import a configuration file, and then use Group Policy to deploy that configuration file.*</span></span>  |[<span data-ttu-id="5d9f2-130">Настройка параметров защиты от эксплойтов</span><span class="sxs-lookup"><span data-stu-id="5d9f2-130">Customize exploit protection settings</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/>[<span data-ttu-id="5d9f2-131">Импорт, экспорт и развертывание конфигураций защиты от эксплойтов</span><span class="sxs-lookup"><span data-stu-id="5d9f2-131">Import, export, and deploy exploit protection configurations</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml)<br/><br/>[<span data-ttu-id="5d9f2-132">Использование групповой политики для распространения конфигурации</span><span class="sxs-lookup"><span data-stu-id="5d9f2-132">Use Group Policy to distribute the configuration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)  |
|<span data-ttu-id="5d9f2-133">**Включить защиту сети,** чтобы предотвратить использование сотрудниками приложений с вредоносным контентом в Интернете</span><span class="sxs-lookup"><span data-stu-id="5d9f2-133">**Enable Network Protection** to help prevent employees from using apps that malicious content on the Internet</span></span> <br/><br/><span data-ttu-id="5d9f2-134">*Сначала рекомендуется использовать [режим аудита](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) для защиты сети в тестовой среде, чтобы узнать, какие приложения будут заблокированы перед развертыванием.*</span><span class="sxs-lookup"><span data-stu-id="5d9f2-134">*We recommend using [audit mode](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) at first for network protection in a test environment to see which apps would be blocked before rolling out.*</span></span> |[<span data-ttu-id="5d9f2-135">Включаем защиту сети с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="5d9f2-135">Turn on network protection using Group Policy</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)  |
|<span data-ttu-id="5d9f2-136">**Настройка управляемого доступа к папкам для** защиты от программ-вымогателей</span><span class="sxs-lookup"><span data-stu-id="5d9f2-136">**Configure controlled folder access** to protect against ransomware</span></span> <br/><br/><span data-ttu-id="5d9f2-137">*[Управляемый доступ к папкам](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) также называется защитой от антивирусных программ.*</span><span class="sxs-lookup"><span data-stu-id="5d9f2-137">*[Controlled folder access](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) is also referred to as antiransomware protection.*</span></span>  |[<span data-ttu-id="5d9f2-138">Включить управляемый доступ к папкам с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="5d9f2-138">Enable controlled folder access using Group Policy</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy) |
|<span data-ttu-id="5d9f2-139">**Настройте Microsoft Defender SmartScreen** для защиты от вредоносных сайтов и файлов в Интернете.</span><span class="sxs-lookup"><span data-stu-id="5d9f2-139">**Configure Microsoft Defender SmartScreen** to protect against malicious sites and files on the internet.</span></span>  |[<span data-ttu-id="5d9f2-140">Настройка параметров групповой политики Microsoft Defender SmartScreen и управления мобильными устройствами (MDM) с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="5d9f2-140">Configure Microsoft Defender SmartScreen Group Policy and mobile device management (MDM) settings using Group Policy</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)  |
|<span data-ttu-id="5d9f2-141">**Настройка шифрования и BitLocker для** защиты информации на устройствах организации под управлением Windows</span><span class="sxs-lookup"><span data-stu-id="5d9f2-141">**Configure encryption and BitLocker** to protect information on your organization's devices running Windows</span></span> |[<span data-ttu-id="5d9f2-142">Параметры групповой политики BitLocker</span><span class="sxs-lookup"><span data-stu-id="5d9f2-142">BitLocker Group Policy settings</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) |
|<span data-ttu-id="5d9f2-143">**Настройка microsoft Defender Credential Guard для** защиты от атак кражи учетных данных</span><span class="sxs-lookup"><span data-stu-id="5d9f2-143">**Configure Microsoft Defender Credential Guard** to protect against credential theft attacks</span></span> |[<span data-ttu-id="5d9f2-144">Включить Защитник Windows учетных данных с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="5d9f2-144">Enable Windows Defender Credential Guard by using Group Policy</span></span>](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy) |

## <a name="configure-your-microsoft-defender-security-center"></a><span data-ttu-id="5d9f2-145">Настройка центра безопасности Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5d9f2-145">Configure your Microsoft Defender Security Center</span></span>

<span data-ttu-id="5d9f2-146">Если вы еще этого не сделали, настройте центр безопасности **Microsoft Defender** Для просмотра оповещений, настройки функций защиты от угроз и просмотра подробных сведений об общей позиции безопасности [https://securitycenter.windows.com](https://securitycenter.windows.com) организации.</span><span class="sxs-lookup"><span data-stu-id="5d9f2-146">If you haven't already done so, **configure your Microsoft Defender Security Center** ([https://securitycenter.windows.com](https://securitycenter.windows.com)) to view alerts, configure threat protection features, and view detailed information about your organization's overall security posture.</span></span> 

<span data-ttu-id="5d9f2-147">Вы также можете настроить, можно ли и какие функции конечные пользователи могут видеть в Центре безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="5d9f2-147">You can also configure whether and what features end users can see in the Microsoft Defender Security Center.</span></span>

- [<span data-ttu-id="5d9f2-148">Обзор Центра безопасности Защитника Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5d9f2-148">Overview of the Microsoft Defender Security Center</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [<span data-ttu-id="5d9f2-149">Защита конечной точки: Центр безопасности Защитника Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5d9f2-149">Endpoint protection: Microsoft Defender Security Center</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a><span data-ttu-id="5d9f2-150">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="5d9f2-150">Next steps</span></span>

- [<span data-ttu-id="5d9f2-151">Обзор управления угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="5d9f2-151">Get an overview of threat and vulnerability management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [<span data-ttu-id="5d9f2-152">Посетите панель мониторинга операций безопасности Центра безопасности Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5d9f2-152">Visit the Microsoft Defender Security Center security operations dashboard</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [<span data-ttu-id="5d9f2-153">Управление microsoft Defender для конечной точки с помощью Intune</span><span class="sxs-lookup"><span data-stu-id="5d9f2-153">Manage Microsoft Defender for Endpoint with Intune</span></span>](manage-atp-post-migration-intune.md)