---
title: Начало работы с локальным сканером для защиты от потери данных Microsoft 365 (предварительная версия)
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
description: Настройка локального сканера для защиты от потери данных Microsoft 365
ms.openlocfilehash: e0d7bc9eeae7d701c14aaaeeed7a01cab33829ea
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/03/2021
ms.locfileid: "50417401"
---
# <a name="get-started-with-the-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="75364-103">Начало работы с локальным сканером для защиты от потери данных (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="75364-103">Get started with the data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="75364-104">В этой статье описаны предварительные условия и конфигурация для локального сканера защиты от потери данных Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="75364-104">This article walks you through the prerequisites and configuration for the Microsoft 365 data loss prevention on-premises scanner.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="75364-105">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="75364-105">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="75364-106">Лицензирование SKU/подписки</span><span class="sxs-lookup"><span data-stu-id="75364-106">SKU/subscriptions licensing</span></span>

<span data-ttu-id="75364-107">Прежде чем приступить к использованию локального сканера защиты от потери данных, подтвердите [подписку Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) и любые дополнительные надстройки.</span><span class="sxs-lookup"><span data-stu-id="75364-107">Before you get started with DLP on-premises scanner, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="75364-108">Чтобы участвовать в предварительной оценке, учетной записи администратора, настраивающей правила защиты от потери данных, должна быть назначена одна из следующих лицензий.</span><span class="sxs-lookup"><span data-stu-id="75364-108">To participate in the preview the admin account that sets up the DLP rules must be assigned one of the following licenses:</span></span>

- <span data-ttu-id="75364-109">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="75364-109">Microsoft 365 E5</span></span>
- <span data-ttu-id="75364-110">Соответствие требованиям Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="75364-110">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="75364-111">Защита информации и управление данными в Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="75364-111">Microsoft 365 E5 Information Protection & Governance</span></span> 


<span data-ttu-id="75364-112">Полные сведения о лицензировании см. в статье [Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)</span><span class="sxs-lookup"><span data-stu-id="75364-112">For full licensing details see: [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)</span></span>

### <a name="permissions"></a><span data-ttu-id="75364-113">Разрешения</span><span class="sxs-lookup"><span data-stu-id="75364-113">Permissions</span></span>


