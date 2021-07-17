---
title: Включить среду оценки для Microsoft Defender для Office 365 в производственной среде, активировать оценку, активацию
description: Действия по активации оценки Microsoft Defender для Office365 с помощью пробных лицензий, обработки записей MX, & аудита принятых доменов и входящие подключения.
keywords: Microsoft 365 Defender пробной версии попробуйте Microsoft 365 Defender, оцените Microsoft 365 Defender, Microsoft 365 Defender лаборатории оценки, пилот Microsoft 365 Defender, кибербезопасность, расширенные постоянные угрозы, безопасность предприятия, устройства, устройства, удостоверения, пользователей, данные, приложения, инциденты, автоматическое расследование и исправление, продвинутая охота
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: c0736b93c314c3086f8a52477622c6bcfa4096a0
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458771"
---
# <a name="enable-the-evaluation-environment"></a><span data-ttu-id="c958a-104">Включить среду оценки</span><span class="sxs-lookup"><span data-stu-id="c958a-104">Enable the evaluation environment</span></span>

<span data-ttu-id="c958a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c958a-105">**Applies to:**</span></span>
- <span data-ttu-id="c958a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c958a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c958a-107">Эта статья — [шаг 2 из 3](eval-defender-office-365-overview.md) в процессе настройки среды оценки для Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="c958a-107">This article is [Step 2 of 3](eval-defender-office-365-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Office 365.</span></span> <span data-ttu-id="c958a-108">Дополнительные сведения об этом процессе см. в статье [обзор.](eval-defender-office-365-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c958a-108">For more information about this process, see the [overview article](eval-defender-office-365-overview.md).</span></span>

<span data-ttu-id="c958a-109">Используйте следующие действия, чтобы включить оценку для Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="c958a-109">Use the following steps to enable the evaluation for Microsoft Defender for Office 365.</span></span>


![Действия, чтобы включить Microsoft Defender для Office 365 в среде оценки Microsoft Defender](../../media/defender/m365-defender-office-eval-enable-steps.png)

- [<span data-ttu-id="c958a-111">Шаг 1. Активация пробных лицензий</span><span class="sxs-lookup"><span data-stu-id="c958a-111">Step 1: Activate trial licenses</span></span>](#step-1-activate-trial-licenses)
- [<span data-ttu-id="c958a-112">Шаг 2. Аудит и проверка общедоступных записей MX</span><span class="sxs-lookup"><span data-stu-id="c958a-112">Step 2: Audit and verify the public MX record</span></span>](#step-2-audit-and-verify-the-public-mx-record)
- [<span data-ttu-id="c958a-113">Шаг 3. Аудит принятых доменов</span><span class="sxs-lookup"><span data-stu-id="c958a-113">Step 3: Audit accepted domains</span></span>](#step-3-audit-accepted-domains)
- [<span data-ttu-id="c958a-114">Шаг 4. Входящие соединители аудита</span><span class="sxs-lookup"><span data-stu-id="c958a-114">Step 4: Audit inbound connectors</span></span>](#step-4-audit-inbound-connectors)
- [<span data-ttu-id="c958a-115">Шаг 5. Активация оценки</span><span class="sxs-lookup"><span data-stu-id="c958a-115">Step 5: Activate the evaluation</span></span>](#step-5-activate-the-evaluation)

## <a name="step-1-activate-trial-licenses"></a><span data-ttu-id="c958a-116">Шаг 1. Активация пробных лицензий</span><span class="sxs-lookup"><span data-stu-id="c958a-116">Step 1: Activate trial licenses</span></span>

<span data-ttu-id="c958a-117">Войдите в существующий microsoft Defender для Office 365 среды или портала администрирования клиентов.</span><span class="sxs-lookup"><span data-stu-id="c958a-117">Log on to your existing Microsoft Defender for Office 365 environment or tenant administration portal.</span></span>

1. <span data-ttu-id="c958a-118">Перейдите на портал администрирования.</span><span class="sxs-lookup"><span data-stu-id="c958a-118">Navigate to the administration portal.</span></span>
2. <span data-ttu-id="c958a-119">Выберите службы покупки при быстром запуске.</span><span class="sxs-lookup"><span data-stu-id="c958a-119">Select Purchase Services from the quick launch.</span></span>

:::image type="content" source="../../media/mdo-eval/1_m365-purchase-services.png" alt-text="Щелкните Службы покупки на области навигации Office 365.":::

3.  <span data-ttu-id="c958a-121">Прокрутите вниз в Add-On (или найдите "Defender"), чтобы найти microsoft Defender для Office 365 планов.</span><span class="sxs-lookup"><span data-stu-id="c958a-121">Scroll down to the Add-On section (or search for "Defender") to locate the Microsoft Defender for Office 365 plans.</span></span>
4.  <span data-ttu-id="c958a-122">Щелкните Подробные сведения далее по плану, который необходимо оценить.</span><span class="sxs-lookup"><span data-stu-id="c958a-122">Click Details next the plan you want to evaluate.</span></span>

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="Нажмите кнопку &quot;Сведения&quot; далее.":::

5. <span data-ttu-id="c958a-124">Щелкните *бесплатную пробную ссылку Начните.*</span><span class="sxs-lookup"><span data-stu-id="c958a-124">Click the *Start free trial* link.</span></span>

:::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="Нажмите кнопку Начните бесплатную пробную пробную ссылку *hyperlink* на этой панели.":::

6. <span data-ttu-id="c958a-126">Подтвердите запрос и нажмите *кнопку Try now.*</span><span class="sxs-lookup"><span data-stu-id="c958a-126">Confirm your request and click the *Try now* button.</span></span>

:::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="Теперь нажмите кнопку Try now *button*.":::

## <a name="step-2-audit-and-verify-the-public-mx-record"></a><span data-ttu-id="c958a-128">Шаг 2. Аудит и проверка общедоступных записей MX</span><span class="sxs-lookup"><span data-stu-id="c958a-128">Step 2: Audit and verify the public MX record</span></span>

<span data-ttu-id="c958a-129">Чтобы эффективно оценить microsoft Defender для Office 365, важно, чтобы входящие внешние сообщения электронной почты ретранслируются через экземпляр Exchange Online Protection (EOP), связанный с клиентом.</span><span class="sxs-lookup"><span data-stu-id="c958a-129">To effectively evaluate Microsoft Defender for Office 365, it's important that inbound external email be relayed through the Exchange Online Protection (EOP) instance associated with your tenant.</span></span>

1. <span data-ttu-id="c958a-130">Войдите на портал администратора M365, Параметры и выберите домены.</span><span class="sxs-lookup"><span data-stu-id="c958a-130">Log on to the M365 Admin Portal, expand Settings, and select Domains.</span></span>
2. <span data-ttu-id="c958a-131">Выберите проверенный домен электронной почты и нажмите кнопку Управление DNS.</span><span class="sxs-lookup"><span data-stu-id="c958a-131">Select your verified email domain and click Manage DNS.</span></span>
3. <span data-ttu-id="c958a-132">Обратите внимание на запись MX, созданную и назначенную вашему клиенту EOP.</span><span class="sxs-lookup"><span data-stu-id="c958a-132">Make note of the MX record generated and assigned to your EOP tenant.</span></span>
4. <span data-ttu-id="c958a-133">Обратитесь к внешней (публичной) DNS-зоне и проверьте основную запись MX, связанную с доменом электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c958a-133">Access your external (public) DNS zone and check the primary MX record associated with your email domain.</span></span>
    - <span data-ttu-id="c958a-134">Если ваша публичная запись MX в настоящее время соответствует назначенного *EOP-адресу (например, tenant-com.mail.protection.outlook.com),* никаких дополнительных изменений маршрутов не требуется.</span><span class="sxs-lookup"><span data-stu-id="c958a-134">*If your public MX record currently matches the assigned EOP address (e.g. tenant-com.mail.protection.outlook.com) then no further routing changes should be required*.</span></span>
    - <span data-ttu-id="c958a-135">Если ваша публичная запись MX в настоящее время решается на сторонний или локальной шлюз SMTP, могут потребоваться дополнительные конфигурации маршрутов.</span><span class="sxs-lookup"><span data-stu-id="c958a-135">If your public MX record currently resolves to a third-party or on-premises SMTP gateway then additional routing configurations may be required.</span></span>
    - <span data-ttu-id="c958a-136">Если ваша публичная запись MX в настоящее время решается на локальное Exchange, вы все равно можете оказаться в гибридной модели, в которой некоторые почтовые ящики получателей еще не были перенесены в EXO.</span><span class="sxs-lookup"><span data-stu-id="c958a-136">If your public MX record currently resolves to on-premises Exchange then you may still be in a hybrid model where some recipient mailbox have not yet been migrated to EXO.</span></span>

## <a name="step-3-audit-accepted-domains"></a><span data-ttu-id="c958a-137">Шаг 3. Аудит принятых доменов</span><span class="sxs-lookup"><span data-stu-id="c958a-137">Step 3: Audit accepted domains</span></span>

1. <span data-ttu-id="c958a-138">Войдите на портал администратора Exchange Online, выберите почтовые Flow и нажмите кнопку "Принятые домены".</span><span class="sxs-lookup"><span data-stu-id="c958a-138">Log on the Exchange Online Admin Portal, select Mail Flow, and then click Accepted Domains.</span></span>
2. <span data-ttu-id="c958a-139">Из списка принятых доменов, которые были добавлены и проверены в клиенте, обратите внимание на тип домена **для** основного домена электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c958a-139">From the list of accepted domains that have been added and verified in your tenant, make note of the **domain type** for your primary email domain.</span></span>
    - <span data-ttu-id="c958a-140">Если тип домена забит до ***"Авторитетный",*** предполагается, что все почтовые ящики получателей для вашей организации в настоящее время находятся в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c958a-140">If the domain type is set to ***Authoritative*** then it is assumed all recipient mailboxes for your organization currently reside in Exchange Online.</span></span>
    - <span data-ttu-id="c958a-141">Если тип домена настроен на ***внутреннюю*** ретрансляцию, вы все равно можете находиться в гибридной модели, в которой некоторые почтовые ящики получателей по-прежнему находятся на месте.</span><span class="sxs-lookup"><span data-stu-id="c958a-141">If the domain type is set to ***Internal Relay*** then you may still be in a hybrid model where some recipient mailboxes still reside on-premises.</span></span>

## <a name="step-4-audit-inbound-connectors"></a><span data-ttu-id="c958a-142">Шаг 4. Входящие соединители аудита</span><span class="sxs-lookup"><span data-stu-id="c958a-142">Step 4: Audit inbound connectors</span></span>

1. <span data-ttu-id="c958a-143">Войдите на портал администратора Exchange Online, выберите почтовые Flow и нажмите соединители.</span><span class="sxs-lookup"><span data-stu-id="c958a-143">Log on the Exchange Online Admin Portal, select Mail Flow, and then click Connectors.</span></span>
2. <span data-ttu-id="c958a-144">Из списка настроенных соединитений обратите внимание на любые записи, которые находятся в партнерской организации и могут соотноситься с сторонним шлюзом SMTP. </span><span class="sxs-lookup"><span data-stu-id="c958a-144">From the list of configured connectors, make note of any entries which are from **Partner Organization** and may correlate to a third-party SMTP gateway.</span></span>
3. <span data-ttu-id="c958a-145">Из списка настроенных соединитений обратите внимание на  все записи, помеченные на сервере электронной почты вашей организации, которые могут указывать на то, что вы все еще находитесь в гибридном сценарии.</span><span class="sxs-lookup"><span data-stu-id="c958a-145">From the list of configured connectors, make note of any entries labeled **From your organization's email server** which may indicate that you are still in hybrid scenario.</span></span>

## <a name="step-5-activate-the-evaluation"></a><span data-ttu-id="c958a-146">Шаг 5. Активация оценки</span><span class="sxs-lookup"><span data-stu-id="c958a-146">Step 5: Activate the evaluation</span></span>

<span data-ttu-id="c958a-147">Используйте инструкции, чтобы активировать microsoft Defender для Office 365 оценки с Microsoft 365 Defender портала.</span><span class="sxs-lookup"><span data-stu-id="c958a-147">Use the instructions here to activate your Microsoft Defender for Office 365 evaluation from the Microsoft 365 Defender portal.</span></span>

1. <span data-ttu-id="c958a-148">Войдите в клиент с учетной записью, которая имеет доступ к Microsoft 365 Defender порталу.</span><span class="sxs-lookup"><span data-stu-id="c958a-148">Log on to your tenant with an account that has access to the Microsoft 365 Defender portal.</span></span>
2. <span data-ttu-id="c958a-149">Выберите, хотите ли вы сделать портал **Microsoft 365 Defender** интерфейсом по умолчанию для Microsoft Defender для Office 365 администрирования (рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="c958a-149">Choose whether you want to make the **Microsoft 365 Defender portal** your default interface for Microsoft Defender for Office 365 administration (recommended).</span></span>

:::image type="content" source="../../media/mdo-eval/1_mdo-eval-activate-eval.png" alt-text="Нажмите кнопку Включайте параметры, чтобы использовать централизованный и улучшенный Microsoft 365 Defender для администрирования.":::

3. <span data-ttu-id="c958a-151">В меню навигации выберите **Правила & в** статье Email & *collaboration*.</span><span class="sxs-lookup"><span data-stu-id="c958a-151">From the navigation menu, select **Policies & Rules** under *Email & Collaboration*.</span></span>

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-activate-eval.png" alt-text="Вот изображение меню & электронной почты, указывав на правила политики &. Щелкните это!":::

4. <span data-ttu-id="c958a-153">На панели *мониторинга & правил нажмите* **кнопку Политики угрозы**.</span><span class="sxs-lookup"><span data-stu-id="c958a-153">On the *Policy & Rules* dashboard, click **Threat Policies**.</span></span>

:::image type="content" source="../../media/mdo-eval/3_mdo-eval-activate-eval.png" alt-text="Изображение панели мониторинга & правил политики и стрелки, указывав на политики угрозы. Нажмите кнопку далее!":::

5. <span data-ttu-id="c958a-155">Прокрутите вниз *до дополнительных политик* и выберите защитник **оценки для Office 365** плитки.</span><span class="sxs-lookup"><span data-stu-id="c958a-155">Scroll down to *Additional Policies* and select the **Evaluate Defender for Office 365** tile.</span></span>

:::image type="content" source="../../media/mdo-eval/4_mdo-eval-activate-eval.png" alt-text="Плитка Eval Defender для Office 365, которая говорит, что это 30-дневная пробная версия по всем векторам совместной & электронной почты. Щелкните.":::

6. <span data-ttu-id="c958a-157">Теперь выберите, будут ли внешние маршруты электронной почты Exchange Online напрямую или на сторонний шлюз или службу, и нажмите кнопку Далее.</span><span class="sxs-lookup"><span data-stu-id="c958a-157">Now choose whether external email routes to Exchange Online directly, or to a third-party gateway or service, and click Next.</span></span>

:::image type="content" source="../../media/mdo-eval/5_mdo-eval-activate-eval.png" alt-text="Defender for Office 365 оценит отправку почты в Exchange Online почтовые ящики. Укажете сведения о маршруте рассылки почты в настоящее время, включая имя исходящие соединители, которые маршрутизовываю вашу почту. Если вы используете Exchange Online Protection (EOP), у вас не будет соединителю. Выберите один из них, в который я использую поставщика 3rd-party или локального поставщика, или я использую только EOP.":::

7. <span data-ttu-id="c958a-159">Если используется сторонний шлюз, выберите имя поставщика из отката вместе с входящий соединителей, связанных с этим решением.</span><span class="sxs-lookup"><span data-stu-id="c958a-159">If you use a third-party gateway, select the vendor name from the drop-down along with the inbound connector associated with that solution.</span></span> <span data-ttu-id="c958a-160">После перечисления ответов нажмите кнопку Далее.</span><span class="sxs-lookup"><span data-stu-id="c958a-160">When you've listed your answers, click Next.</span></span>

:::image type="content" source="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png" alt-text="В этом диалоговом окте вы выбираете службу поставщика 3rd-party, используемую организацией, или выберите *Other*. В следующем диалоговом окне выберите входящий соединитель. Затем нажмите кнопку Далее.":::

8. <span data-ttu-id="c958a-162">Просмотрите параметры и нажмите **кнопку Создать оценку.**</span><span class="sxs-lookup"><span data-stu-id="c958a-162">Review your settings and click the **Create Evaluation** button.</span></span>

|  |  |
|---------|---------|
|  :::image type="content" source="../../media/mdo-eval/7-mdo-eval-activate-review.png" alt-text="В этой области есть отсев для просмотра параметров. Он также имеет щелкаемую ссылку на изменение типа маршрутивки, если это необходимо. Когда вы будете готовы, нажмите кнопку большая голубая кнопка Создание оценки.":::   |   :::image type="content" source="../../media/mdo-eval/8-mdo-eval-activate-complete.png" alt-text="И теперь настройка завершена. На синей кнопке на этой странице написано &quot;Перейти к оценке&quot;.":::      |

## <a name="next-steps"></a><span data-ttu-id="c958a-165">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="c958a-165">Next steps</span></span>

<span data-ttu-id="c958a-166">Шаг 3 из 3. Настройка пилотного проекта для Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="c958a-166">Step 3 of 3: Set up the pilot for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="c958a-167">Вернись к обзору [для Оценки Microsoft Defender для Office 365](eval-defender-office-365-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c958a-167">Return to the overview for [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span></span>

<span data-ttu-id="c958a-168">Возвращайся к обзору [для оценки и пилотных Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c958a-168">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>