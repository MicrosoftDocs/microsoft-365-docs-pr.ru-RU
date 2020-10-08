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
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 'Защита от потери данных в конечной точке Microsoft 365 расширяет отслеживание действий с файлами и защитных действий для конечных точек этих файлов. В решениях для обеспечения соответствия требованиям Microsoft 365 файлы являются видимыми '
ms.openlocfilehash: fe4ce05c1f9dd0ebce9a6c3be6fffbecfb36c2af
ms.sourcegitcommit: 5e40c760c1af2a4cc6d85cb782b17f5c979677c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2020
ms.locfileid: "48379237"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="f125e-104">Узнайте о защите от потери данных в конечной точке Microsoft 365 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="f125e-104">Learn about Microsoft 365 Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="f125e-105">Защиту от потери данных (DLP) в Microsoft 365 можно использовать для отслеживания действий, принятых в отношении элементов, которые были определены как конфиденциальные, и для защиты от непреднамеренного обмена этими элементами.</span><span class="sxs-lookup"><span data-stu-id="f125e-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="f125e-106">Подробная информация приведена в статье [Обзор защиты от потери данных](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f125e-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="f125e-107">**Защита от потери данных в конечной точке (DLP в конечной точке)** расширяет возможности отслеживания действий и защиты от потери данных для конфиденциальных элементов на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f125e-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="f125e-108">После того как устройства будут подключены к решениям по обеспечению соответствия требованиям Microsoft 365, сведения о действиях пользователей с конфиденциальными элементами становятся видимыми в [обозревателе действий](data-classification-activity-explorer.md) и вы можете принудительно применять защитные действия к ним с помощью [политик защиты от потери данных](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="f125e-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="f125e-109">Действия в конечных точках, которые вы можете отслеживать и реагировать на них</span><span class="sxs-lookup"><span data-stu-id="f125e-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="f125e-110">Защита от потери данных в конечной точке от Майкрософт позволяет проверять и управлять следующими типами действий, выполняемыми пользователями в отношении конфиденциальных элементов на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f125e-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> <span data-ttu-id="f125e-111">К ним относятся:</span><span class="sxs-lookup"><span data-stu-id="f125e-111">This includes:</span></span>


|<span data-ttu-id="f125e-112">действие с элементом</span><span class="sxs-lookup"><span data-stu-id="f125e-112">activity on item</span></span> |<span data-ttu-id="f125e-113">проверяемое/ограниченное</span><span class="sxs-lookup"><span data-stu-id="f125e-113">auditable/restrictable</span></span>  |
|---------|---------|
|<span data-ttu-id="f125e-114">создано</span><span class="sxs-lookup"><span data-stu-id="f125e-114">created</span></span>    | <span data-ttu-id="f125e-115">проверяемое</span><span class="sxs-lookup"><span data-stu-id="f125e-115">auditable</span></span>      |
|<span data-ttu-id="f125e-116">переименовано</span><span class="sxs-lookup"><span data-stu-id="f125e-116">renamed</span></span>    |  <span data-ttu-id="f125e-117">проверяемое</span><span class="sxs-lookup"><span data-stu-id="f125e-117">auditable</span></span>       |
|<span data-ttu-id="f125e-118">скопировано на съемные носители или созданное на них</span><span class="sxs-lookup"><span data-stu-id="f125e-118">copied to or created on removable media</span></span>     |     <span data-ttu-id="f125e-119">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="f125e-119">auditable and restrictable</span></span>|
|<span data-ttu-id="f125e-120">скопировано в общую сетевую папку, например \\my-server\fileshare</span><span class="sxs-lookup"><span data-stu-id="f125e-120">copied to network share, e.g. \\my-server\fileshare</span></span>   |     <span data-ttu-id="f125e-121">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="f125e-121">auditable and restrictable</span></span>    |
|<span data-ttu-id="f125e-122">напечатано</span><span class="sxs-lookup"><span data-stu-id="f125e-122">printed</span></span> |    <span data-ttu-id="f125e-123">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="f125e-123">auditable and restrictable</span></span>       |
|<span data-ttu-id="f125e-124">скопировано в облако с помощью Chromium Edge</span><span class="sxs-lookup"><span data-stu-id="f125e-124">copied to cloud via Chromium Edge</span></span>    |   <span data-ttu-id="f125e-125">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="f125e-125">auditable and restrictable</span></span>        |
|<span data-ttu-id="f125e-126">получен доступ посредством неразрешенных приложений и браузеров</span><span class="sxs-lookup"><span data-stu-id="f125e-126">accessed by unallowed apps and browsers</span></span>    |  <span data-ttu-id="f125e-127">проверяемое и ограниченное</span><span class="sxs-lookup"><span data-stu-id="f125e-127">auditable and restrictable</span></span>       |

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="f125e-128">Чем отличается защита от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="f125e-128">What's different in Endpoint DLP</span></span>

