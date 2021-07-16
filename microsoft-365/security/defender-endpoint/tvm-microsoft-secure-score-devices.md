---
title: Оценка безопасности (Майкрософт) для устройств
description: В вашей оценке для устройств показано общее состояние конфигурации устройств в приложениях, операционной системе, сети, учетных записях и средствах управления безопасностью.
keywords: Microsoft Secure Score for Devices, Microsoft Defender for Endpoint Microsoft Secure Score for Devices, secure score, configuration score, контроль угроз и уязвимостей, security controls, improvement opportunities, security configuration score over time, security posture, baseline
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 13307d3205818d41e7b2219b4e3a4ed6e9f2d5bb
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454790"
---
# <a name="microsoft-secure-score-for-devices"></a><span data-ttu-id="4b49b-104">Оценка безопасности (Майкрософт) для устройств</span><span class="sxs-lookup"><span data-stu-id="4b49b-104">Microsoft Secure Score for Devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4b49b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="4b49b-105">**Applies to:**</span></span>

- [<span data-ttu-id="4b49b-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="4b49b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="4b49b-107">Контроль угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="4b49b-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="4b49b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4b49b-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4b49b-109">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="4b49b-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4b49b-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="4b49b-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


>[!NOTE]
> <span data-ttu-id="4b49b-111">Оценка конфигурации теперь является частью контроль угроз и уязвимостей microsoft Secure Score для устройств.</span><span class="sxs-lookup"><span data-stu-id="4b49b-111">Configuration score is now part of threat and vulnerability management as Microsoft Secure Score for Devices.</span></span>

<span data-ttu-id="4b49b-112">Ваша оценка для устройств отображается на контроль угроз и уязвимостей панели [мониторинга](tvm-dashboard-insights.md) Microsoft 365 Defender портала.</span><span class="sxs-lookup"><span data-stu-id="4b49b-112">Your score for devices is visible in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) of the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="4b49b-113">Более высокий показатель microsoft Secure Score для устройств означает, что конечные точки более устойчивы к атакам угроз кибербезопасности.</span><span class="sxs-lookup"><span data-stu-id="4b49b-113">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> <span data-ttu-id="4b49b-114">Он отражает состояние конфигурации коллективной безопасности устройств в следующих категориях:</span><span class="sxs-lookup"><span data-stu-id="4b49b-114">It reflects the collective security configuration state of your devices across the following categories:</span></span>

- <span data-ttu-id="4b49b-115">Приложение</span><span class="sxs-lookup"><span data-stu-id="4b49b-115">Application</span></span>
- <span data-ttu-id="4b49b-116">Операционная система</span><span class="sxs-lookup"><span data-stu-id="4b49b-116">Operating system</span></span>
- <span data-ttu-id="4b49b-117">Сеть</span><span class="sxs-lookup"><span data-stu-id="4b49b-117">Network</span></span>
- <span data-ttu-id="4b49b-118">Учетные записи</span><span class="sxs-lookup"><span data-stu-id="4b49b-118">Accounts</span></span>
- <span data-ttu-id="4b49b-119">Средства контроля безопасности</span><span class="sxs-lookup"><span data-stu-id="4b49b-119">Security controls</span></span>

<span data-ttu-id="4b49b-120">Выберите категорию, чтобы перейти на страницу [**Рекомендации безопасности**](tvm-security-recommendation.md) и просмотреть соответствующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="4b49b-120">Select a category to go to the [**Security recommendations**](tvm-security-recommendation.md) page and view the relevant recommendations.</span></span>

## <a name="turn-on-the-microsoft-secure-score-connector"></a><span data-ttu-id="4b49b-121">Включив соединители microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="4b49b-121">Turn on the Microsoft Secure Score connector</span></span>

<span data-ttu-id="4b49b-122">Forward Microsoft Defender for Endpoint signals, giving Microsoft Secure Score visibility into the device security posture.</span><span class="sxs-lookup"><span data-stu-id="4b49b-122">Forward Microsoft Defender for Endpoint signals, giving Microsoft Secure Score visibility into the device security posture.</span></span> <span data-ttu-id="4b49b-123">Переададные данные хранятся и обрабатываются в том же месте, что и данные Microsoft Secure Score.</span><span class="sxs-lookup"><span data-stu-id="4b49b-123">Forwarded data is stored and processed in the same location as your Microsoft Secure Score data.</span></span>

