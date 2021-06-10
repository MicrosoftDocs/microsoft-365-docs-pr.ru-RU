---
title: Использование защиты от потери данных в конечной точке
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Узнайте, как настроить политики защиты от потери данных (DLP), чтобы использовать соответствующие расположения защиты от потери данных в конечной точке Microsoft 365.
ms.openlocfilehash: 1a0297271c3e0e8fb94a476982f146aa8c221e7a
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809135"
---
# <a name="using-endpoint-data-loss-prevention"></a><span data-ttu-id="a4e87-103">Использование защиты от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="a4e87-103">Using Endpoint data loss prevention</span></span>

<span data-ttu-id="a4e87-104">В этой статье описаны три сценария создания и изменения политики защиты от потери данных, которая использует устройства как расположение.</span><span class="sxs-lookup"><span data-stu-id="a4e87-104">This article walks you through three scenarios where you create and modify a DLP policy that uses devices as a location.</span></span>

## <a name="dlp-settings"></a><span data-ttu-id="a4e87-105">Параметры защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="a4e87-105">DLP settings</span></span>

<span data-ttu-id="a4e87-106">Прежде чем приступить к работе, настройте параметры защиты от потери данных для всех соответствующих политик устройств.</span><span class="sxs-lookup"><span data-stu-id="a4e87-106">Before you get started you should set up your DLP settings which are applied to all DLP policies for devices.</span></span> <span data-ttu-id="a4e87-107">Это необходимо сделать, если вы планируете создавать политики, которые предполагают:</span><span class="sxs-lookup"><span data-stu-id="a4e87-107">You must configure these if you intend to create policies that enforce:</span></span>

- <span data-ttu-id="a4e87-108">ограничения для выхода в облако</span><span class="sxs-lookup"><span data-stu-id="a4e87-108">cloud egress restrictions</span></span>
- <span data-ttu-id="a4e87-109">ограничения для запрещенных приложений</span><span class="sxs-lookup"><span data-stu-id="a4e87-109">unallowed apps restrictions</span></span>

<span data-ttu-id="a4e87-110">или</span><span class="sxs-lookup"><span data-stu-id="a4e87-110">Or</span></span>

- <span data-ttu-id="a4e87-111">Если вы хотите исключить пути к шумным файлам</span><span class="sxs-lookup"><span data-stu-id="a4e87-111">If you want to exclude noisy file paths from monitoring</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="a4e87-112">![Параметры защиты от потери данных](../media/endpoint-dlp-1-using-dlp-settings.png)</span><span class="sxs-lookup"><span data-stu-id="a4e87-112">![DLP settings](../media/endpoint-dlp-1-using-dlp-settings.png)</span></span>

### <a name="file-path-exclusions"></a><span data-ttu-id="a4e87-113">Исключения путей к файлам</span><span class="sxs-lookup"><span data-stu-id="a4e87-113">File path exclusions</span></span>

<span data-ttu-id="a4e87-114">При необходимости вы можете исключить пути к некоторым файлам из мониторинга, оповещений и политик защиты от потери данных на своих устройствах, так как они слишком шумные или не содержат нужных файлов.</span><span class="sxs-lookup"><span data-stu-id="a4e87-114">You may want to exclude certain paths from DLP monitoring, DLP alerting, and DLP policy enforcement on your devices because they are too noisy or don’t contain files you are interested in.</span></span> <span data-ttu-id="a4e87-115">Файлы, расположенные в этих местах, не будут подвергаться аудиту, а файлы, созданные или измененные в них, не будут проверяться политикой защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="a4e87-115">Files in those locations will not be audited and any files that are created or modified in those locations will not be subject to DLP policy enforcement.</span></span> <span data-ttu-id="a4e87-116">Исключения путей можно настраивать в параметрах защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="a4e87-116">You can configure path exclusions in DLP settings.</span></span>

<span data-ttu-id="a4e87-117">Для создания путей исключения можно использовать эту логику:</span><span class="sxs-lookup"><span data-stu-id="a4e87-117">You can use this logic to construct your exclusion paths:</span></span>