<span data-ttu-id="f125e-129">Перед началом глубокой работы с защитой от потери данных в конечной точке необходимо учитывать ряд дополнительных понятий.</span><span class="sxs-lookup"><span data-stu-id="f125e-129">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="f125e-130">Включение управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="f125e-130">Enabling Device management</span></span>

<span data-ttu-id="f125e-131">Управление устройствами — это функция, позволяющая осуществлять сбор данных телеметрии с устройств и преобразование их в решения для обеспечения соответствия требованиям Microsoft 365, такие как Защита от потери данных в конечной точке и [Управление рисками в рамках программы предварительной оценки](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="f125e-131">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="f125e-132">Вам потребуется подключить все устройства, которые вы хотите использовать в качестве расположений в политиках защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="f125e-132">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

![включение управления устройствами](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

<span data-ttu-id="f125e-134">Подключение и отключение выполняется с помощью сценариев, скачанных из Центра управления устройствами.</span><span class="sxs-lookup"><span data-stu-id="f125e-134">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="f125e-135">В центре есть настраиваемые сценарии для каждого из этих методов развертывания:</span><span class="sxs-lookup"><span data-stu-id="f125e-135">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="f125e-136">локальный сценарий (до 10 компьютеров)</span><span class="sxs-lookup"><span data-stu-id="f125e-136">local script (up to 10 machines)</span></span>
- <span data-ttu-id="f125e-137">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="f125e-137">Group policy</span></span>
- <span data-ttu-id="f125e-138">System Center Configuration Manager (версия 1610 или более поздняя)</span><span class="sxs-lookup"><span data-stu-id="f125e-138">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="f125e-139">Управление мобильными устройствами/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f125e-139">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="f125e-140">Сценарии подключения в инфраструктуре виртуальных рабочих столов (VDI) для временных компьютеров</span><span class="sxs-lookup"><span data-stu-id="f125e-140">VDI onboarding scripts for non-persistent machines</span></span>

![страница подключения устройств](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 <span data-ttu-id="f125e-142">Для подключения устройств используйте процедуры, описанные в статье [Начало работы с Защитой от потери данных в конечной точке в Microsoft 365](endpoint-dlp-getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="f125e-142">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="f125e-143">При наличии подключенных устройств с помощью [службы Advanced Threat Protection (ATP в Microsoft Defender)](https://docs.microsoft.com/windows/security/threat-protection/) эти устройства будут автоматически отображаться в списке устройств.</span><span class="sxs-lookup"><span data-stu-id="f125e-143">If you have onboarded devices through [Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

![список управляемых устройств](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="f125e-145">Просмотр данных защиты от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="f125e-145">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="f125e-146">Защита от потери данных в конечной точке зависит от типа MIME, поэтому действия будут записываться даже при изменении расширения файла.</span><span class="sxs-lookup"><span data-stu-id="f125e-146">Endpoint DLP monitors activity based om MIME type, so activities will be captured even if the file extension is changed.</span></span> <span data-ttu-id="f125e-147">В общедоступном предварительном просмотре просматривается все:</span><span class="sxs-lookup"><span data-stu-id="f125e-147">At public preview it watches all:</span></span>

- <span data-ttu-id="f125e-148">Файлы Word</span><span class="sxs-lookup"><span data-stu-id="f125e-148">Word files</span></span>
- <span data-ttu-id="f125e-149">Файлы PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f125e-149">PowerPoint files</span></span>
- <span data-ttu-id="f125e-150">Файлы Excel</span><span class="sxs-lookup"><span data-stu-id="f125e-150">Excel files</span></span>
- <span data-ttu-id="f125e-151">PDF-файлы</span><span class="sxs-lookup"><span data-stu-id="f125e-151">PDF files</span></span>
- <span data-ttu-id="f125e-152">CSV-файлы</span><span class="sxs-lookup"><span data-stu-id="f125e-152">.csv files</span></span>
- <span data-ttu-id="f125e-153">ТSV-файлы</span><span class="sxs-lookup"><span data-stu-id="f125e-153">.tsv files</span></span>
- <span data-ttu-id="f125e-154">С-файлы</span><span class="sxs-lookup"><span data-stu-id="f125e-154">c files</span></span>
- <span data-ttu-id="f125e-155">Файлы классов</span><span class="sxs-lookup"><span data-stu-id="f125e-155">class files</span></span>
- <span data-ttu-id="f125e-156">CPP-файлы</span><span class="sxs-lookup"><span data-stu-id="f125e-156">cpp files</span></span>
- <span data-ttu-id="f125e-157">CS-файлы</span><span class="sxs-lookup"><span data-stu-id="f125e-157">cs files</span></span>
- <span data-ttu-id="f125e-158">H-файлы</span><span class="sxs-lookup"><span data-stu-id="f125e-158">h files</span></span>
- <span data-ttu-id="f125e-159">Файлы Java</span><span class="sxs-lookup"><span data-stu-id="f125e-159">java files</span></span>

> [!NOTE]
> <span data-ttu-id="f125e-160">Файлы. txt и исходного кода не подлежат аудиту по умолчанию, а система защиты от потери данных оценивает их согласно применяемым политикам, после чего выполняет аудит или блокировку действий пользователя, соответственно.</span><span class="sxs-lookup"><span data-stu-id="f125e-160">.txt and source code files are not audited by default, DLP evaluates them against the applied policies and then user actions are audited or blocked accordingly.</span></span>

<span data-ttu-id="f125e-161">После подключения устройства сведения о действиях, прошедших аудит, передаются в обозреватель действий даже до настройки и развертывания любой политики защиты от потери данных с устройствами в качестве расположения.</span><span class="sxs-lookup"><span data-stu-id="f125e-161">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

![события защиты от потери данных в конечной точке в обозревателе действий](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

<span data-ttu-id="f125e-163">Защита от потери данных в конечной точке собирает подробную информацию о действиях, прошедших аудит.</span><span class="sxs-lookup"><span data-stu-id="f125e-163">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="f125e-164">Например, если файл копируется на съемный USB-носитель, то в подробных сведениях о действиях будут отображаться указанные ниже атрибуты:</span><span class="sxs-lookup"><span data-stu-id="f125e-164">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="f125e-165">тип действия</span><span class="sxs-lookup"><span data-stu-id="f125e-165">activity type</span></span>
- <span data-ttu-id="f125e-166">IP-адрес клиента</span><span class="sxs-lookup"><span data-stu-id="f125e-166">client IP</span></span>
- <span data-ttu-id="f125e-167">путь к целевому файлу</span><span class="sxs-lookup"><span data-stu-id="f125e-167">target file path</span></span>
- <span data-ttu-id="f125e-168">временная метка события</span><span class="sxs-lookup"><span data-stu-id="f125e-168">happened timestamp</span></span>
- <span data-ttu-id="f125e-169">имя файла</span><span class="sxs-lookup"><span data-stu-id="f125e-169">file name</span></span>
- <span data-ttu-id="f125e-170">пользователь</span><span class="sxs-lookup"><span data-stu-id="f125e-170">user</span></span>
- <span data-ttu-id="f125e-171">расширение файла</span><span class="sxs-lookup"><span data-stu-id="f125e-171">file extension</span></span>
- <span data-ttu-id="f125e-172">размер файла</span><span class="sxs-lookup"><span data-stu-id="f125e-172">file size</span></span>
- <span data-ttu-id="f125e-173">типы конфиденциальной информации (если применимо)</span><span class="sxs-lookup"><span data-stu-id="f125e-173">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="f125e-174">значение SHA1</span><span class="sxs-lookup"><span data-stu-id="f125e-174">sha1 value</span></span>
- <span data-ttu-id="f125e-175">значение SHA256</span><span class="sxs-lookup"><span data-stu-id="f125e-175">sha256 value</span></span>
- <span data-ttu-id="f125e-176">предыдущее имя файла</span><span class="sxs-lookup"><span data-stu-id="f125e-176">previous file name</span></span>
- <span data-ttu-id="f125e-177">расположение</span><span class="sxs-lookup"><span data-stu-id="f125e-177">location</span></span>
- <span data-ttu-id="f125e-178">родитель</span><span class="sxs-lookup"><span data-stu-id="f125e-178">parent</span></span>
- <span data-ttu-id="f125e-179">путь к файлу</span><span class="sxs-lookup"><span data-stu-id="f125e-179">filepath</span></span>
- <span data-ttu-id="f125e-180">тип исходного расположения</span><span class="sxs-lookup"><span data-stu-id="f125e-180">source location type</span></span>
- <span data-ttu-id="f125e-181">платформа</span><span class="sxs-lookup"><span data-stu-id="f125e-181">platform</span></span>
- <span data-ttu-id="f125e-182">имя устройства</span><span class="sxs-lookup"><span data-stu-id="f125e-182">device name</span></span>
- <span data-ttu-id="f125e-183">тип конечного расположения</span><span class="sxs-lookup"><span data-stu-id="f125e-183">destination location type</span></span>
- <span data-ttu-id="f125e-184">приложение, которое выполнило копирование</span><span class="sxs-lookup"><span data-stu-id="f125e-184">application that performed the copy</span></span>
- <span data-ttu-id="f125e-185">ИД устройства Microsoft Defender для конечной точки (если применимо)</span><span class="sxs-lookup"><span data-stu-id="f125e-185">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="f125e-186">производитель съемного носителя</span><span class="sxs-lookup"><span data-stu-id="f125e-186">removable media device manufacturer</span></span>
- <span data-ttu-id="f125e-187">модель съемного носителя</span><span class="sxs-lookup"><span data-stu-id="f125e-187">removable media device model</span></span>
- <span data-ttu-id="f125e-188">серийный номер съемного носителя</span><span class="sxs-lookup"><span data-stu-id="f125e-188">removable media device serial number</span></span>

![копирование атрибутов действий на USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a><span data-ttu-id="f125e-190">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="f125e-190">Next steps</span></span>

<span data-ttu-id="f125e-191">Теперь, когда вы узнали о защите от потери данных в конечной точке, ознакомьтесь со следующим:</span><span class="sxs-lookup"><span data-stu-id="f125e-191">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="f125e-192">Начало работы с защитой от потери данных в конечной точке от Майкрософт (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="f125e-192">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="f125e-193">Использование защиты от потери данных в конечной точке от Майкрософт (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="f125e-193">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="f125e-194">См. также</span><span class="sxs-lookup"><span data-stu-id="f125e-194">See also</span></span>

- [<span data-ttu-id="f125e-195">Начало работы с защитой от потери данных в конечной точке от Майкрософт (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="f125e-195">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="f125e-196">Использование защиты от потери данных в конечной точке от Майкрософт (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="f125e-196">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="f125e-197">Общие сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="f125e-197">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="f125e-198">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="f125e-198">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="f125e-199">Начало работы с обозревателем действий</span><span class="sxs-lookup"><span data-stu-id="f125e-199">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="f125e-200">Microsoft Defender Advanced Threat Protection (ATP в Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="f125e-200">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="f125e-201">Управление рисками в рамках программы предварительной оценки</span><span class="sxs-lookup"><span data-stu-id="f125e-201">Insider Risk management</span></span>](insider-risk-management.md)