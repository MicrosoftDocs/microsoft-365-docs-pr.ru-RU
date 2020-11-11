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
ms.openlocfilehash: 966e201acb8038d85f0d06c0800c9845fd79097e
ms.sourcegitcommit: 89f56c3e0b619a4700a75a21927d9ffc90658632
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "48984933"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="580d6-104">Сведения о защите от потери данных в конечных точках Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="580d6-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="580d6-p102">Можно использовать защиту от потери данных (DLP) в Microsoft 365 для мониторинга действий, выполняемых с элементами, определенными в качестве конфиденциальных, а также для предотвращения непреднамеренного предоставления общего доступа к таким элементам. Дополнительные сведения о DLP см. в статье [Обзор защиты от потери данных](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="580d6-p102">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items. For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="580d6-p103">**Решение для защиты от потери данных в конечных точках** (Endpoint DLP) расширяет охват мониторинга и защитных функций DLP на конфиденциальные элементы на устройствах с Windows 10. После подключения устройств к решениям Центра соответствия требованиям Microsoft 365 информация о действиях пользователей с конфиденциальными элементами отображается в [обозревателе действий](data-classification-activity-explorer.md). Можно применять защитные действия к таким элементам с помощью [политик DLP](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="580d6-p103">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices. Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="580d6-109">Действия в конечных точках, доступные для отслеживания и реагирования</span><span class="sxs-lookup"><span data-stu-id="580d6-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="580d6-p104">Решение Майкрософт для защиты от потери данных в конечных точках дает возможность проводить аудит для следующих действий, выполняемых пользователями в отношении конфиденциальных элементов на устройствах с Windows 10, и управлять этими действиями:</span><span class="sxs-lookup"><span data-stu-id="580d6-p104">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10. This includes:</span></span>


|<span data-ttu-id="580d6-112">действие с элементом</span><span class="sxs-lookup"><span data-stu-id="580d6-112">activity on item</span></span> |<span data-ttu-id="580d6-113">проверяемое/ограниченное</span><span class="sxs-lookup"><span data-stu-id="580d6-113">auditable/restrictable</span></span>  |
|---------|---------|
|<span data-ttu-id="580d6-114">создано</span><span class="sxs-lookup"><span data-stu-id="580d6-114">created</span></span>    | <span data-ttu-id="580d6-115">проверяемое</span><span class="sxs-lookup"><span data-stu-id="580d6-115">auditable</span></span>      |
|<span data-ttu-id="580d6-116">переименовано</span><span class="sxs-lookup"><span data-stu-id="580d6-116">renamed</span></span>    |  <span data-ttu-id="580d6-117">проверяемое</span><span class="sxs-lookup"><span data-stu-id="580d6-117">auditable</span></span>       |
|<span data-ttu-id="580d6-118">скопировано на съемные носители или созданное на них</span><span class="sxs-lookup"><span data-stu-id="580d6-118">copied to or created on removable media</span></span>     |     <span data-ttu-id="580d6-119">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="580d6-119">auditable and restrictable</span></span>|
|<span data-ttu-id="580d6-120">скопировано в общую сетевую папку, например \\my-server\fileshare</span><span class="sxs-lookup"><span data-stu-id="580d6-120">copied to network share, e.g. \\my-server\fileshare</span></span>   |     <span data-ttu-id="580d6-121">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="580d6-121">auditable and restrictable</span></span>    |
|<span data-ttu-id="580d6-122">напечатано</span><span class="sxs-lookup"><span data-stu-id="580d6-122">printed</span></span> |    <span data-ttu-id="580d6-123">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="580d6-123">auditable and restrictable</span></span>       |
|<span data-ttu-id="580d6-124">скопировано в облако с помощью Chromium Edge</span><span class="sxs-lookup"><span data-stu-id="580d6-124">copied to cloud via Chromium Edge</span></span>    |   <span data-ttu-id="580d6-125">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="580d6-125">auditable and restrictable</span></span>        |
|<span data-ttu-id="580d6-126">получен доступ посредством неразрешенных приложений и браузеров</span><span class="sxs-lookup"><span data-stu-id="580d6-126">accessed by unallowed apps and browsers</span></span>    |  <span data-ttu-id="580d6-127">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="580d6-127">auditable and restrictable</span></span>       |

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="580d6-128">Чем отличается защита от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="580d6-128">What's different in Endpoint DLP</span></span>

