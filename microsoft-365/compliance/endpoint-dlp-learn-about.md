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
description: 'Защита от потери данных в конечных точках Microsoft 365 расширяет возможности мониторинга действий с файлами и защитных действий с этими файлами до уровня конечных точек. Файлы отображаются в решениях Центра соответствия требованиям Microsoft 365. '
ms.openlocfilehash: e469872dac19db08f7b525c8a5ada725c75bfa10
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2020
ms.locfileid: "49072978"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="443b0-104">Сведения о защите от потери данных в конечных точках Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="443b0-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="443b0-p102">Можно использовать защиту от потери данных (DLP) в Microsoft 365 для мониторинга действий, выполняемых с элементами, определенными в качестве конфиденциальных, а также для предотвращения непреднамеренного предоставления общего доступа к таким элементам. Дополнительные сведения о DLP см. в статье [Обзор защиты от потери данных](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="443b0-p102">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items. For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="443b0-p103">**Решение для защиты от потери данных в конечных точках** (Endpoint DLP) расширяет охват мониторинга и защитных функций DLP на конфиденциальные элементы на устройствах с Windows 10. После подключения устройств к решениям Центра соответствия требованиям Microsoft 365 информация о действиях пользователей с конфиденциальными элементами отображается в [обозревателе действий](data-classification-activity-explorer.md). Можно применять защитные действия к таким элементам с помощью [политик DLP](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="443b0-p103">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices. Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="443b0-109">Действия в конечных точках, доступные для отслеживания и реагирования</span><span class="sxs-lookup"><span data-stu-id="443b0-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="443b0-p104">Решение Майкрософт для защиты от потери данных в конечных точках дает возможность проводить аудит для следующих действий, выполняемых пользователями в отношении конфиденциальных элементов на устройствах с Windows 10, и управлять этими действиями:</span><span class="sxs-lookup"><span data-stu-id="443b0-p104">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10. This includes:</span></span>


|<span data-ttu-id="443b0-112">действие с элементом</span><span class="sxs-lookup"><span data-stu-id="443b0-112">activity on item</span></span> |<span data-ttu-id="443b0-113">проверяемое/ограниченное</span><span class="sxs-lookup"><span data-stu-id="443b0-113">auditable/restrictable</span></span>  |
|---------|---------|
|<span data-ttu-id="443b0-114">создано</span><span class="sxs-lookup"><span data-stu-id="443b0-114">created</span></span>    | <span data-ttu-id="443b0-115">проверяемое</span><span class="sxs-lookup"><span data-stu-id="443b0-115">auditable</span></span>      |
|<span data-ttu-id="443b0-116">переименовано</span><span class="sxs-lookup"><span data-stu-id="443b0-116">renamed</span></span>    |  <span data-ttu-id="443b0-117">проверяемое</span><span class="sxs-lookup"><span data-stu-id="443b0-117">auditable</span></span>       |
|<span data-ttu-id="443b0-118">скопировано на съемные носители или созданное на них</span><span class="sxs-lookup"><span data-stu-id="443b0-118">copied to or created on removable media</span></span>     |     <span data-ttu-id="443b0-119">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="443b0-119">auditable and restrictable</span></span>|
|<span data-ttu-id="443b0-120">скопировано в общую сетевую папку, например \\my-server\fileshare</span><span class="sxs-lookup"><span data-stu-id="443b0-120">copied to network share, e.g. \\my-server\fileshare</span></span>   |     <span data-ttu-id="443b0-121">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="443b0-121">auditable and restrictable</span></span>    |
|<span data-ttu-id="443b0-122">напечатано</span><span class="sxs-lookup"><span data-stu-id="443b0-122">printed</span></span> |    <span data-ttu-id="443b0-123">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="443b0-123">auditable and restrictable</span></span>       |
|<span data-ttu-id="443b0-124">скопировано в облако с помощью Chromium Edge</span><span class="sxs-lookup"><span data-stu-id="443b0-124">copied to cloud via Chromium Edge</span></span>    |   <span data-ttu-id="443b0-125">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="443b0-125">auditable and restrictable</span></span>        |
|<span data-ttu-id="443b0-126">получен доступ посредством неразрешенных приложений и браузеров</span><span class="sxs-lookup"><span data-stu-id="443b0-126">accessed by unallowed apps and browsers</span></span>    |  <span data-ttu-id="443b0-127">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="443b0-127">auditable and restrictable</span></span>       |

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="443b0-128">Чем отличается защита от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="443b0-128">What's different in Endpoint DLP</span></span>

