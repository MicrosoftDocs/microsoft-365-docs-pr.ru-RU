---
title: Использование функции защиты от потери данных в конечной точке (предварительная версия)
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
ms.openlocfilehash: 0f1fc3159de6545007ddd62da2fca17ce87ad1dc
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636820"
---
# <a name="using-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="c347e-103">Использование функции защиты от потери данных в конечной точке (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="c347e-103">Using Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="c347e-104">В этой статье описаны три сценария создания и изменения политики защиты от потери данных, которая использует устройства как расположение.</span><span class="sxs-lookup"><span data-stu-id="c347e-104">This article walks you through three scenarios where you create and modify a DLP policy that uses devices as a location.</span></span>

## <a name="dlp-settings"></a><span data-ttu-id="c347e-105">Параметры защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="c347e-105">DLP settings</span></span>

<span data-ttu-id="c347e-106">Прежде чем приступить к работе, настройте параметры защиты от потери данных для всех соответствующих политик устройств.</span><span class="sxs-lookup"><span data-stu-id="c347e-106">Before you get started you should set up your DLP settings which are applied to all DLP policies for devices.</span></span> <span data-ttu-id="c347e-107">Это необходимо сделать, если вы планируете создавать политики, которые предполагают:</span><span class="sxs-lookup"><span data-stu-id="c347e-107">You must configure these if you intend to create policies that enforce:</span></span>

- <span data-ttu-id="c347e-108">ограничения для выхода в облако</span><span class="sxs-lookup"><span data-stu-id="c347e-108">cloud egress restrictions</span></span>
- <span data-ttu-id="c347e-109">ограничения для запрещенных приложений</span><span class="sxs-lookup"><span data-stu-id="c347e-109">unallowed apps restrictions</span></span>

<span data-ttu-id="c347e-110">или</span><span class="sxs-lookup"><span data-stu-id="c347e-110">Or</span></span>

- <span data-ttu-id="c347e-111">Если вы хотите исключить пути к шумным файлам</span><span class="sxs-lookup"><span data-stu-id="c347e-111">If you want to exclude noisy file paths from monitoring</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="c347e-112">![Параметры защиты от потери данных](../media/endpoint-dlp-1-using-dlp-settings.png)</span><span class="sxs-lookup"><span data-stu-id="c347e-112">![DLP settings](../media/endpoint-dlp-1-using-dlp-settings.png)</span></span>

### <a name="file-path-exclusions"></a><span data-ttu-id="c347e-113">Исключения путей к файлам</span><span class="sxs-lookup"><span data-stu-id="c347e-113">File path exclusions</span></span>

<span data-ttu-id="c347e-114">При необходимости вы можете исключить пути к некоторым файлам из мониторинга, оповещений и политик защиты от потери данных на своих устройствах, так как они слишком шумные или не содержат нужных файлов.</span><span class="sxs-lookup"><span data-stu-id="c347e-114">You may want to exclude certain paths from DLP monitoring, DLP alerting, and DLP policy enforcement on your devices because they are too noisy or don’t contain files you are interested in.</span></span> <span data-ttu-id="c347e-115">Файлы, расположенные в этих местах, не будут подвергаться аудиту, а файлы, созданные или измененные в них, не будут проверяться политикой защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="c347e-115">Files in those locations will not be audited and any files that are created or modified in those locations will not be subject to DLP policy enforcement.</span></span> <span data-ttu-id="c347e-116">Исключения путей можно настраивать в параметрах защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="c347e-116">You can configure path exclusions in DLP settings.</span></span>

<span data-ttu-id="c347e-117">Для создания путей исключения можно использовать эту логику:</span><span class="sxs-lookup"><span data-stu-id="c347e-117">You can use this logic to construct your exclusion paths:</span></span>

- <span data-ttu-id="c347e-118">Допустимый путь к файлу, заканчивающийся на "\", обозначает файлы, находящиеся в папке.</span><span class="sxs-lookup"><span data-stu-id="c347e-118">Valid file path that ends with ‘\’, which means only files directly under folder.</span></span> <br/><span data-ttu-id="c347e-119">Например: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="c347e-119">For example: C:\Temp</span></span>\

