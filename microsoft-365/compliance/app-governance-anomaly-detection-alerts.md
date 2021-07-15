---
title: Изучение оповещений об обнаружении аномалий
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Изучите оповещения об обнаружении аномалий.
ms.openlocfilehash: 6797cdcbfd2a2d3c32768a158a5f8cd0fc579d56
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420474"
---
# <a name="investigate-anomaly-detection-alerts"></a><span data-ttu-id="d067d-103">Изучение оповещений об обнаружении аномалий</span><span class="sxs-lookup"><span data-stu-id="d067d-103">Investigate anomaly detection alerts</span></span>

 <span data-ttu-id="d067d-104">Управление приложениями Майкрософт обеспечивает обнаружение угроз безопасности и оповещение о вредоносных действиях.</span><span class="sxs-lookup"><span data-stu-id="d067d-104">Microsoft app governance provides security detections and alerts for malicious activities.</span></span> <span data-ttu-id="d067d-105">Цель этого руководства — предоставить общие и практические сведения о каждом оповещении, чтобы помочь вам в задачах по исследованию и исправлению.</span><span class="sxs-lookup"><span data-stu-id="d067d-105">The purpose of this guide is to provide you with general and practical information on each alert, to help with your investigation and remediation tasks.</span></span> <span data-ttu-id="d067d-106">В этом руководстве содержатся общие сведения об условиях запуска оповещений.</span><span class="sxs-lookup"><span data-stu-id="d067d-106">Included in this guide is general information about the conditions for triggering alerts.</span></span> <span data-ttu-id="d067d-107">Так как обнаружения аномалий по своей сути не являются детерменированными, они запускаются только при отклонении поведения от нормы.</span><span class="sxs-lookup"><span data-stu-id="d067d-107">Because anomaly detections are non-deterministic by nature, they're only triggered when there's behavior that deviates from the norm.</span></span> <span data-ttu-id="d067d-108">Наконец, некоторые оповещения могут быть предварительными, поэтому регулярно проверяйте официальную документацию на наличие обновленного состояния оповещений.</span><span class="sxs-lookup"><span data-stu-id="d067d-108">Finally, some alerts may be in preview, so regularly review the official documentation for updated alert status.</span></span>

## <a name="mitre-attck"></a><span data-ttu-id="d067d-109">MITRE ATT&CK</span><span class="sxs-lookup"><span data-stu-id="d067d-109">MITRE ATT&CK</span></span>

<span data-ttu-id="d067d-110">Чтобы упростить сопоставление связей между оповещениями системы управления приложениями Майкрософт и знакомой матрицей MITRE ATT&CK, мы классифицировали оповещения по соответствующей тактике MITRE ATT&CK.</span><span class="sxs-lookup"><span data-stu-id="d067d-110">To make it easier to map the relationship between Microsoft app governance alerts and the familiar MITRE ATT&CK Matrix, we've categorized the alerts by their corresponding MITRE ATT&CK tactic.</span></span> <span data-ttu-id="d067d-111">Этот дополнительный справочник упрощает понимание метода обнаружения предполагаемых атак, который может использоваться при инициировании оповещения системы безопасности и управления приложениями (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="d067d-111">This additional reference makes it easier to understand the suspected attacks technique potentially in use when Microsoft Application Security and Governance alert is triggered.</span></span>

<span data-ttu-id="d067d-112">В этом руководстве содержится информация об исследовании и устранении оповещений системы управления приложениями Майкрософт в следующих категориях.</span><span class="sxs-lookup"><span data-stu-id="d067d-112">This guide provides information about investigating and remediating Microsoft app governance alerts in the following categories.</span></span>

- <span data-ttu-id="d067d-113">Исходный доступ</span><span class="sxs-lookup"><span data-stu-id="d067d-113">Initial Access</span></span>
- <span data-ttu-id="d067d-114">Выполнение</span><span class="sxs-lookup"><span data-stu-id="d067d-114">Execution</span></span>
- <span data-ttu-id="d067d-115">Сохранение</span><span class="sxs-lookup"><span data-stu-id="d067d-115">Persistence</span></span>
- <span data-ttu-id="d067d-116">Повышение привилегий</span><span class="sxs-lookup"><span data-stu-id="d067d-116">Privilege Escalation</span></span>
- <span data-ttu-id="d067d-117">Обход мер защиты</span><span class="sxs-lookup"><span data-stu-id="d067d-117">Defense Evasion</span></span>
- <span data-ttu-id="d067d-118">Доступ к учетным данным</span><span class="sxs-lookup"><span data-stu-id="d067d-118">Credential Access</span></span>
- <span data-ttu-id="d067d-119">Сбор</span><span class="sxs-lookup"><span data-stu-id="d067d-119">Collection</span></span>
- <span data-ttu-id="d067d-120">Кража данных</span><span class="sxs-lookup"><span data-stu-id="d067d-120">Exfiltration</span></span>
- <span data-ttu-id="d067d-121">Влияние</span><span class="sxs-lookup"><span data-stu-id="d067d-121">Impact</span></span>

