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
ms.openlocfilehash: 457701a514159e54e932db3e4ad04a7428165fdc
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604319"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="a9f2a-104">Сведения о защите от потери данных в конечной точке Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a9f2a-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="a9f2a-105">Защиту от потери данных (DLP) в Microsoft 365 можно использовать для отслеживания действий, принятых в отношении элементов, которые были определены как конфиденциальные, и для защиты от непреднамеренного обмена этими элементами.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="a9f2a-106">Подробная информация приведена в статье [Обзор защиты от потери данных](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a9f2a-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="a9f2a-107">**Защита от потери данных в конечной точке (DLP в конечной точке)** расширяет возможности отслеживания действий и защиты от потери данных для конфиденциальных элементов на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="a9f2a-108">После того как устройства будут подключены к решениям по обеспечению соответствия требованиям Microsoft 365, сведения о действиях пользователей с конфиденциальными элементами становятся видимыми в [обозревателе действий](data-classification-activity-explorer.md) и вы можете принудительно применять защитные действия к ним с помощью [политик защиты от потери данных](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="a9f2a-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="a9f2a-109">Действия в конечных точках, которые вы можете отслеживать и реагировать на них</span><span class="sxs-lookup"><span data-stu-id="a9f2a-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="a9f2a-110">Защита от потери данных в конечной точке от Майкрософт позволяет проверять и управлять следующими типами действий, выполняемыми пользователями в отношении конфиденциальных элементов на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> <span data-ttu-id="a9f2a-111">К ним относятся:</span><span class="sxs-lookup"><span data-stu-id="a9f2a-111">This includes:</span></span>


|<span data-ttu-id="a9f2a-112">действие с элементом</span><span class="sxs-lookup"><span data-stu-id="a9f2a-112">activity on item</span></span> |<span data-ttu-id="a9f2a-113">проверяемое/ограниченное</span><span class="sxs-lookup"><span data-stu-id="a9f2a-113">auditable/restrictable</span></span>  |
|---------|---------|
|<span data-ttu-id="a9f2a-114">создано</span><span class="sxs-lookup"><span data-stu-id="a9f2a-114">created</span></span>    | <span data-ttu-id="a9f2a-115">проверяемое</span><span class="sxs-lookup"><span data-stu-id="a9f2a-115">auditable</span></span>      |
|<span data-ttu-id="a9f2a-116">переименовано</span><span class="sxs-lookup"><span data-stu-id="a9f2a-116">renamed</span></span>    |  <span data-ttu-id="a9f2a-117">проверяемое</span><span class="sxs-lookup"><span data-stu-id="a9f2a-117">auditable</span></span>       |
|<span data-ttu-id="a9f2a-118">скопировано на съемные носители или созданное на них</span><span class="sxs-lookup"><span data-stu-id="a9f2a-118">copied to or created on removable media</span></span>     |     <span data-ttu-id="a9f2a-119">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="a9f2a-119">auditable and restrictable</span></span>|
|<span data-ttu-id="a9f2a-120">скопировано в общую сетевую папку, например \\my-server\fileshare</span><span class="sxs-lookup"><span data-stu-id="a9f2a-120">copied to network share, e.g. \\my-server\fileshare</span></span>   |     <span data-ttu-id="a9f2a-121">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="a9f2a-121">auditable and restrictable</span></span>    |
|<span data-ttu-id="a9f2a-122">напечатано</span><span class="sxs-lookup"><span data-stu-id="a9f2a-122">printed</span></span> |    <span data-ttu-id="a9f2a-123">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="a9f2a-123">auditable and restrictable</span></span>       |
|<span data-ttu-id="a9f2a-124">скопировано в облако с помощью Chromium Edge</span><span class="sxs-lookup"><span data-stu-id="a9f2a-124">copied to cloud via Chromium Edge</span></span>    |   <span data-ttu-id="a9f2a-125">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="a9f2a-125">auditable and restrictable</span></span>        |
|<span data-ttu-id="a9f2a-126">получен доступ посредством неразрешенных приложений и браузеров</span><span class="sxs-lookup"><span data-stu-id="a9f2a-126">accessed by unallowed apps and browsers</span></span>    |  <span data-ttu-id="a9f2a-127">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="a9f2a-127">auditable and restrictable</span></span>       |

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="a9f2a-128">Чем отличается защита от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="a9f2a-128">What's different in Endpoint DLP</span></span>

