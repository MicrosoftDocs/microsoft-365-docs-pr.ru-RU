---
title: Узнайте о защите от потери данных в конечной точке Microsoft 365 (предварительная версия)
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
- SPO_Content
search.appverid:
- MET150
description: 'Защита от потери данных в конечной точке Microsoft 365 расширяет отслеживание действий с файлами и защитных действий для конечных точек этих файлов. В решениях для обеспечения соответствия требованиям Microsoft 365 файлы являются видимыми '
ms.openlocfilehash: 7403f20fa7c97c63be0e5001e8d3f5b37b409eee
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2020
ms.locfileid: "48131551"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="cba89-104">Узнайте о защите от потери данных в конечной точке Microsoft 365 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="cba89-104">Learn about Microsoft 365 Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="cba89-105">Защиту от потери данных (DLP) в Microsoft 365 можно использовать для отслеживания действий, принятых в отношении элементов, которые были определены как конфиденциальные, и для защиты от непреднамеренного обмена этими элементами.</span><span class="sxs-lookup"><span data-stu-id="cba89-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="cba89-106">Подробная информация приведена в статье [Обзор защиты от потери данных](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cba89-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="cba89-107">**Защита от потери данных в конечной точке (DLP в конечной точке)** расширяет возможности отслеживания действий и защиты от потери данных для конфиденциальных элементов на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="cba89-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="cba89-108">После того как устройства будут подключены к решениям по обеспечению соответствия требованиям Microsoft 365, сведения о действиях пользователей с конфиденциальными элементами становятся видимыми в [обозревателе действий](data-classification-activity-explorer.md) и вы можете принудительно применять защитные действия к ним с помощью [политик защиты от потери данных](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="cba89-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="cba89-109">Действия в конечных точках, которые вы можете отслеживать и реагировать на них</span><span class="sxs-lookup"><span data-stu-id="cba89-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="cba89-110">Защита от потери данных в конечной точке от Майкрософт позволяет проверять и управлять следующими типами действий, выполняемыми пользователями в отношении конфиденциальных элементов на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="cba89-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> <span data-ttu-id="cba89-111">К ним относятся:</span><span class="sxs-lookup"><span data-stu-id="cba89-111">This includes:</span></span>


|<span data-ttu-id="cba89-112">действие с элементом</span><span class="sxs-lookup"><span data-stu-id="cba89-112">activity on item</span></span> |<span data-ttu-id="cba89-113">проверяемое/ограниченное</span><span class="sxs-lookup"><span data-stu-id="cba89-113">auditable/restrictable</span></span>  |
|---------|---------|
|<span data-ttu-id="cba89-114">создано</span><span class="sxs-lookup"><span data-stu-id="cba89-114">created</span></span>    | <span data-ttu-id="cba89-115">проверяемое</span><span class="sxs-lookup"><span data-stu-id="cba89-115">auditable</span></span>      |
|<span data-ttu-id="cba89-116">переименовано</span><span class="sxs-lookup"><span data-stu-id="cba89-116">renamed</span></span>    |  <span data-ttu-id="cba89-117">проверяемое</span><span class="sxs-lookup"><span data-stu-id="cba89-117">auditable</span></span>       |
|<span data-ttu-id="cba89-118">скопировано на съемные носители или созданное на них</span><span class="sxs-lookup"><span data-stu-id="cba89-118">copied to or created on removable media</span></span>     |     <span data-ttu-id="cba89-119">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="cba89-119">auditable and restrictable</span></span>|
|<span data-ttu-id="cba89-120">скопировано в общую сетевую папку, например \\my-server\fileshare</span><span class="sxs-lookup"><span data-stu-id="cba89-120">copied to network share, e.g. \\my-server\fileshare</span></span>   |     <span data-ttu-id="cba89-121">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="cba89-121">auditable and restrictable</span></span>    |
|<span data-ttu-id="cba89-122">напечатано</span><span class="sxs-lookup"><span data-stu-id="cba89-122">printed</span></span> |    <span data-ttu-id="cba89-123">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="cba89-123">auditable and restrictable</span></span>       |
|<span data-ttu-id="cba89-124">скопировано в облако с помощью Chromium Edge</span><span class="sxs-lookup"><span data-stu-id="cba89-124">copied to cloud via Chromium Edge</span></span>    |   <span data-ttu-id="cba89-125">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="cba89-125">auditable and restrictable</span></span>        |
|<span data-ttu-id="cba89-126">получен доступ посредством неразрешенных приложений и браузеров</span><span class="sxs-lookup"><span data-stu-id="cba89-126">accessed by unallowed apps and browsers</span></span>    |  <span data-ttu-id="cba89-127">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="cba89-127">auditable and restrictable</span></span>       |

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="cba89-128">Чем отличается защита от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="cba89-128">What's different in Endpoint DLP</span></span>

<span data-ttu-id="cba89-129">Перед началом глубокой работы с защитой от потери данных в конечной точке необходимо учитывать ряд дополнительных понятий.</span><span class="sxs-lookup"><span data-stu-id="cba89-129">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="cba89-130">Включение управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="cba89-130">Enabling Device management</span></span>

<span data-ttu-id="cba89-131">Управление устройствами — это функция, позволяющая осуществлять сбор данных телеметрии с устройств и преобразование их в решения для обеспечения соответствия требованиям Microsoft 365, такие как Защита от потери данных в конечной точке и [Управление рисками в рамках программы предварительной оценки](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="cba89-131">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="cba89-132">Вам потребуется подключить все устройства, которые вы хотите использовать в качестве расположений в политиках защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="cba89-132">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

![включение управления устройствами](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

<span data-ttu-id="cba89-134">Подключение и отключение выполняется с помощью сценариев, скачанных из Центра управления устройствами.</span><span class="sxs-lookup"><span data-stu-id="cba89-134">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="cba89-135">В центре есть настраиваемые сценарии для каждого из этих методов развертывания:</span><span class="sxs-lookup"><span data-stu-id="cba89-135">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="cba89-136">локальный сценарий (до 10 компьютеров)</span><span class="sxs-lookup"><span data-stu-id="cba89-136">local script (up to 10 machines)</span></span>
- <span data-ttu-id="cba89-137">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="cba89-137">Group policy</span></span>
- <span data-ttu-id="cba89-138">System Center Configuration Manager (версия 1610 или более поздняя)</span><span class="sxs-lookup"><span data-stu-id="cba89-138">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="cba89-139">Управление мобильными устройствами/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="cba89-139">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="cba89-140">Сценарии подключения в инфраструктуре виртуальных рабочих столов (VDI) для временных компьютеров</span><span class="sxs-lookup"><span data-stu-id="cba89-140">VDI onboarding scripts for non-persistent machines</span></span>

![страница подключения устройств](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 <span data-ttu-id="cba89-142">Для подключения устройств используйте процедуры, описанные в статье [Начало работы с Защитой от потери данных в конечной точке в Microsoft 365](endpoint-dlp-getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="cba89-142">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="cba89-143">При наличии подключенных устройств с помощью [службы Advanced Threat Protection (ATP в Microsoft Defender)](https://docs.microsoft.com/windows/security/threat-protection/) эти устройства будут автоматически отображаться в списке устройств.</span><span class="sxs-lookup"><span data-stu-id="cba89-143">If you have onboarded devices through [Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

![список управляемых устройств](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="cba89-145">Просмотр данных защиты от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="cba89-145">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="cba89-146">Защита от потери данных в конечной точке зависит от типа MIME, поэтому действия будут записываться даже при изменении расширения файла.</span><span class="sxs-lookup"><span data-stu-id="cba89-146">Endpoint DLP monitors activity based om MIME type, so activities will be captured even if the file extension is changed.</span></span> <span data-ttu-id="cba89-147">В общедоступном предварительном просмотре просматривается все:</span><span class="sxs-lookup"><span data-stu-id="cba89-147">At public preview it watches all:</span></span>

- <span data-ttu-id="cba89-148">Файлы Word</span><span class="sxs-lookup"><span data-stu-id="cba89-148">Word files</span></span>
- <span data-ttu-id="cba89-149">Файлы PowerPoint</span><span class="sxs-lookup"><span data-stu-id="cba89-149">PowerPoint files</span></span>
- <span data-ttu-id="cba89-150">Файлы Excel</span><span class="sxs-lookup"><span data-stu-id="cba89-150">Excel files</span></span>
- <span data-ttu-id="cba89-151">PDF-файлы</span><span class="sxs-lookup"><span data-stu-id="cba89-151">PDF files</span></span>
- <span data-ttu-id="cba89-152">CSV-файлы</span><span class="sxs-lookup"><span data-stu-id="cba89-152">.csv files</span></span>
- <span data-ttu-id="cba89-153">ТSV-файлы</span><span class="sxs-lookup"><span data-stu-id="cba89-153">.tsv files</span></span>
- <span data-ttu-id="cba89-154">С-файлы</span><span class="sxs-lookup"><span data-stu-id="cba89-154">c files</span></span>
- <span data-ttu-id="cba89-155">Файлы классов</span><span class="sxs-lookup"><span data-stu-id="cba89-155">class files</span></span>
- <span data-ttu-id="cba89-156">CPP-файлы</span><span class="sxs-lookup"><span data-stu-id="cba89-156">cpp files</span></span>
- <span data-ttu-id="cba89-157">CS-файлы</span><span class="sxs-lookup"><span data-stu-id="cba89-157">cs files</span></span>
- <span data-ttu-id="cba89-158">H-файлы</span><span class="sxs-lookup"><span data-stu-id="cba89-158">h files</span></span>
- <span data-ttu-id="cba89-159">Файлы Java</span><span class="sxs-lookup"><span data-stu-id="cba89-159">java files</span></span>

> [!NOTE]
> <span data-ttu-id="cba89-160">Файлы. txt и исходного кода не подлежат аудиту по умолчанию, а система защиты от потери данных оценивает их согласно применяемым политикам, после чего выполняет аудит или блокировку действий пользователя, соответственно.</span><span class="sxs-lookup"><span data-stu-id="cba89-160">.txt and source code files are not audited by default, DLP evaluates them against the applied policies and then user actions are audited or blocked accordingly.</span></span>

<span data-ttu-id="cba89-161">После подключения устройства сведения о действиях, прошедших аудит, передаются в обозреватель действий даже до настройки и развертывания любой политики защиты от потери данных с устройствами в качестве расположения.</span><span class="sxs-lookup"><span data-stu-id="cba89-161">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

![события защиты от потери данных в конечной точке в обозревателе действий](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

<span data-ttu-id="cba89-163">Защита от потери данных в конечной точке собирает подробную информацию о действиях, прошедших аудит.</span><span class="sxs-lookup"><span data-stu-id="cba89-163">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="cba89-164">Например, если файл копируется на съемный USB-носитель, то в подробных сведениях о действиях будут отображаться указанные ниже атрибуты:</span><span class="sxs-lookup"><span data-stu-id="cba89-164">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="cba89-165">тип действия</span><span class="sxs-lookup"><span data-stu-id="cba89-165">activity type</span></span>
- <span data-ttu-id="cba89-166">IP-адрес клиента</span><span class="sxs-lookup"><span data-stu-id="cba89-166">client IP</span></span>
- <span data-ttu-id="cba89-167">путь к целевому файлу</span><span class="sxs-lookup"><span data-stu-id="cba89-167">target file path</span></span>
- <span data-ttu-id="cba89-168">временная метка события</span><span class="sxs-lookup"><span data-stu-id="cba89-168">happened timestamp</span></span>
- <span data-ttu-id="cba89-169">имя файла</span><span class="sxs-lookup"><span data-stu-id="cba89-169">file name</span></span>
- <span data-ttu-id="cba89-170">пользователь</span><span class="sxs-lookup"><span data-stu-id="cba89-170">user</span></span>
- <span data-ttu-id="cba89-171">расширение файла</span><span class="sxs-lookup"><span data-stu-id="cba89-171">file extension</span></span>
- <span data-ttu-id="cba89-172">размер файла</span><span class="sxs-lookup"><span data-stu-id="cba89-172">file size</span></span>
- <span data-ttu-id="cba89-173">типы конфиденциальной информации (если применимо)</span><span class="sxs-lookup"><span data-stu-id="cba89-173">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="cba89-174">значение SHA1</span><span class="sxs-lookup"><span data-stu-id="cba89-174">sha1 value</span></span>
- <span data-ttu-id="cba89-175">значение SHA256</span><span class="sxs-lookup"><span data-stu-id="cba89-175">sha256 value</span></span>
- <span data-ttu-id="cba89-176">предыдущее имя файла</span><span class="sxs-lookup"><span data-stu-id="cba89-176">previous file name</span></span>
- <span data-ttu-id="cba89-177">расположение</span><span class="sxs-lookup"><span data-stu-id="cba89-177">location</span></span>
- <span data-ttu-id="cba89-178">родитель</span><span class="sxs-lookup"><span data-stu-id="cba89-178">parent</span></span>
- <span data-ttu-id="cba89-179">путь к файлу</span><span class="sxs-lookup"><span data-stu-id="cba89-179">filepath</span></span>
- <span data-ttu-id="cba89-180">тип исходного расположения</span><span class="sxs-lookup"><span data-stu-id="cba89-180">source location type</span></span>
- <span data-ttu-id="cba89-181">платформа</span><span class="sxs-lookup"><span data-stu-id="cba89-181">platform</span></span>
- <span data-ttu-id="cba89-182">имя устройства</span><span class="sxs-lookup"><span data-stu-id="cba89-182">device name</span></span>
- <span data-ttu-id="cba89-183">тип конечного расположения</span><span class="sxs-lookup"><span data-stu-id="cba89-183">destination location type</span></span>
- <span data-ttu-id="cba89-184">приложение, которое выполнило копирование</span><span class="sxs-lookup"><span data-stu-id="cba89-184">application that performed the copy</span></span>
- <span data-ttu-id="cba89-185">ИД устройства Microsoft Defender для конечной точки (если применимо)</span><span class="sxs-lookup"><span data-stu-id="cba89-185">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="cba89-186">производитель съемного носителя</span><span class="sxs-lookup"><span data-stu-id="cba89-186">removable media device manufacturer</span></span>
- <span data-ttu-id="cba89-187">модель съемного носителя</span><span class="sxs-lookup"><span data-stu-id="cba89-187">removable media device model</span></span>
- <span data-ttu-id="cba89-188">серийный номер съемного носителя</span><span class="sxs-lookup"><span data-stu-id="cba89-188">removable media device serial number</span></span>

![копирование атрибутов действий на USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a><span data-ttu-id="cba89-190">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="cba89-190">Next steps</span></span>

<span data-ttu-id="cba89-191">Теперь, когда вы узнали о защите от потери данных в конечной точке, ознакомьтесь со следующим:</span><span class="sxs-lookup"><span data-stu-id="cba89-191">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="cba89-192">Начало работы с защитой от потери данных в конечной точке от Майкрософт (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="cba89-192">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="cba89-193">Использование защиты от потери данных в конечной точке от Майкрософт (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="cba89-193">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="cba89-194">См. также</span><span class="sxs-lookup"><span data-stu-id="cba89-194">See also</span></span>

- [<span data-ttu-id="cba89-195">Начало работы с защитой от потери данных в конечной точке от Майкрософт (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="cba89-195">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="cba89-196">Использование защиты от потери данных в конечной точке от Майкрософт (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="cba89-196">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="cba89-197">Общие сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="cba89-197">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="cba89-198">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="cba89-198">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="cba89-199">Начало работы с обозревателем действий</span><span class="sxs-lookup"><span data-stu-id="cba89-199">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="cba89-200">Microsoft Defender Advanced Threat Protection (ATP в Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="cba89-200">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="cba89-201">Управление рисками в рамках программы предварительной оценки</span><span class="sxs-lookup"><span data-stu-id="cba89-201">Insider Risk management</span></span>](insider-risk-management.md)