- <span data-ttu-id="a4e87-118">Допустимый путь к файлу, заканчивающийся на "\", обозначает файлы, находящиеся в папке.</span><span class="sxs-lookup"><span data-stu-id="a4e87-118">Valid file path that ends with ‘\’, which means only files directly under folder.</span></span> <br/><span data-ttu-id="a4e87-119">Например: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="a4e87-119">For example: C:\Temp</span></span>\

- <span data-ttu-id="a4e87-120">Допустимый путь к файлу, заканчивающийся на "\*", обозначает файлы, находящиеся во вложенных папках.</span><span class="sxs-lookup"><span data-stu-id="a4e87-120">Valid file path that ends with ‘\*’, which means only files under sub-folders, besides the files directly under the folder.</span></span> <br/><span data-ttu-id="a4e87-121">Например: C:\Temp\*</span><span class="sxs-lookup"><span data-stu-id="a4e87-121">For example: C:\Temp\*</span></span>

- <span data-ttu-id="a4e87-122">Допустимый путь к файлу, который не заканчивается на "\" или "\*", обозначает все файлы в папке и во вложенных папках.</span><span class="sxs-lookup"><span data-stu-id="a4e87-122">Valid file path that ends without ‘\’ or ‘\*’, which means all files directly under folder and all sub-folders.</span></span> <br/><span data-ttu-id="a4e87-123">Например: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="a4e87-123">For example: C:\Temp</span></span>

- <span data-ttu-id="a4e87-124">Путь с подстановочными знаками между "\".</span><span class="sxs-lookup"><span data-stu-id="a4e87-124">A path with wildcard between ‘\’ from each side.</span></span> <br/><span data-ttu-id="a4e87-125">Например: C:\Users\*\Рабочий стол</span><span class="sxs-lookup"><span data-stu-id="a4e87-125">For example: C:\Users\*\Desktop</span></span>\

- <span data-ttu-id="a4e87-126">Путь с подстановочными знаками между "\" с обеих сторон и "(число)" для предоставления точного числа вложенных папок.</span><span class="sxs-lookup"><span data-stu-id="a4e87-126">A path with wildcard between ‘\’ from each side and with ‘(number)’ to give exact number of subfolders.</span></span> <br/><span data-ttu-id="a4e87-127">Например: C:\Users\*(1) \Downloads</span><span class="sxs-lookup"><span data-stu-id="a4e87-127">For example: C:\Users\*(1)\Downloads</span></span>\

- <span data-ttu-id="a4e87-128">Путь с переменными СИСТЕМНОЙ среды.</span><span class="sxs-lookup"><span data-stu-id="a4e87-128">A path with SYSTEM environment variables.</span></span> <br/><span data-ttu-id="a4e87-129">Например:%SystemDrive%\Test\*</span><span class="sxs-lookup"><span data-stu-id="a4e87-129">For example: %SystemDrive%\Test\*</span></span>

- <span data-ttu-id="a4e87-130">Комбинация всех вышеуказанных элементов.</span><span class="sxs-lookup"><span data-stu-id="a4e87-130">A mix of all the above.</span></span> <br/><span data-ttu-id="a4e87-131">Например: %SystemDrive%\Users\*\Documents\*(2) \Sub</span><span class="sxs-lookup"><span data-stu-id="a4e87-131">For example: %SystemDrive%\Users\*\Documents\*(2)\Sub</span></span>\

### <a name="unallowed-apps"></a><span data-ttu-id="a4e87-132">Запрещенные приложения</span><span class="sxs-lookup"><span data-stu-id="a4e87-132">Unallowed apps</span></span>

<span data-ttu-id="a4e87-133">Если параметр **Доступ к неразрешенным приложениям и браузерам** включен, а пользователи попытаются получить доступ к защищенному файлу с помощью этих приложений, действие может быть разрешено, заблокировано полностью или с возможностью переопределить это ограничение.</span><span class="sxs-lookup"><span data-stu-id="a4e87-133">When a policy's **Access by unallowed apps and browsers** setting is turned on and users attempt to use these apps to access a protected file, the activity will be allowed, blocked, or blocked but users can override the restriction.</span></span> <span data-ttu-id="a4e87-134">Все действия будут подвержены аудиту и доступны для просмотра в обозревателе действий.</span><span class="sxs-lookup"><span data-stu-id="a4e87-134">All activity is audited and available to review in activity explorer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4e87-135">Путь к исполняемому файлу указывать не нужно, следует только задать имя исполняемого файла (например, browser.exe).</span><span class="sxs-lookup"><span data-stu-id="a4e87-135">Do not include the path to the executable, but only the executable name (such as browser.exe).</span></span>