## <a name="security-alert-classifications"></a><span data-ttu-id="d067d-122">Классификации оповещений системы безопасности</span><span class="sxs-lookup"><span data-stu-id="d067d-122">Security alert classifications</span></span>

<span data-ttu-id="d067d-123">После надлежащего исследования все оповещения системы управления приложениями Майкрософт можно классифицировать с помощью одного из следующих типов действий.</span><span class="sxs-lookup"><span data-stu-id="d067d-123">Following proper investigation, all Microsoft app governance alerts can be classified as one of the following activity types:</span></span>

- <span data-ttu-id="d067d-124">Истинноположительный результат (TP): оповещение о подтвержденной вредоносной активности.</span><span class="sxs-lookup"><span data-stu-id="d067d-124">True positive (TP): An alert on a confirmed malicious activity.</span></span>
- <span data-ttu-id="d067d-125">Неопасный истинноположительный результат (B-TP): оповещение о подозрительных, но не вредоносных действиях, например о тесте на проникновение или о другом разрешенном подозрительном действии.</span><span class="sxs-lookup"><span data-stu-id="d067d-125">Benign true positive (B-TP): An alert on suspicious but not malicious activity, such as a penetration test or other authorized suspicious action.</span></span>
- <span data-ttu-id="d067d-126">Ложное срабатывание (FP): оповещение о невредоносных действиях.</span><span class="sxs-lookup"><span data-stu-id="d067d-126">False positive (FP): An alert on a non-malicious activity.</span></span>

## <a name="general-investigation-steps"></a><span data-ttu-id="d067d-127">Общие шаги исследования</span><span class="sxs-lookup"><span data-stu-id="d067d-127">General investigation steps</span></span>

<span data-ttu-id="d067d-128">Используйте следующие общие рекомендации при исследовании любого типа оповещений, чтобы получить более четкое представление о потенциальной угрозе перед применением рекомендуемого действия.</span><span class="sxs-lookup"><span data-stu-id="d067d-128">Use the following general guidelines when investigating any type of alert to gain a clearer understanding of the potential threat before applying the recommended action.</span></span>

- <span data-ttu-id="d067d-129">Проверьте уровень серьезности приложения и сравните его с остальными приложениями в клиенте.</span><span class="sxs-lookup"><span data-stu-id="d067d-129">Review the App severity level and compare with the rest of the app in your tenant.</span></span> <span data-ttu-id="d067d-130">Эта проверка поможет определить, какие приложения в вашем клиенте представляют более высокий риск.</span><span class="sxs-lookup"><span data-stu-id="d067d-130">This review will help you identify which Apps in your tenant pose the greater risk.</span></span>
- <span data-ttu-id="d067d-131">Если определен TP, проверьте все действия приложения, чтобы получить представление о влиянии.</span><span class="sxs-lookup"><span data-stu-id="d067d-131">If you identify a TP, review all the App activities to gain an understanding of the impact.</span></span> <span data-ttu-id="d067d-132">Например, проверьте следующие сведения приложения.</span><span class="sxs-lookup"><span data-stu-id="d067d-132">For example, review the following App information:</span></span>

  - <span data-ttu-id="d067d-133">Области, к которым предоставлен доступ</span><span class="sxs-lookup"><span data-stu-id="d067d-133">Scopes granted access</span></span>
  - <span data-ttu-id="d067d-134">Необычное поведение</span><span class="sxs-lookup"><span data-stu-id="d067d-134">Unusual behavior</span></span>  
  - <span data-ttu-id="d067d-135">IP-адрес и расположение</span><span class="sxs-lookup"><span data-stu-id="d067d-135">IP address and location</span></span>