<span data-ttu-id="4b49b-124">На отражение изменений на панели мониторинга может потребоваться до нескольких часов.</span><span class="sxs-lookup"><span data-stu-id="4b49b-124">Changes might take up to a few hours to reflect in the dashboard.</span></span>

1. <span data-ttu-id="4b49b-125">В области навигации перейдите **к Параметры**  >  **Конечные точки**  >  **Общие**  >  **расширенные функции**</span><span class="sxs-lookup"><span data-stu-id="4b49b-125">In the navigation pane, go to **Settings** > **Endpoints** > **General** > **Advanced features**</span></span> 

2. <span data-ttu-id="4b49b-126">Прокрутите **вниз до Microsoft Secure Score** и перейдите к параметру **On**.</span><span class="sxs-lookup"><span data-stu-id="4b49b-126">Scroll down to **Microsoft Secure Score** and toggle the setting to **On**.</span></span>

3. <span data-ttu-id="4b49b-127">Выберите **Параметры Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4b49b-127">Select **Save preferences**.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="4b49b-128">Принципы работы</span><span class="sxs-lookup"><span data-stu-id="4b49b-128">How it works</span></span>

>[!NOTE]
> <span data-ttu-id="4b49b-129">Microsoft Secure Score для устройств в настоящее время поддерживает конфигурации, заданная с помощью групповой политики.</span><span class="sxs-lookup"><span data-stu-id="4b49b-129">Microsoft Secure Score for Devices currently supports configurations set via Group Policy.</span></span> <span data-ttu-id="4b49b-130">Из-за текущей частичной поддержки Intune конфигурации, которые могли быть настроены через Intune, могут быть неправильно настроены.</span><span class="sxs-lookup"><span data-stu-id="4b49b-130">Due to the current partial Intune support, configurations which might have been set through Intune might show up as misconfigured.</span></span> <span data-ttu-id="4b49b-131">Обратитесь к ИТ-администратору, чтобы проверить фактическое состояние конфигурации в случае, если ваша организация использует Intune для безопасного управления конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="4b49b-131">Contact your IT Administrator to verify the actual configuration status in case your organization is using Intune for secure configuration management.</span></span>

<span data-ttu-id="4b49b-132">Данные в карточке Microsoft Secure Score for Devices — это продукт тщательного и непрерывного процесса обнаружения уязвимости.</span><span class="sxs-lookup"><span data-stu-id="4b49b-132">The data in the Microsoft Secure Score for Devices card is the product of meticulous and ongoing vulnerability discovery process.</span></span> <span data-ttu-id="4b49b-133">Она агрегируется с оценками обнаружения конфигурации, которые непрерывно:</span><span class="sxs-lookup"><span data-stu-id="4b49b-133">It is aggregated with configuration discovery assessments that continuously:</span></span>

- <span data-ttu-id="4b49b-134">Сравнение собранных конфигураций с собранными тестами, чтобы обнаружить неправильное расположение активов</span><span class="sxs-lookup"><span data-stu-id="4b49b-134">Compare collected configurations to the collected benchmarks to discover misconfigured assets</span></span>
- <span data-ttu-id="4b49b-135">Конфигурации карт для уязвимостей, которые можно устранять или частично устранять (снижение риска)</span><span class="sxs-lookup"><span data-stu-id="4b49b-135">Map configurations to vulnerabilities that can be remediated or partially remediated (risk reduction)</span></span>
- <span data-ttu-id="4b49b-136">Сбор и обслуживание контрольных показателей конфигурации (поставщики, каналы безопасности, внутренние исследовательские группы)</span><span class="sxs-lookup"><span data-stu-id="4b49b-136">Collect and maintain best practice configuration benchmarks (vendors, security feeds, internal research teams)</span></span>
- <span data-ttu-id="4b49b-137">Сбор и мониторинг изменений состояния конфигурации управления безопасностью из всех активов</span><span class="sxs-lookup"><span data-stu-id="4b49b-137">Collect and monitor changes of security control configuration state from all assets</span></span>