<span data-ttu-id="75364-114">Данные из локального сканера службы защиты от потери данных доступны в [обозревателе действий](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="75364-114">Data from DLP on-premises scanner can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="75364-115">Существует четыре роли, которые предоставляют разрешения обозревателю действий, учетная запись, которую вы используете для доступа к данным, должна входить в любую из этих ролей:</span><span class="sxs-lookup"><span data-stu-id="75364-115">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="75364-116">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="75364-116">Global administrator</span></span>
- <span data-ttu-id="75364-117">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="75364-117">Compliance administrator</span></span>
- <span data-ttu-id="75364-118">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="75364-118">Security administrator</span></span>
- <span data-ttu-id="75364-119">Администратор данных о соответствии требованиям</span><span class="sxs-lookup"><span data-stu-id="75364-119">Compliance data administrator</span></span>

### <a name="dlp-on-premises-scanner-prerequisites"></a><span data-ttu-id="75364-120">Необходимые условия для локального сканера защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="75364-120">DLP on-premises scanner prerequisites</span></span>

- <span data-ttu-id="75364-121">Сканер Azure Information Protection (AIP) обеспечивает соответствие политике защиты от потери данных и применение политики.</span><span class="sxs-lookup"><span data-stu-id="75364-121">The Azure Information Protection (AIP) scanner implements DLP policy matching and policy enforcement.</span></span> <span data-ttu-id="75364-122">Сканер устанавливается в составе клиента AIP, поэтому установка должна соответствовать всем предварительным условиям для AIP, клиента AIP и сканера унифицированных меток AIP.</span><span class="sxs-lookup"><span data-stu-id="75364-122">The scanner is installed as part of the AIP client so your installation must meet all the prerequisites  for AIP, the AIP client, and the AIP unified labeling scanner.</span></span>
- <span data-ttu-id="75364-123">Разверните клиент и сканер AIP.</span><span class="sxs-lookup"><span data-stu-id="75364-123">Deploy the AIP  client and scanner.</span></span> <span data-ttu-id="75364-124">Дополнительные сведения: [Установка клиента унифицированных меток AIP](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app) и [Настройка и установка сканера унифицированных меток Azure Information Protection](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install).</span><span class="sxs-lookup"><span data-stu-id="75364-124">For more information [Install the AIP unified labeling client](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app) and [], see [Configuring and installing the Azure Information Protection unified labeling scanner](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install).</span></span>
- <span data-ttu-id="75364-125">В клиенте должна быть опубликована хотя бы одна метка и политика, даже если все правила обнаружения основаны только на типах конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="75364-125">There must be at least one label and policy published in the tenant, even if all your detection rules are based on sensitive information types only.</span></span>

## <a name="deploy-the-dlp-on-premises-scanner"></a><span data-ttu-id="75364-126">Развертывание локального сканера защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="75364-126">Deploy the DLP on-premises scanner</span></span>

1. <span data-ttu-id="75364-127">Выполните процедуры из статьи [Установка клиента унифицированных меток AIP](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app).</span><span class="sxs-lookup"><span data-stu-id="75364-127">Follow the procedures in [Install the AIP unified labeling client](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app).</span></span> 
2. <span data-ttu-id="75364-128">Выполните процедуры из статьи [Настройка и установка сканера унифицированных меток Azure Information Protection](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install), чтобы завершить установку сканера.</span><span class="sxs-lookup"><span data-stu-id="75364-128">Follow the procedures in [Configuring and installing the Azure Information Protection unified labeling scanner](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install) to complete the scanner installation.</span></span>
    1. <span data-ttu-id="75364-129">Настройка заданий сетевого обнаружения является необязательным шагом.</span><span class="sxs-lookup"><span data-stu-id="75364-129">Network discovery jobs configuration is an optional step.</span></span> <span data-ttu-id="75364-130">Вы можете пропустить его и определить конкретные репозитории для сканирования в своем задании сканирования содержимого.</span><span class="sxs-lookup"><span data-stu-id="75364-130">You can skip it and define specific repositories to be scanned in your content scan job.</span></span>
    2. <span data-ttu-id="75364-131">Создайте задание сканирования содержимого и укажите репозитории, хранящие файлы, которые должны оцениваться подсистемой защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="75364-131">You must create content scan job and specify the repositories that host files that need to be evaluated by the DLP engine.</span></span>
    3. <span data-ttu-id="75364-132">Включите правила защиты от потери данных в созданном задании сканирования содержимого и установите для параметра **Применить** значение **Выкл**, если вы не хотите перейти непосредственно к этапу применения защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="75364-132">Enable DLP rules in the created Content scan job, and set the **Enforce** option to **Off**, unless you want to proceed directly to the DLP enforcement stage.</span></span>
3. <span data-ttu-id="75364-133">Назначьте задание сканирования содержимого нужному кластеру.</span><span class="sxs-lookup"><span data-stu-id="75364-133">Verify that you content scan job is assigned to the right cluster.</span></span> <span data-ttu-id="75364-134">Если вы еще не создали задание сканирования содержимого, создайте и назначьте его кластеру, содержащему узлы сканера, в которых запускается общедоступная предварительная версия.</span><span class="sxs-lookup"><span data-stu-id="75364-134">If you still did not create a content scan job create a new one and assign it to the cluster that contains the scanner nodes that run the public preview version.</span></span>

4. <span data-ttu-id="75364-135">Подключитесь к [расширению Azure Information Protection на портале Azure](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) и добавьте свои репозитории в задание сканирования содержимого, которое будет выполнять сканирование.</span><span class="sxs-lookup"><span data-stu-id="75364-135">Connect to the [Azure Information Protection extension in Azure portal](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) and add your repositories to the content scan job that will perform the scan.</span></span>

5. <span data-ttu-id="75364-136">Чтобы запустить сканирование, выполните одно из перечисленных ниже действий. </span><span class="sxs-lookup"><span data-stu-id="75364-136">Do one of the following to run your scan:</span></span>
    1. <span data-ttu-id="75364-137">Настройте расписание сканера.</span><span class="sxs-lookup"><span data-stu-id="75364-137">set the scanner schedule</span></span>
    1. <span data-ttu-id="75364-138">Используйте ручной параметр **Сканировать сейчас** на портале</span><span class="sxs-lookup"><span data-stu-id="75364-138">use the manual **Scan Now** option in the portal</span></span>
    1. <span data-ttu-id="75364-139">Или запустите командлет **Start-AIPScan** в PowerShell</span><span class="sxs-lookup"><span data-stu-id="75364-139">or run **Start-AIPScan** PowerShell cmdlet</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="75364-140">Помните, что сканер по умолчанию выполняет разностную проверку репозитория, а файлы, которые уже проверены в предыдущем цикле сканирования, будут пропущены, если файл не был изменен или вы не запустили полное повторное сканирование.</span><span class="sxs-lookup"><span data-stu-id="75364-140">Remember that the scanner runs a delta scan of the repository by default and the files that were already scanned in the previous scan cycle will be skipped unless the file was changed or you initiated a full rescan.</span></span> <span data-ttu-id="75364-141">Полное повторное сканирование можно запустить с помощью параметра **Повторить сканирование всех файлов** в пользовательском интерфейсе или путем запуска командлета **Start-AIPScan-Reset**.</span><span class="sxs-lookup"><span data-stu-id="75364-141">Full rescan can be initiated by using **Rescan all files** option in the UI or by running **Start-AIPScan-Reset**.</span></span>

6.  <span data-ttu-id="75364-142">Откройте страницу [Защита от потери данных](https://compliance.microsoft.com/datalossprevention?viewid=policies) в Центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="75364-142">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) in the Microsoft 365 Compliance center.</span></span>

7. <span data-ttu-id="75364-143">Выберите **Создать политику** и создайте тестовую политику защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="75364-143">Choose **Create policy** and create a test DLP policy.</span></span> <span data-ttu-id="75364-144">Справку по созданию политики см. в статье [Создание политики защиты от потери данных на основе шаблона](create-a-dlp-policy-from-a-template.md).</span><span class="sxs-lookup"><span data-stu-id="75364-144">See [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md) if you need help creating a policy.</span></span> <span data-ttu-id="75364-145">Запускайте ее в тестовом режиме, пока не ознакомитесь с этой функцией достаточно подробно.</span><span class="sxs-lookup"><span data-stu-id="75364-145">Be sure to run it in test until you are comfortable with this feature.</span></span> <span data-ttu-id="75364-146">Используйте следующие параметры для политики.</span><span class="sxs-lookup"><span data-stu-id="75364-146">Use these parameters for your policy:</span></span>
    1. <span data-ttu-id="75364-147">При необходимости ограничьте область применения правила локального сканера защиты от потери данных определенными расположениями.</span><span class="sxs-lookup"><span data-stu-id="75364-147">Scope the DLP on-premises scanner rule to specific locations if needed.</span></span> <span data-ttu-id="75364-148">Если для **расположений** выбран параметр **Все**, для всех файлов, проверяемых сканером, будет применяться правило защиты от потери данных и его соответствия.</span><span class="sxs-lookup"><span data-stu-id="75364-148">If you scope **locations** to **All**, all files scanned by the scanner will be subject to the DLP rule matching and enforcement.</span></span>
    1. <span data-ttu-id="75364-149">При указании расположений вы можете использовать список исключений или включений.</span><span class="sxs-lookup"><span data-stu-id="75364-149">When specifying the locations, you can use either exclusion or inclusion list.</span></span> <span data-ttu-id="75364-150">В общедоступной предварительной версии нельзя настроить оба этих списка.</span><span class="sxs-lookup"><span data-stu-id="75364-150">During public preview you cannot set both of them.</span></span> <span data-ttu-id="75364-151">Вы можете указать, что правило относится только к путям, соответствующим одному из шаблонов списка включений, или ко всем файлам, кроме тех, которые соответствуют шаблону из списка включений.</span><span class="sxs-lookup"><span data-stu-id="75364-151">You can either define that the rule is relevant only to paths matching one of the patterns listed in inclusion list or, all files, except the files matching the pattern listed in inclusion list.</span></span> <span data-ttu-id="75364-152">Локальные пути не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="75364-152">No local paths are supported.</span></span> <span data-ttu-id="75364-153">Вот несколько примеров допустимых путей:</span><span class="sxs-lookup"><span data-stu-id="75364-153">Here are some examples of valid paths:</span></span>
      - <span data-ttu-id="75364-154">\\\server\share</span><span class="sxs-lookup"><span data-stu-id="75364-154">\\\server\share</span></span>
      - <span data-ttu-id="75364-155">\\\server\share\folder1\subfolderabc</span><span class="sxs-lookup"><span data-stu-id="75364-155">\\\server\share\folder1\subfolderabc</span></span>
      - <span data-ttu-id="75364-156">\*\\folder1</span><span class="sxs-lookup"><span data-stu-id="75364-156">\*\\folder1</span></span>
      - <span data-ttu-id="75364-157">\*secret\*.docx</span><span class="sxs-lookup"><span data-stu-id="75364-157">\*secret\*.docx</span></span>
      - <span data-ttu-id="75364-158">\*secret\*.\*</span><span class="sxs-lookup"><span data-stu-id="75364-158">\*secret\*.\*</span></span>
      - <span data-ttu-id="75364-159"> https:// sp2010.local/sites/HR</span><span class="sxs-lookup"><span data-stu-id="75364-159">https:// sp2010.local/sites/HR</span></span>
      - <span data-ttu-id="75364-160"> https://\*/HR</span><span class="sxs-lookup"><span data-stu-id="75364-160">https://\*/HR</span></span> 
    3. <span data-ttu-id="75364-161">Вот несколько примеров недопустимых значений:</span><span class="sxs-lookup"><span data-stu-id="75364-161">Here are some examples of unacceptable values use:</span></span>
      - \*
      - <span data-ttu-id="75364-162">\*\\a</span><span class="sxs-lookup"><span data-stu-id="75364-162">\*\\a</span></span>
      - <span data-ttu-id="75364-163">Aaa</span><span class="sxs-lookup"><span data-stu-id="75364-163">Aaa</span></span>
      - <span data-ttu-id="75364-164">c:</span><span class="sxs-lookup"><span data-stu-id="75364-164">c:</span></span>\
      - <span data-ttu-id="75364-165">C:\test</span><span class="sxs-lookup"><span data-stu-id="75364-165">C:\test</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75364-166">Список исключений имеет приоритет над списком включений.</span><span class="sxs-lookup"><span data-stu-id="75364-166">The exclusion list takes precedence over the inclusions list.</span></span>

### <a name="viewing-dlp-on-premises-scanner-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="75364-167">Просмотр оповещений локального сканера защиты от потери данных на панели управления оповещениями защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="75364-167">Viewing DLP on-premises scanner alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="75364-168">Откройте страницу [Защита от потери данных](https://compliance.microsoft.com/datalossprevention?viewid=policies) в Центре соответствия требованиям Microsoft 365 и выберите **Оповещения**.</span><span class="sxs-lookup"><span data-stu-id="75364-168">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) in the Microsoft 365 Compliance center and select **Alerts**.</span></span>

2. <span data-ttu-id="75364-169">Используйте процедуры из статьи [Настройка и просмотр оповещений для политик защиты от потери данных](dlp-configure-view-alerts-policies.md), чтобы просмотреть оповещения для своих политик защиты от потери данных в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="75364-169">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>

### <a name="viewing-dlp-on-premises-scanner-in-activity-explorer-and-audit-log"></a><span data-ttu-id="75364-170">Просмотр локального сканера защиты от потери данных в обозревателе действий и журнале аудита</span><span class="sxs-lookup"><span data-stu-id="75364-170">Viewing DLP on-premises scanner in activity explorer and audit log</span></span>

> [!NOTE]
> <span data-ttu-id="75364-171">Для локального сканера требуется включить аудит.</span><span class="sxs-lookup"><span data-stu-id="75364-171">The on-premises scanner requires that auditing be enabled.</span></span> <span data-ttu-id="75364-172">В Microsoft 365 аудит включен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="75364-172">In Microsoft 365 auditing is enabled by default.</span></span>

1. <span data-ttu-id="75364-173">Откройте страницу [Классификация данных](https://compliance.microsoft.com/dataclassification?viewid=overview) для своего домена в Центре соответствия требованиям Microsoft 365 и выберите обозреватель действий.</span><span class="sxs-lookup"><span data-stu-id="75364-173">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and select Activity explorer.</span></span>

2. <span data-ttu-id="75364-174">Выполните действия, описанные в статье [Начало работы с обозревателем действий](data-classification-activity-explorer.md), чтобы получить доступ к данным и отфильтровать их в расположениях локального сканера.</span><span class="sxs-lookup"><span data-stu-id="75364-174">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your on-premises scanner locations.</span></span>

3. <span data-ttu-id="75364-175">Откройте [Журнал аудита](https://security.microsoft.com/auditlogsearch) в Центре соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="75364-175">Open the [Audit log in the Compliance center](https://security.microsoft.com/auditlogsearch).</span></span> <span data-ttu-id="75364-176">В общедоступной предварительной версии соответствия правилу защиты от потери данных доступны в пользовательском интерфейсе журнала аудита или с помощью командлета [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) в PowerShell</span><span class="sxs-lookup"><span data-stu-id="75364-176">During the public preview the DLP rule matches are available in Audit log UI or accessible by [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell</span></span> 


## <a name="next-steps"></a><span data-ttu-id="75364-177">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="75364-177">Next steps</span></span>
<span data-ttu-id="75364-178">После развертывания тестовой политики для расположений локального сканера защиты от потери данных вы можете просмотреть данные об активности в обозревателе действий и перейти к этапу создания политик защиты от потери данных для конфиденциальных элементов.</span><span class="sxs-lookup"><span data-stu-id="75364-178">Now that you have deployed a test policy for DLP on-premises locations and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="75364-179">Использование локальной защиты от потери данных (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="75364-179">Using DLP on-premises (preview)</span></span>](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a><span data-ttu-id="75364-180">См. также</span><span class="sxs-lookup"><span data-stu-id="75364-180">See also</span></span>

- [<span data-ttu-id="75364-181">Сведения о локальном сканере защиты от потери данных (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="75364-181">Learn about DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="75364-182">Использование локального сканера защиты от потери данных (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="75364-182">Use DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-use.md)
- [<span data-ttu-id="75364-183">Общие сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="75364-183">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="75364-184">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="75364-184">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="75364-185">Начало работы с обозревателем действий</span><span class="sxs-lookup"><span data-stu-id="75364-185">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="75364-186">Подписка на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="75364-186">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