## <a name="initial-access-alerts"></a><span data-ttu-id="d067d-136">Оповещения об исходном доступе</span><span class="sxs-lookup"><span data-stu-id="d067d-136">Initial access alerts</span></span>

<span data-ttu-id="d067d-137">В этом разделе описываются оповещения, указывающие на то, что вредоносное приложение может пытаться сохранить свой плацдарм в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d067d-137">This section describes alerts indicating that a malicious app may be attempting to maintain their foothold in your organization.</span></span>  

### <a name="encoded-app-name-with-suspicious-consent-scopes"></a><span data-ttu-id="d067d-138">Закодированное имя приложения с подозрительными областями согласия</span><span class="sxs-lookup"><span data-stu-id="d067d-138">Encoded app name with suspicious consent scopes</span></span>

<span data-ttu-id="d067d-139">**Серьезность:** средний уровень</span><span class="sxs-lookup"><span data-stu-id="d067d-139">**Severity:** Medium</span></span>

<span data-ttu-id="d067d-140">**Описание**. Это обнаружение идентифицирует приложения OAuth с символами, такими как Юникод или закодированные символы, запросившие подозрительные области согласия, и что доступ к почтовым папкам пользователей был получен посредством API Graph.</span><span class="sxs-lookup"><span data-stu-id="d067d-140">**Description**: This detection identifies OAuth apps with characters, such as Unicode or Encoded characters, requested for suspicious consent scopes and that accessed users mail folders through the Graph API.</span></span> <span data-ttu-id="d067d-141">Это оповещение может указывать на попытку замаскировать вредоносное приложения как известное и доверенное приложение, чтобы злоумышленники могли ввести пользователей в заблуждение и получить их согласие на вредоносное приложение.</span><span class="sxs-lookup"><span data-stu-id="d067d-141">This alert can indicate an attempt to camouflage a malicious app as a known and trusted app so that adversaries can mislead the users into consenting to the malicious app.</span></span>

<span data-ttu-id="d067d-142">**TP или FP?**</span><span class="sxs-lookup"><span data-stu-id="d067d-142">**TP or FP?**</span></span>

- <span data-ttu-id="d067d-143">**TP**: если вы можете подтвердить, что приложение OAuth содержит закодированное отображаемое имя с подозрительными областями и предоставлено из неизвестного источника, будет указан истинноположительный результат.</span><span class="sxs-lookup"><span data-stu-id="d067d-143">**TP**: If you can confirm that the OAuth app has Encoded the display name with suspicious scopes delivered from unknown source, then a true positive is indicated.</span></span>  

  <span data-ttu-id="d067d-144">**Рекомендуемое действие**. Проверьте уровень разрешения, запрашиваемого этим приложением, и пользователей, которые предоставили доступ.</span><span class="sxs-lookup"><span data-stu-id="d067d-144">**Recommended action**: Review the level of permission requested by this app and which users granted access.</span></span> <span data-ttu-id="d067d-145">На основе исследования вы можете запретить доступ к этому приложению.</span><span class="sxs-lookup"><span data-stu-id="d067d-145">Based on your investigation you can choose to ban access to this app.</span></span>

  <span data-ttu-id="d067d-146">Чтобы запретить доступ к приложению, на странице приложений OAuth в строке, отображающей приложение для запрещения, щелкните значок блокировки.</span><span class="sxs-lookup"><span data-stu-id="d067d-146">To ban access to the app, on the OAuth apps page, on the row in which the app you want to ban appears, select the ban icon.</span></span> <span data-ttu-id="d067d-147">Вы можете выбрать, нужно ли сообщать пользователям о том, что приложение, которое они установили и авторизовали, было заблокировано.</span><span class="sxs-lookup"><span data-stu-id="d067d-147">You can choose whether you want to tell users the app they installed and authorized has been banned.</span></span> <span data-ttu-id="d067d-148">Уведомление сообщает пользователям, что приложение будет отключено и у них не будет доступа к подключенному приложению.</span><span class="sxs-lookup"><span data-stu-id="d067d-148">The notification lets users know the app will be disabled and they will not have access to the connected app.</span></span> <span data-ttu-id="d067d-149">Если вы не хотите сообщать об этом, снимите флажок "Сообщить пользователям, которые предоставили доступ к этому запрещенному приложению" в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="d067d-149">If you do not want them to know, unselect Notify users who granted access to this banned app in the dialog.</span></span> <span data-ttu-id="d067d-150">Рекомендуется сообщать пользователям о запрете их приложений.</span><span class="sxs-lookup"><span data-stu-id="d067d-150">We recommend that you let the app users know their app is about to be banned from use.</span></span>

