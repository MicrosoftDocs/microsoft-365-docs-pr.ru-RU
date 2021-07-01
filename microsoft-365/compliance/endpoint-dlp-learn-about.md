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
ms.openlocfilehash: 39474f54440ba33c8d7140981c1495a5c46bf0fc
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226687"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="ca523-104">Сведения о защите от потери данных в конечной точке Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ca523-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="ca523-105">Защиту от потери данных (DLP) в Microsoft 365 можно использовать для отслеживания действий, принятых в отношении элементов, которые были определены как конфиденциальные, и для защиты от непреднамеренного обмена этими элементами.</span><span class="sxs-lookup"><span data-stu-id="ca523-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="ca523-106">Подробная информация приведена в статье [Сведения о защите от потери данных](dlp-learn-about-dlp.md).</span><span class="sxs-lookup"><span data-stu-id="ca523-106">For more information on DLP, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="ca523-107">**Защита от потери данных в конечной точке (DLP в конечной точке)** расширяет возможности отслеживания действий и защиты от потери данных для конфиденциальных элементов на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ca523-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="ca523-108">После того как устройства будут подключены к решениям по обеспечению соответствия требованиям Microsoft 365, сведения о действиях пользователей с конфиденциальными элементами становятся видимыми в [обозревателе действий](data-classification-activity-explorer.md) и вы можете принудительно применять защитные действия к ним с помощью [политик защиты от потери данных](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="ca523-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="ca523-109">Действия в конечных точках, которые вы можете отслеживать и реагировать на них</span><span class="sxs-lookup"><span data-stu-id="ca523-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="ca523-110">Защита от потери данных в конечной точке от Майкрософт позволяет проверять и управлять следующими типами действий, выполняемыми пользователями в отношении конфиденциальных элементов на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ca523-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>

|<span data-ttu-id="ca523-111">Действие</span><span class="sxs-lookup"><span data-stu-id="ca523-111">Activity</span></span> |<span data-ttu-id="ca523-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ca523-112">Description</span></span>  | <span data-ttu-id="ca523-113">Проверяемое/ограниченное</span><span class="sxs-lookup"><span data-stu-id="ca523-113">Auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="ca523-114">отправка в облачную службу или доступ запрещенными браузерами</span><span class="sxs-lookup"><span data-stu-id="ca523-114">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="ca523-115">Обнаруживает, когда пользователь пытается отправить элемент в запрещенный домен службы или получить доступ к элементу через браузер.</span><span class="sxs-lookup"><span data-stu-id="ca523-115">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="ca523-116">Если пользователь использует браузер, указанный в политике защиты от потери данных в качестве запрещенного браузера, то отправка будет заблокирована, а пользователь будет перенаправлен на использование Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="ca523-116">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="ca523-117">Edge Chromium либо разрешит, либо заблокирует отправку или доступ, в зависимости от конфигурации политики защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="ca523-117">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="ca523-118">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="ca523-118">auditable and restrictable</span></span>|
|<span data-ttu-id="ca523-119">копирование в другое приложение</span><span class="sxs-lookup"><span data-stu-id="ca523-119">copy to other app</span></span>    |<span data-ttu-id="ca523-120">Обнаруживает, когда пользователь пытается скопировать сведения из защищенного элемента, а затем вставить их в другое приложение, процесс или элемент.</span><span class="sxs-lookup"><span data-stu-id="ca523-120">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="ca523-121">Данное действие не обнаруживает копирование и вставку сведений в пределах одного приложения, процесса или элемента.</span><span class="sxs-lookup"><span data-stu-id="ca523-121">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="ca523-122">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="ca523-122">auditable and restrictable</span></span>|
|<span data-ttu-id="ca523-123">копирование на съемный USB-носитель</span><span class="sxs-lookup"><span data-stu-id="ca523-123">copy to USB removable media</span></span> |<span data-ttu-id="ca523-124">Обнаруживает, когда пользователь пытается скопировать элемент или сведения на съемный носитель или USB-устройство.</span><span class="sxs-lookup"><span data-stu-id="ca523-124">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="ca523-125">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="ca523-125">auditable and restrictable</span></span>|
|<span data-ttu-id="ca523-126">копирование в сетевую папку</span><span class="sxs-lookup"><span data-stu-id="ca523-126">copy to a network share</span></span>    |<span data-ttu-id="ca523-127">Обнаруживает, когда пользователь пытается скопировать элемент в сетевую папку или подключенный сетевой диск</span><span class="sxs-lookup"><span data-stu-id="ca523-127">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="ca523-128">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="ca523-128">auditable and restrictable</span></span>|
|<span data-ttu-id="ca523-129">печать документа</span><span class="sxs-lookup"><span data-stu-id="ca523-129">print a document</span></span>    |<span data-ttu-id="ca523-130">Обнаруживает, когда пользователь пытается распечатать защищенный элемент на локальном или сетевом принтере.</span><span class="sxs-lookup"><span data-stu-id="ca523-130">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="ca523-131">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="ca523-131">auditable and restrictable</span></span>         |
|<span data-ttu-id="ca523-132">копирование в удаленный сеанс</span><span class="sxs-lookup"><span data-stu-id="ca523-132">copy to a remote session</span></span>|<span data-ttu-id="ca523-133">Обнаруживает, когда пользователь пытается скопировать элемент в сеанс удаленного рабочего стола</span><span class="sxs-lookup"><span data-stu-id="ca523-133">Detects when a user attempts to copy an item to a remote desktop session</span></span> |  <span data-ttu-id="ca523-134">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="ca523-134">auditable and restrictable</span></span>|
|<span data-ttu-id="ca523-135">копирование на устройство Bluetooth</span><span class="sxs-lookup"><span data-stu-id="ca523-135">copy to a Bluetooth device</span></span>|<span data-ttu-id="ca523-136">Обнаруживает, когда пользователь пытается скопировать элемент в неразрешенное приложение Bluetooth (в соответствии с определением в списке неразрешенных приложений Bluetooth в параметрах DLP в конечной точке).</span><span class="sxs-lookup"><span data-stu-id="ca523-136">Detects when a user attempts to copy an item to an unallowed Bluetooth app (as defined in the list of unallowed Bluetooth aps in Endpoint DLP settings).</span></span>| <span data-ttu-id="ca523-137">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="ca523-137">auditable and restrictable</span></span>|
|<span data-ttu-id="ca523-138">создание элемента</span><span class="sxs-lookup"><span data-stu-id="ca523-138">create an item</span></span>|<span data-ttu-id="ca523-139">Обнаруживает, когда пользователь создает элемент.</span><span class="sxs-lookup"><span data-stu-id="ca523-139">Detects when a user creates an item</span></span>| <span data-ttu-id="ca523-140">проверяемое</span><span class="sxs-lookup"><span data-stu-id="ca523-140">auditable</span></span>|
|<span data-ttu-id="ca523-141">переименование элемента</span><span class="sxs-lookup"><span data-stu-id="ca523-141">rename an item</span></span>|<span data-ttu-id="ca523-142">Обнаруживает, когда пользователь переименовывает элемент.</span><span class="sxs-lookup"><span data-stu-id="ca523-142">Detects when a user renames an item</span></span>| <span data-ttu-id="ca523-143">проверяемое</span><span class="sxs-lookup"><span data-stu-id="ca523-143">auditable</span></span>|

## <a name="monitored-files"></a><span data-ttu-id="ca523-144">Отслеживаемые файлы</span><span class="sxs-lookup"><span data-stu-id="ca523-144">Monitored files</span></span>

<span data-ttu-id="ca523-145">Защита от потери данных для конечной точки поддерживает отслеживание следующих типов файлов.</span><span class="sxs-lookup"><span data-stu-id="ca523-145">Endpoint DLP supports monitoring of these file types:</span></span>

- <span data-ttu-id="ca523-146">Файлы Word</span><span class="sxs-lookup"><span data-stu-id="ca523-146">Word files</span></span>
- <span data-ttu-id="ca523-147">Файлы PowerPoint</span><span class="sxs-lookup"><span data-stu-id="ca523-147">PowerPoint files</span></span>
- <span data-ttu-id="ca523-148">Файлы Excel</span><span class="sxs-lookup"><span data-stu-id="ca523-148">Excel files</span></span>
- <span data-ttu-id="ca523-149">PDF-файлы</span><span class="sxs-lookup"><span data-stu-id="ca523-149">PDF files</span></span>
- <span data-ttu-id="ca523-150">CSV-файлы</span><span class="sxs-lookup"><span data-stu-id="ca523-150">.csv files</span></span>
- <span data-ttu-id="ca523-151">ТSV-файлы</span><span class="sxs-lookup"><span data-stu-id="ca523-151">.tsv files</span></span>
- <span data-ttu-id="ca523-152">TXT-файлы</span><span class="sxs-lookup"><span data-stu-id="ca523-152">.txt files</span></span>
- <span data-ttu-id="ca523-153">RTF-файлы</span><span class="sxs-lookup"><span data-stu-id="ca523-153">.rtf files</span></span>
- <span data-ttu-id="ca523-154">С-файлы</span><span class="sxs-lookup"><span data-stu-id="ca523-154">.c files</span></span>
- <span data-ttu-id="ca523-155">CLASS-файлы</span><span class="sxs-lookup"><span data-stu-id="ca523-155">.class files</span></span>
- <span data-ttu-id="ca523-156">CPP-файлы</span><span class="sxs-lookup"><span data-stu-id="ca523-156">.cpp files</span></span>
- <span data-ttu-id="ca523-157">CS-файлы</span><span class="sxs-lookup"><span data-stu-id="ca523-157">.cs files</span></span>
- <span data-ttu-id="ca523-158">H-файлы</span><span class="sxs-lookup"><span data-stu-id="ca523-158">.h files</span></span>
- <span data-ttu-id="ca523-159">JAVA-файлы</span><span class="sxs-lookup"><span data-stu-id="ca523-159">.java files</span></span>

<span data-ttu-id="ca523-160">По умолчанию защита от потери данных проводит аудит действий для этих типов файлов, даже если отсутствует соответствие политике.</span><span class="sxs-lookup"><span data-stu-id="ca523-160">By default, endpoint DLP audits the activities for these file types, even if there isn't a policy match.</span></span> <span data-ttu-id="ca523-161">Если вам нужно отслеживать данные только из совпадений политик, можно отключить параметр **Всегда проводить аудит активности файлов для устройств** в глобальных параметрах DLP конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ca523-161">If you only want monitoring data from policy matches, you can turn off the **Always audit file activity for devices** in the endpoint DLP global settings.</span></span> <span data-ttu-id="ca523-162">Если этот параметр включен, действия с любыми файлами Word, PowerPoint, Excel, PDF и CSV всегда проверяются, даже если устройство не регулируется никакой политикой.</span><span class="sxs-lookup"><span data-stu-id="ca523-162">If this setting is on, activities on any Word, PowerPoint, Excel, PDF, and .csv file are always audited even if the device is not targeted by any policy.</span></span>

<span data-ttu-id="ca523-163">Защита от потери данных в конечной точке зависит от типа MIME, поэтому действия будут записываться даже при изменении расширения файла.</span><span class="sxs-lookup"><span data-stu-id="ca523-163">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span>

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="ca523-164">Чем отличается защита от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="ca523-164">What's different in Endpoint DLP</span></span>

<span data-ttu-id="ca523-165">Перед началом глубокой работы с защитой от потери данных в конечной точке необходимо учитывать ряд дополнительных понятий.</span><span class="sxs-lookup"><span data-stu-id="ca523-165">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="ca523-166">Включение управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="ca523-166">Enabling Device management</span></span>

<span data-ttu-id="ca523-167">Управление устройствами — это функция, позволяющая осуществлять сбор данных телеметрии с устройств и преобразование их в решения для обеспечения соответствия требованиям Microsoft 365, такие как Защита от потери данных в конечной точке и [Управление рисками в рамках программы предварительной оценки](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="ca523-167">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="ca523-168">Вам потребуется подключить все устройства, которые вы хотите использовать в качестве расположений в политиках защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="ca523-168">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ca523-169">![включение управления устройствами](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="ca523-169">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="ca523-170">Подключение и отключение выполняется с помощью сценариев, скачанных из Центра управления устройствами.</span><span class="sxs-lookup"><span data-stu-id="ca523-170">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="ca523-171">В центре есть настраиваемые сценарии для каждого из этих методов развертывания:</span><span class="sxs-lookup"><span data-stu-id="ca523-171">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="ca523-172">локальный сценарий (до 10 компьютеров)</span><span class="sxs-lookup"><span data-stu-id="ca523-172">local script (up to 10 machines)</span></span>
- <span data-ttu-id="ca523-173">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="ca523-173">Group policy</span></span>
- <span data-ttu-id="ca523-174">System Center Configuration Manager (версия 1610 или более поздняя)</span><span class="sxs-lookup"><span data-stu-id="ca523-174">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="ca523-175">Управление мобильными устройствами/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ca523-175">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="ca523-176">Сценарии подключения в инфраструктуре виртуальных рабочих столов (VDI) для временных компьютеров</span><span class="sxs-lookup"><span data-stu-id="ca523-176">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ca523-177">![страница подключения устройств](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="ca523-177">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="ca523-178">Для подключения устройств используйте процедуры, описанные в статье [Начало работы с Защитой от потери данных в конечной точке в Microsoft 365](endpoint-dlp-getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="ca523-178">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="ca523-179">Если вы подключили устройства с помощью [Microsoft Defender для конечной точки](/windows/security/threat-protection/), эти устройства будут автоматически отображаться в списке устройств.</span><span class="sxs-lookup"><span data-stu-id="ca523-179">If you have onboarded devices through [Microsoft Defender for Endpoint](/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ca523-180">![список управляемых устройств](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="ca523-180">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="ca523-181">Просмотр данных защиты от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="ca523-181">Viewing Endpoint DLP data</span></span>

<span data-ttu-id="ca523-182">Вы можете просмотреть оповещения, связанные с политиками защиты от потери данных, примененными на устройствах конечных точек, перейдя на [панель мониторинга для управления оповещениями защиты от потери данных](dlp-configure-view-alerts-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ca523-182">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ca523-183">![Сведения оповещения](../media/Alert-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="ca523-183">![Alert info](../media/Alert-info-1.png)</span></span>

<span data-ttu-id="ca523-184">Вы также можете просматривать сведения о родственном событии с расширенными метаданными на той же панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="ca523-184">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ca523-185">![сведения о событии](../media/Event-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="ca523-185">![event info](../media/Event-info-1.png)</span></span>

<span data-ttu-id="ca523-186">После подключения устройства сведения о действиях, прошедших аудит, передаются в обозреватель действий даже до настройки и развертывания любой политики защиты от потери данных с устройствами в качестве расположения.</span><span class="sxs-lookup"><span data-stu-id="ca523-186">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ca523-187">![события защиты от потери данных в конечной точке в обозревателе действий](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="ca523-187">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="ca523-188">Защита от потери данных в конечной точке собирает подробную информацию о действиях, прошедших аудит.</span><span class="sxs-lookup"><span data-stu-id="ca523-188">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="ca523-189">Например, если файл копируется на съемный USB-носитель, то в подробных сведениях о действиях будут отображаться указанные ниже атрибуты:</span><span class="sxs-lookup"><span data-stu-id="ca523-189">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="ca523-190">тип действия</span><span class="sxs-lookup"><span data-stu-id="ca523-190">activity type</span></span>
- <span data-ttu-id="ca523-191">IP-адрес клиента</span><span class="sxs-lookup"><span data-stu-id="ca523-191">client IP</span></span>
- <span data-ttu-id="ca523-192">путь к целевому файлу</span><span class="sxs-lookup"><span data-stu-id="ca523-192">target file path</span></span>
- <span data-ttu-id="ca523-193">временная метка события</span><span class="sxs-lookup"><span data-stu-id="ca523-193">happened timestamp</span></span>
- <span data-ttu-id="ca523-194">имя файла</span><span class="sxs-lookup"><span data-stu-id="ca523-194">file name</span></span>
- <span data-ttu-id="ca523-195">пользователь</span><span class="sxs-lookup"><span data-stu-id="ca523-195">user</span></span>
- <span data-ttu-id="ca523-196">расширение файла</span><span class="sxs-lookup"><span data-stu-id="ca523-196">file extension</span></span>
- <span data-ttu-id="ca523-197">размер файла</span><span class="sxs-lookup"><span data-stu-id="ca523-197">file size</span></span>
- <span data-ttu-id="ca523-198">типы конфиденциальной информации (если применимо)</span><span class="sxs-lookup"><span data-stu-id="ca523-198">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="ca523-199">значение SHA1</span><span class="sxs-lookup"><span data-stu-id="ca523-199">sha1 value</span></span>
- <span data-ttu-id="ca523-200">значение SHA256</span><span class="sxs-lookup"><span data-stu-id="ca523-200">sha256 value</span></span>
- <span data-ttu-id="ca523-201">предыдущее имя файла</span><span class="sxs-lookup"><span data-stu-id="ca523-201">previous file name</span></span>
- <span data-ttu-id="ca523-202">расположение</span><span class="sxs-lookup"><span data-stu-id="ca523-202">location</span></span>
- <span data-ttu-id="ca523-203">родитель</span><span class="sxs-lookup"><span data-stu-id="ca523-203">parent</span></span>
- <span data-ttu-id="ca523-204">путь к файлу</span><span class="sxs-lookup"><span data-stu-id="ca523-204">filepath</span></span>
- <span data-ttu-id="ca523-205">тип исходного расположения</span><span class="sxs-lookup"><span data-stu-id="ca523-205">source location type</span></span>
- <span data-ttu-id="ca523-206">платформа</span><span class="sxs-lookup"><span data-stu-id="ca523-206">platform</span></span>
- <span data-ttu-id="ca523-207">имя устройства</span><span class="sxs-lookup"><span data-stu-id="ca523-207">device name</span></span>
- <span data-ttu-id="ca523-208">тип конечного расположения</span><span class="sxs-lookup"><span data-stu-id="ca523-208">destination location type</span></span>
- <span data-ttu-id="ca523-209">приложение, которое выполнило копирование</span><span class="sxs-lookup"><span data-stu-id="ca523-209">application that performed the copy</span></span>
- <span data-ttu-id="ca523-210">ИД устройства Microsoft Defender для конечной точки (если применимо)</span><span class="sxs-lookup"><span data-stu-id="ca523-210">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="ca523-211">производитель съемного носителя</span><span class="sxs-lookup"><span data-stu-id="ca523-211">removable media device manufacturer</span></span>
- <span data-ttu-id="ca523-212">модель съемного носителя</span><span class="sxs-lookup"><span data-stu-id="ca523-212">removable media device model</span></span>
- <span data-ttu-id="ca523-213">серийный номер съемного носителя</span><span class="sxs-lookup"><span data-stu-id="ca523-213">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ca523-214">![атрибуты действий копирования на USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="ca523-214">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="ca523-215">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="ca523-215">Next steps</span></span>

<span data-ttu-id="ca523-216">Теперь, когда вы узнали о защите от потери данных в конечной точке, ознакомьтесь со следующим:</span><span class="sxs-lookup"><span data-stu-id="ca523-216">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1. [<span data-ttu-id="ca523-217">Начало работы с защитой от потери данных в конечной точке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ca523-217">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
2. [<span data-ttu-id="ca523-218">Использование защиты от потери данных в конечной точке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ca523-218">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="ca523-219">См. также</span><span class="sxs-lookup"><span data-stu-id="ca523-219">See also</span></span>

- [<span data-ttu-id="ca523-220">Начало работы с защитой от потери данных в конечной точке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ca523-220">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="ca523-221">Использование защиты от потери данных в конечной точке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ca523-221">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="ca523-222">Сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="ca523-222">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="ca523-223">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="ca523-223">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="ca523-224">Начало работы с обозревателем действий</span><span class="sxs-lookup"><span data-stu-id="ca523-224">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="ca523-225">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ca523-225">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="ca523-226">Управление рисками в рамках программы предварительной оценки</span><span class="sxs-lookup"><span data-stu-id="ca523-226">Insider Risk management</span></span>](insider-risk-management.md)
