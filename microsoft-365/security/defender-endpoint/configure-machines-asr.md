---
title: Оптимизация развертывания и обнаружений правил сокращения направлений атак
description: Оптимизируйте правила уменьшения поверхности атаки для выявления и предотвращения типичных эксплойтов вредоносных программ.
keywords: на борту, управление Intune, Microsoft Defender для конечной точки, Microsoft Defender, Защитник Windows, уменьшение поверхности атаки, ASR, базовый уровень безопасности
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a5590e62e7838bb9f611320b6d0e5c573b2be084
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841562"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a><span data-ttu-id="e04f2-104">Оптимизация развертывания и обнаружений правил сокращения направлений атак</span><span class="sxs-lookup"><span data-stu-id="e04f2-104">Optimize ASR rule deployment and detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e04f2-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e04f2-105">**Applies to:**</span></span>
- [<span data-ttu-id="e04f2-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e04f2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e04f2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e04f2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e04f2-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="e04f2-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="e04f2-109">[Зарегистрився для бесплатной пробной.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="e04f2-109">[Sign up for a free trial](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink).</span></span>

<span data-ttu-id="e04f2-110">[Правила уменьшения поверхности атаки (ASR) определяют](./attack-surface-reduction.md) и предотвращают типичные эксплойты вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="e04f2-110">[Attack surface reduction (ASR) rules](./attack-surface-reduction.md) identify and prevent typical malware exploits.</span></span> <span data-ttu-id="e04f2-111">Они контролируют, когда и как может запускаться потенциально вредоносный код.</span><span class="sxs-lookup"><span data-stu-id="e04f2-111">They control when and how potentially malicious code can run.</span></span> <span data-ttu-id="e04f2-112">Например, они могут запретить JavaScript или VBScript запускать загруженный исполняемый файл, блокировать вызовы API Win32 из макроса Office и блокировать процессы, которые выполняются с USB-дисков.</span><span class="sxs-lookup"><span data-stu-id="e04f2-112">For example, they can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, and block processes that run from USB drives.</span></span>

<span data-ttu-id="e04f2-113">![Карта управления поверхностью атаки](images/secconmgmt_asr_card.png)</span><span class="sxs-lookup"><span data-stu-id="e04f2-113">![Attack surface management card](images/secconmgmt_asr_card.png)</span></span><br>
<span data-ttu-id="e04f2-114">*Карта управления поверхностью атаки*</span><span class="sxs-lookup"><span data-stu-id="e04f2-114">*Attack surface management card*</span></span>

<span data-ttu-id="e04f2-115">Карта *управления поверхностью атаки* — это точка входа в инструменты в центре Microsoft 365 безопасности, которые можно использовать для:</span><span class="sxs-lookup"><span data-stu-id="e04f2-115">The *Attack surface management card* is an entry point to tools in Microsoft 365 security center that you can use to:</span></span>

* <span data-ttu-id="e04f2-116">Понимание того, как в настоящее время в организации развернуты правила ASR.</span><span class="sxs-lookup"><span data-stu-id="e04f2-116">Understand how ASR rules are currently deployed in your organization.</span></span>
* <span data-ttu-id="e04f2-117">Просмотрите обнаружение ASR и определите возможные неправильные обнаружения.</span><span class="sxs-lookup"><span data-stu-id="e04f2-117">Review ASR detections and identify possible incorrect detections.</span></span>
* <span data-ttu-id="e04f2-118">Анализ воздействия исключений и создание списка путей для исключения файлов.</span><span class="sxs-lookup"><span data-stu-id="e04f2-118">Analyze the impact of exclusions and generate the list of file paths to exclude.</span></span>

<span data-ttu-id="e04f2-119">Выберите **Go для** мониторинга мониторинга поверхности & отчетов > правил уменьшения поверхности > добавления  >  **исключений.**</span><span class="sxs-lookup"><span data-stu-id="e04f2-119">Select **Go to attack surface management** > **Monitoring & reports > Attack surface reduction rules > Add exclusions**.</span></span> <span data-ttu-id="e04f2-120">Оттуда можно перейти к другим разделам центра Microsoft 365 безопасности.</span><span class="sxs-lookup"><span data-stu-id="e04f2-120">From there, you can navigate to other sections of Microsoft 365 security center.</span></span>

<span data-ttu-id="e04f2-121">![Добавление вкладки исключений на странице Правил уменьшения поверхности атаки в центре Microsoft 365 безопасности](images/secconmgmt_asr_m365exlusions.png)</span><span class="sxs-lookup"><span data-stu-id="e04f2-121">![Add exclusions tab in the Attack surface reduction rules page in Microsoft 365 security center](images/secconmgmt_asr_m365exlusions.png)</span></span><br>
<span data-ttu-id="e04f2-122">Вкладка ***Добавление исключений** на странице Правил уменьшения поверхности атаки в центре Microsoft 365 безопасности*</span><span class="sxs-lookup"><span data-stu-id="e04f2-122">The ***Add exclusions** tab in the Attack surface reduction rules page in Microsoft 365 security center*</span></span>

> [!NOTE]
> <span data-ttu-id="e04f2-123">Чтобы получить Microsoft 365 центр безопасности, вам потребуется лицензия Microsoft 365 E3 E5 и учетная запись, которая имеет определенные роли в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e04f2-123">To access Microsoft 365 security center, you need a Microsoft 365 E3 or E5 license and an account that has certain roles on Azure Active Directory.</span></span> <span data-ttu-id="e04f2-124">[Ознакомьтесь с требуемой лицензией и разрешениями.](/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="e04f2-124">[Read about required licenses and permissions](/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

<span data-ttu-id="e04f2-125">Дополнительные сведения о развертывании правил ASR в центре Microsoft 365 см. в рубрике Монитор и управление развертыванием и обнаружением правил [ASR.](/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)</span><span class="sxs-lookup"><span data-stu-id="e04f2-125">For more information about ASR rule deployment in Microsoft 365 security center, see [Monitor and manage ASR rule deployment and detections](/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections).</span></span>

<span data-ttu-id="e04f2-126">**Связанные темы**</span><span class="sxs-lookup"><span data-stu-id="e04f2-126">**Related topics**</span></span>

* [<span data-ttu-id="e04f2-127">Убедитесь, что ваши устройства настроены правильно</span><span class="sxs-lookup"><span data-stu-id="e04f2-127">Ensure your devices are configured properly</span></span>](configure-machines.md)
* [<span data-ttu-id="e04f2-128">Запись устройств в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e04f2-128">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
* [<span data-ttu-id="e04f2-129">Отслеживание соответствия базовому стандарту безопасности Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e04f2-129">Monitor compliance to the Microsoft Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