- <span data-ttu-id="d067d-151">**FP**: если вы подтверждаете, что приложение содержит закодированное имя, но предназначено для обоснованного бизнес-использования в организации.</span><span class="sxs-lookup"><span data-stu-id="d067d-151">**FP**: If you are to confirm that the app has an encoded name but has a legitimate business use in the organization.</span></span>

  <span data-ttu-id="d067d-152">**Рекомендуемое действие**. Закройте оповещение.</span><span class="sxs-lookup"><span data-stu-id="d067d-152">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="d067d-153">Знакомство с областью бреши в системе безопасности</span><span class="sxs-lookup"><span data-stu-id="d067d-153">Understand the scope of the breach</span></span>

<span data-ttu-id="d067d-154">Следуйте инструкциям учебника по [изучению рискованных приложений OAuth](/cloud-app-security/investigate-risky-oauth).</span><span class="sxs-lookup"><span data-stu-id="d067d-154">Follow the tutorial on how to [investigate risky OAuth apps](/cloud-app-security/investigate-risky-oauth).</span></span>

### <a name="oauth-app-with-read-scopes-have-suspicious-reply-url"></a><span data-ttu-id="d067d-155">Приложение OAuth с областями чтения содержит подозрительный URL-адрес ответа</span><span class="sxs-lookup"><span data-stu-id="d067d-155">OAuth App with read Scopes have suspicious Reply URL</span></span>

<span data-ttu-id="d067d-156">**Серьезность:** средний уровень</span><span class="sxs-lookup"><span data-stu-id="d067d-156">**Severity**: Medium</span></span>

<span data-ttu-id="d067d-157">**Описание**. Это обнаружение идентифицирует, что приложение OAuth с областями только для чтения, например User.Read, People.Read, Contacts.Read, Mail.Read, Contacts.Read.Shared, перенаправляет на подозрительный URL-адрес ответа с помощью API Graph.</span><span class="sxs-lookup"><span data-stu-id="d067d-157">**Description**: This detection identifies an OAuth app with only Read scopes such as User.Read, People.Read, Contacts.Read, Mail.Read, Contacts.Read.Shared redirects to suspicious Reply URL through Graph API.</span></span> <span data-ttu-id="d067d-158">Это действие пытается указать, что вредоносное приложение с меньшими привилегиями (например, с областями чтения) может эксплуатироваться для проведения рекогносцировки учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="d067d-158">This activity attempts to indicate that malicious app with less privilege permission (such as Read scopes) could be exploited to conduct users account reconnaissance.</span></span>

<span data-ttu-id="d067d-159">**TP или FP?**</span><span class="sxs-lookup"><span data-stu-id="d067d-159">**TP or FP?**</span></span>

