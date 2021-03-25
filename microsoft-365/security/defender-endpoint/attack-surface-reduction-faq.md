---
title: Уменьшение поверхности атаки, часто задаваемой вопросами (часто задаваемой вопросы)
description: Найдите ответы на часто задамые вопросы о правилах сокращения поверхности атак в Microsoft Defender ATP.
keywords: Правила уменьшения поверхности атаки, asr, hips, система предотвращения вторжения хостов, правила защиты, антиэкспозиция, антиэкспозит, эксплойт, профилактика инфекций, защитник Майкрософт для конечной точки
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: martyav
ms.author: v-maave
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: 7685bd70d85ecebe759ade762b78ee2c3639cea8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069837"
---
# <a name="attack-surface-reduction-frequently-asked-questions-faq"></a><span data-ttu-id="2c205-104">Уменьшение поверхности атаки, часто задаваемой вопросами (часто задаваемой вопросы)</span><span class="sxs-lookup"><span data-stu-id="2c205-104">Attack surface reduction frequently asked questions (FAQ)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2c205-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="2c205-105">**Applies to:**</span></span>
- [<span data-ttu-id="2c205-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="2c205-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="2c205-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c205-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="is-attack-surface-reduction-asr-part-of-windows"></a><span data-ttu-id="2c205-108">Является ли уменьшение поверхности атаки (ASR) частью Windows?</span><span class="sxs-lookup"><span data-stu-id="2c205-108">Is attack surface reduction (ASR) part of Windows?</span></span>

<span data-ttu-id="2c205-109">ASR изначально была особенностью набора функций защиты эксплойтов, введенных в качестве крупного обновления антивируса Microsoft Defender в Windows 10 версии 1709.</span><span class="sxs-lookup"><span data-stu-id="2c205-109">ASR was originally a feature of the suite of exploit guard features introduced as a major update to Microsoft Defender Antivirus, in Windows 10, version 1709.</span></span> <span data-ttu-id="2c205-110">Антивирус Microsoft Defender — это родной компонент антивирусного обеспечения Windows.</span><span class="sxs-lookup"><span data-stu-id="2c205-110">Microsoft Defender Antivirus is the native antimalware component of Windows.</span></span> <span data-ttu-id="2c205-111">Однако полный набор функций ASR доступен только с корпоративной лицензией Windows.</span><span class="sxs-lookup"><span data-stu-id="2c205-111">However, the full ASR feature-set is only available with a Windows enterprise license.</span></span> <span data-ttu-id="2c205-112">Кроме того, обратите внимание, что исключения из правил ASR управляются отдельно от исключений антивируса Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="2c205-112">Also note that ASR rule exclusions are managed separately from Microsoft Defender Antivirus exclusions.</span></span>

## <a name="do-i-need-to-have-an-enterprise-license-to-run-asr-rules"></a><span data-ttu-id="2c205-113">Нужна ли лицензия предприятия для запуска правил ASR?</span><span class="sxs-lookup"><span data-stu-id="2c205-113">Do I need to have an enterprise license to run ASR rules?</span></span>

<span data-ttu-id="2c205-114">Полный набор правил и функций ASR поддерживается только в том случае, если у вас есть корпоративная лицензия для Windows 10.</span><span class="sxs-lookup"><span data-stu-id="2c205-114">The full set of ASR rules and features is only supported if you have an enterprise license for Windows 10.</span></span> <span data-ttu-id="2c205-115">Ограниченное число правил может работать без корпоративной лицензии.</span><span class="sxs-lookup"><span data-stu-id="2c205-115">A limited number of rules may work without an enterprise license.</span></span> <span data-ttu-id="2c205-116">Если у вас есть Microsoft 365 Business, установите антивирус Microsoft Defender в качестве основного решения безопасности и встройте правила через PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2c205-116">If you have Microsoft 365 Business, set Microsoft Defender Antivirus as your primary security solution, and enable the rules through PowerShell.</span></span> <span data-ttu-id="2c205-117">Однако использование ASR без корпоративной лицензии официально не поддерживается, и все возможности ASR недоступны.</span><span class="sxs-lookup"><span data-stu-id="2c205-117">However, ASR usage without an enterprise license is not officially supported and the full capabilities of ASR will not be available.</span></span>

<span data-ttu-id="2c205-118">Дополнительные информацию о лицензировании Windows см. в руководстве по лицензированию [Windows 10](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) и руководстве по лицензированию томов [для Windows 10.](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)</span><span class="sxs-lookup"><span data-stu-id="2c205-118">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

## <a name="is-asr-supported-if-i-have-an-e3-license"></a><span data-ttu-id="2c205-119">Поддерживается ли ASR, если у меня есть лицензия E3?</span><span class="sxs-lookup"><span data-stu-id="2c205-119">Is ASR supported if I have an E3 license?</span></span>

<span data-ttu-id="2c205-120">Да.</span><span class="sxs-lookup"><span data-stu-id="2c205-120">Yes.</span></span> <span data-ttu-id="2c205-121">ASR поддерживается для Windows Enterprise E3 и выше.</span><span class="sxs-lookup"><span data-stu-id="2c205-121">ASR is supported for Windows Enterprise E3 and above.</span></span> 

## <a name="which-features-are-supported-with-an-e5-license"></a><span data-ttu-id="2c205-122">Какие функции поддерживаются с помощью лицензии E5?</span><span class="sxs-lookup"><span data-stu-id="2c205-122">Which features are supported with an E5 license?</span></span>

<span data-ttu-id="2c205-123">Все правила, поддерживаемые E3, также поддерживаются с помощью E5.</span><span class="sxs-lookup"><span data-stu-id="2c205-123">All of the rules supported with E3 are also supported with E5.</span></span>

<span data-ttu-id="2c205-124">E5 также добавила большую интеграцию с Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="2c205-124">E5 also added greater integration with Defender for Endpoint.</span></span> <span data-ttu-id="2c205-125">С помощью E5 можно использовать [Defender для](https://docs.microsoft.com/microsoft-365/security/defender/monitor-devices?view=o365-worldwide&preserve-view=true#monitor-and-manage-asr-rule-deployment-and-detections) конечной точки для мониторинга и анализа аналитики оповещений в режиме реального времени, исключения правил тонкой настройки, настройки правил ASR и просмотра списков отчетов о событиях.</span><span class="sxs-lookup"><span data-stu-id="2c205-125">With E5, you can [use Defender for Endpoint to monitor and review analytics](https://docs.microsoft.com/microsoft-365/security/defender/monitor-devices?view=o365-worldwide&preserve-view=true#monitor-and-manage-asr-rule-deployment-and-detections) on alerts in real-time, fine-tune rule exclusions, configure ASR rules, and view lists of event reports.</span></span>

## <a name="what-are-the-currently-supported-asr-rules"></a><span data-ttu-id="2c205-126">Какие в настоящее время поддерживаются правила ASR?</span><span class="sxs-lookup"><span data-stu-id="2c205-126">What are the currently supported ASR rules?</span></span>

<span data-ttu-id="2c205-127">В настоящее время ASR поддерживает все нижеугодние правила:</span><span class="sxs-lookup"><span data-stu-id="2c205-127">ASR currently supports all of the rules below:</span></span>

* [<span data-ttu-id="2c205-128">Блокировка исполняемого контента из клиента электронной почты и веб-почты</span><span class="sxs-lookup"><span data-stu-id="2c205-128">Block executable content from email client and webmail</span></span>](attack-surface-reduction.md#block-executable-content-from-email-client-and-webmail)
* [<span data-ttu-id="2c205-129">Блокировка всех приложений Office от создания детских процессов</span><span class="sxs-lookup"><span data-stu-id="2c205-129">Block all Office applications from creating child processes</span></span>](attack-surface-reduction.md#block-all-office-applications-from-creating-child-processes)
* [<span data-ttu-id="2c205-130">Блокировка приложений Office от создания исполняемого контента</span><span class="sxs-lookup"><span data-stu-id="2c205-130">Block Office applications from creating executable content</span></span>](attack-surface-reduction.md#block-office-applications-from-creating-executable-content)
* [<span data-ttu-id="2c205-131">Блокировка приложений Office от внесения кода в другие процессы</span><span class="sxs-lookup"><span data-stu-id="2c205-131">Block Office applications from injecting code into other processes</span></span>](attack-surface-reduction.md#block-office-applications-from-injecting-code-into-other-processes)
* [<span data-ttu-id="2c205-132">Блокировка JavaScript или VBScript от запуска загружаемого исполняемого контента</span><span class="sxs-lookup"><span data-stu-id="2c205-132">Block JavaScript or VBScript from launching downloaded executable content</span></span>](attack-surface-reduction.md#block-javascript-or-vbscript-from-launching-downloaded-executable-content)
* [<span data-ttu-id="2c205-133">Блокировка выполнения потенциально запутаных скриптов</span><span class="sxs-lookup"><span data-stu-id="2c205-133">Block execution of potentially obfuscated scripts</span></span>](attack-surface-reduction.md#block-execution-of-potentially-obfuscated-scripts)
* [<span data-ttu-id="2c205-134">Блокировка вызовов API Win32 из макроса Office</span><span class="sxs-lookup"><span data-stu-id="2c205-134">Block Win32 API calls from Office macro</span></span>](attack-surface-reduction.md#block-win32-api-calls-from-office-macros)
* [<span data-ttu-id="2c205-135">Используйте расширенные средства защиты от программ-вымогателей</span><span class="sxs-lookup"><span data-stu-id="2c205-135">Use advanced protection against ransomware</span></span>](attack-surface-reduction.md#use-advanced-protection-against-ransomware)
* <span data-ttu-id="2c205-136">[Блокировка кражи учетных данных](attack-surface-reduction.md#block-credential-stealing-from-the-windows-local-security-authority-subsystem) из подсистемы локального органа безопасности Windows (lsass.exe)</span><span class="sxs-lookup"><span data-stu-id="2c205-136">[Block credential stealing from the Windows local security authority subsystem](attack-surface-reduction.md#block-credential-stealing-from-the-windows-local-security-authority-subsystem) (lsass.exe)</span></span>
* [<span data-ttu-id="2c205-137">Блокировка создания процессов, происходящих из команд PSExec и WMI</span><span class="sxs-lookup"><span data-stu-id="2c205-137">Block process creations originating from PSExec and WMI commands</span></span>](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)
* [<span data-ttu-id="2c205-138">Блокировка ненарушимых и неподписаных процессов, которые запускают из USB</span><span class="sxs-lookup"><span data-stu-id="2c205-138">Block untrusted and unsigned processes that run from USB</span></span>](attack-surface-reduction.md#block-untrusted-and-unsigned-processes-that-run-from-usb)
* [<span data-ttu-id="2c205-139">Блокировать выполнение файлов, если они не соответствуют критериям распространенности, возраста или доверенного списка</span><span class="sxs-lookup"><span data-stu-id="2c205-139">Block executable files from running unless they meet a prevalence, age, or trusted list criteria</span></span>](attack-surface-reduction.md#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)
* [<span data-ttu-id="2c205-140">Блокировка приложений связи Office от создания детских процессов</span><span class="sxs-lookup"><span data-stu-id="2c205-140">Block Office communication applications from creating child processes</span></span>](attack-surface-reduction.md#block-office-communication-application-from-creating-child-processes)
* [<span data-ttu-id="2c205-141">Блокировка Adobe Reader от создания детских процессов</span><span class="sxs-lookup"><span data-stu-id="2c205-141">Block Adobe Reader from creating child processes</span></span>](attack-surface-reduction.md#block-adobe-reader-from-creating-child-processes)
* [<span data-ttu-id="2c205-142">Блокировка сохраняемости с помощью подписки на события WMI</span><span class="sxs-lookup"><span data-stu-id="2c205-142">Block persistence through WMI event subscription</span></span>](attack-surface-reduction.md#block-persistence-through-wmi-event-subscription)

## <a name="what-are-some-good-recommendations-for-getting-started-with-asr"></a><span data-ttu-id="2c205-143">Какие рекомендации по началу работы с ASR можно получить?</span><span class="sxs-lookup"><span data-stu-id="2c205-143">What are some good recommendations for getting started with ASR?</span></span>

<span data-ttu-id="2c205-144">Проверьте, как правила ASR будут влиять на организацию, прежде чем включите их, запуская правила ASR в режиме аудита в течение короткого периода времени.</span><span class="sxs-lookup"><span data-stu-id="2c205-144">Test how ASR rules will impact your organization before enabling them by running ASR rules in audit mode for a brief period of time.</span></span> <span data-ttu-id="2c205-145">Во время работы правил в режиме аудита можно определить любые бизнес-приложения, которые могут быть заблокированы ошибочно, и исключить их из ASR.</span><span class="sxs-lookup"><span data-stu-id="2c205-145">While you are running the rules in audit mode, you can identify any line-of-business applications that might get blocked erroneously, and exclude them from ASR.</span></span>

<span data-ttu-id="2c205-146">Более крупным организациям следует рассмотреть возможность внедрения правил ASR в "кольцах", путем аудита и включения правил во все более широких подмастериях устройств.</span><span class="sxs-lookup"><span data-stu-id="2c205-146">Larger organizations should consider rolling out ASR rules in "rings," by auditing and enabling rules in increasingly broader subsets of devices.</span></span> <span data-ttu-id="2c205-147">Вы можете упорядошить устройства организации на кольца с помощью Intune или средства управления групповой политикой.</span><span class="sxs-lookup"><span data-stu-id="2c205-147">You can arrange your organization's devices into rings by using Intune or a Group Policy management tool.</span></span>

## <a name="how-long-should-i-test-an-asr-rule-in-audit-mode-before-enabling-it"></a><span data-ttu-id="2c205-148">Как долго следует проверять правило ASR в режиме аудита, прежде чем его включать?</span><span class="sxs-lookup"><span data-stu-id="2c205-148">How long should I test an ASR rule in audit mode before enabling it?</span></span>

<span data-ttu-id="2c205-149">Держите правило в режиме аудита в течение 30 дней, чтобы получить хорошую базовую информацию о том, как правило будет действовать после его работы в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2c205-149">Keep the rule in audit mode for about 30 days to get a good baseline for how the rule will operate once it goes live throughout your organization.</span></span> <span data-ttu-id="2c205-150">В период аудита можно определить любые бизнес-приложения, которые могут быть заблокированы правилом, и настроить правило, чтобы исключить их.</span><span class="sxs-lookup"><span data-stu-id="2c205-150">During the audit period, you can identify any line-of-business applications that might get blocked by the rule, and configure the rule to exclude them.</span></span>

## <a name="im-making-the-switch-from-a-third-party-security-solution-to-defender-for-endpoint-is-there-an-easy-way-to-export-rules-from-another-security-solution-to-asr"></a><span data-ttu-id="2c205-151">Я перешел от сторонного решения безопасности к Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2c205-151">I'm making the switch from a third-party security solution to Defender for Endpoint.</span></span> <span data-ttu-id="2c205-152">Существует ли "простой" способ экспорта правил из другого решения безопасности в ASR?</span><span class="sxs-lookup"><span data-stu-id="2c205-152">Is there an "easy" way to export rules from another security solution to ASR?</span></span>

<span data-ttu-id="2c205-153">В большинстве случаев проще и лучше начать с базовых рекомендаций, предложенных [Defender для конечной](https://docs.microsoft.com/windows/security/threat-protection) точки, чем пытаться импортировать правила из другого решения безопасности.</span><span class="sxs-lookup"><span data-stu-id="2c205-153">In most cases, it's easier and better to start with the baseline recommendations suggested by [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) than to attempt to import rules from another security solution.</span></span> <span data-ttu-id="2c205-154">Затем используйте такие средства, как режим аудита, мониторинг и аналитика, чтобы настроить новое решение в соответствии с вашими уникальными потребностями.</span><span class="sxs-lookup"><span data-stu-id="2c205-154">Then, use tools such as audit mode, monitoring, and analytics to configure your new solution to suit your unique needs.</span></span> 

<span data-ttu-id="2c205-155">Конфигурация по умолчанию для большинства правил ASR в сочетании с защитой Defender для endpoint в режиме реального времени защитит от большого количества эксплойтов и уязвимостей.</span><span class="sxs-lookup"><span data-stu-id="2c205-155">The default configuration for most ASR rules, combined with Defender for Endpoint's real-time protection, will protect against a large number of exploits and vulnerabilities.</span></span>

<span data-ttu-id="2c205-156">В Защитнике для конечной точки можно обновить защиту с помощью настраиваемого индикатора, чтобы разрешить и заблокировать определенные действия программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="2c205-156">From within Defender for Endpoint, you can update your defenses with custom indicators, to allow and block certain software behaviors.</span></span> <span data-ttu-id="2c205-157">ASR также позволяет настраивать правила в виде исключений файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="2c205-157">ASR also allows for some customization of rules, in the form of file and folder exclusions.</span></span> <span data-ttu-id="2c205-158">Как правило, лучше всего проверять правило в течение определенного периода времени и настраивать исключения для любых бизнес-приложений, которые могут быть заблокированы.</span><span class="sxs-lookup"><span data-stu-id="2c205-158">As a general rule, it is best to audit a rule for a period of time, and configure exclusions for any line-of-business applications that might get blocked.</span></span>

## <a name="does-asr-support-file-or-folder-exclusions-that-include-system-variables-and-wildcards-in-the-path"></a><span data-ttu-id="2c205-159">Есть ли исключения из asR-файлов или папок, которые включают системные переменные и подкарды в пути?</span><span class="sxs-lookup"><span data-stu-id="2c205-159">Does ASR support file or folder exclusions that include system variables and wildcards in the path?</span></span>

<span data-ttu-id="2c205-160">Да.</span><span class="sxs-lookup"><span data-stu-id="2c205-160">Yes.</span></span> <span data-ttu-id="2c205-161">Дополнительные сведения об исключении файлов и папок из правил [ASR](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) см. в дополнительных сведениях об исключении файлов или папок из правил ASR, а также настройка и проверка исключений на основе расположения расширений файлов и папок для использования системных переменных и подкардов в исключенных пути файлов.</span><span class="sxs-lookup"><span data-stu-id="2c205-161">See [Excluding files and folders from ASR rules](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) for more details on excluding files or folders from ASR rules, and [Configure and validate exclusions based on file extension and folder location](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) for more on using system variables and wildcards in excluded file paths.</span></span>

## <a name="do-asr-rules-cover-all-applications-by-default"></a><span data-ttu-id="2c205-162">Охватывают ли правила ASR все приложения по умолчанию?</span><span class="sxs-lookup"><span data-stu-id="2c205-162">Do ASR rules cover all applications by default?</span></span>

<span data-ttu-id="2c205-163">Это зависит от правила.</span><span class="sxs-lookup"><span data-stu-id="2c205-163">It depends on the rule.</span></span> <span data-ttu-id="2c205-164">Большинство правил ASR охватывают поведение Microsoft Office и служб, таких как Word, Excel, PowerPoint и OneNote или Outlook.</span><span class="sxs-lookup"><span data-stu-id="2c205-164">Most ASR rules cover the behavior of Microsoft Office products and services, such as Word, Excel, PowerPoint, and OneNote, or Outlook.</span></span> <span data-ttu-id="2c205-165">Некоторые правила ASR, такие как *блок-выполнение* потенциально запутаных скриптов, являются более общими по области.</span><span class="sxs-lookup"><span data-stu-id="2c205-165">Certain ASR rules, such as *Block execution of potentially obfuscated scripts*, are more general in scope.</span></span>

## <a name="does-asr-support-third-party-security-solutions"></a><span data-ttu-id="2c205-166">Поддерживает ли ASR сторонние решения безопасности?</span><span class="sxs-lookup"><span data-stu-id="2c205-166">Does ASR support third-party security solutions?</span></span>

<span data-ttu-id="2c205-167">AsR использует антивирус Microsoft Defender для блокировки приложений.</span><span class="sxs-lookup"><span data-stu-id="2c205-167">ASR uses Microsoft Defender Antivirus to block applications.</span></span> <span data-ttu-id="2c205-168">В настоящее время невозможно настроить ASR для использования другого решения безопасности для блокировки.</span><span class="sxs-lookup"><span data-stu-id="2c205-168">It is not possible to configure ASR to use another security solution for blocking at this time.</span></span>

## <a name="i-have-an-e5-license-and-enabled-some-asr-rules-in-conjunction-with-defender-for-endpoint-is-it-possible-for-an-asr-event-to-not-show-up-at-all-in-defender-for-endpoints-event-timeline"></a><span data-ttu-id="2c205-169">У меня есть лицензия E5 и включены некоторые правила ASR в сочетании с Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="2c205-169">I have an E5 license and enabled some ASR rules in conjunction with Defender for Endpoint.</span></span> <span data-ttu-id="2c205-170">Возможно ли, что событие ASR вообще не будет показываться в временной шкале событий Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="2c205-170">Is it possible for an ASR event to not show up at all in Defender for Endpoint's event timeline?</span></span>

<span data-ttu-id="2c205-171">Всякий раз, когда уведомление запускается локально правилом ASR, отчет о событии также отправляется на портал Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2c205-171">Whenever a notification is triggered locally by an ASR rule, a report on the event is also sent to the Defender for Endpoint portal.</span></span> <span data-ttu-id="2c205-172">Если у вас возникли проблемы с поиском события, вы можете фильтровать временную шкалу событий с помощью окна поиска.</span><span class="sxs-lookup"><span data-stu-id="2c205-172">If you're having trouble finding the event, you can filter the events timeline using the search box.</span></span> <span data-ttu-id="2c205-173">Вы также можете просмотреть события ASR, посетив  **Перейти** к управлению поверхностью атаки из значка управления конфигурацией в панели задач Центра безопасности.</span><span class="sxs-lookup"><span data-stu-id="2c205-173">You can also view ASR events by visiting **Go to attack surface management**, from the **Configuration management** icon in the Security Center taskbar.</span></span> <span data-ttu-id="2c205-174">На странице управления поверхностью атаки содержится вкладка для обнаружения отчетов, которая включает полный список событий правил ASR, о которых сообщается в Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2c205-174">The attack surface management page includes a tab for report detections, which includes a full list of ASR rule events reported to Defender for Endpoint.</span></span>

## <a name="i-applied-a-rule-using-gpo-now-when-i-try-to-check-the-indexing-options-for-the-rule-in-microsoft-outlook-i-get-a-message-stating-access-denied"></a><span data-ttu-id="2c205-175">Я применил правило с помощью GPO.</span><span class="sxs-lookup"><span data-stu-id="2c205-175">I applied a rule using GPO.</span></span> <span data-ttu-id="2c205-176">Теперь, когда я пытаюсь проверить параметры индексации для правила в Microsoft Outlook, я получаю сообщение с указанием", "Доступ отказано".</span><span class="sxs-lookup"><span data-stu-id="2c205-176">Now when I try to check the indexing options for the rule in Microsoft Outlook, I get a message stating, 'Access denied'.</span></span>

<span data-ttu-id="2c205-177">Попробуйте открыть параметры индексации непосредственно из Windows 10.</span><span class="sxs-lookup"><span data-stu-id="2c205-177">Try opening the indexing options directly from Windows 10.</span></span>

1. <span data-ttu-id="2c205-178">Выберите **значок Поиска** на панели задач Windows.</span><span class="sxs-lookup"><span data-stu-id="2c205-178">Select the **Search** icon on the Windows taskbar.</span></span>

1. <span data-ttu-id="2c205-179">Введите **параметры индексации** в поле поиска.</span><span class="sxs-lookup"><span data-stu-id="2c205-179">Enter **Indexing options** into the search box.</span></span>

## <a name="are-the-criteria-used-by-the-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-configurable-by-an-admin"></a><span data-ttu-id="2c205-180">Можно ли настроить администратором критерии, используемые правилом " Блокировать выполнение файлов, если они не соответствуют критерию распространенности, возраста или доверенного списка"?</span><span class="sxs-lookup"><span data-stu-id="2c205-180">Are the criteria used by the rule, "Block executable files from running unless they meet a prevalence, age, or trusted list criterion," configurable by an admin?</span></span>

<span data-ttu-id="2c205-181">Нет.</span><span class="sxs-lookup"><span data-stu-id="2c205-181">No.</span></span> <span data-ttu-id="2c205-182">Критерии, используемые этим правилом, поддерживаются облачной защитой Майкрософт, чтобы поддерживать надежный список постоянно в курсе данных, собранных со всего мира.</span><span class="sxs-lookup"><span data-stu-id="2c205-182">The criteria used by this rule are maintained by Microsoft cloud protection, to keep the trusted list constantly up to date with data gathered from around the world.</span></span> <span data-ttu-id="2c205-183">Местные администраторы не имеют доступа к записи для изменения этих данных.</span><span class="sxs-lookup"><span data-stu-id="2c205-183">Local admins do not have write access to alter this data.</span></span> <span data-ttu-id="2c205-184">Если вы хотите настроить это правило, чтобы настроить его для предприятия, вы можете добавить определенные приложения в список исключений, чтобы предотвратить запуск этого правила.</span><span class="sxs-lookup"><span data-stu-id="2c205-184">If you are looking to configure this rule to tailor it for your enterprise, you can add certain applications to the exclusions list to prevent the rule from being triggered.</span></span>

## <a name="i-enabled-the-asr-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-after-some-time-i-updated-a-piece-of-software-and-the-rule-is-now-blocking-it-even-though-it-didnt-before-did-something-go-wrong"></a><span data-ttu-id="2c205-185">Я включил правило ASR, блокировал выполнение файлов, если они не соответствуют критерию распространенности, возраста или *доверенного списка.*</span><span class="sxs-lookup"><span data-stu-id="2c205-185">I enabled the ASR rule, *Block executable files from running unless they meet a prevalence, age, or trusted list criterion*.</span></span> <span data-ttu-id="2c205-186">Через некоторое время я обновила часть программного обеспечения, и теперь правило блокирует его, хотя раньше этого не было.</span><span class="sxs-lookup"><span data-stu-id="2c205-186">After some time, I updated a piece of software, and the rule is now blocking it, even though it didn't before.</span></span> <span data-ttu-id="2c205-187">Что-то пошло не так?</span><span class="sxs-lookup"><span data-stu-id="2c205-187">Did something go wrong?</span></span>

<span data-ttu-id="2c205-188">Это правило основывается на том, что каждое приложение с известной репутацией измеряется по распространенности, возрасту или включению в список доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="2c205-188">This rule relies upon each application having a known reputation, as measured by prevalence, age, or inclusion on a list of trusted apps.</span></span> <span data-ttu-id="2c205-189">Решение правила заблокировать или разрешить приложение в конечном счете определяется оценкой этих критериев облачной защитой Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2c205-189">The rule's decision to block or allow an application is ultimately determined by Microsoft cloud protection's assessment of these criteria.</span></span>

<span data-ttu-id="2c205-190">Обычно облачная защита может определить, что новая версия приложения настолько похожа на предыдущие версии, что ее не нужно пересматривать.</span><span class="sxs-lookup"><span data-stu-id="2c205-190">Usually, cloud protection can determine that a new version of an application is similar enough to previous versions that it does not need to be reassessed at length.</span></span> <span data-ttu-id="2c205-191">Однако для создания репутации после переключения версий, особенно после серьезного обновления, может потребоваться некоторое время.</span><span class="sxs-lookup"><span data-stu-id="2c205-191">However, it might take some time for the app to build reputation after switching versions, particularly after a major update.</span></span> <span data-ttu-id="2c205-192">В то же время вы можете добавить приложение в список исключений, чтобы это правило не блокировало важные приложения.</span><span class="sxs-lookup"><span data-stu-id="2c205-192">In the meantime, you can add the application to the exclusions list, to prevent this rule from blocking important applications.</span></span> <span data-ttu-id="2c205-193">Если вы часто обновляете и работаете с новыми версиями приложений, вы можете вместо этого запустить это правило в режиме аудита.</span><span class="sxs-lookup"><span data-stu-id="2c205-193">If you are frequently updating and working with new versions of applications, you may opt instead to run this rule in audit mode.</span></span>

## <a name="i-recently-enabled-the-asr-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-and-i-am-getting-a-large-number-of-notifications-what-is-going-on"></a><span data-ttu-id="2c205-194">Недавно я включил правило ASR, блокировал кражу учетных данных из подсистемы локального органа безопасности Windows *(lsass.exe)* и получаю большое количество уведомлений.</span><span class="sxs-lookup"><span data-stu-id="2c205-194">I recently enabled the ASR rule, *Block credential stealing from the Windows local security authority subsystem (lsass.exe)*, and I am getting a large number of notifications.</span></span> <span data-ttu-id="2c205-195">Что происходит?</span><span class="sxs-lookup"><span data-stu-id="2c205-195">What is going on?</span></span>

<span data-ttu-id="2c205-196">Уведомление, сформированное этим правилом, не обязательно указывает на вредоносную активность; однако это правило по-прежнему полезно для блокировки вредоносных действий, так как вредоносные программы часто lsass.exe для получения незаконного доступа к учетным записям.</span><span class="sxs-lookup"><span data-stu-id="2c205-196">A notification generated by this rule does not necessarily indicate malicious activity; however, this rule is still useful for blocking malicious activity, since malware often targets lsass.exe to gain illicit access to accounts.</span></span> <span data-ttu-id="2c205-197">Процесс lsass.exe сохраняет учетные данные пользователей в памяти после входа пользователя.</span><span class="sxs-lookup"><span data-stu-id="2c205-197">The lsass.exe process stores user credentials in memory after a user has logged in.</span></span> <span data-ttu-id="2c205-198">Windows использует эти учетные данные для проверки пользователей и применения локальных политик безопасности.</span><span class="sxs-lookup"><span data-stu-id="2c205-198">Windows uses these credentials to validate users and apply local security policies.</span></span>

<span data-ttu-id="2c205-199">Поскольку многие законные процессы в течение обычного дня будут вызывать lsass.exe для учетных данных, это правило может быть особенно шумным.</span><span class="sxs-lookup"><span data-stu-id="2c205-199">Because many legitimate processes throughout a typical day will be calling on lsass.exe for credentials, this rule can be especially noisy.</span></span> <span data-ttu-id="2c205-200">Если известное законное приложение вызывает это правило для создания чрезмерного количества уведомлений, его можно добавить в список исключений.</span><span class="sxs-lookup"><span data-stu-id="2c205-200">If a known legitimate application causes this rule to generate an excessive number of notifications, you can add it to the exclusion list.</span></span> <span data-ttu-id="2c205-201">Большинство других правил ASR генерирует относительно меньшее количество уведомлений по сравнению с этим, так как вызов lsass.exe является типичным для нормального функционирования многих приложений.</span><span class="sxs-lookup"><span data-stu-id="2c205-201">Most other ASR rules will generate a relatively smaller number of notifications, in comparison to this one, since calling on lsass.exe is typical of many applications' normal functioning.</span></span>

## <a name="is-it-a-good-idea-to-enable-the-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-alongside-lsa-protection"></a><span data-ttu-id="2c205-202">Это хорошая идея, чтобы включить правило, блокировать кражу учетных данных из подсистемы локального органа безопасности *Windows (lsass.exe),* наряду с защитой LSA?</span><span class="sxs-lookup"><span data-stu-id="2c205-202">Is it a good idea to enable the rule, *Block credential stealing from the Windows local security authority subsystem (lsass.exe)*, alongside LSA protection?</span></span>

<span data-ttu-id="2c205-203">Включение этого правила не обеспечит дополнительную защиту, если также включена защита [LSA.](https://docs.microsoft.com/windows-server/security/credentials-protection-and-management/configuring-additional-lsa-protection#BKMK_HowToConfigure)</span><span class="sxs-lookup"><span data-stu-id="2c205-203">Enabling this rule will not provide additional protection if you have [LSA protection](https://docs.microsoft.com/windows-server/security/credentials-protection-and-management/configuring-additional-lsa-protection#BKMK_HowToConfigure) enabled as well.</span></span> <span data-ttu-id="2c205-204">И правило, и защита LSA работают одинаково, поэтому наличие одновременного запуска было бы избыточным.</span><span class="sxs-lookup"><span data-stu-id="2c205-204">Both the rule and LSA protection work in much the same way, so having both running at the same time would be redundant.</span></span> <span data-ttu-id="2c205-205">Однако иногда вы не можете включить защиту LSA.</span><span class="sxs-lookup"><span data-stu-id="2c205-205">However, sometimes you may not be able to enable LSA protection.</span></span> <span data-ttu-id="2c205-206">В этих случаях можно включить это правило, чтобы обеспечить эквивалентную защиту от вредоносных программ, которые lsass.exe.</span><span class="sxs-lookup"><span data-stu-id="2c205-206">In those cases, you can enable this rule to provide equivalent protection against malware that target lsass.exe.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c205-207">См. также</span><span class="sxs-lookup"><span data-stu-id="2c205-207">See also</span></span>

* [<span data-ttu-id="2c205-208">Обзор уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="2c205-208">Attack surface reduction overview</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="2c205-209">Оценка правил уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="2c205-209">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
* [<span data-ttu-id="2c205-210">Настройка правил уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="2c205-210">Customize attack surface reduction rules</span></span>](customize-attack-surface-reduction.md)
* [<span data-ttu-id="2c205-211">Включить правила уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="2c205-211">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)
* [<span data-ttu-id="2c205-212">Совместимость Microsoft Defender с другими антивирусными и антивирусными программами</span><span class="sxs-lookup"><span data-stu-id="2c205-212">Compatibility of Microsoft Defender with other antivirus/antimalware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)