## <a name="improve-your-security-configuration"></a><span data-ttu-id="4b49b-138">Улучшение конфигурации безопасности</span><span class="sxs-lookup"><span data-stu-id="4b49b-138">Improve your security configuration</span></span>

<span data-ttu-id="4b49b-139">Улучшение конфигурации безопасности путем устранения проблем из списка рекомендаций по безопасности.</span><span class="sxs-lookup"><span data-stu-id="4b49b-139">Improve your security configuration by remediating issues from the security recommendations list.</span></span> <span data-ttu-id="4b49b-140">По мере этого ваша оценка microsoft Secure Для устройств улучшается, а ваша организация становится более устойчивой к угрозам и уязвимостям кибербезопасности.</span><span class="sxs-lookup"><span data-stu-id="4b49b-140">As you do so, your Microsoft Secure Score for Devices improves and your organization becomes more resilient against cybersecurity threats and vulnerabilities.</span></span>

1. <span data-ttu-id="4b49b-141">Из карты Microsoft Secure Score for Devices в контроль угроз и уязвимостей панели мониторинга выберите одну из категорий.</span><span class="sxs-lookup"><span data-stu-id="4b49b-141">From the Microsoft Secure Score for Devices card in the threat and vulnerability management dashboard, select one of the categories.</span></span> <span data-ttu-id="4b49b-142">Вы увидите список рекомендаций, связанных с этой категорией.</span><span class="sxs-lookup"><span data-stu-id="4b49b-142">You'll view the list of recommendations related to that category.</span></span> <span data-ttu-id="4b49b-143">Он будет принимать вас на [**страницу рекомендации безопасности.**](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="4b49b-143">It will take you to the [**Security recommendations**](tvm-security-recommendation.md) page.</span></span> <span data-ttu-id="4b49b-144">Если вы хотите увидеть все рекомендации по безопасности, как только вы доберетсяе до страницы Рекомендации безопасности, очистить поле поиска.</span><span class="sxs-lookup"><span data-stu-id="4b49b-144">If you want to see all security recommendations, once you get to the Security recommendations page, clear the search field.</span></span>

2. <span data-ttu-id="4b49b-145">Выберите элемент в списке.</span><span class="sxs-lookup"><span data-stu-id="4b49b-145">Select an item on the list.</span></span> <span data-ttu-id="4b49b-146">Панель вылетов откроется с подробными сведениями, связанными с рекомендацией.</span><span class="sxs-lookup"><span data-stu-id="4b49b-146">The flyout panel will open with details related to the recommendation.</span></span> <span data-ttu-id="4b49b-147">Выберите **параметры исправлений.**</span><span class="sxs-lookup"><span data-stu-id="4b49b-147">Select **Remediation options**.</span></span>

   :::image type="content" alt-text="Рекомендации по контролю безопасности, связанные с безопасностью." source="images/security-controls.png":::

3. <span data-ttu-id="4b49b-149">Ознакомьтесь с описанием, чтобы понять контекст проблемы и что делать дальше.</span><span class="sxs-lookup"><span data-stu-id="4b49b-149">Read the description to understand the context of the issue and what to do next.</span></span> <span data-ttu-id="4b49b-150">Выберите дату, добавить заметки и экспортировать все данные о деятельности по исправлению в **CSV,** чтобы можно было прикрепить их к электронной почте для последующей работы.</span><span class="sxs-lookup"><span data-stu-id="4b49b-150">Select a due date, add notes, and select **Export all remediation activity data to CSV** so you can attach it to an email for follow-up.</span></span>

4. <span data-ttu-id="4b49b-151">**Отправка запроса**.</span><span class="sxs-lookup"><span data-stu-id="4b49b-151">**Submit request**.</span></span> <span data-ttu-id="4b49b-152">Вы увидите сообщение подтверждения о том, что задача по исправлению была создана.</span><span class="sxs-lookup"><span data-stu-id="4b49b-152">You'll see a confirmation message that the remediation task has been created.</span></span>

   :::image type="content" alt-text="Подтверждение создания задач по исправлению." source="images/remediation-task-created.png":::