- <span data-ttu-id="d067d-160">**TP**: если вы можете подтвердить, что приложение OAuth с областью чтения доставлено из неизвестного источника и перенаправляет на подозрительный URL-адрес, будет указан истинноположительный результат.</span><span class="sxs-lookup"><span data-stu-id="d067d-160">**TP**: If you’re able to confirm that the OAuth app with read scope is delivered from an unknown source, and redirects to a suspicious URL, then a true positive is indicated.</span></span>

  <span data-ttu-id="d067d-161">**Рекомендуемое действие**. Проверьте URL-адрес ответа и области, запрашиваемые приложением.</span><span class="sxs-lookup"><span data-stu-id="d067d-161">**Recommended action**: Review the Reply URL and scopes requested by the app.</span></span> <span data-ttu-id="d067d-162">На основе исследования вы можете запретить доступ к этому приложению.</span><span class="sxs-lookup"><span data-stu-id="d067d-162">Based on your investigation you can choose to ban access to this app.</span></span> <span data-ttu-id="d067d-163">Проверьте уровень разрешения, запрашиваемого этим приложением, и пользователей, которые предоставили доступ.</span><span class="sxs-lookup"><span data-stu-id="d067d-163">Review the level of permission requested by this app and which users have granted access.</span></span>

  <span data-ttu-id="d067d-164">Чтобы запретить доступ к приложению, на странице приложений OAuth в строке, отображающей приложение для запрещения, щелкните значок блокировки.</span><span class="sxs-lookup"><span data-stu-id="d067d-164">To ban access to the app, on the OAuth apps page, on the row in which the app you want to ban appears, select the ban icon.</span></span> <span data-ttu-id="d067d-165">Вы можете выбрать, нужно ли сообщать пользователям о том, что приложение, которое они установили и авторизовали, было заблокировано.</span><span class="sxs-lookup"><span data-stu-id="d067d-165">You can choose whether you want to tell users the app they installed and authorized has been banned.</span></span> <span data-ttu-id="d067d-166">Уведомление сообщает пользователям, что приложение будет отключено и у них не будет доступа к подключенному приложению.</span><span class="sxs-lookup"><span data-stu-id="d067d-166">The notification lets users know the app will be disabled and they will not have access to the connected app.</span></span> <span data-ttu-id="d067d-167">Если вы не хотите сообщать об этом, снимите флажок "Сообщить пользователям, которые предоставили доступ к этому запрещенному приложению" в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="d067d-167">If you do not want them to know, unselect Notify users who granted access to this banned app in the dialog.</span></span> <span data-ttu-id="d067d-168">Рекомендуется сообщать пользователям о запрете их приложений.</span><span class="sxs-lookup"><span data-stu-id="d067d-168">We recommend that you let the app users know their app is about to be banned from use.</span></span>

- <span data-ttu-id="d067d-169">**B-TP**: если после исследования вы можете подтвердить, что приложение предназначено для обоснованного бизнес-использования в организации.</span><span class="sxs-lookup"><span data-stu-id="d067d-169">**B-TP**: If after investigation, you can confirm that the app has a legitimate business use in the organization.</span></span>

  <span data-ttu-id="d067d-170">**Рекомендуемое действие**. Закройте оповещение.</span><span class="sxs-lookup"><span data-stu-id="d067d-170">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="d067d-171">Знакомство с областью бреши в системе безопасности</span><span class="sxs-lookup"><span data-stu-id="d067d-171">Understand the scope of the breach</span></span> 

1. <span data-ttu-id="d067d-172">Проверьте все действия, выполненные приложением.</span><span class="sxs-lookup"><span data-stu-id="d067d-172">Review all activities done by the app.</span></span>
1. <span data-ttu-id="d067d-173">Если вы полагаете, что приложение является подозрительным, рекомендуется исследовать его имя и URL-адрес ответа в разных магазинах приложений.</span><span class="sxs-lookup"><span data-stu-id="d067d-173">If you suspect that an app is suspicious, we recommend that you investigate the app’s name and Reply URL in different app stores.</span></span> <span data-ttu-id="d067d-174">При проверке магазинов приложений уделите внимание следующим типам приложений.</span><span class="sxs-lookup"><span data-stu-id="d067d-174">When checking app stores, focus on the following types of apps:</span></span>
   - <span data-ttu-id="d067d-175">Приложения, созданные недавно.</span><span class="sxs-lookup"><span data-stu-id="d067d-175">Apps that have been created recently.</span></span>
   - <span data-ttu-id="d067d-176">Приложения с подозрительным URL-адресом ответа</span><span class="sxs-lookup"><span data-stu-id="d067d-176">Apps with a suspicious Reply URL</span></span>
   - <span data-ttu-id="d067d-177">Приложения, которые не обновлялись в последнее время.</span><span class="sxs-lookup"><span data-stu-id="d067d-177">Apps that haven't been recently updated.</span></span> <span data-ttu-id="d067d-178">Отсутствие обновлений может означать, что приложение больше не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="d067d-178">Lack of updates might indicate the app is no longer supported.</span></span>
1. <span data-ttu-id="d067d-179">Если вы все еще полагаете, что приложение является подозрительным, вы можете исследовать имя приложения, имя издателя и URL-адрес ответа в Интернете</span><span class="sxs-lookup"><span data-stu-id="d067d-179">If you still suspect that an app is suspicious, you can research the app name, publisher name, and reply URL online</span></span>  

## <a name="persistence-alerts"></a><span data-ttu-id="d067d-180">Оповещения о сохраняемости</span><span class="sxs-lookup"><span data-stu-id="d067d-180">Persistence alerts</span></span>