- <span data-ttu-id="c347e-120">Допустимый путь к файлу, заканчивающийся на "\*", обозначает файлы, находящиеся во вложенных папках.</span><span class="sxs-lookup"><span data-stu-id="c347e-120">Valid file path that ends with ‘\*’, which means only files under sub-folders, besides the files directly under the folder.</span></span> <br/><span data-ttu-id="c347e-121">Например: C:\Temp\*</span><span class="sxs-lookup"><span data-stu-id="c347e-121">For example: C:\Temp\*</span></span>

- <span data-ttu-id="c347e-122">Допустимый путь к файлу, который не заканчивается на "\" или "\*", обозначает все файлы в папке и во вложенных папках.</span><span class="sxs-lookup"><span data-stu-id="c347e-122">Valid file path that ends without ‘\’ or ‘\*’, which means all files directly under folder and all sub-folders.</span></span> <br/><span data-ttu-id="c347e-123">Например: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="c347e-123">For example: C:\Temp</span></span>

- <span data-ttu-id="c347e-124">Путь с подстановочными знаками между "\".</span><span class="sxs-lookup"><span data-stu-id="c347e-124">A path with wildcard between ‘\’ from each side.</span></span> <br/><span data-ttu-id="c347e-125">Например: C:\Users\*\Рабочий стол</span><span class="sxs-lookup"><span data-stu-id="c347e-125">For example: C:\Users\*\Desktop</span></span>\

- <span data-ttu-id="c347e-126">Путь с подстановочными знаками между "\" с обеих сторон и "(число)" для предоставления точного числа вложенных папок.</span><span class="sxs-lookup"><span data-stu-id="c347e-126">A path with wildcard between ‘\’ from each side and with ‘(number)’ to give exact number of subfolders.</span></span> <br/><span data-ttu-id="c347e-127">Например: C:\Users\*(1) \Downloads</span><span class="sxs-lookup"><span data-stu-id="c347e-127">For example: C:\Users\*(1)\Downloads</span></span>\

- <span data-ttu-id="c347e-128">Путь с переменными СИСТЕМНОЙ среды.</span><span class="sxs-lookup"><span data-stu-id="c347e-128">A path with SYSTEM environment variables.</span></span> <br/><span data-ttu-id="c347e-129">Например:%SystemDrive%\Test\*</span><span class="sxs-lookup"><span data-stu-id="c347e-129">For example: %SystemDrive%\Test\*</span></span>

- <span data-ttu-id="c347e-130">Комбинация всех вышеуказанных элементов.</span><span class="sxs-lookup"><span data-stu-id="c347e-130">A mix of all the above.</span></span> <br/><span data-ttu-id="c347e-131">Например: %SystemDrive%\Users\*\Documents\*(2) \Sub</span><span class="sxs-lookup"><span data-stu-id="c347e-131">For example: %SystemDrive%\Users\*\Documents\*(2)\Sub</span></span>\

### <a name="service-domains"></a><span data-ttu-id="c347e-132">Сервисные домены</span><span class="sxs-lookup"><span data-stu-id="c347e-132">Service domains</span></span>

<span data-ttu-id="c347e-133">Вы можете добавить в этот список домены, на которые будет ссылаться Edge Chromium во время применения ограничений доступа к облачной загрузке в пределах политики защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="c347e-133">You can add domains to this list that Edge Chromium will refer to when enforcing the Endpoint DLP policy cloud upload access restriction.</span></span> 

<span data-ttu-id="c347e-134">Если для режима списка задано значение **Блокировать**, пользователь не сможет загружать в них конфиденциальные данные.</span><span class="sxs-lookup"><span data-stu-id="c347e-134">If the list mode is set to **Block**, then user will not be able to upload sensitive items to those domains.</span></span> <span data-ttu-id="c347e-135">Если действие отправки заблокировано, потому что элемент подпадает под политику защиты от потери данных, то при этом создается предупреждение или блокируется отправка конфиденциального элемента.</span><span class="sxs-lookup"><span data-stu-id="c347e-135">When an upload action is blocked because an item matches a DLP policy, DLP will either generate a warning or block the upload of the sensitive item.</span></span>