5. <span data-ttu-id="4b49b-154">Сохраните CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="4b49b-154">Save your CSV file.</span></span>

   :::image type="content" alt-text="Сохранение csv-файла." source="images/tvm_save_csv_file.png":::

6. <span data-ttu-id="4b49b-156">Отправьте ИТ-администратору по электронной почте последующее письмо и дайте время, отведенное для распространения исправлений в системе.</span><span class="sxs-lookup"><span data-stu-id="4b49b-156">Send a follow-up email to your IT Administrator and allow the time that you've allotted for the remediation to propagate in the system.</span></span>

7. <span data-ttu-id="4b49b-157">Снова **просмотрите карту Microsoft Secure Score для устройств** на панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="4b49b-157">Review the **Microsoft Secure Score for Devices** card again on the dashboard.</span></span> <span data-ttu-id="4b49b-158">Количество рекомендаций по контролю безопасности будет уменьшаться.</span><span class="sxs-lookup"><span data-stu-id="4b49b-158">The number of security controls recommendations will decrease.</span></span> <span data-ttu-id="4b49b-159">Когда вы выберите элементы управления  **безопасностью,** чтобы вернуться на страницу рекомендации по безопасности, элемент, который вы рассмотрели, больше не будет перечислены там.</span><span class="sxs-lookup"><span data-stu-id="4b49b-159">When you select **Security controls** to go back to the **Security recommendations** page, the item that you've addressed won't be listed there anymore.</span></span> <span data-ttu-id="4b49b-160">Необходимо увеличить оценку microsoft Secure Для устройств.</span><span class="sxs-lookup"><span data-stu-id="4b49b-160">Your Microsoft Secure Score for Devices should increase.</span></span>

>[!IMPORTANT]
><span data-ttu-id="4b49b-161">Чтобы повысить уровень обнаружения уязвимости, скачайте следующие обязательные обновления безопасности и разместите их в сети:</span><span class="sxs-lookup"><span data-stu-id="4b49b-161">To boost your vulnerability assessment detection rates, download the following mandatory security updates and deploy them in your network:</span></span>
>- <span data-ttu-id="4b49b-162">Клиенты 19H1 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)</span><span class="sxs-lookup"><span data-stu-id="4b49b-162">19H1 customers | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)</span></span>
>- <span data-ttu-id="4b49b-163">Клиенты RS5 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)</span><span class="sxs-lookup"><span data-stu-id="4b49b-163">RS5 customers | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)</span></span>
>- <span data-ttu-id="4b49b-164">Клиенты RS4 | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="4b49b-164">RS4 customers | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
>- <span data-ttu-id="4b49b-165">Клиенты RS3 | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="4b49b-165">RS3 customers | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
>
><span data-ttu-id="4b49b-166">Чтобы скачать обновления безопасности:</span><span class="sxs-lookup"><span data-stu-id="4b49b-166">To download the security updates:</span></span>
>1. <span data-ttu-id="4b49b-167">Перейдите [в каталог обновлений Майкрософт](https://www.catalog.update.microsoft.com/home.aspx).</span><span class="sxs-lookup"><span data-stu-id="4b49b-167">Go to [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/home.aspx).</span></span>
>2. <span data-ttu-id="4b49b-168">Вйдите в номер КБ обновления безопасности, который необходимо скачать, а затем нажмите **кнопку Поиск**.</span><span class="sxs-lookup"><span data-stu-id="4b49b-168">Key-in the security update KB number that you need to download, then click **Search**.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="4b49b-169">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="4b49b-169">Related topics</span></span>

- [<span data-ttu-id="4b49b-170">Обзор угроз и управление уязвимостями</span><span class="sxs-lookup"><span data-stu-id="4b49b-170">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="4b49b-171">Панель мониторинга</span><span class="sxs-lookup"><span data-stu-id="4b49b-171">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="4b49b-172">Показатель уязвимости</span><span class="sxs-lookup"><span data-stu-id="4b49b-172">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="4b49b-173">Рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="4b49b-173">Security recommendations</span></span>](tvm-security-recommendation.md)