<span data-ttu-id="d067d-181">В этом разделе описываются оповещения, указывающие на то, что злоумышленник может пытаться сохранить свой плацдарм в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d067d-181">This section describes alerts indicating that a malicious actor may be attempting to maintain their foothold in your organization.</span></span>

### <a name="app-with-suspicious-oauth-scope-creates-inbox-rule"></a><span data-ttu-id="d067d-182">Приложение с подозрительной областью OAuth создает правило для папки "Входящие"</span><span class="sxs-lookup"><span data-stu-id="d067d-182">App with Suspicious OAuth scope creates Inbox Rule</span></span>  

<span data-ttu-id="d067d-183">**Серьезность:** средний уровень</span><span class="sxs-lookup"><span data-stu-id="d067d-183">**Severity**: Medium</span></span>

<span data-ttu-id="d067d-184">**ИД MITRE**: T1137.005, T1114</span><span class="sxs-lookup"><span data-stu-id="d067d-184">**MITRE ID’s**: T1137.005, T1114</span></span>  

<span data-ttu-id="d067d-185">Это обнаружение определяет приложение OAuth, которое предоставило согласие на подозрительные области, создает подозрительное правило для папки "Входящие", а затем обращается к почтовым папкам и сообщениям пользователей посредством API Graph.</span><span class="sxs-lookup"><span data-stu-id="d067d-185">This detection identifies an OAuth App that consented to suspicious scopes, creates a suspicious inbox rule, and then accessed users mail folders and messages through the Graph API.</span></span> <span data-ttu-id="d067d-186">Правила для папки "Входящие", например перенаправление всех или определенных писем в другую учетную запись электронной почты, а также вызовы Graph для доступа к письмам и их отправки в другую учетную запись электронной почты, могут быть попыткой извлечь сведения из вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d067d-186">Inbox rules, such as forwarding all or specific emails to another email account, and Graph calls to access emails and send to another email account, may be an attempt to exfiltrate information from your organization.</span></span>  

<span data-ttu-id="d067d-187">**TP или FP?**</span><span class="sxs-lookup"><span data-stu-id="d067d-187">**TP or FP?**</span></span>

- <span data-ttu-id="d067d-188">**TP**: если вы можете подтвердить, что правило для папки "Входящие" было создано сторонним приложением OAuth с подозрительными областями, предоставленным из неизвестного источника, будет указан истинноположительный результат.</span><span class="sxs-lookup"><span data-stu-id="d067d-188">**TP**: If you can confirm that inbox rule was created by an OAuth third-party app with suspicious scopes delivered from an unknown source, then a true positive is indicated.</span></span>

  <span data-ttu-id="d067d-189">**Рекомендуемое действие**. Отключите и удалите приложение, сбросьте пароль и удалите правило для папки "Входящие".</span><span class="sxs-lookup"><span data-stu-id="d067d-189">**Recommended action**:  Disable and remove the app, reset the password, and remove the inbox rule.</span></span>

  <span data-ttu-id="d067d-190">Следуйте инструкциям из учебника по сбросу пароля с помощью Azure Active Directory и из учебника по удалению правила для папки "Входящие".</span><span class="sxs-lookup"><span data-stu-id="d067d-190">Follow the tutorial on how to Reset a password using Azure Active Directory and follow the tutorial on how to remove the inbox rule.</span></span>

- <span data-ttu-id="d067d-191">**FP**: если вы можете подтвердить, что приложение создало правило для папки "Входящие" в новой или личной внешней учетной записи электронной почты по обоснованным причинам.</span><span class="sxs-lookup"><span data-stu-id="d067d-191">**FP**: If you can confirm that app created an inbox rule to a new or personal external email account for legitimate reasons.</span></span>

  <span data-ttu-id="d067d-192">**Рекомендуемое действие**. Закройте оповещение.</span><span class="sxs-lookup"><span data-stu-id="d067d-192">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="d067d-193">Знакомство с областью бреши в системе безопасности</span><span class="sxs-lookup"><span data-stu-id="d067d-193">Understand the scope of the breach</span></span>

1. <span data-ttu-id="d067d-194">Проверьте все действия, выполненные приложением.</span><span class="sxs-lookup"><span data-stu-id="d067d-194">Review all activities done by the app.</span></span>
1. <span data-ttu-id="d067d-195">Проверьте области разрешений, предоставленные приложением.</span><span class="sxs-lookup"><span data-stu-id="d067d-195">Review the scopes granted by the app.</span></span>
1. <span data-ttu-id="d067d-196">Проверьте действие и условие правила для папки "Входящие", созданные приложением.</span><span class="sxs-lookup"><span data-stu-id="d067d-196">Review the inbox rule action and condition created by the app.</span></span>