<span data-ttu-id="c347e-136">Если для режима списка задано значение **Разрешить**, пользователи смогут загружать конфиденциальные данные \**_только_*_ в эти домены, но доступ к загрузке в другие домены будет запрещен.</span><span class="sxs-lookup"><span data-stu-id="c347e-136">If the list mode is set to **Allow**, then users will be able to upload sensitive items \**_only_*_ to those domains, and upload access to all other domains is not allowed.</span></span>

### <a name="unallowed-apps"></a><span data-ttu-id="c347e-137">Запрещенные приложения</span><span class="sxs-lookup"><span data-stu-id="c347e-137">Unallowed apps</span></span>

<span data-ttu-id="c347e-138">Если параметр _*Доступ к неразрешенным приложениям и браузерам*\* включен, а пользователи попытаются получить доступ к защищенному файлу с помощью этих приложений, действие может быть разрешено, заблокировано полностью или с возможностью переопределить это ограничение.</span><span class="sxs-lookup"><span data-stu-id="c347e-138">When a policy's _*Access by unallowed apps and browsers*\* setting is turned on and users attempt to use these apps to access a protected file, the activity will be allowed, blocked, or blocked but users can override the restriction.</span></span> <span data-ttu-id="c347e-139">Все действия будут подвержены аудиту и доступны для просмотра в обозревателе действий.</span><span class="sxs-lookup"><span data-stu-id="c347e-139">All activity is audited and available to review in activity explorer.</span></span>

### <a name="unallowed-browsers"></a><span data-ttu-id="c347e-140">Запрещенные браузеры</span><span class="sxs-lookup"><span data-stu-id="c347e-140">Unallowed browsers</span></span>

<span data-ttu-id="c347e-141">Вы можете добавить браузеры, которые определяются по именам исполняемых файлов и которым будет заблокирован доступ к файлам, соответствующим условиям принудительного применения политики защиты от потери данных. В таком случае загрузка данных в облачные сервисы блокируется полностью или с возможностью переопределения.</span><span class="sxs-lookup"><span data-stu-id="c347e-141">You add browsers, identified by their executable names, that will be blocked from accessing files that match the conditions of an enforced a DLP policy where the upload to cloud services restriction is set to block or block override.</span></span> <span data-ttu-id="c347e-142">Если доступ к файлу заблокирован в этих браузерах, пользователи увидят всплывающее уведомление о том, что им нужно открыть файл через Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="c347e-142">When these browsers are blocked from accessing a file, the end users will see a toast notification asking them to open the file through Edge Chromium.</span></span>

[!IMPORTANT]
<span data-ttu-id="c347e-143">Не указывайте путь к исполняемому файлу, а только имя исполняемого файла (например, browser.exe).</span><span class="sxs-lookup"><span data-stu-id="c347e-143">Do not include the path to the executable, but only the executable name (i.e., browser.exe).</span></span>

## <a name="tying-dlp-settings-together"></a><span data-ttu-id="c347e-144">Установка привязки параметров защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="c347e-144">Tying DLP settings together</span></span>

<span data-ttu-id="c347e-145">Благодаря защите от потери данных в конечной точке и браузеру Edge Chromium можно ограничить случайный общий доступ к конфиденциальным элементам для неразрешенных облачных приложений и служб.</span><span class="sxs-lookup"><span data-stu-id="c347e-145">With Endpoint DLP and Edge Chromium Web browser, you can restrict unintentional sharing of sensitive items to unallowed cloud apps and services.</span></span> <span data-ttu-id="c347e-146">Edge Chromium понимает, что элемент ограничен политикой защиты от потери данных и применяет ограничения доступа.</span><span class="sxs-lookup"><span data-stu-id="c347e-146">Edge Chromium understands when an item is restricted by an Endpoint DLP policy and enforces access restrictions.</span></span>

