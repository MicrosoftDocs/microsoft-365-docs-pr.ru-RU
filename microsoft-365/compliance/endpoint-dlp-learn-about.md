---
title: Сведения о защите от потери данных в конечных точках Microsoft 365
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 'Защита от потери данных в конечной точке Microsoft 365 расширяет отслеживание действий с файлами и защитных действий с этими файлами до конечных точек. В решениях для обеспечения соответствия требованиям Microsoft 365 файлы являются видимыми '
ms.openlocfilehash: c97368dd48515dc787dbac66aa93844889efbdbc
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314420"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="49c77-104">Сведения о защите от потери данных в конечной точке Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="49c77-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="49c77-105">Защиту от потери данных (DLP) в Microsoft 365 можно использовать для отслеживания действий, принятых в отношении элементов, которые были определены как конфиденциальные, и для защиты от непреднамеренного обмена этими элементами.</span><span class="sxs-lookup"><span data-stu-id="49c77-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="49c77-106">Подробная информация приведена в статье [Сведения о защите от потери данных](dlp-learn-about-dlp.md).</span><span class="sxs-lookup"><span data-stu-id="49c77-106">For more information on DLP, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="49c77-107">**Защита от потери данных в конечной точке (DLP в конечной точке)** расширяет возможности отслеживания действий и защиты от потери данных для конфиденциальных элементов на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="49c77-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="49c77-108">После того как устройства будут подключены к решениям по обеспечению соответствия требованиям Microsoft 365, сведения о действиях пользователей с конфиденциальными элементами становятся видимыми в [обозревателе действий](data-classification-activity-explorer.md) и вы можете принудительно применять защитные действия к ним с помощью [политик защиты от потери данных](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="49c77-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

> [!TIP]
> <span data-ttu-id="49c77-109">Если вы ищете управление устройствами для съемного хранилища, см. [Управление доступом к управлению устройствами съемного хранилища в Microsoft Defender для конечной точки](../security/defender-endpoint/device-control-removable-storage-access-control.md#microsoft-defender-for-endpoint-device-control-removable-storage-access-control).</span><span class="sxs-lookup"><span data-stu-id="49c77-109">If you are looking for device control for removable storage, see [Microsoft Defender for Endpoint Device Control Removable Storage Access Control](../security/defender-endpoint/device-control-removable-storage-access-control.md#microsoft-defender-for-endpoint-device-control-removable-storage-access-control).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="49c77-110">Действия в конечных точках, которые вы можете отслеживать и реагировать на них</span><span class="sxs-lookup"><span data-stu-id="49c77-110">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="49c77-111">Защита от потери данных в конечной точке от Майкрософт позволяет проверять и управлять следующими типами действий, выполняемыми пользователями в отношении конфиденциальных элементов на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="49c77-111">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>

|<span data-ttu-id="49c77-112">Действие</span><span class="sxs-lookup"><span data-stu-id="49c77-112">Activity</span></span> |<span data-ttu-id="49c77-113">Описание</span><span class="sxs-lookup"><span data-stu-id="49c77-113">Description</span></span>  | <span data-ttu-id="49c77-114">Проверяемое/ограниченное</span><span class="sxs-lookup"><span data-stu-id="49c77-114">Auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="49c77-115">отправка в облачную службу или доступ запрещенными браузерами</span><span class="sxs-lookup"><span data-stu-id="49c77-115">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="49c77-116">Обнаруживает, когда пользователь пытается отправить элемент в запрещенный домен службы или получить доступ к элементу через браузер.</span><span class="sxs-lookup"><span data-stu-id="49c77-116">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="49c77-117">Если пользователь использует браузер, указанный в политике защиты от потери данных в качестве запрещенного браузера, то отправка будет заблокирована, а пользователь будет перенаправлен на использование Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="49c77-117">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="49c77-118">Edge Chromium либо разрешит, либо заблокирует отправку или доступ, в зависимости от конфигурации политики защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="49c77-118">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="49c77-119">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="49c77-119">auditable and restrictable</span></span>|
|<span data-ttu-id="49c77-120">копирование в другое приложение</span><span class="sxs-lookup"><span data-stu-id="49c77-120">copy to other app</span></span>    |<span data-ttu-id="49c77-121">Обнаруживает, когда пользователь пытается скопировать сведения из защищенного элемента, а затем вставить их в другое приложение, процесс или элемент.</span><span class="sxs-lookup"><span data-stu-id="49c77-121">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="49c77-122">Данное действие не обнаруживает копирование и вставку сведений в пределах одного приложения, процесса или элемента.</span><span class="sxs-lookup"><span data-stu-id="49c77-122">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="49c77-123">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="49c77-123">auditable and restrictable</span></span>|
|<span data-ttu-id="49c77-124">копирование на съемный USB-носитель</span><span class="sxs-lookup"><span data-stu-id="49c77-124">copy to USB removable media</span></span> |<span data-ttu-id="49c77-125">Обнаруживает, когда пользователь пытается скопировать элемент или сведения на съемный носитель или USB-устройство.</span><span class="sxs-lookup"><span data-stu-id="49c77-125">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="49c77-126">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="49c77-126">auditable and restrictable</span></span>|
|<span data-ttu-id="49c77-127">копирование в сетевую папку</span><span class="sxs-lookup"><span data-stu-id="49c77-127">copy to a network share</span></span>    |<span data-ttu-id="49c77-128">Обнаруживает, когда пользователь пытается скопировать элемент в сетевую папку или подключенный сетевой диск</span><span class="sxs-lookup"><span data-stu-id="49c77-128">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="49c77-129">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="49c77-129">auditable and restrictable</span></span>|
|<span data-ttu-id="49c77-130">печать документа</span><span class="sxs-lookup"><span data-stu-id="49c77-130">print a document</span></span>    |<span data-ttu-id="49c77-131">Обнаруживает, когда пользователь пытается распечатать защищенный элемент на локальном или сетевом принтере.</span><span class="sxs-lookup"><span data-stu-id="49c77-131">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="49c77-132">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="49c77-132">auditable and restrictable</span></span>         |
|<span data-ttu-id="49c77-133">копирование в удаленный сеанс</span><span class="sxs-lookup"><span data-stu-id="49c77-133">copy to a remote session</span></span>|<span data-ttu-id="49c77-134">Обнаруживает, когда пользователь пытается скопировать элемент в сеанс удаленного рабочего стола</span><span class="sxs-lookup"><span data-stu-id="49c77-134">Detects when a user attempts to copy an item to a remote desktop session</span></span> |  <span data-ttu-id="49c77-135">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="49c77-135">auditable and restrictable</span></span>|
|<span data-ttu-id="49c77-136">копирование на устройство Bluetooth</span><span class="sxs-lookup"><span data-stu-id="49c77-136">copy to a Bluetooth device</span></span>|<span data-ttu-id="49c77-137">Обнаруживает, когда пользователь пытается скопировать элемент в неразрешенное приложение Bluetooth (в соответствии с определением в списке неразрешенных приложений Bluetooth в параметрах DLP в конечной точке).</span><span class="sxs-lookup"><span data-stu-id="49c77-137">Detects when a user attempts to copy an item to an unallowed Bluetooth app (as defined in the list of unallowed Bluetooth aps in Endpoint DLP settings).</span></span>| <span data-ttu-id="49c77-138">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="49c77-138">auditable and restrictable</span></span>|
|<span data-ttu-id="49c77-139">создание элемента</span><span class="sxs-lookup"><span data-stu-id="49c77-139">create an item</span></span>|<span data-ttu-id="49c77-140">Обнаруживает, когда пользователь создает элемент.</span><span class="sxs-lookup"><span data-stu-id="49c77-140">Detects when a user creates an item</span></span>| <span data-ttu-id="49c77-141">проверяемое</span><span class="sxs-lookup"><span data-stu-id="49c77-141">auditable</span></span>|
|<span data-ttu-id="49c77-142">переименование элемента</span><span class="sxs-lookup"><span data-stu-id="49c77-142">rename an item</span></span>|<span data-ttu-id="49c77-143">Обнаруживает, когда пользователь переименовывает элемент.</span><span class="sxs-lookup"><span data-stu-id="49c77-143">Detects when a user renames an item</span></span>| <span data-ttu-id="49c77-144">проверяемое</span><span class="sxs-lookup"><span data-stu-id="49c77-144">auditable</span></span>|

## <a name="monitored-files"></a><span data-ttu-id="49c77-145">Отслеживаемые файлы</span><span class="sxs-lookup"><span data-stu-id="49c77-145">Monitored files</span></span>

<span data-ttu-id="49c77-146">Защита от потери данных для конечной точки поддерживает отслеживание следующих типов файлов.</span><span class="sxs-lookup"><span data-stu-id="49c77-146">Endpoint DLP supports monitoring of these file types:</span></span>

- <span data-ttu-id="49c77-147">Файлы Word</span><span class="sxs-lookup"><span data-stu-id="49c77-147">Word files</span></span>
- <span data-ttu-id="49c77-148">Файлы PowerPoint</span><span class="sxs-lookup"><span data-stu-id="49c77-148">PowerPoint files</span></span>
- <span data-ttu-id="49c77-149">Файлы Excel</span><span class="sxs-lookup"><span data-stu-id="49c77-149">Excel files</span></span>
- <span data-ttu-id="49c77-150">PDF-файлы</span><span class="sxs-lookup"><span data-stu-id="49c77-150">PDF files</span></span>
- <span data-ttu-id="49c77-151">CSV-файлы</span><span class="sxs-lookup"><span data-stu-id="49c77-151">.csv files</span></span>
- <span data-ttu-id="49c77-152">ТSV-файлы</span><span class="sxs-lookup"><span data-stu-id="49c77-152">.tsv files</span></span>
- <span data-ttu-id="49c77-153">TXT-файлы</span><span class="sxs-lookup"><span data-stu-id="49c77-153">.txt files</span></span>
- <span data-ttu-id="49c77-154">RTF-файлы</span><span class="sxs-lookup"><span data-stu-id="49c77-154">.rtf files</span></span>
- <span data-ttu-id="49c77-155">С-файлы</span><span class="sxs-lookup"><span data-stu-id="49c77-155">.c files</span></span>
- <span data-ttu-id="49c77-156">CLASS-файлы</span><span class="sxs-lookup"><span data-stu-id="49c77-156">.class files</span></span>
- <span data-ttu-id="49c77-157">CPP-файлы</span><span class="sxs-lookup"><span data-stu-id="49c77-157">.cpp files</span></span>
- <span data-ttu-id="49c77-158">CS-файлы</span><span class="sxs-lookup"><span data-stu-id="49c77-158">.cs files</span></span>
- <span data-ttu-id="49c77-159">H-файлы</span><span class="sxs-lookup"><span data-stu-id="49c77-159">.h files</span></span>
- <span data-ttu-id="49c77-160">JAVA-файлы</span><span class="sxs-lookup"><span data-stu-id="49c77-160">.java files</span></span>

<span data-ttu-id="49c77-161">По умолчанию защита от потери данных проводит аудит действий для этих типов файлов, даже если отсутствует соответствие политике.</span><span class="sxs-lookup"><span data-stu-id="49c77-161">By default, endpoint DLP audits the activities for these file types, even if there isn't a policy match.</span></span> <span data-ttu-id="49c77-162">Если вам нужно отслеживать данные только из совпадений политик, можно отключить параметр **Всегда проводить аудит активности файлов для устройств** в глобальных параметрах DLP конечной точки.</span><span class="sxs-lookup"><span data-stu-id="49c77-162">If you only want monitoring data from policy matches, you can turn off the **Always audit file activity for devices** in the endpoint DLP global settings.</span></span> <span data-ttu-id="49c77-163">Если этот параметр включен, действия с любыми файлами Word, PowerPoint, Excel, PDF и CSV всегда проверяются, даже если устройство не регулируется никакой политикой.</span><span class="sxs-lookup"><span data-stu-id="49c77-163">If this setting is on, activities on any Word, PowerPoint, Excel, PDF, and .csv file are always audited even if the device is not targeted by any policy.</span></span>

<span data-ttu-id="49c77-164">Защита от потери данных в конечной точке зависит от типа MIME, поэтому действия будут записываться даже при изменении расширения файла.</span><span class="sxs-lookup"><span data-stu-id="49c77-164">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span>

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="49c77-165">Чем отличается защита от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="49c77-165">What's different in Endpoint DLP</span></span>

<span data-ttu-id="49c77-166">Перед началом глубокой работы с защитой от потери данных в конечной точке необходимо учитывать ряд дополнительных понятий.</span><span class="sxs-lookup"><span data-stu-id="49c77-166">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="49c77-167">Включение управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="49c77-167">Enabling Device management</span></span>

<span data-ttu-id="49c77-168">Управление устройствами — это функция, позволяющая осуществлять сбор данных телеметрии с устройств и преобразование их в решения для обеспечения соответствия требованиям Microsoft 365, такие как Защита от потери данных в конечной точке и [Управление рисками в рамках программы предварительной оценки](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="49c77-168">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="49c77-169">Вам потребуется подключить все устройства, которые вы хотите использовать в качестве расположений в политиках защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="49c77-169">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="49c77-170">![включение управления устройствами](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="49c77-170">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="49c77-171">Подключение и отключение выполняется с помощью сценариев, скачанных из Центра управления устройствами.</span><span class="sxs-lookup"><span data-stu-id="49c77-171">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="49c77-172">В центре есть настраиваемые сценарии для каждого из этих методов развертывания:</span><span class="sxs-lookup"><span data-stu-id="49c77-172">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="49c77-173">локальный сценарий (до 10 компьютеров)</span><span class="sxs-lookup"><span data-stu-id="49c77-173">local script (up to 10 machines)</span></span>
- <span data-ttu-id="49c77-174">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="49c77-174">Group policy</span></span>
- <span data-ttu-id="49c77-175">System Center Configuration Manager (версия 1610 или более поздняя)</span><span class="sxs-lookup"><span data-stu-id="49c77-175">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="49c77-176">Управление мобильными устройствами/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="49c77-176">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="49c77-177">Сценарии подключения в инфраструктуре виртуальных рабочих столов (VDI) для временных компьютеров</span><span class="sxs-lookup"><span data-stu-id="49c77-177">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="49c77-178">![страница подключения устройств](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="49c77-178">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="49c77-179">Для подключения устройств используйте процедуры, описанные в статье [Начало работы с Защитой от потери данных в конечной точке в Microsoft 365](endpoint-dlp-getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="49c77-179">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="49c77-180">Если вы подключили устройства с помощью [Microsoft Defender для конечной точки](/windows/security/threat-protection/), эти устройства будут автоматически отображаться в списке устройств.</span><span class="sxs-lookup"><span data-stu-id="49c77-180">If you have onboarded devices through [Microsoft Defender for Endpoint](/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="49c77-181">![список управляемых устройств](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="49c77-181">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="49c77-182">Просмотр данных защиты от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="49c77-182">Viewing Endpoint DLP data</span></span>

<span data-ttu-id="49c77-183">Вы можете просмотреть оповещения, связанные с политиками защиты от потери данных, примененными на устройствах конечных точек, перейдя на [панель мониторинга для управления оповещениями защиты от потери данных](dlp-configure-view-alerts-policies.md).</span><span class="sxs-lookup"><span data-stu-id="49c77-183">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="49c77-184">![Сведения оповещения](../media/Alert-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="49c77-184">![Alert info](../media/Alert-info-1.png)</span></span>

<span data-ttu-id="49c77-185">Вы также можете просматривать сведения о родственном событии с расширенными метаданными на той же панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="49c77-185">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="49c77-186">![сведения о событии](../media/Event-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="49c77-186">![event info](../media/Event-info-1.png)</span></span>

<span data-ttu-id="49c77-187">После подключения устройства сведения о действиях, прошедших аудит, передаются в обозреватель действий даже до настройки и развертывания любой политики защиты от потери данных с устройствами в качестве расположения.</span><span class="sxs-lookup"><span data-stu-id="49c77-187">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="49c77-188">![события защиты от потери данных в конечной точке в обозревателе действий](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="49c77-188">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="49c77-189">Защита от потери данных в конечной точке собирает подробную информацию о действиях, прошедших аудит.</span><span class="sxs-lookup"><span data-stu-id="49c77-189">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="49c77-190">Например, если файл копируется на съемный USB-носитель, то в подробных сведениях о действиях будут отображаться указанные ниже атрибуты:</span><span class="sxs-lookup"><span data-stu-id="49c77-190">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="49c77-191">тип действия</span><span class="sxs-lookup"><span data-stu-id="49c77-191">activity type</span></span>
- <span data-ttu-id="49c77-192">IP-адрес клиента</span><span class="sxs-lookup"><span data-stu-id="49c77-192">client IP</span></span>
- <span data-ttu-id="49c77-193">путь к целевому файлу</span><span class="sxs-lookup"><span data-stu-id="49c77-193">target file path</span></span>
- <span data-ttu-id="49c77-194">временная метка события</span><span class="sxs-lookup"><span data-stu-id="49c77-194">happened timestamp</span></span>
- <span data-ttu-id="49c77-195">имя файла</span><span class="sxs-lookup"><span data-stu-id="49c77-195">file name</span></span>
- <span data-ttu-id="49c77-196">пользователь</span><span class="sxs-lookup"><span data-stu-id="49c77-196">user</span></span>
- <span data-ttu-id="49c77-197">расширение файла</span><span class="sxs-lookup"><span data-stu-id="49c77-197">file extension</span></span>
- <span data-ttu-id="49c77-198">размер файла</span><span class="sxs-lookup"><span data-stu-id="49c77-198">file size</span></span>
- <span data-ttu-id="49c77-199">типы конфиденциальной информации (если применимо)</span><span class="sxs-lookup"><span data-stu-id="49c77-199">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="49c77-200">значение SHA1</span><span class="sxs-lookup"><span data-stu-id="49c77-200">sha1 value</span></span>
- <span data-ttu-id="49c77-201">значение SHA256</span><span class="sxs-lookup"><span data-stu-id="49c77-201">sha256 value</span></span>
- <span data-ttu-id="49c77-202">предыдущее имя файла</span><span class="sxs-lookup"><span data-stu-id="49c77-202">previous file name</span></span>
- <span data-ttu-id="49c77-203">расположение</span><span class="sxs-lookup"><span data-stu-id="49c77-203">location</span></span>
- <span data-ttu-id="49c77-204">родитель</span><span class="sxs-lookup"><span data-stu-id="49c77-204">parent</span></span>
- <span data-ttu-id="49c77-205">путь к файлу</span><span class="sxs-lookup"><span data-stu-id="49c77-205">filepath</span></span>
- <span data-ttu-id="49c77-206">тип исходного расположения</span><span class="sxs-lookup"><span data-stu-id="49c77-206">source location type</span></span>
- <span data-ttu-id="49c77-207">платформа</span><span class="sxs-lookup"><span data-stu-id="49c77-207">platform</span></span>
- <span data-ttu-id="49c77-208">имя устройства</span><span class="sxs-lookup"><span data-stu-id="49c77-208">device name</span></span>
- <span data-ttu-id="49c77-209">тип конечного расположения</span><span class="sxs-lookup"><span data-stu-id="49c77-209">destination location type</span></span>
- <span data-ttu-id="49c77-210">приложение, которое выполнило копирование</span><span class="sxs-lookup"><span data-stu-id="49c77-210">application that performed the copy</span></span>
- <span data-ttu-id="49c77-211">ИД устройства Microsoft Defender для конечной точки (если применимо)</span><span class="sxs-lookup"><span data-stu-id="49c77-211">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="49c77-212">производитель съемного носителя</span><span class="sxs-lookup"><span data-stu-id="49c77-212">removable media device manufacturer</span></span>
- <span data-ttu-id="49c77-213">модель съемного носителя</span><span class="sxs-lookup"><span data-stu-id="49c77-213">removable media device model</span></span>
- <span data-ttu-id="49c77-214">серийный номер съемного носителя</span><span class="sxs-lookup"><span data-stu-id="49c77-214">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="49c77-215">![атрибуты действий копирования на USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="49c77-215">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="49c77-216">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="49c77-216">Next steps</span></span>

<span data-ttu-id="49c77-217">Теперь, когда вы узнали о защите от потери данных в конечной точке, ознакомьтесь со следующим:</span><span class="sxs-lookup"><span data-stu-id="49c77-217">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1. [<span data-ttu-id="49c77-218">Начало работы с защитой от потери данных в конечной точке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="49c77-218">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
2. [<span data-ttu-id="49c77-219">Использование защиты от потери данных в конечной точке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="49c77-219">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="49c77-220">См. также</span><span class="sxs-lookup"><span data-stu-id="49c77-220">See also</span></span>

- [<span data-ttu-id="49c77-221">Начало работы с защитой от потери данных в конечной точке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="49c77-221">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="49c77-222">Использование защиты от потери данных в конечной точке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="49c77-222">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="49c77-223">Сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="49c77-223">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="49c77-224">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="49c77-224">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="49c77-225">Начало работы с обозревателем действий</span><span class="sxs-lookup"><span data-stu-id="49c77-225">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="49c77-226">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="49c77-226">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="49c77-227">Управление рисками в рамках программы предварительной оценки</span><span class="sxs-lookup"><span data-stu-id="49c77-227">Insider Risk management</span></span>](insider-risk-management.md)