<span data-ttu-id="580d6-129">Перед началом глубокой работы с защитой от потери данных в конечной точке необходимо учитывать ряд дополнительных понятий.</span><span class="sxs-lookup"><span data-stu-id="580d6-129">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="580d6-130">Включение управления устройствами</span><span class="sxs-lookup"><span data-stu-id="580d6-130">Enabling Device management</span></span>

<span data-ttu-id="580d6-p105">Функциональность управления устройствами дает возможность собирать телеметрию на устройствах и реализовать эту возможность в решениях Центра соответствия требованиям Microsoft 365, таких как Endpoint DLP и [управление внутренними рисками](insider-risk-management.md). Потребуется подключить все устройства, которые вы собираетесь использовать в качестве расположений в политиках DLP.</span><span class="sxs-lookup"><span data-stu-id="580d6-p105">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md). You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="580d6-133">![включение управления устройствами](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="580d6-133">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="580d6-p106">Подключение и отключение устройств осуществляется с помощью сценариев, которые можно загрузить в Центре управления устройствами. Доступны настраиваемые сценарии для следующих методов развертывания:</span><span class="sxs-lookup"><span data-stu-id="580d6-p106">Onboarding and offboarding are handled via scripts you download from the Device management center. The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="580d6-136">локальный сценарий (до 10 компьютеров)</span><span class="sxs-lookup"><span data-stu-id="580d6-136">local script (up to 10 machines)</span></span>
- <span data-ttu-id="580d6-137">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="580d6-137">Group policy</span></span>
- <span data-ttu-id="580d6-138">System Center Configuration Manager (версия 1610 или более поздняя)</span><span class="sxs-lookup"><span data-stu-id="580d6-138">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="580d6-139">Управление мобильными устройствами/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="580d6-139">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="580d6-140">Сценарии подключения в инфраструктуре виртуальных рабочих столов (VDI) для временных компьютеров</span><span class="sxs-lookup"><span data-stu-id="580d6-140">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="580d6-141">![страница подключения устройств](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="580d6-141">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="580d6-142">Для подключения устройств используйте процедуры, описанные в статье [Начало работы с функцией защиты от потери данных в конечной точке Microsoft 365](endpoint-dlp-getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="580d6-142">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="580d6-143">Если вы подключили устройства с помощью [Microsoft Defender для конечной точки](https://docs.microsoft.com/windows/security/threat-protection/), эти устройства будут автоматически отображаться в списке устройств.</span><span class="sxs-lookup"><span data-stu-id="580d6-143">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="580d6-144">![список управляемых устройств](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="580d6-144">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="580d6-145">Просмотр данных Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="580d6-145">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="580d6-p107">Endpoint DLP отслеживает действия на основе типа MIME, поэтому действия будут записаны даже при изменении расширения файлов. В общедоступной предварительной версии отслеживаются действия со всеми следующими типами файлов:</span><span class="sxs-lookup"><span data-stu-id="580d6-p107">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed. At public preview it watches all:</span></span>

- <span data-ttu-id="580d6-148">Файлы Word</span><span class="sxs-lookup"><span data-stu-id="580d6-148">Word files</span></span>
- <span data-ttu-id="580d6-149">Файлы PowerPoint</span><span class="sxs-lookup"><span data-stu-id="580d6-149">PowerPoint files</span></span>
- <span data-ttu-id="580d6-150">Файлы Excel</span><span class="sxs-lookup"><span data-stu-id="580d6-150">Excel files</span></span>
- <span data-ttu-id="580d6-151">PDF-файлы</span><span class="sxs-lookup"><span data-stu-id="580d6-151">PDF files</span></span>
- <span data-ttu-id="580d6-152">CSV-файлы</span><span class="sxs-lookup"><span data-stu-id="580d6-152">.csv files</span></span>
- <span data-ttu-id="580d6-153">ТSV-файлы</span><span class="sxs-lookup"><span data-stu-id="580d6-153">.tsv files</span></span>
- <span data-ttu-id="580d6-154">TXT-файлы</span><span class="sxs-lookup"><span data-stu-id="580d6-154">.txt files</span></span>
- <span data-ttu-id="580d6-155">RTF-файлы</span><span class="sxs-lookup"><span data-stu-id="580d6-155">.rtf files</span></span>
- <span data-ttu-id="580d6-156">С-файлы</span><span class="sxs-lookup"><span data-stu-id="580d6-156">.c files</span></span>
- <span data-ttu-id="580d6-157">CLASS-файлы</span><span class="sxs-lookup"><span data-stu-id="580d6-157">.class files</span></span>
- <span data-ttu-id="580d6-158">CPP-файлы</span><span class="sxs-lookup"><span data-stu-id="580d6-158">.cpp files</span></span>
- <span data-ttu-id="580d6-159">CS-файлы</span><span class="sxs-lookup"><span data-stu-id="580d6-159">.cs files</span></span>
- <span data-ttu-id="580d6-160">H-файлы</span><span class="sxs-lookup"><span data-stu-id="580d6-160">.h files</span></span>
- <span data-ttu-id="580d6-161">JAVA-файлы</span><span class="sxs-lookup"><span data-stu-id="580d6-161">.java files</span></span>

> [!NOTE]
> <span data-ttu-id="580d6-p108">Endpoint DLP проверяет файлы перечисленных выше типов на соответствие политике DLP и применяет соответствующие защитные действия. Для всех файлов, соответствующих политике DLP, проводится аудит для всех поддерживаемых действий, даже если они не заблокированы. Кроме того, по умолчанию проводится аудит действий с файлами Word, PowerPoint, Excel, PDF и CSV вне зависимости от наличия политики DLP для таких файлов и от соответствия файлов этой политике.</span><span class="sxs-lookup"><span data-stu-id="580d6-p108">Endpoint DLP evaluates files of all the above types against the DLP policy and applies protection actions accordingly. All files that match a DLP policy are audited for all supported actions, even if they aren't blocked. In addition, file activity performed on any Word, PowerPoint, Excel, PDF, and .csv file is audited by default, independent of whether a DLP policy exists or matches these files.</span></span>

<span data-ttu-id="580d6-165">После подключения устройства сведения о действиях, прошедших аудит, передаются в обозреватель действий даже до настройки и развертывания любых политик защиты от потери данных, в качестве расположения в которых заданы устройства.</span><span class="sxs-lookup"><span data-stu-id="580d6-165">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="580d6-166">![события защиты от потери данных в конечной точке в обозревателе действий](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="580d6-166">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="580d6-167">Защита от потери данных в конечной точке собирает подробную информацию о действиях, прошедших аудит.</span><span class="sxs-lookup"><span data-stu-id="580d6-167">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="580d6-168">Например, если файл копируется на съемный USB-носитель, то в подробных сведениях о действиях будут отображаться указанные ниже атрибуты:</span><span class="sxs-lookup"><span data-stu-id="580d6-168">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="580d6-169">тип действия</span><span class="sxs-lookup"><span data-stu-id="580d6-169">activity type</span></span>
- <span data-ttu-id="580d6-170">IP-адрес клиента</span><span class="sxs-lookup"><span data-stu-id="580d6-170">client IP</span></span>
- <span data-ttu-id="580d6-171">путь к целевому файлу</span><span class="sxs-lookup"><span data-stu-id="580d6-171">target file path</span></span>
- <span data-ttu-id="580d6-172">временная метка события</span><span class="sxs-lookup"><span data-stu-id="580d6-172">happened timestamp</span></span>
- <span data-ttu-id="580d6-173">имя файла</span><span class="sxs-lookup"><span data-stu-id="580d6-173">file name</span></span>
- <span data-ttu-id="580d6-174">пользователь</span><span class="sxs-lookup"><span data-stu-id="580d6-174">user</span></span>
- <span data-ttu-id="580d6-175">расширение файла</span><span class="sxs-lookup"><span data-stu-id="580d6-175">file extension</span></span>
- <span data-ttu-id="580d6-176">размер файла</span><span class="sxs-lookup"><span data-stu-id="580d6-176">file size</span></span>
- <span data-ttu-id="580d6-177">типы конфиденциальной информации (если применимо)</span><span class="sxs-lookup"><span data-stu-id="580d6-177">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="580d6-178">значение SHA1</span><span class="sxs-lookup"><span data-stu-id="580d6-178">sha1 value</span></span>
- <span data-ttu-id="580d6-179">значение SHA256</span><span class="sxs-lookup"><span data-stu-id="580d6-179">sha256 value</span></span>
- <span data-ttu-id="580d6-180">предыдущее имя файла</span><span class="sxs-lookup"><span data-stu-id="580d6-180">previous file name</span></span>
- <span data-ttu-id="580d6-181">расположение</span><span class="sxs-lookup"><span data-stu-id="580d6-181">location</span></span>
- <span data-ttu-id="580d6-182">родитель</span><span class="sxs-lookup"><span data-stu-id="580d6-182">parent</span></span>
- <span data-ttu-id="580d6-183">путь к файлу</span><span class="sxs-lookup"><span data-stu-id="580d6-183">filepath</span></span>
- <span data-ttu-id="580d6-184">тип исходного расположения</span><span class="sxs-lookup"><span data-stu-id="580d6-184">source location type</span></span>
- <span data-ttu-id="580d6-185">платформа</span><span class="sxs-lookup"><span data-stu-id="580d6-185">platform</span></span>
- <span data-ttu-id="580d6-186">имя устройства</span><span class="sxs-lookup"><span data-stu-id="580d6-186">device name</span></span>
- <span data-ttu-id="580d6-187">тип конечного расположения</span><span class="sxs-lookup"><span data-stu-id="580d6-187">destination location type</span></span>
- <span data-ttu-id="580d6-188">приложение, которое выполнило копирование</span><span class="sxs-lookup"><span data-stu-id="580d6-188">application that performed the copy</span></span>
- <span data-ttu-id="580d6-189">ИД устройства Microsoft Defender для конечной точки (если применимо)</span><span class="sxs-lookup"><span data-stu-id="580d6-189">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="580d6-190">производитель съемного носителя</span><span class="sxs-lookup"><span data-stu-id="580d6-190">removable media device manufacturer</span></span>
- <span data-ttu-id="580d6-191">модель съемного носителя</span><span class="sxs-lookup"><span data-stu-id="580d6-191">removable media device model</span></span>
- <span data-ttu-id="580d6-192">серийный номер съемного носителя</span><span class="sxs-lookup"><span data-stu-id="580d6-192">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="580d6-193">![атрибуты действий копирования на USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="580d6-193">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="580d6-194">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="580d6-194">Next steps</span></span>

<span data-ttu-id="580d6-195">Теперь, когда вы узнали о защите от потери данных в конечной точке, ознакомьтесь со следующим:</span><span class="sxs-lookup"><span data-stu-id="580d6-195">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="580d6-196">Начало работы с защитой от потери данных в конечной точке от Майкрософт (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="580d6-196">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="580d6-197">Использование защиты от потери данных в конечной точке от Майкрософт (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="580d6-197">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="580d6-198">См. также</span><span class="sxs-lookup"><span data-stu-id="580d6-198">See also</span></span>

- [<span data-ttu-id="580d6-199">Начало работы с защитой от потери данных в конечной точке от Майкрософт (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="580d6-199">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="580d6-200">Использование защиты от потери данных в конечной точке от Майкрософт (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="580d6-200">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="580d6-201">Общие сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="580d6-201">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="580d6-202">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="580d6-202">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="580d6-203">Начало работы с обозревателем действий</span><span class="sxs-lookup"><span data-stu-id="580d6-203">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="580d6-204">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="580d6-204">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="580d6-205">Управление рисками в рамках программы предварительной оценки</span><span class="sxs-lookup"><span data-stu-id="580d6-205">Insider Risk management</span></span>](insider-risk-management.md)
