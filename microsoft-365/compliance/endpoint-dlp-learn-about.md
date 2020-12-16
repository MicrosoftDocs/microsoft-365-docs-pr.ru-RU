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
ms.openlocfilehash: 1dac32505144c3966ad2219cc69a33ba29f194dc
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682630"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="84c19-104">Сведения о защите от потери данных в конечной точке Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="84c19-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="84c19-105">Защиту от потери данных (DLP) в Microsoft 365 можно использовать для отслеживания действий, принятых в отношении элементов, которые были определены как конфиденциальные, и для защиты от непреднамеренного обмена этими элементами.</span><span class="sxs-lookup"><span data-stu-id="84c19-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="84c19-106">Подробная информация приведена в статье [Обзор защиты от потери данных](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="84c19-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="84c19-107">**Защита от потери данных в конечной точке (DLP в конечной точке)** расширяет возможности отслеживания действий и защиты от потери данных для конфиденциальных элементов на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="84c19-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="84c19-108">После того как устройства будут подключены к решениям по обеспечению соответствия требованиям Microsoft 365, сведения о действиях пользователей с конфиденциальными элементами становятся видимыми в [обозревателе действий](data-classification-activity-explorer.md) и вы можете принудительно применять защитные действия к ним с помощью [политик защиты от потери данных](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="84c19-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="84c19-109">Действия в конечных точках, которые вы можете отслеживать и реагировать на них</span><span class="sxs-lookup"><span data-stu-id="84c19-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="84c19-110">Защита от потери данных в конечной точке от Майкрософт позволяет проверять и управлять следующими типами действий, выполняемыми пользователями в отношении конфиденциальных элементов на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="84c19-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>


|<span data-ttu-id="84c19-111">действие</span><span class="sxs-lookup"><span data-stu-id="84c19-111">activity</span></span> |<span data-ttu-id="84c19-112">описание</span><span class="sxs-lookup"><span data-stu-id="84c19-112">description</span></span>  | <span data-ttu-id="84c19-113">проверяемое/ограниченное</span><span class="sxs-lookup"><span data-stu-id="84c19-113">auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="84c19-114">отправка в облачную службу или доступ запрещенными браузерами</span><span class="sxs-lookup"><span data-stu-id="84c19-114">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="84c19-115">Обнаруживает, когда пользователь пытается отправить элемент в запрещенный домен службы или получить доступ к элементу через браузер.</span><span class="sxs-lookup"><span data-stu-id="84c19-115">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="84c19-116">Если пользователь использует браузер, указанный в политике защиты от потери данных в качестве запрещенного браузера, то отправка будет заблокирована, а пользователь будет перенаправлен на использование Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="84c19-116">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="84c19-117">Edge Chromium либо разрешит, либо заблокирует отправку или доступ, в зависимости от конфигурации политики защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="84c19-117">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="84c19-118">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="84c19-118">auditable and restrictable</span></span>|
|<span data-ttu-id="84c19-119">копирование в другое приложение</span><span class="sxs-lookup"><span data-stu-id="84c19-119">copy to other app</span></span>    |<span data-ttu-id="84c19-120">Обнаруживает, когда пользователь пытается скопировать сведения из защищенного элемента, а затем вставить их в другое приложение, процесс или элемент.</span><span class="sxs-lookup"><span data-stu-id="84c19-120">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="84c19-121">Данное действие не обнаруживает копирование и вставку сведений в пределах одного приложения, процесса или элемента.</span><span class="sxs-lookup"><span data-stu-id="84c19-121">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="84c19-122">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="84c19-122">auditable and restrictable</span></span>|
|<span data-ttu-id="84c19-123">копирование на съемный USB-носитель</span><span class="sxs-lookup"><span data-stu-id="84c19-123">copy to USB removable media</span></span> |<span data-ttu-id="84c19-124">Обнаруживает, когда пользователь пытается скопировать элемент или сведения на съемный носитель или USB-устройство.</span><span class="sxs-lookup"><span data-stu-id="84c19-124">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="84c19-125">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="84c19-125">auditable and restrictable</span></span>|
|<span data-ttu-id="84c19-126">копирование в сетевую папку</span><span class="sxs-lookup"><span data-stu-id="84c19-126">copy to a network share</span></span>    |<span data-ttu-id="84c19-127">Обнаруживает, когда пользователь пытается скопировать элемент в сетевую папку или подключенный сетевой диск</span><span class="sxs-lookup"><span data-stu-id="84c19-127">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="84c19-128">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="84c19-128">auditable and restrictable</span></span>|
|<span data-ttu-id="84c19-129">печать документа</span><span class="sxs-lookup"><span data-stu-id="84c19-129">print a document</span></span>    |<span data-ttu-id="84c19-130">Обнаруживает, когда пользователь пытается распечатать защищенный элемент на локальном или сетевом принтере.</span><span class="sxs-lookup"><span data-stu-id="84c19-130">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="84c19-131">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="84c19-131">auditable and restrictable</span></span>         |
|<span data-ttu-id="84c19-132">создание элемента</span><span class="sxs-lookup"><span data-stu-id="84c19-132">create an item</span></span>|<span data-ttu-id="84c19-133">Обнаруживает, когда пользователь создает элемент.</span><span class="sxs-lookup"><span data-stu-id="84c19-133">Detects when a user creates an item</span></span>| <span data-ttu-id="84c19-134">проверяемое</span><span class="sxs-lookup"><span data-stu-id="84c19-134">auditable</span></span>|
|<span data-ttu-id="84c19-135">переименование элемента</span><span class="sxs-lookup"><span data-stu-id="84c19-135">rename an item</span></span>|<span data-ttu-id="84c19-136">Обнаруживает, когда пользователь переименовывает элемент.</span><span class="sxs-lookup"><span data-stu-id="84c19-136">Detects when a user renames an item</span></span>| <span data-ttu-id="84c19-137">проверяемое</span><span class="sxs-lookup"><span data-stu-id="84c19-137">auditable</span></span>|


## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="84c19-138">Чем отличается защита от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="84c19-138">What's different in Endpoint DLP</span></span>

<span data-ttu-id="84c19-139">Перед началом глубокой работы с защитой от потери данных в конечной точке необходимо учитывать ряд дополнительных понятий.</span><span class="sxs-lookup"><span data-stu-id="84c19-139">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="84c19-140">Включение управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="84c19-140">Enabling Device management</span></span>

<span data-ttu-id="84c19-141">Управление устройствами — это функция, позволяющая осуществлять сбор данных телеметрии с устройств и преобразование их в решения для обеспечения соответствия требованиям Microsoft 365, такие как Защита от потери данных в конечной точке и [Управление рисками в рамках программы предварительной оценки](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="84c19-141">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="84c19-142">Вам потребуется подключить все устройства, которые вы хотите использовать в качестве расположений в политиках защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="84c19-142">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="84c19-143">![включение управления устройствами](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="84c19-143">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="84c19-144">Подключение и отключение выполняется с помощью сценариев, скачанных из Центра управления устройствами.</span><span class="sxs-lookup"><span data-stu-id="84c19-144">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="84c19-145">В центре есть настраиваемые сценарии для каждого из этих методов развертывания:</span><span class="sxs-lookup"><span data-stu-id="84c19-145">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="84c19-146">локальный сценарий (до 10 компьютеров)</span><span class="sxs-lookup"><span data-stu-id="84c19-146">local script (up to 10 machines)</span></span>
- <span data-ttu-id="84c19-147">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="84c19-147">Group policy</span></span>
- <span data-ttu-id="84c19-148">System Center Configuration Manager (версия 1610 или более поздняя)</span><span class="sxs-lookup"><span data-stu-id="84c19-148">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="84c19-149">Управление мобильными устройствами/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="84c19-149">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="84c19-150">Сценарии подключения в инфраструктуре виртуальных рабочих столов (VDI) для временных компьютеров</span><span class="sxs-lookup"><span data-stu-id="84c19-150">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="84c19-151">![страница подключения устройств](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="84c19-151">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="84c19-152">Для подключения устройств используйте процедуры, описанные в статье [Начало работы с Защитой от потери данных в конечной точке в Microsoft 365](endpoint-dlp-getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="84c19-152">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="84c19-153">Если вы подключили устройства с помощью [Microsoft Defender для конечной точки](https://docs.microsoft.com/windows/security/threat-protection/), эти устройства будут автоматически отображаться в списке устройств.</span><span class="sxs-lookup"><span data-stu-id="84c19-153">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="84c19-154">![список управляемых устройств](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="84c19-154">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="84c19-155">Просмотр данных защиты от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="84c19-155">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="84c19-156">Защита от потери данных в конечной точке зависит от типа MIME, поэтому действия будут записываться даже при изменении расширения файла.</span><span class="sxs-lookup"><span data-stu-id="84c19-156">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span> <span data-ttu-id="84c19-157">В настоящее время поддерживаются следующие типы файлов:</span><span class="sxs-lookup"><span data-stu-id="84c19-157">At this time the following file types are supported:</span></span>

- <span data-ttu-id="84c19-158">Файлы Word</span><span class="sxs-lookup"><span data-stu-id="84c19-158">Word files</span></span>
- <span data-ttu-id="84c19-159">Файлы PowerPoint</span><span class="sxs-lookup"><span data-stu-id="84c19-159">PowerPoint files</span></span>
- <span data-ttu-id="84c19-160">Файлы Excel</span><span class="sxs-lookup"><span data-stu-id="84c19-160">Excel files</span></span>
- <span data-ttu-id="84c19-161">PDF-файлы</span><span class="sxs-lookup"><span data-stu-id="84c19-161">PDF files</span></span>
- <span data-ttu-id="84c19-162">CSV-файлы</span><span class="sxs-lookup"><span data-stu-id="84c19-162">.csv files</span></span>
- <span data-ttu-id="84c19-163">ТSV-файлы</span><span class="sxs-lookup"><span data-stu-id="84c19-163">.tsv files</span></span>
- <span data-ttu-id="84c19-164">TXT-файлы</span><span class="sxs-lookup"><span data-stu-id="84c19-164">.txt files</span></span>
- <span data-ttu-id="84c19-165">RTF-файлы</span><span class="sxs-lookup"><span data-stu-id="84c19-165">.rtf files</span></span>
- <span data-ttu-id="84c19-166">С-файлы</span><span class="sxs-lookup"><span data-stu-id="84c19-166">.c files</span></span>
- <span data-ttu-id="84c19-167">CLASS-файлы</span><span class="sxs-lookup"><span data-stu-id="84c19-167">.class files</span></span>
- <span data-ttu-id="84c19-168">CPP-файлы</span><span class="sxs-lookup"><span data-stu-id="84c19-168">.cpp files</span></span>
- <span data-ttu-id="84c19-169">CS-файлы</span><span class="sxs-lookup"><span data-stu-id="84c19-169">.cs files</span></span>
- <span data-ttu-id="84c19-170">H-файлы</span><span class="sxs-lookup"><span data-stu-id="84c19-170">.h files</span></span>
- <span data-ttu-id="84c19-171">JAVA-файлы</span><span class="sxs-lookup"><span data-stu-id="84c19-171">.java files</span></span>

> [!NOTE]
> <span data-ttu-id="84c19-172">Защита от потери данных в конечной точке оценивает файлы всех указанных выше типов на соответствие политике защиты от потери данных и применяет соответствующие защитные действия.</span><span class="sxs-lookup"><span data-stu-id="84c19-172">Endpoint DLP evaluates files of all the above types against the DLP policy and applies protection actions accordingly.</span></span> <span data-ttu-id="84c19-173">Все файлы, соответствующие политике защиты от потери данных, подвергаются аудиту для всех поддерживаемых действий, даже если они не заблокированы.</span><span class="sxs-lookup"><span data-stu-id="84c19-173">All files that match a DLP policy are audited for all supported actions, even if they aren't blocked.</span></span> <span data-ttu-id="84c19-174">Кроме того, по умолчанию аудит выполняется для всех файлов Word, PowerPoint, Excel, PDF и CSV, независимо от наличия политики защиты от потери данных или ее соответствия этим файлам.</span><span class="sxs-lookup"><span data-stu-id="84c19-174">In addition, file activity performed on any Word, PowerPoint, Excel, PDF, and .csv file is audited by default, independent of whether a DLP policy exists or matches these files.</span></span>

<span data-ttu-id="84c19-175">Вы можете просмотреть оповещения, связанные с политиками защиты от потери данных, примененными на устройствах конечных точек, перейдя на [панель мониторинга для управления оповещениями защиты от потери данных](dlp-configure-view-alerts-policies.md).</span><span class="sxs-lookup"><span data-stu-id="84c19-175">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

![Сведения оповещения](../media/Alert-info-1.png)

<span data-ttu-id="84c19-177">Вы также можете просматривать сведения о связанном событии с расширенными метаданными на той же панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="84c19-177">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

![сведения о событии](../media/Event-info-1.png)

<span data-ttu-id="84c19-179">После подключения устройства сведения о действиях, прошедших аудит, передаются в обозреватель действий даже до настройки и развертывания любой политики защиты от потери данных с устройствами в качестве расположения.</span><span class="sxs-lookup"><span data-stu-id="84c19-179">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="84c19-180">![события защиты от потери данных в конечной точке в обозревателе действий](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="84c19-180">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="84c19-181">Защита от потери данных в конечной точке собирает подробную информацию о действиях, прошедших аудит.</span><span class="sxs-lookup"><span data-stu-id="84c19-181">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="84c19-182">Например, если файл копируется на съемный USB-носитель, то в подробных сведениях о действиях будут отображаться указанные ниже атрибуты:</span><span class="sxs-lookup"><span data-stu-id="84c19-182">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="84c19-183">тип действия</span><span class="sxs-lookup"><span data-stu-id="84c19-183">activity type</span></span>
- <span data-ttu-id="84c19-184">IP-адрес клиента</span><span class="sxs-lookup"><span data-stu-id="84c19-184">client IP</span></span>
- <span data-ttu-id="84c19-185">путь к целевому файлу</span><span class="sxs-lookup"><span data-stu-id="84c19-185">target file path</span></span>
- <span data-ttu-id="84c19-186">временная метка события</span><span class="sxs-lookup"><span data-stu-id="84c19-186">happened timestamp</span></span>
- <span data-ttu-id="84c19-187">имя файла</span><span class="sxs-lookup"><span data-stu-id="84c19-187">file name</span></span>
- <span data-ttu-id="84c19-188">пользователь</span><span class="sxs-lookup"><span data-stu-id="84c19-188">user</span></span>
- <span data-ttu-id="84c19-189">расширение файла</span><span class="sxs-lookup"><span data-stu-id="84c19-189">file extension</span></span>
- <span data-ttu-id="84c19-190">размер файла</span><span class="sxs-lookup"><span data-stu-id="84c19-190">file size</span></span>
- <span data-ttu-id="84c19-191">типы конфиденциальной информации (если применимо)</span><span class="sxs-lookup"><span data-stu-id="84c19-191">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="84c19-192">значение SHA1</span><span class="sxs-lookup"><span data-stu-id="84c19-192">sha1 value</span></span>
- <span data-ttu-id="84c19-193">значение SHA256</span><span class="sxs-lookup"><span data-stu-id="84c19-193">sha256 value</span></span>
- <span data-ttu-id="84c19-194">предыдущее имя файла</span><span class="sxs-lookup"><span data-stu-id="84c19-194">previous file name</span></span>
- <span data-ttu-id="84c19-195">расположение</span><span class="sxs-lookup"><span data-stu-id="84c19-195">location</span></span>
- <span data-ttu-id="84c19-196">родитель</span><span class="sxs-lookup"><span data-stu-id="84c19-196">parent</span></span>
- <span data-ttu-id="84c19-197">путь к файлу</span><span class="sxs-lookup"><span data-stu-id="84c19-197">filepath</span></span>
- <span data-ttu-id="84c19-198">тип исходного расположения</span><span class="sxs-lookup"><span data-stu-id="84c19-198">source location type</span></span>
- <span data-ttu-id="84c19-199">платформа</span><span class="sxs-lookup"><span data-stu-id="84c19-199">platform</span></span>
- <span data-ttu-id="84c19-200">имя устройства</span><span class="sxs-lookup"><span data-stu-id="84c19-200">device name</span></span>
- <span data-ttu-id="84c19-201">тип конечного расположения</span><span class="sxs-lookup"><span data-stu-id="84c19-201">destination location type</span></span>
- <span data-ttu-id="84c19-202">приложение, которое выполнило копирование</span><span class="sxs-lookup"><span data-stu-id="84c19-202">application that performed the copy</span></span>
- <span data-ttu-id="84c19-203">ИД устройства Microsoft Defender для конечной точки (если применимо)</span><span class="sxs-lookup"><span data-stu-id="84c19-203">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="84c19-204">производитель съемного носителя</span><span class="sxs-lookup"><span data-stu-id="84c19-204">removable media device manufacturer</span></span>
- <span data-ttu-id="84c19-205">модель съемного носителя</span><span class="sxs-lookup"><span data-stu-id="84c19-205">removable media device model</span></span>
- <span data-ttu-id="84c19-206">серийный номер съемного носителя</span><span class="sxs-lookup"><span data-stu-id="84c19-206">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="84c19-207">![атрибуты действий копирования на USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="84c19-207">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="84c19-208">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="84c19-208">Next steps</span></span>

<span data-ttu-id="84c19-209">Теперь, когда вы узнали о защите от потери данных в конечной точке, ознакомьтесь со следующим:</span><span class="sxs-lookup"><span data-stu-id="84c19-209">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="84c19-210">Начало работы с защитой от потери данных в конечной точке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="84c19-210">Getting started with Microsoft Endpoint data loss prevention </span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="84c19-211">Использование защиты от потери данных в конечной точке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="84c19-211">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="84c19-212">См. также</span><span class="sxs-lookup"><span data-stu-id="84c19-212">See also</span></span>

- [<span data-ttu-id="84c19-213">Начало работы с защитой от потери данных в конечной точке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="84c19-213">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="84c19-214">Использование защиты от потери данных в конечной точке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="84c19-214">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="84c19-215">Общие сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="84c19-215">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="84c19-216">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="84c19-216">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="84c19-217">Начало работы с обозревателем действий</span><span class="sxs-lookup"><span data-stu-id="84c19-217">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="84c19-218">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="84c19-218">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="84c19-219">Управление рисками в рамках программы предварительной оценки</span><span class="sxs-lookup"><span data-stu-id="84c19-219">Insider Risk management</span></span>](insider-risk-management.md)