<span data-ttu-id="443b0-129">Перед началом глубокой работы с защитой от потери данных в конечной точке необходимо учитывать ряд дополнительных понятий.</span><span class="sxs-lookup"><span data-stu-id="443b0-129">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="443b0-130">Включение управления устройствами</span><span class="sxs-lookup"><span data-stu-id="443b0-130">Enabling Device management</span></span>

<span data-ttu-id="443b0-p105">Функциональность управления устройствами дает возможность собирать телеметрию на устройствах и реализовать эту возможность в решениях Центра соответствия требованиям Microsoft 365, таких как Endpoint DLP и [управление внутренними рисками](insider-risk-management.md). Потребуется подключить все устройства, которые вы собираетесь использовать в качестве расположений в политиках DLP.</span><span class="sxs-lookup"><span data-stu-id="443b0-p105">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md). You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="443b0-133">![включение управления устройствами](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="443b0-133">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="443b0-p106">Подключение и отключение устройств осуществляется с помощью сценариев, которые можно загрузить в Центре управления устройствами. Доступны настраиваемые сценарии для следующих методов развертывания:</span><span class="sxs-lookup"><span data-stu-id="443b0-p106">Onboarding and offboarding are handled via scripts you download from the Device management center. The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="443b0-136">локальный сценарий (до 10 компьютеров)</span><span class="sxs-lookup"><span data-stu-id="443b0-136">local script (up to 10 machines)</span></span>
- <span data-ttu-id="443b0-137">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="443b0-137">Group policy</span></span>
- <span data-ttu-id="443b0-138">System Center Configuration Manager (версия 1610 или более поздняя)</span><span class="sxs-lookup"><span data-stu-id="443b0-138">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="443b0-139">Управление мобильными устройствами/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="443b0-139">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="443b0-140">Сценарии подключения в инфраструктуре виртуальных рабочих столов (VDI) для временных компьютеров</span><span class="sxs-lookup"><span data-stu-id="443b0-140">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="443b0-141">![страница подключения устройств](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="443b0-141">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="443b0-142">Для подключения устройств используйте процедуры, описанные в статье [Начало работы с функцией защиты от потери данных в конечной точке Microsoft 365](endpoint-dlp-getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="443b0-142">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="443b0-143">Если вы подключили устройства с помощью [Microsoft Defender для конечной точки](https://docs.microsoft.com/windows/security/threat-protection/), эти устройства будут автоматически отображаться в списке устройств.</span><span class="sxs-lookup"><span data-stu-id="443b0-143">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="443b0-144">![список управляемых устройств](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="443b0-144">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="443b0-145">Просмотр данных Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="443b0-145">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="443b0-p107">Endpoint DLP отслеживает действия на основе типа MIME, поэтому действия будут записаны даже при изменении расширения файлов. В общедоступной предварительной версии отслеживаются действия со всеми следующими типами файлов:</span><span class="sxs-lookup"><span data-stu-id="443b0-p107">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed. At public preview it watches all:</span></span>

- <span data-ttu-id="443b0-148">Файлы Word</span><span class="sxs-lookup"><span data-stu-id="443b0-148">Word files</span></span>
- <span data-ttu-id="443b0-149">Файлы PowerPoint</span><span class="sxs-lookup"><span data-stu-id="443b0-149">PowerPoint files</span></span>
- <span data-ttu-id="443b0-150">Файлы Excel</span><span class="sxs-lookup"><span data-stu-id="443b0-150">Excel files</span></span>
- <span data-ttu-id="443b0-151">PDF-файлы</span><span class="sxs-lookup"><span data-stu-id="443b0-151">PDF files</span></span>
- <span data-ttu-id="443b0-152">CSV-файлы</span><span class="sxs-lookup"><span data-stu-id="443b0-152">.csv files</span></span>
- <span data-ttu-id="443b0-153">ТSV-файлы</span><span class="sxs-lookup"><span data-stu-id="443b0-153">.tsv files</span></span>
- <span data-ttu-id="443b0-154">TXT-файлы</span><span class="sxs-lookup"><span data-stu-id="443b0-154">.txt files</span></span>
- <span data-ttu-id="443b0-155">RTF-файлы</span><span class="sxs-lookup"><span data-stu-id="443b0-155">.rtf files</span></span>
- <span data-ttu-id="443b0-156">С-файлы</span><span class="sxs-lookup"><span data-stu-id="443b0-156">.c files</span></span>
- <span data-ttu-id="443b0-157">CLASS-файлы</span><span class="sxs-lookup"><span data-stu-id="443b0-157">.class files</span></span>
- <span data-ttu-id="443b0-158">CPP-файлы</span><span class="sxs-lookup"><span data-stu-id="443b0-158">.cpp files</span></span>
- <span data-ttu-id="443b0-159">CS-файлы</span><span class="sxs-lookup"><span data-stu-id="443b0-159">.cs files</span></span>
- <span data-ttu-id="443b0-160">H-файлы</span><span class="sxs-lookup"><span data-stu-id="443b0-160">.h files</span></span>
- <span data-ttu-id="443b0-161">JAVA-файлы</span><span class="sxs-lookup"><span data-stu-id="443b0-161">.java files</span></span>

> [!NOTE]
> <span data-ttu-id="443b0-p108">Защита от потери данных в конечной точке оценивает файлы всех указанных выше типов на соответствие политике защиты от потери данных и применяет соответствующие защитные действия. Все файлы, соответствующие политике защиты от потери данных, подвергаются аудиту для всех поддерживаемых действий, даже если они не заблокированы. Кроме того, по умолчанию аудит выполняется для всех файлов Word, PowerPoint, Excel, PDF и CSV, независимо от наличия политики защиты от потери данных или ее соответствия этим файлам.</span><span class="sxs-lookup"><span data-stu-id="443b0-p108">Endpoint DLP evaluates files of all the above types against the DLP policy and applies protection actions accordingly. All files that match a DLP policy are audited for all supported actions, even if they aren't blocked. In addition, file activity performed on any Word, PowerPoint, Excel, PDF, and .csv file is audited by default, independent of whether a DLP policy exists or matches these files.</span></span>

<span data-ttu-id="443b0-165">Вы можете просмотреть оповещения, связанные с политиками защиты от потери данных, примененными на устройствах конечных точек, перейдя на [панель мониторинга для управления оповещениями защиты от потери данных](dlp-configure-view-alerts-policies.md).</span><span class="sxs-lookup"><span data-stu-id="443b0-165">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

![Сведения оповещения](../media/Alert-info-1.png)

<span data-ttu-id="443b0-167">Вы также можете просматривать сведения о связанном событии с расширенными метаданными на той же панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="443b0-167">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

![сведения о событии](../media/Event-info-1.png)

<span data-ttu-id="443b0-169">После подключения устройства сведения о действиях, прошедших аудит, передаются в обозреватель действий даже до настройки и развертывания любых политик защиты от потери данных, в качестве расположения в которых заданы устройства.</span><span class="sxs-lookup"><span data-stu-id="443b0-169">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="443b0-170">![события защиты от потери данных в конечной точке в обозревателе действий](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="443b0-170">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="443b0-171">Защита от потери данных в конечной точке собирает подробную информацию о действиях, прошедших аудит.</span><span class="sxs-lookup"><span data-stu-id="443b0-171">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="443b0-172">Например, если файл копируется на съемный USB-носитель, то в подробных сведениях о действиях будут отображаться указанные ниже атрибуты:</span><span class="sxs-lookup"><span data-stu-id="443b0-172">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="443b0-173">тип действия</span><span class="sxs-lookup"><span data-stu-id="443b0-173">activity type</span></span>
- <span data-ttu-id="443b0-174">IP-адрес клиента</span><span class="sxs-lookup"><span data-stu-id="443b0-174">client IP</span></span>
- <span data-ttu-id="443b0-175">путь к целевому файлу</span><span class="sxs-lookup"><span data-stu-id="443b0-175">target file path</span></span>
- <span data-ttu-id="443b0-176">временная метка события</span><span class="sxs-lookup"><span data-stu-id="443b0-176">happened timestamp</span></span>
- <span data-ttu-id="443b0-177">имя файла</span><span class="sxs-lookup"><span data-stu-id="443b0-177">file name</span></span>
- <span data-ttu-id="443b0-178">пользователь</span><span class="sxs-lookup"><span data-stu-id="443b0-178">user</span></span>
- <span data-ttu-id="443b0-179">расширение файла</span><span class="sxs-lookup"><span data-stu-id="443b0-179">file extension</span></span>
- <span data-ttu-id="443b0-180">размер файла</span><span class="sxs-lookup"><span data-stu-id="443b0-180">file size</span></span>
- <span data-ttu-id="443b0-181">типы конфиденциальной информации (если применимо)</span><span class="sxs-lookup"><span data-stu-id="443b0-181">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="443b0-182">значение SHA1</span><span class="sxs-lookup"><span data-stu-id="443b0-182">sha1 value</span></span>
- <span data-ttu-id="443b0-183">значение SHA256</span><span class="sxs-lookup"><span data-stu-id="443b0-183">sha256 value</span></span>
- <span data-ttu-id="443b0-184">предыдущее имя файла</span><span class="sxs-lookup"><span data-stu-id="443b0-184">previous file name</span></span>
- <span data-ttu-id="443b0-185">расположение</span><span class="sxs-lookup"><span data-stu-id="443b0-185">location</span></span>
- <span data-ttu-id="443b0-186">родитель</span><span class="sxs-lookup"><span data-stu-id="443b0-186">parent</span></span>
- <span data-ttu-id="443b0-187">путь к файлу</span><span class="sxs-lookup"><span data-stu-id="443b0-187">filepath</span></span>
- <span data-ttu-id="443b0-188">тип исходного расположения</span><span class="sxs-lookup"><span data-stu-id="443b0-188">source location type</span></span>
- <span data-ttu-id="443b0-189">платформа</span><span class="sxs-lookup"><span data-stu-id="443b0-189">platform</span></span>
- <span data-ttu-id="443b0-190">имя устройства</span><span class="sxs-lookup"><span data-stu-id="443b0-190">device name</span></span>
- <span data-ttu-id="443b0-191">тип конечного расположения</span><span class="sxs-lookup"><span data-stu-id="443b0-191">destination location type</span></span>
- <span data-ttu-id="443b0-192">приложение, которое выполнило копирование</span><span class="sxs-lookup"><span data-stu-id="443b0-192">application that performed the copy</span></span>
- <span data-ttu-id="443b0-193">ИД устройства Microsoft Defender для конечной точки (если применимо)</span><span class="sxs-lookup"><span data-stu-id="443b0-193">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="443b0-194">производитель съемного носителя</span><span class="sxs-lookup"><span data-stu-id="443b0-194">removable media device manufacturer</span></span>
- <span data-ttu-id="443b0-195">модель съемного носителя</span><span class="sxs-lookup"><span data-stu-id="443b0-195">removable media device model</span></span>
- <span data-ttu-id="443b0-196">серийный номер съемного носителя</span><span class="sxs-lookup"><span data-stu-id="443b0-196">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="443b0-197">![атрибуты действий копирования на USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="443b0-197">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="443b0-198">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="443b0-198">Next steps</span></span>

<span data-ttu-id="443b0-199">Теперь, когда вы узнали о защите от потери данных в конечной точке, ознакомьтесь со следующим:</span><span class="sxs-lookup"><span data-stu-id="443b0-199">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="443b0-200">Начало работы с защитой от потери данных в конечной точке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="443b0-200">Getting started with Microsoft Endpoint data loss prevention </span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="443b0-201">Использование защиты от потери данных в конечной точке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="443b0-201">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="443b0-202">См. также</span><span class="sxs-lookup"><span data-stu-id="443b0-202">See also</span></span>

- [<span data-ttu-id="443b0-203">Начало работы с защитой от потери данных в конечной точке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="443b0-203">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="443b0-204">Использование защиты от потери данных в конечной точке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="443b0-204">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="443b0-205">Общие сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="443b0-205">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="443b0-206">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="443b0-206">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="443b0-207">Начало работы с обозревателем действий</span><span class="sxs-lookup"><span data-stu-id="443b0-207">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="443b0-208">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="443b0-208">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="443b0-209">Управление рисками в рамках программы предварительной оценки</span><span class="sxs-lookup"><span data-stu-id="443b0-209">Insider Risk management</span></span>](insider-risk-management.md)