<span data-ttu-id="a9f2a-129">Перед началом глубокой работы с защитой от потери данных в конечной точке необходимо учитывать ряд дополнительных понятий.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-129">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="a9f2a-130">Включение управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="a9f2a-130">Enabling Device management</span></span>

<span data-ttu-id="a9f2a-131">Управление устройствами — это функция, позволяющая осуществлять сбор данных телеметрии с устройств и преобразование их в решения для обеспечения соответствия требованиям Microsoft 365, такие как Защита от потери данных в конечной точке и [Управление рисками в рамках программы предварительной оценки](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="a9f2a-131">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="a9f2a-132">Вам потребуется подключить все устройства, которые вы хотите использовать в качестве расположений в политиках защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-132">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a9f2a-133">![включение управления устройствами](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="a9f2a-133">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="a9f2a-134">Подключение и отключение выполняется с помощью сценариев, скачанных из Центра управления устройствами.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-134">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="a9f2a-135">В центре есть настраиваемые сценарии для каждого из этих методов развертывания:</span><span class="sxs-lookup"><span data-stu-id="a9f2a-135">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="a9f2a-136">локальный сценарий (до 10 компьютеров)</span><span class="sxs-lookup"><span data-stu-id="a9f2a-136">local script (up to 10 machines)</span></span>
- <span data-ttu-id="a9f2a-137">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="a9f2a-137">Group policy</span></span>
- <span data-ttu-id="a9f2a-138">System Center Configuration Manager (версия 1610 или более поздняя)</span><span class="sxs-lookup"><span data-stu-id="a9f2a-138">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="a9f2a-139">Управление мобильными устройствами/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a9f2a-139">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="a9f2a-140">Сценарии подключения в инфраструктуре виртуальных рабочих столов (VDI) для временных компьютеров</span><span class="sxs-lookup"><span data-stu-id="a9f2a-140">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a9f2a-141">![страница подключения устройств](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="a9f2a-141">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="a9f2a-142">Для подключения устройств используйте процедуры, описанные в статье [Начало работы с Защитой от потери данных в конечной точке в Microsoft 365](endpoint-dlp-getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="a9f2a-142">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="a9f2a-143">Если вы подключили устройства с помощью [Microsoft Defender для конечной точки](https://docs.microsoft.com/windows/security/threat-protection/), эти устройства будут автоматически отображаться в списке устройств.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-143">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a9f2a-144">![список управляемых устройств](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="a9f2a-144">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="a9f2a-145">Просмотр данных защиты от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="a9f2a-145">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="a9f2a-146">Защита от потери данных в конечной точке зависит от типа MIME, поэтому действия будут записываться даже при изменении расширения файла.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-146">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span> <span data-ttu-id="a9f2a-147">В настоящее время поддерживаются следующие типы файлов:</span><span class="sxs-lookup"><span data-stu-id="a9f2a-147">At this time the following file types are supported:</span></span>

- <span data-ttu-id="a9f2a-148">Файлы Word</span><span class="sxs-lookup"><span data-stu-id="a9f2a-148">Word files</span></span>
- <span data-ttu-id="a9f2a-149">Файлы PowerPoint</span><span class="sxs-lookup"><span data-stu-id="a9f2a-149">PowerPoint files</span></span>
- <span data-ttu-id="a9f2a-150">Файлы Excel</span><span class="sxs-lookup"><span data-stu-id="a9f2a-150">Excel files</span></span>
- <span data-ttu-id="a9f2a-151">PDF-файлы</span><span class="sxs-lookup"><span data-stu-id="a9f2a-151">PDF files</span></span>
- <span data-ttu-id="a9f2a-152">CSV-файлы</span><span class="sxs-lookup"><span data-stu-id="a9f2a-152">.csv files</span></span>
- <span data-ttu-id="a9f2a-153">ТSV-файлы</span><span class="sxs-lookup"><span data-stu-id="a9f2a-153">.tsv files</span></span>
- <span data-ttu-id="a9f2a-154">TXT-файлы</span><span class="sxs-lookup"><span data-stu-id="a9f2a-154">.txt files</span></span>
- <span data-ttu-id="a9f2a-155">RTF-файлы</span><span class="sxs-lookup"><span data-stu-id="a9f2a-155">.rtf files</span></span>
- <span data-ttu-id="a9f2a-156">С-файлы</span><span class="sxs-lookup"><span data-stu-id="a9f2a-156">.c files</span></span>
- <span data-ttu-id="a9f2a-157">CLASS-файлы</span><span class="sxs-lookup"><span data-stu-id="a9f2a-157">.class files</span></span>
- <span data-ttu-id="a9f2a-158">CPP-файлы</span><span class="sxs-lookup"><span data-stu-id="a9f2a-158">.cpp files</span></span>
- <span data-ttu-id="a9f2a-159">CS-файлы</span><span class="sxs-lookup"><span data-stu-id="a9f2a-159">.cs files</span></span>
- <span data-ttu-id="a9f2a-160">H-файлы</span><span class="sxs-lookup"><span data-stu-id="a9f2a-160">.h files</span></span>
- <span data-ttu-id="a9f2a-161">JAVA-файлы</span><span class="sxs-lookup"><span data-stu-id="a9f2a-161">.java files</span></span>

> [!NOTE]
> <span data-ttu-id="a9f2a-162">Защита от потери данных в конечной точке оценивает файлы всех указанных выше типов на соответствие политике защиты от потери данных и применяет соответствующие защитные действия.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-162">Endpoint DLP evaluates files of all the above types against the DLP policy and applies protection actions accordingly.</span></span> <span data-ttu-id="a9f2a-163">Все файлы, соответствующие политике защиты от потери данных, подвергаются аудиту для всех поддерживаемых действий, даже если они не заблокированы.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-163">All files that match a DLP policy are audited for all supported actions, even if they aren't blocked.</span></span> <span data-ttu-id="a9f2a-164">Кроме того, по умолчанию аудит выполняется для всех файлов Word, PowerPoint, Excel, PDF и CSV, независимо от наличия политики защиты от потери данных или ее соответствия этим файлам.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-164">In addition, file activity performed on any Word, PowerPoint, Excel, PDF, and .csv file is audited by default, independent of whether a DLP policy exists or matches these files.</span></span>

<span data-ttu-id="a9f2a-165">Вы можете просмотреть оповещения, связанные с политиками защиты от потери данных, примененными на устройствах конечных точек, перейдя на [панель мониторинга для управления оповещениями защиты от потери данных](dlp-configure-view-alerts-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a9f2a-165">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

![Сведения оповещения](../media/Alert-info-1.png)

<span data-ttu-id="a9f2a-167">Вы также можете просматривать сведения о связанном событии с расширенными метаданными на той же панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-167">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

![сведения о событии](../media/Event-info-1.png)

<span data-ttu-id="a9f2a-169">После подключения устройства сведения о действиях, прошедших аудит, передаются в обозреватель действий даже до настройки и развертывания любой политики защиты от потери данных с устройствами в качестве расположения.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-169">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a9f2a-170">![события защиты от потери данных в конечной точке в обозревателе действий](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="a9f2a-170">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="a9f2a-171">Защита от потери данных в конечной точке собирает подробную информацию о действиях, прошедших аудит.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-171">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="a9f2a-172">Например, если файл копируется на съемный USB-носитель, то в подробных сведениях о действиях будут отображаться указанные ниже атрибуты:</span><span class="sxs-lookup"><span data-stu-id="a9f2a-172">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="a9f2a-173">тип действия</span><span class="sxs-lookup"><span data-stu-id="a9f2a-173">activity type</span></span>
- <span data-ttu-id="a9f2a-174">IP-адрес клиента</span><span class="sxs-lookup"><span data-stu-id="a9f2a-174">client IP</span></span>
- <span data-ttu-id="a9f2a-175">путь к целевому файлу</span><span class="sxs-lookup"><span data-stu-id="a9f2a-175">target file path</span></span>
- <span data-ttu-id="a9f2a-176">временная метка события</span><span class="sxs-lookup"><span data-stu-id="a9f2a-176">happened timestamp</span></span>
- <span data-ttu-id="a9f2a-177">имя файла</span><span class="sxs-lookup"><span data-stu-id="a9f2a-177">file name</span></span>
- <span data-ttu-id="a9f2a-178">пользователь</span><span class="sxs-lookup"><span data-stu-id="a9f2a-178">user</span></span>
- <span data-ttu-id="a9f2a-179">расширение файла</span><span class="sxs-lookup"><span data-stu-id="a9f2a-179">file extension</span></span>
- <span data-ttu-id="a9f2a-180">размер файла</span><span class="sxs-lookup"><span data-stu-id="a9f2a-180">file size</span></span>
- <span data-ttu-id="a9f2a-181">типы конфиденциальной информации (если применимо)</span><span class="sxs-lookup"><span data-stu-id="a9f2a-181">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="a9f2a-182">значение SHA1</span><span class="sxs-lookup"><span data-stu-id="a9f2a-182">sha1 value</span></span>
- <span data-ttu-id="a9f2a-183">значение SHA256</span><span class="sxs-lookup"><span data-stu-id="a9f2a-183">sha256 value</span></span>
- <span data-ttu-id="a9f2a-184">предыдущее имя файла</span><span class="sxs-lookup"><span data-stu-id="a9f2a-184">previous file name</span></span>
- <span data-ttu-id="a9f2a-185">расположение</span><span class="sxs-lookup"><span data-stu-id="a9f2a-185">location</span></span>
- <span data-ttu-id="a9f2a-186">родитель</span><span class="sxs-lookup"><span data-stu-id="a9f2a-186">parent</span></span>
- <span data-ttu-id="a9f2a-187">путь к файлу</span><span class="sxs-lookup"><span data-stu-id="a9f2a-187">filepath</span></span>
- <span data-ttu-id="a9f2a-188">тип исходного расположения</span><span class="sxs-lookup"><span data-stu-id="a9f2a-188">source location type</span></span>
- <span data-ttu-id="a9f2a-189">платформа</span><span class="sxs-lookup"><span data-stu-id="a9f2a-189">platform</span></span>
- <span data-ttu-id="a9f2a-190">имя устройства</span><span class="sxs-lookup"><span data-stu-id="a9f2a-190">device name</span></span>
- <span data-ttu-id="a9f2a-191">тип конечного расположения</span><span class="sxs-lookup"><span data-stu-id="a9f2a-191">destination location type</span></span>
- <span data-ttu-id="a9f2a-192">приложение, которое выполнило копирование</span><span class="sxs-lookup"><span data-stu-id="a9f2a-192">application that performed the copy</span></span>
- <span data-ttu-id="a9f2a-193">ИД устройства Microsoft Defender для конечной точки (если применимо)</span><span class="sxs-lookup"><span data-stu-id="a9f2a-193">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="a9f2a-194">производитель съемного носителя</span><span class="sxs-lookup"><span data-stu-id="a9f2a-194">removable media device manufacturer</span></span>
- <span data-ttu-id="a9f2a-195">модель съемного носителя</span><span class="sxs-lookup"><span data-stu-id="a9f2a-195">removable media device model</span></span>
- <span data-ttu-id="a9f2a-196">серийный номер съемного носителя</span><span class="sxs-lookup"><span data-stu-id="a9f2a-196">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a9f2a-197">![атрибуты действий копирования на USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="a9f2a-197">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="a9f2a-198">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="a9f2a-198">Next steps</span></span>

<span data-ttu-id="a9f2a-199">Теперь, когда вы узнали о защите от потери данных в конечной точке, ознакомьтесь со следующим:</span><span class="sxs-lookup"><span data-stu-id="a9f2a-199">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="a9f2a-200">Начало работы с защитой от потери данных в конечной точке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a9f2a-200">Getting started with Microsoft Endpoint data loss prevention </span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="a9f2a-201">Использование защиты от потери данных в конечной точке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a9f2a-201">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="a9f2a-202">См. также</span><span class="sxs-lookup"><span data-stu-id="a9f2a-202">See also</span></span>

- [<span data-ttu-id="a9f2a-203">Начало работы с защитой от потери данных в конечной точке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a9f2a-203">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="a9f2a-204">Использование защиты от потери данных в конечной точке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a9f2a-204">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="a9f2a-205">Общие сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="a9f2a-205">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="a9f2a-206">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="a9f2a-206">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="a9f2a-207">Начало работы с обозревателем действий</span><span class="sxs-lookup"><span data-stu-id="a9f2a-207">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="a9f2a-208">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a9f2a-208">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="a9f2a-209">Управление рисками в рамках программы предварительной оценки</span><span class="sxs-lookup"><span data-stu-id="a9f2a-209">Insider Risk management</span></span>](insider-risk-management.md)