### <a name="unallowed-bluetooth-apps"></a><span data-ttu-id="a4e87-136">Неразрешенные приложения Bluetooth</span><span class="sxs-lookup"><span data-stu-id="a4e87-136">Unallowed Bluetooth apps</span></span>

<span data-ttu-id="a4e87-137">Запретите пользователям перенос файлов, защищенных вашими политиками, с помощью определенных приложений Bluetooth.</span><span class="sxs-lookup"><span data-stu-id="a4e87-137">Prevent people from transferring files protected by your policies via specific Bluetooth apps.</span></span>

### <a name="browser-and-domain-restrictions"></a><span data-ttu-id="a4e87-138">Ограничения браузера и домена</span><span class="sxs-lookup"><span data-stu-id="a4e87-138">Browser and domain restrictions</span></span>
<span data-ttu-id="a4e87-139">Запретите отправку конфиденциальных файлов, соответствующих вашим политикам, в домены служб, для которых отсутствуют ограничения.</span><span class="sxs-lookup"><span data-stu-id="a4e87-139">Restrict sensitive files that match your policies from being shared with unrestricted cloud service domains.</span></span>

#### <a name="service-domains"></a><span data-ttu-id="a4e87-140">Домены служб</span><span class="sxs-lookup"><span data-stu-id="a4e87-140">Service domains</span></span>

<span data-ttu-id="a4e87-141">Вы можете управлять возможностью отправки конфиденциальных файлов, защищенных вашими политиками, в определенные домены служб из Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="a4e87-141">You can control whether sensitive files protected by your policies can be uploaded to specific service domains from Microsoft Edge.</span></span>

<span data-ttu-id="a4e87-142">Если для режима списка задано значение **Блокировать**, пользователь не сможет отправлять конфиденциальные данные в эти домены.</span><span class="sxs-lookup"><span data-stu-id="a4e87-142">If the list mode is set to **Block**, then user will not be able to upload sensitive items to those domains.</span></span> <span data-ttu-id="a4e87-143">Если действие отправки заблокировано, потому что элемент подпадает под политику защиты от потери данных, то при этом создается предупреждение или блокируется отправка конфиденциального элемента.</span><span class="sxs-lookup"><span data-stu-id="a4e87-143">When an upload action is blocked because an item matches a DLP policy, DLP will either generate a warning or block the upload of the sensitive item.</span></span>

<span data-ttu-id="a4e87-144">Если для режима списка задан параметр **Разрешить**, пользователи смогут отправлять конфиденциальные данные **_только_** в эти домены, но доступ к отправке в другие домены будет запрещен.</span><span class="sxs-lookup"><span data-stu-id="a4e87-144">If the list mode is set to **Allow**, then users will be able to upload sensitive items **_only_** to those domains, and upload access to all other domains is not allowed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4e87-145">Если для режима ограничения службы установлено "Разрешить", перед применением ограничений необходимо настроить хотя бы один домен службы.</span><span class="sxs-lookup"><span data-stu-id="a4e87-145">When the service restriction mode is set to "Allow", you must have at least one service domain configured before restrictions are enforced.</span></span>

#### <a name="unallowed-browsers"></a><span data-ttu-id="a4e87-146">Запрещенные браузеры</span><span class="sxs-lookup"><span data-stu-id="a4e87-146">Unallowed browsers</span></span>