<span data-ttu-id="c347e-147">Когда вы используете защиту от потери данных в конечной точке в правильно настроенной политике и браузере Edge Chromium, неразрешенные браузеры, определенные в этих параметрах, не смогут получить доступ к конфиденциальным элементам, соответствующим вашей политике защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="c347e-147">When you use Endpoint DLP as a location in a properly configured DLP policy and the Edge Chromium browser, the unallowed browsers that you've defined in these settings will be prevented from accessing the sensitive items that match your DLP policy controls.</span></span> <span data-ttu-id="c347e-148">Вместо этого пользователи будут перенаправляться в Edge Chromium, а он благодаря ограничениям защиты от потери данных может заблокировать или ограничить действия, если они подпадают под данные ограничения.</span><span class="sxs-lookup"><span data-stu-id="c347e-148">Instead, users will be redirected to use Edge Chromium and Edge Chromium, with its understanding of DLP imposed restrictions, can block or restrict activities when the conditions in the DLP policy are met.</span></span>

<span data-ttu-id="c347e-149">Чтобы использовать это ограничение, нужно настроить три важных параметра:</span><span class="sxs-lookup"><span data-stu-id="c347e-149">To use this restriction you’ll need to configure three important pieces:</span></span>

1. <span data-ttu-id="c347e-150">Укажите места расположения (сервисы, домены, IP-адреса), которым вы хотите запретить доступ к конфиденциальным элементам.</span><span class="sxs-lookup"><span data-stu-id="c347e-150">Specify the places – services, domains, IP addresses – that you want to prevent sensitive items from being shared to.</span></span>

2. <span data-ttu-id="c347e-151">Добавьте браузеры, которым не разрешено получать доступ к определенным конфиденциальным элементам при совпадении с политикой защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="c347e-151">Add the browsers that aren’t allowed to access certain sensitive items when a DLP policy match occurs.</span></span>

3. <span data-ttu-id="c347e-152">Настройте политики защиты от потери данных, чтобы определить типы конфиденциальных элементов, которые нельзя загружать, включив параметры **Загрузка в облачные службы** и **Доступ из запрещенного браузера**.</span><span class="sxs-lookup"><span data-stu-id="c347e-152">Configure DLP policies to define the kinds of sensitive items for which upload should be restricted to these places by turning on **Upload to cloud services** and **Access from unallowed browser**.</span></span>

<span data-ttu-id="c347e-153">Вы можете продолжить добавление новых служб, приложений и политик, расширив свои ограничения, чтобы они соответствовали вашим потребностям и защищали конфиденциальные данные.</span><span class="sxs-lookup"><span data-stu-id="c347e-153">You can continue to add new services, apps, and policies to extend and augment your restrictions to meet your business needs and protect sensitive data.</span></span> 

<span data-ttu-id="c347e-154">Эта конфигурация обеспечит надежную защиту данных, а также поможет избежать ненужных ограничений, которые не позволяют пользователям получать доступ к общедоступным элементам.</span><span class="sxs-lookup"><span data-stu-id="c347e-154">This configuration will help ensure your data remains safe while also avoiding unnecessary restrictions that prevent or restrict users from accessing and sharing non-sensitive items.</span></span>

## <a name="endpoint-dlp-policy-scenarios"></a><span data-ttu-id="c347e-155">Сценарии политики защиты от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="c347e-155">Endpoint DLP policy scenarios</span></span>