## <a name="collection-alerts"></a><span data-ttu-id="d067d-197">Оповещения о сборе</span><span class="sxs-lookup"><span data-stu-id="d067d-197">Collection alerts</span></span>

<span data-ttu-id="d067d-198">В этом разделе описываются оповещения, указывающие на то, что злоумышленник может пытаться собирать интересующие его данные в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d067d-198">This section describes alerts indicating that a malicious actor may be attempting to gather data of interest to their goal from your organization.</span></span>

### <a name="app-made-anomalous-graph-calls-to-read-e-mail"></a><span data-ttu-id="d067d-199">Приложение выполняло аномальные вызовы Graph для чтения электронной почты</span><span class="sxs-lookup"><span data-stu-id="d067d-199">App made anomalous Graph calls to read e-mail</span></span>

<span data-ttu-id="d067d-200">**Серьезность:** средний уровень</span><span class="sxs-lookup"><span data-stu-id="d067d-200">**Severity**: Medium</span></span>

<span data-ttu-id="d067d-201">**MITRE ID**: T1114</span><span class="sxs-lookup"><span data-stu-id="d067d-201">**MITRE ID**: T1114</span></span>

<span data-ttu-id="d067d-202">Это обнаружение определяет случаи, когда бизнес-приложение OAuth получает доступ к необычному и большому объему почтовых папок и сообщений пользователя с помощью API Graph, что может указывать на попытку нарушения безопасности вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d067d-202">This detection identifies when Line of Business (LOB) OAuth App accesses an unusual and high volume of user's mail folders and messages through the Graph API, which can indicate an attempted breach of your organization.</span></span>

<span data-ttu-id="d067d-203">**TP или FP?**</span><span class="sxs-lookup"><span data-stu-id="d067d-203">**TP or FP?**</span></span>

- <span data-ttu-id="d067d-204">**TP**: если вы можете подтвердить, что необычные действия Graph были выполнены бизнес-приложением OAuth, будет указан истинноположительный результат.</span><span class="sxs-lookup"><span data-stu-id="d067d-204">**TP**: If you can confirm that the unusual graph activity was performed by the Line of Business (LOB) OAuth App, then a true positive is indicated.</span></span>

  <span data-ttu-id="d067d-205">**Рекомендуемые действия**. Временно отключите приложение и сбросьте пароль, а затем повторно включите приложение.</span><span class="sxs-lookup"><span data-stu-id="d067d-205">**Recommend actions**: Temporarily disable the app and reset the password and then re-enable the app.</span></span>

  <span data-ttu-id="d067d-206">Следуйте инструкциям из учебника по сбросу пароля с помощью Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d067d-206">Follow the tutorial on how to Reset a password using Azure Active Directory.</span></span>

- <span data-ttu-id="d067d-207">**FP**: если вы можете подтвердить, что приложение предназначено для выполнения необычно большого объема вызовов Graph.</span><span class="sxs-lookup"><span data-stu-id="d067d-207">**FP**: If you can confirm that the app is intended to do unusually high volume of graph calls.</span></span>

  <span data-ttu-id="d067d-208">**Рекомендуемое действие**. Закройте оповещение.</span><span class="sxs-lookup"><span data-stu-id="d067d-208">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="d067d-209">Знакомство с областью бреши в системе безопасности</span><span class="sxs-lookup"><span data-stu-id="d067d-209">Understand the scope of the breach</span></span>

1. <span data-ttu-id="d067d-210">Проверьте журнал действий на наличие событий, выполненных этим приложением, чтобы лучше понять другие действия Graph для чтения писем и попытки сбора конфиденциальной информации из писем пользователей.</span><span class="sxs-lookup"><span data-stu-id="d067d-210">Review the activity log for events performed by this app to gain a better understanding of other Graph activities to read emails and attempt to collect users sensitive email information.</span></span>
1. <span data-ttu-id="d067d-211">Отслеживайте неожиданное добавление учетных данных в приложение.</span><span class="sxs-lookup"><span data-stu-id="d067d-211">Monitor for unexpected credential being added to the app.</span></span>