<span data-ttu-id="a4e87-147">Вы можете добавить браузеры, которые определяются по именам исполняемых файлов и которым будет заблокирован доступ к файлам, соответствующим условиям принудительного применения политики защиты от потери данных. В таком случае загрузка данных в облачные сервисы блокируется полностью или с возможностью переопределения.</span><span class="sxs-lookup"><span data-stu-id="a4e87-147">You add browsers, identified by their executable names, that will be blocked from accessing files that match the conditions of an enforced a DLP policy where the upload to cloud services restriction is set to block or block override.</span></span> <span data-ttu-id="a4e87-148">Если доступ к файлу заблокирован в этих браузерах, пользователи увидят всплывающее уведомление о том, что им нужно открыть файл через Microsoft Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="a4e87-148">When these browsers are blocked from accessing a file, the end users will see a toast notification asking them to open the file through Edge Chromium.</span></span>

### <a name="business-justification-in-policy-tips"></a><span data-ttu-id="a4e87-149">Деловое обоснование в Подсказках политики</span><span class="sxs-lookup"><span data-stu-id="a4e87-149">Business justification in policy tips</span></span>

<span data-ttu-id="a4e87-150">Вы можете управлять тем, как пользователи взаимодействуют с параметром делового обоснования в уведомлениях подсказки политики защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="a4e87-150">You can control how users interact with the business justification option in DLP policy tip notifications.</span></span> <span data-ttu-id="a4e87-151">Он отображается, когда пользователи выполняют действия, защищенные параметром **Блокировать с возможностью переопределения** в политике защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="a4e87-151">This option appears when users perform an activity that's protected by the **Block with override** setting in a DLP policy.</span></span> <span data-ttu-id="a4e87-152">Вы можете выбрать один из вариантов:</span><span class="sxs-lookup"><span data-stu-id="a4e87-152">You can choose from one the following options:</span></span>

- <span data-ttu-id="a4e87-153">По умолчанию пользователи могут выбирать встроенное обоснование или вводить собственный текст.</span><span class="sxs-lookup"><span data-stu-id="a4e87-153">By default, users can select either a built-in justification, or enter their own text.</span></span>
- <span data-ttu-id="a4e87-154">Пользователи могут выбрать только встроенное обоснование.</span><span class="sxs-lookup"><span data-stu-id="a4e87-154">Users can only select a built-in justification.</span></span>
- <span data-ttu-id="a4e87-155">Пользователи могут вводить только собственное обоснование.</span><span class="sxs-lookup"><span data-stu-id="a4e87-155">Users can only enter their own justification.</span></span>

### <a name="always-audit-file-activity-for-devices"></a><span data-ttu-id="a4e87-156">Всегда контролировать действия с файлами для устройств</span><span class="sxs-lookup"><span data-stu-id="a4e87-156">Always audit file activity for devices</span></span>

<span data-ttu-id="a4e87-157">По умолчанию при подключении устройств, действия для файлов Office, PDF и CSV автоматически проверяются и доступны для просмотра в обозревателе действий.</span><span class="sxs-lookup"><span data-stu-id="a4e87-157">By default, when devices are onboarded, activity for Office, PDF, and CSV files is automatically audited and available for review in activity explorer.</span></span> <span data-ttu-id="a4e87-158">Отключите эту функцию, если вы хотите, чтобы эти действия проверялись только в том случае, если в активную политику включены подключенные устройства.</span><span class="sxs-lookup"><span data-stu-id="a4e87-158">Turn this feature off if you want this activity to be audited only when onboarded devices are included in an active policy.</span></span>

<span data-ttu-id="a4e87-159">Действия с файлами для подключенных устройств всегда будут контролироваться, независимо от того, включены ли они в активную политику.</span><span class="sxs-lookup"><span data-stu-id="a4e87-159">File activity will always be audited for onboarded devices, regardless of whether they are included in an active policy.</span></span>

## <a name="tying-dlp-settings-together"></a><span data-ttu-id="a4e87-160">Установка привязки параметров защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="a4e87-160">Tying DLP settings together</span></span>