<span data-ttu-id="c347e-156">Чтобы помочь вам ознакомиться с функциями защиты от потери данных и их возможностями, мы составили для вас несколько сценариев.</span><span class="sxs-lookup"><span data-stu-id="c347e-156">To help familiarize you with Endpoint DLP features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span> <span data-ttu-id="c347e-157">Все программы защиты от потери данных в конечной точке будут включены в основной пакет, когда функция будет доступна.</span><span class="sxs-lookup"><span data-stu-id="c347e-157">All the Endpoint DLP content will be folded in to the main DLP content set when Endpoint DLP becomes generally available.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c347e-158">Эти сценарии защиты от потери данных — не официальные процедуры для создания и настройки политик защиты.</span><span class="sxs-lookup"><span data-stu-id="c347e-158">These Endpoint DLP scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="c347e-159">Если вам нужно использовать политики защиты от потери данных в общих ситуациях, прочитайте эти статьи:</span><span class="sxs-lookup"><span data-stu-id="c347e-159">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>- [<span data-ttu-id="c347e-160">Общие сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="c347e-160">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
>- [<span data-ttu-id="c347e-161">Начало работы со стандартной политикой защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="c347e-161">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="c347e-162">Создание политики защиты от потери данных на основе шаблона</span><span class="sxs-lookup"><span data-stu-id="c347e-162">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="c347e-163">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="c347e-163">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a><span data-ttu-id="c347e-164">Сценарий 1. Создание политики на основе шаблона, только аудит</span><span class="sxs-lookup"><span data-stu-id="c347e-164">Scenario 1: Create a policy from a template, audit only</span></span>

<span data-ttu-id="c347e-165">Для использования этого сценария необходимо, чтобы ваши устройства были подключены и доступны в обозревателе активности.</span><span class="sxs-lookup"><span data-stu-id="c347e-165">These scenarios require that you already have devices onboarded and reporting into Activity explorer.</span></span> <span data-ttu-id="c347e-166">Если вы еще не настроили устройства, прочитайте статью [Начало работы с функцией защиты от потери данных (предварительная версия)](endpoint-dlp-getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="c347e-166">If you haven't onboarded devices yet, see [Get started with Endpoint data loss prevention (preview)](endpoint-dlp-getting-started.md).</span></span>

1. <span data-ttu-id="c347e-167">Откройте страницу [Настройка защиты от потери данных](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="c347e-167">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="c347e-168">Выберите **Создать политику (предварительная версия)**.</span><span class="sxs-lookup"><span data-stu-id="c347e-168">Choose **Create policy (preview)**.</span></span>

3. <span data-ttu-id="c347e-169">Для этого сценария выберите **Конфиденциальность**, потом **Личные сведения, США**, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c347e-169">For this scenario, choose **Privacy**, then **U.S. Personally Identifiable Information (PII) Data** and choose **Next**.</span></span>

4. <span data-ttu-id="c347e-170">Переключите поле **Статус** в режим "Выкл." для всех расположений кроме **Устройства**.</span><span class="sxs-lookup"><span data-stu-id="c347e-170">Toggle the **Status** field to off for all locations except **Devices**.</span></span> <span data-ttu-id="c347e-171">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c347e-171">Choose **Next**.</span></span>

5. <span data-ttu-id="c347e-172">Примите значение по умолчанию **Проверка и настройка параметров из шаблона** и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c347e-172">Accept the default **Review and customize settings from the template** selection and choose **Next**.</span></span>

6. <span data-ttu-id="c347e-173">Примите значение по умолчанию **Защита** и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c347e-173">Accept the default **Protection actions** values and choose **Next**.</span></span>

7. <span data-ttu-id="c347e-174">Выберите **Аудит или ограничение действий на устройствах Windows**, а затем выберите набор действий **Только аудит**.</span><span class="sxs-lookup"><span data-stu-id="c347e-174">Select **Audit or restrict activities on Windows devices** and leave the actions set to **Audit only**.</span></span> <span data-ttu-id="c347e-175">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c347e-175">Choose **Next**.</span></span>

8. <span data-ttu-id="c347e-176">Примите значение по умолчанию **Я хочу сначала протестировать** и выберите **Показывать подсказки политики в режиме тестирования**.</span><span class="sxs-lookup"><span data-stu-id="c347e-176">Accept the default **I'd like to test it out first** value and choose **Show policy tips while in test mode**.</span></span> <span data-ttu-id="c347e-177">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c347e-177">Choose **Next**.</span></span>

9. <span data-ttu-id="c347e-178">Проверьте параметры и выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="c347e-178">Review your settings and choose **Submit**.</span></span>

10. <span data-ttu-id="c347e-179">Новая политика защиты от потери данных появится в списке политик.</span><span class="sxs-lookup"><span data-stu-id="c347e-179">The new DLP policy will appear in the policy list.</span></span>

11. <span data-ttu-id="c347e-180">Проверьте, есть ли в обозревателе активности данные из наблюдаемых конечных точек.</span><span class="sxs-lookup"><span data-stu-id="c347e-180">Check Activity explorer for data from the monitored endpoints.</span></span> <span data-ttu-id="c347e-181">Настройте фильтр расположения устройств, добавьте политику, а затем выполните фильтрацию по имени политики, чтобы увидеть, как она работает.</span><span class="sxs-lookup"><span data-stu-id="c347e-181">Set the location filter for devices and add the policy, then filter by policy name to see the impact of this policy.</span></span> <span data-ttu-id="c347e-182">С дополнительными сведениями можно ознакомиться здесь [Начало работы с обозревателем действий](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="c347e-182">See, [Get started with activity explorer](data-classification-activity-explorer.md) if needed.</span></span>

12. <span data-ttu-id="c347e-183">Попробуйте отправить тестовый файл, содержащий личные сведения, человеку, не входящему в вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="c347e-183">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="c347e-184">Это активирует политику.</span><span class="sxs-lookup"><span data-stu-id="c347e-184">This should trigger the policy.</span></span>

13. <span data-ttu-id="c347e-185">Проверьте, отображается ли действие в обозревателе.</span><span class="sxs-lookup"><span data-stu-id="c347e-185">Check Activity explorer for the event.</span></span>

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a><span data-ttu-id="c347e-186">Сценарий 2. Изменение существующей политики, настройка оповещения</span><span class="sxs-lookup"><span data-stu-id="c347e-186">Scenario 2: Modify the existing policy, set an alert</span></span>

1. <span data-ttu-id="c347e-187">Откройте страницу [Настройка защиты от потери данных](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="c347e-187">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="c347e-188">Выберите политику **Личные сведения для США**, созданную в сценарии 1.</span><span class="sxs-lookup"><span data-stu-id="c347e-188">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="c347e-189">Нажмите кнопку **Изменение политики (предварительная версия)**.</span><span class="sxs-lookup"><span data-stu-id="c347e-189">Choose **edit policy (preview)**.</span></span>

4. <span data-ttu-id="c347e-190">Перейдите на страницу **Расширенные правила защиты от потери данных** и измените пункт **Обнаружен небольшой объем личных данных для США**.</span><span class="sxs-lookup"><span data-stu-id="c347e-190">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="c347e-191">Прокрутите страницу вниз до раздела **Отчеты об инцидентах** и переключите параметр **Отправлять оповещения администраторам при возникновении соответствия правилам** на значение **Вкл.**.</span><span class="sxs-lookup"><span data-stu-id="c347e-191">Scroll down to the **Incident reports** section and set **Send an alert to admins when a rule match occurs** to **On**.</span></span> <span data-ttu-id="c347e-192">Сообщения электронной почты автоматически отправляются администратору и другим пользователям, которых вы добавите в список получателей.</span><span class="sxs-lookup"><span data-stu-id="c347e-192">Email alerts will be automatically sent to the administrator and anyone else you add to the list of recipients.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c347e-193">![Включить отчеты об инцидентах](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span><span class="sxs-lookup"><span data-stu-id="c347e-193">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span></span>
   
6. <span data-ttu-id="c347e-194">В этом случае выберите **Отправлять оповещения каждый раз, когда действие будет соответствовать правилу**.</span><span class="sxs-lookup"><span data-stu-id="c347e-194">For the purposes of this scenario, choose **Send alert every time an activity matches the rule**.</span></span>

7. <span data-ttu-id="c347e-195">Выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c347e-195">Choose **Save**.</span></span>

8. <span data-ttu-id="c347e-196">Сохраните все прежние параметры, выбрав **Далее**, а затем **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="c347e-196">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="c347e-197">Попробуйте отправить тестовый файл, содержащий личные сведения, человеку, не входящему в вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="c347e-197">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="c347e-198">Это активирует политику.</span><span class="sxs-lookup"><span data-stu-id="c347e-198">This should trigger the policy.</span></span>

10. <span data-ttu-id="c347e-199">Проверьте, отображается ли действие в обозревателе.</span><span class="sxs-lookup"><span data-stu-id="c347e-199">Check Activity explorer for the event.</span></span>

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a><span data-ttu-id="c347e-200">Сценарий 3. Изменение существующей политики, блокировка действия, разрешающая переопределение</span><span class="sxs-lookup"><span data-stu-id="c347e-200">Scenario 3: Modify the existing policy, block the action with allow override</span></span>

1. <span data-ttu-id="c347e-201">Откройте страницу [Настройка защиты от потери данных](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="c347e-201">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="c347e-202">Выберите политику **Личные сведения для США**, созданную в сценарии 1.</span><span class="sxs-lookup"><span data-stu-id="c347e-202">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="c347e-203">Нажмите кнопку **Изменение политики (предварительная версия)**.</span><span class="sxs-lookup"><span data-stu-id="c347e-203">Choose **edit policy (preview)**.</span></span>

4. <span data-ttu-id="c347e-204">Перейдите на страницу **Расширенные правила защиты от потери данных** и измените пункт **Обнаружен небольшой объем личных данных для США**.</span><span class="sxs-lookup"><span data-stu-id="c347e-204">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="c347e-205">Прокрутите страницу вниз до раздела **Аудит или ограничение действий на устройстве Windows** и для каждого действия задайте соответствующую команду **Блокировать с возможностью переопределения**.</span><span class="sxs-lookup"><span data-stu-id="c347e-205">Scroll down to the **Audit or restrict activities on Windows device** section and for each activity set the corresponding action to  **Block with override**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c347e-206">![Установка блокировки с возможностью переопределения](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span><span class="sxs-lookup"><span data-stu-id="c347e-206">![set block with override action](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span></span>
   
6. <span data-ttu-id="c347e-207">Выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c347e-207">Choose **Save**.</span></span>

7. <span data-ttu-id="c347e-208">Повторите действия 4–7 для параметра **Большой объем личных данных для США**.</span><span class="sxs-lookup"><span data-stu-id="c347e-208">Repeat steps 4-7 for the **High volume of content detected U.S. Personally Identifiable Inf**.</span></span>

8. <span data-ttu-id="c347e-209">Сохраните все прежние параметры, выбрав **Далее**, а затем **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="c347e-209">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="c347e-210">Попробуйте отправить тестовый файл, содержащий личные сведения, человеку, не входящему в вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="c347e-210">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="c347e-211">Это активирует политику.</span><span class="sxs-lookup"><span data-stu-id="c347e-211">This should trigger the policy.</span></span>

   <span data-ttu-id="c347e-212">Вы увидите такое всплывающее окно на устройстве клиента:</span><span class="sxs-lookup"><span data-stu-id="c347e-212">You'll see a popup like this on the client device:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c347e-213">![уведомление о переопределении блокировки защиты от потери данных клиента](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span><span class="sxs-lookup"><span data-stu-id="c347e-213">![endpoint dlp client blocked override notification](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span></span>

10. <span data-ttu-id="c347e-214">Проверьте, отображается ли действие в обозревателе.</span><span class="sxs-lookup"><span data-stu-id="c347e-214">Check Activity explorer for the event.</span></span>

## <a name="see-also"></a><span data-ttu-id="c347e-215">Дополнительные ресурсы:</span><span class="sxs-lookup"><span data-stu-id="c347e-215">See also</span></span>

- [<span data-ttu-id="c347e-216">Сведения о защите от потери данных в конечной точке (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="c347e-216">Learn about Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="c347e-217">Начало работы с функцией защиты от потери данных в конечной точке (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="c347e-217">Get started with Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="c347e-218">Общие сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="c347e-218">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="c347e-219">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="c347e-219">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="c347e-220">Начало работы с обозревателем действий</span><span class="sxs-lookup"><span data-stu-id="c347e-220">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="c347e-221">Microsoft Defender Advanced Threat Protection (ATP в Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="c347e-221">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="c347e-222">Средства и методы подключения для компьютеров с Windows 10</span><span class="sxs-lookup"><span data-stu-id="c347e-222">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="c347e-223">Подписка на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c347e-223">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="c347e-224">Подключено к Azure Active Directory (AAD)</span><span class="sxs-lookup"><span data-stu-id="c347e-224">Azure Active Directory (AAD) joined</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="c347e-225">Загрузка нового браузера Microsoft Edge на основе Chromium</span><span class="sxs-lookup"><span data-stu-id="c347e-225">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [<span data-ttu-id="c347e-226">Начало работы со стандартной политикой защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="c347e-226">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="c347e-227">Создание политики защиты от потери данных на основе шаблона</span><span class="sxs-lookup"><span data-stu-id="c347e-227">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