<span data-ttu-id="a4e87-161">Благодаря защите от потери данных в конечной точке и браузеру Edge Chromium можно ограничить случайный общий доступ к конфиденциальным элементам для неразрешенных облачных приложений и служб.</span><span class="sxs-lookup"><span data-stu-id="a4e87-161">With Endpoint DLP and Edge Chromium Web browser, you can restrict unintentional sharing of sensitive items to unallowed cloud apps and services.</span></span> <span data-ttu-id="a4e87-162">Edge Chromium понимает, что элемент ограничен политикой защиты от потери данных и применяет ограничения доступа.</span><span class="sxs-lookup"><span data-stu-id="a4e87-162">Edge Chromium understands when an item is restricted by an Endpoint DLP policy and enforces access restrictions.</span></span>

<span data-ttu-id="a4e87-163">Когда вы используете защиту от потери данных в конечной точке в правильно настроенной политике и браузере Edge Chromium, неразрешенные браузеры, определенные в этих параметрах, не смогут получить доступ к конфиденциальным элементам, соответствующим вашей политике защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="a4e87-163">When you use Endpoint DLP as a location in a properly configured DLP policy and the Edge Chromium browser, the unallowed browsers that you've defined in these settings will be prevented from accessing the sensitive items that match your DLP policy controls.</span></span> <span data-ttu-id="a4e87-164">Вместо этого пользователи будут перенаправляться в Edge Chromium, а он благодаря ограничениям защиты от потери данных может заблокировать или ограничить действия, если они подпадают под данные ограничения.</span><span class="sxs-lookup"><span data-stu-id="a4e87-164">Instead, users will be redirected to use Edge Chromium and Edge Chromium, with its understanding of DLP imposed restrictions, can block or restrict activities when the conditions in the DLP policy are met.</span></span>

<span data-ttu-id="a4e87-165">Чтобы использовать это ограничение, нужно настроить три важных параметра:</span><span class="sxs-lookup"><span data-stu-id="a4e87-165">To use this restriction you’ll need to configure three important pieces:</span></span>

1. <span data-ttu-id="a4e87-166">Укажите места расположения (сервисы, домены, IP-адреса), которым вы хотите запретить доступ к конфиденциальным элементам.</span><span class="sxs-lookup"><span data-stu-id="a4e87-166">Specify the places – services, domains, IP addresses – that you want to prevent sensitive items from being shared to.</span></span>

2. <span data-ttu-id="a4e87-167">Добавьте браузеры, которым не разрешено получать доступ к определенным конфиденциальным элементам при совпадении с политикой защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="a4e87-167">Add the browsers that aren’t allowed to access certain sensitive items when a DLP policy match occurs.</span></span>

3. <span data-ttu-id="a4e87-168">Настройте политики защиты от потери данных, чтобы определить типы конфиденциальных элементов, которые нельзя загружать, включив параметры **Загрузка в облачные службы** и **Доступ из запрещенного браузера**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-168">Configure DLP policies to define the kinds of sensitive items for which upload should be restricted to these places by turning on **Upload to cloud services** and **Access from unallowed browser**.</span></span>

<span data-ttu-id="a4e87-169">Вы можете продолжить добавление новых служб, приложений и политик, расширив свои ограничения, чтобы они соответствовали вашим потребностям и защищали конфиденциальные данные.</span><span class="sxs-lookup"><span data-stu-id="a4e87-169">You can continue to add new services, apps, and policies to extend and augment your restrictions to meet your business needs and protect sensitive data.</span></span> 

<span data-ttu-id="a4e87-170">Эта конфигурация обеспечит надежную защиту данных, а также поможет избежать ненужных ограничений, которые не позволяют пользователям получать доступ к общедоступным элементам.</span><span class="sxs-lookup"><span data-stu-id="a4e87-170">This configuration will help ensure your data remains safe while also avoiding unnecessary restrictions that prevent or restrict users from accessing and sharing non-sensitive items.</span></span>

## <a name="endpoint-dlp-policy-scenarios"></a><span data-ttu-id="a4e87-171">Сценарии политики защиты от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="a4e87-171">Endpoint DLP policy scenarios</span></span>

<span data-ttu-id="a4e87-172">Чтобы помочь вам ознакомиться с функциями защиты от потери данных и их возможностями, мы составили для вас несколько сценариев.</span><span class="sxs-lookup"><span data-stu-id="a4e87-172">To help familiarize you with Endpoint DLP features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4e87-173">Эти сценарии защиты от потери данных — не официальные процедуры для создания и настройки политик защиты.</span><span class="sxs-lookup"><span data-stu-id="a4e87-173">These Endpoint DLP scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="a4e87-174">Если вам нужно использовать политики защиты от потери данных в общих ситуациях, прочитайте эти статьи:</span><span class="sxs-lookup"><span data-stu-id="a4e87-174">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>

>- [<span data-ttu-id="a4e87-175">Сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="a4e87-175">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
>- [<span data-ttu-id="a4e87-176">Начало работы со стандартной политикой защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="a4e87-176">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="a4e87-177">Создание политики защиты от потери данных на основе шаблона</span><span class="sxs-lookup"><span data-stu-id="a4e87-177">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="a4e87-178">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="a4e87-178">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a><span data-ttu-id="a4e87-179">Сценарий 1. Создание политики на основе шаблона, только аудит</span><span class="sxs-lookup"><span data-stu-id="a4e87-179">Scenario 1: Create a policy from a template, audit only</span></span>

<span data-ttu-id="a4e87-180">Для использования этого сценария необходимо, чтобы ваши устройства были подключены и доступны в обозревателе действий.</span><span class="sxs-lookup"><span data-stu-id="a4e87-180">These scenarios require that you already have devices onboarded and reporting into Activity explorer.</span></span> <span data-ttu-id="a4e87-181">Если вы еще не настроили устройства, прочитайте статью [Начало работы с функцией защиты от потери данных](endpoint-dlp-getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="a4e87-181">If you haven't onboarded devices yet, see [Get started with Endpoint data loss prevention](endpoint-dlp-getting-started.md).</span></span>

1. <span data-ttu-id="a4e87-182">Откройте страницу [Защита от потери данных](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="a4e87-182">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="a4e87-183">Выберите **Создать политику**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-183">Choose **Create policy**.</span></span>

3. <span data-ttu-id="a4e87-184">Для этого сценария выберите **Конфиденциальность**, потом — **Личные сведения, США** и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-184">For this scenario, choose **Privacy**, then **U.S. Personally Identifiable Information (PII) Data** and choose **Next**.</span></span>

4. <span data-ttu-id="a4e87-185">Переключите поле **Статус** в режим "Выкл." для всех расположений кроме **Устройства**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-185">Toggle the **Status** field to off for all locations except **Devices**.</span></span> <span data-ttu-id="a4e87-186">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-186">Choose **Next**.</span></span>

5. <span data-ttu-id="a4e87-187">Примите значение по умолчанию **Проверка и настройка параметров из шаблона** и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-187">Accept the default **Review and customize settings from the template** selection and choose **Next**.</span></span>

6. <span data-ttu-id="a4e87-188">Примите значение по умолчанию **Защита** и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-188">Accept the default **Protection actions** values and choose **Next**.</span></span>

7. <span data-ttu-id="a4e87-189">Выберите **Аудит или ограничение действий на устройствах Windows**, а затем выберите набор действий **Только аудит**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-189">Select **Audit or restrict activities on Windows devices** and leave the actions set to **Audit only**.</span></span> <span data-ttu-id="a4e87-190">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-190">Choose **Next**.</span></span>

8. <span data-ttu-id="a4e87-191">Примите значение по умолчанию **Я хочу сначала протестировать** и выберите **Показывать подсказки политики в режиме тестирования**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-191">Accept the default **I'd like to test it out first** value and choose **Show policy tips while in test mode**.</span></span> <span data-ttu-id="a4e87-192">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-192">Choose **Next**.</span></span>

9. <span data-ttu-id="a4e87-193">Проверьте параметры и выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-193">Review your settings and choose **Submit**.</span></span>

10. <span data-ttu-id="a4e87-194">Новая политика защиты от потери данных появится в списке политик.</span><span class="sxs-lookup"><span data-stu-id="a4e87-194">The new DLP policy will appear in the policy list.</span></span>

11. <span data-ttu-id="a4e87-195">Проверьте, есть ли в обозревателе активности данные из наблюдаемых конечных точек.</span><span class="sxs-lookup"><span data-stu-id="a4e87-195">Check Activity explorer for data from the monitored endpoints.</span></span> <span data-ttu-id="a4e87-196">Настройте фильтр расположения устройств, добавьте политику, а затем выполните фильтрацию по имени политики, чтобы увидеть, как она работает.</span><span class="sxs-lookup"><span data-stu-id="a4e87-196">Set the location filter for devices and add the policy, then filter by policy name to see the impact of this policy.</span></span> <span data-ttu-id="a4e87-197">С дополнительными сведениями можно ознакомиться здесь [Начало работы с обозревателем действий](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="a4e87-197">See, [Get started with activity explorer](data-classification-activity-explorer.md) if needed.</span></span>

12. <span data-ttu-id="a4e87-198">Попробуйте отправить тестовый файл, содержащий личные сведения, человеку, не входящему в вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="a4e87-198">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="a4e87-199">Это активирует политику.</span><span class="sxs-lookup"><span data-stu-id="a4e87-199">This should trigger the policy.</span></span>

13. <span data-ttu-id="a4e87-200">Проверьте, отображается ли действие в обозревателе.</span><span class="sxs-lookup"><span data-stu-id="a4e87-200">Check Activity explorer for the event.</span></span>

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a><span data-ttu-id="a4e87-201">Сценарий 2. Изменение существующей политики, настройка оповещения</span><span class="sxs-lookup"><span data-stu-id="a4e87-201">Scenario 2: Modify the existing policy, set an alert</span></span>

1. <span data-ttu-id="a4e87-202">Откройте страницу [Защита от потери данных](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="a4e87-202">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="a4e87-203">Выберите политику **Личные сведения, США**, созданную в сценарии 1.</span><span class="sxs-lookup"><span data-stu-id="a4e87-203">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="a4e87-204">Нажмите кнопку **Изменить политику**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-204">Choose **edit policy**.</span></span>

4. <span data-ttu-id="a4e87-205">Перейдите на страницу **Расширенные правила защиты от потери данных** и измените пункт **Обнаружен небольшой объем личных данных, США**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-205">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="a4e87-206">Прокрутите страницу вниз до раздела **Отчеты об инцидентах** и переключите параметр **Отправлять оповещения администраторам при возникновении соответствия правилам** на значение **Вкл.**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-206">Scroll down to the **Incident reports** section and set **Send an alert to admins when a rule match occurs** to **On**.</span></span> <span data-ttu-id="a4e87-207">Сообщения электронной почты автоматически отправляются администратору и другим пользователям, которых вы добавите в список получателей.</span><span class="sxs-lookup"><span data-stu-id="a4e87-207">Email alerts will be automatically sent to the administrator and anyone else you add to the list of recipients.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a4e87-208">![Включить отчеты об инцидентах](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span><span class="sxs-lookup"><span data-stu-id="a4e87-208">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span></span>
   
6. <span data-ttu-id="a4e87-209">В этом случае выберите **Отправлять оповещения каждый раз, когда действие будет соответствовать правилу**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-209">For the purposes of this scenario, choose **Send alert every time an activity matches the rule**.</span></span>

7. <span data-ttu-id="a4e87-210">Выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-210">Choose **Save**.</span></span>

8. <span data-ttu-id="a4e87-211">Сохраните все прежние параметры, выбрав **Далее**, а затем **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-211">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="a4e87-212">Попробуйте отправить тестовый файл, содержащий личные сведения, человеку, не входящему в вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="a4e87-212">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="a4e87-213">Это активирует политику.</span><span class="sxs-lookup"><span data-stu-id="a4e87-213">This should trigger the policy.</span></span>

10. <span data-ttu-id="a4e87-214">Проверьте, отображается ли действие в обозревателе.</span><span class="sxs-lookup"><span data-stu-id="a4e87-214">Check Activity explorer for the event.</span></span>

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a><span data-ttu-id="a4e87-215">Сценарий 3. Изменение существующей политики, блокировка действия, разрешающая переопределение</span><span class="sxs-lookup"><span data-stu-id="a4e87-215">Scenario 3: Modify the existing policy, block the action with allow override</span></span>

1. <span data-ttu-id="a4e87-216">Откройте страницу [Защита от потери данных](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="a4e87-216">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="a4e87-217">Выберите политику **Личные сведения, США**, созданную в сценарии 1.</span><span class="sxs-lookup"><span data-stu-id="a4e87-217">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="a4e87-218">Нажмите кнопку **Изменить политику**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-218">Choose **edit policy**.</span></span>

4. <span data-ttu-id="a4e87-219">Перейдите на страницу **Расширенные правила защиты от потери данных** и измените пункт **Обнаружен небольшой объем личных данных, США**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-219">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="a4e87-220">Прокрутите страницу вниз до раздела **Аудит или ограничение действий на устройстве Windows** и для каждого действия задайте соответствующую команду **Блокировать с возможностью переопределения**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-220">Scroll down to the **Audit or restrict activities on Windows device** section and for each activity set the corresponding action to  **Block with override**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a4e87-221">![Установка блокировки с возможностью переопределения](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span><span class="sxs-lookup"><span data-stu-id="a4e87-221">![set block with override action](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span></span>
   
6. <span data-ttu-id="a4e87-222">Выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-222">Choose **Save**.</span></span>

7. <span data-ttu-id="a4e87-223">Повторите действия 4–7 для параметра **Большой объем личных данных для США**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-223">Repeat steps 4-7 for the **High volume of content detected U.S. Personally Identifiable Inf**.</span></span>

8. <span data-ttu-id="a4e87-224">Сохраните все прежние параметры, выбрав **Далее**, а затем **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="a4e87-224">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="a4e87-225">Попробуйте отправить тестовый файл, содержащий личные сведения, человеку, не входящему в вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="a4e87-225">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="a4e87-226">Это активирует политику.</span><span class="sxs-lookup"><span data-stu-id="a4e87-226">This should trigger the policy.</span></span>

   <span data-ttu-id="a4e87-227">Вы увидите такое всплывающее окно на устройстве клиента:</span><span class="sxs-lookup"><span data-stu-id="a4e87-227">You'll see a popup like this on the client device:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a4e87-228">![уведомление о переопределении блокировки защиты от потери данных клиента](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span><span class="sxs-lookup"><span data-stu-id="a4e87-228">![endpoint dlp client blocked override notification](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span></span>

10. <span data-ttu-id="a4e87-229">Проверьте, отображается ли действие в обозревателе.</span><span class="sxs-lookup"><span data-stu-id="a4e87-229">Check Activity explorer for the event.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4e87-230">См. также</span><span class="sxs-lookup"><span data-stu-id="a4e87-230">See also</span></span>

- [<span data-ttu-id="a4e87-231">Сведения о защите от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="a4e87-231">Learn about Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="a4e87-232">Начало работы с функцией защиты от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="a4e87-232">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="a4e87-233">Сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="a4e87-233">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="a4e87-234">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="a4e87-234">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="a4e87-235">Начало работы с обозревателем действий</span><span class="sxs-lookup"><span data-stu-id="a4e87-235">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="a4e87-236">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a4e87-236">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="a4e87-237">Средства и методы подключения для компьютеров с Windows 10</span><span class="sxs-lookup"><span data-stu-id="a4e87-237">Onboarding tools and methods for Windows 10 machines</span></span>](/microsoft-365/compliance/dlp-configure-endpoints)
- [<span data-ttu-id="a4e87-238">Подписка на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a4e87-238">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="a4e87-239">Подключено к Azure Active Directory (AAD)</span><span class="sxs-lookup"><span data-stu-id="a4e87-239">Azure Active Directory (AAD) joined</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="a4e87-240">Загрузка нового браузера Microsoft Edge на основе Chromium</span><span class="sxs-lookup"><span data-stu-id="a4e87-240">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [<span data-ttu-id="a4e87-241">Начало работы со стандартной политикой защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="a4e87-241">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="a4e87-242">Создание политики защиты от потери данных на основе шаблона</span><span class="sxs-lookup"><span data-stu-id="a4e87-242">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
