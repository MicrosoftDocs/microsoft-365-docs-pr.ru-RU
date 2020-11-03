---
title: Симулятор атак в защитнике Майкрософт для Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как использовать симулятор для атаки для запуска имитации фишинговых атак и атак с использованием паролей в Microsoft 365, а также в защитнике Майкрософт для Office 365 с планом 2.
ms.openlocfilehash: b7d04b3c81791bfc107b48176373ffc84fc8f6c5
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846000"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="1a90a-103">Симулятор атак в защитнике Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="1a90a-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="1a90a-104">Если в вашей организации используется защитник Microsoft для Office 365 (план 2), который включает [расследования и функции реагирования](office-365-ti.md), вы можете использовать симулятор для атаки в центре безопасности & соответствия требованиям, чтобы выполнять сценарии атак в Организации.</span><span class="sxs-lookup"><span data-stu-id="1a90a-104">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="1a90a-105">Эти имитации атак могут помочь вам определить и найти уязвимых пользователей, прежде чем реальная атака повлияет на нижнюю линию.</span><span class="sxs-lookup"><span data-stu-id="1a90a-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="1a90a-106">Ознакомьтесь с этой статьей, чтобы узнать больше.</span><span class="sxs-lookup"><span data-stu-id="1a90a-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="1a90a-107">Моделирование атак и связанные с обучениеми данные хранятся вместе с другими данными клиентов для служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1a90a-107">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="1a90a-108">Дополнительные сведения см. в [статье Microsoft 365 Data Locations](/microsoft-365/enterprise/o365-data-locations).</span><span class="sxs-lookup"><span data-stu-id="1a90a-108">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1a90a-109">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="1a90a-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1a90a-110">Чтобы открыть Центр безопасности и соответствия требованиям, перейдите по ссылке <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="1a90a-110">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="1a90a-111">Симулятор атак доступен в **Threat management** \> **симуляторе атак** с управлением угрозами.</span><span class="sxs-lookup"><span data-stu-id="1a90a-111">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="1a90a-112">Перейдите прямо к симулятору атак, откройте <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="1a90a-112">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="1a90a-113">Дополнительные сведения о доступности симуляторов атак в различных подписках Microsoft 365 можно найти в [статье защитник Майкрософт для Office 365 Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="1a90a-113">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="1a90a-114">Необходимо быть участником группы ролей " **Управление организацией** " или " **администратор безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="1a90a-114">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="1a90a-115">Дополнительные сведения о группах ролей в Центре безопасности и соответствия требованиям см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="1a90a-115">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="1a90a-116">Ваша учетная запись должна быть настроена для многофакторной проверки подлинности (MFA) для создания кампаний в симуляторе атак и управления ими.</span><span class="sxs-lookup"><span data-stu-id="1a90a-116">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="1a90a-117">Инструкции приведены в разделе [Настройка многофакторной проверки подлинности](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="1a90a-117">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="1a90a-118">Фишинговые кампании будут собирать и обрабатывать события в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="1a90a-118">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="1a90a-119">Исторические данные кампании будут доступны в течение до 90 дней после запуска кампании.</span><span class="sxs-lookup"><span data-stu-id="1a90a-119">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="1a90a-120">Для симулятора атак нет соответствующих командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a90a-120">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="1a90a-121">Фишинговые кампании спеар</span><span class="sxs-lookup"><span data-stu-id="1a90a-121">Spear phishing campaigns</span></span>

<span data-ttu-id="1a90a-122">*Фишинг* — это общий термин для атак электронной почты, которые пытаются украсть конфиденциальные данные в сообщениях, которые не являются законными или надежными отправителями.</span><span class="sxs-lookup"><span data-stu-id="1a90a-122">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="1a90a-123">*Фишинг спеар* — это нацеленная атака фишинга, которая использует отсортированный и настроенный контент, специально предназначенный для целевых получателей (как правило, после реконнаиссанце от получателей).</span><span class="sxs-lookup"><span data-stu-id="1a90a-123">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="1a90a-124">В симуляторе атак доступны два различных типа спеар фишинговых кампаний:</span><span class="sxs-lookup"><span data-stu-id="1a90a-124">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="1a90a-125">**Спеар фишинга (учетные данные)** : атака пытается убедить получателей щелкнуть URL-адрес в сообщении.</span><span class="sxs-lookup"><span data-stu-id="1a90a-125">**Spear phishing (credentials harvest)** : The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="1a90a-126">Если щелкнуть ссылку, им будет предложено ввести учетные данные.</span><span class="sxs-lookup"><span data-stu-id="1a90a-126">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="1a90a-127">В этом случае они берутся из одного из следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="1a90a-127">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="1a90a-128">Страница по умолчанию с объяснением того, что это только тест, и приводятся советы по распознаванию фишинговых сообщений.</span><span class="sxs-lookup"><span data-stu-id="1a90a-128">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Сведения о том, как пользователи видят ссылку фишинга и вводят свои учетные данные](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="1a90a-130">Настраиваемая страница (URL-адрес).</span><span class="sxs-lookup"><span data-stu-id="1a90a-130">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="1a90a-131">**Спеар фишинга (вложение)** : атака пытается убедить получателей открыть DOCX-или PDF-вложение в сообщении.</span><span class="sxs-lookup"><span data-stu-id="1a90a-131">**Spear phishing (attachment)** : The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="1a90a-132">Вложение содержит то же содержимое, что и адрес фишинга по умолчанию, но первое предложение начинается с " \<Display Name\> , что вы видите это сообщение как последнее открытое сообщение электронной почты...".</span><span class="sxs-lookup"><span data-stu-id="1a90a-132">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="1a90a-133">В настоящее время спеар фишинговых кампаний в симуляторе атак не истечет.</span><span class="sxs-lookup"><span data-stu-id="1a90a-133">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="1a90a-134">Создание спеар фишинговых кампаний</span><span class="sxs-lookup"><span data-stu-id="1a90a-134">Create a spear phishing campaign</span></span>

<span data-ttu-id="1a90a-135">Важной частью любой антифишинговой кампании спеар является внешний вид сообщения электронной почты, которое отправляется получателям.</span><span class="sxs-lookup"><span data-stu-id="1a90a-135">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="1a90a-136">Чтобы создать и настроить сообщение электронной почты, вы можете использовать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="1a90a-136">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="1a90a-137">**Используйте встроенный шаблон электронной почты** : доступны два встроенных шаблона: **приз Гивеавай** и **Обновление зарплаты**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-137">**Use a built-in email template** : Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="1a90a-138">Вы можете настроить некоторые, все или ни одно из свойств электронной почты из шаблона при создании и запуске кампании.</span><span class="sxs-lookup"><span data-stu-id="1a90a-138">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="1a90a-139">**Создание шаблона электронной почты для повторного использования** : после создания и сохранения шаблона электронной почты его можно использовать повторно в будущих спеар фишинговых кампаний.</span><span class="sxs-lookup"><span data-stu-id="1a90a-139">**Create a reusable email template** : After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="1a90a-140">Вы можете настроить некоторые, все или ни одно из свойств электронной почты из шаблона при создании и запуске кампании.</span><span class="sxs-lookup"><span data-stu-id="1a90a-140">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="1a90a-141">**Создайте сообщение электронной почты в мастере** : вы можете создать сообщение электронной почты непосредственно в мастере при создании и запуске антифишинговой кампании спеар.</span><span class="sxs-lookup"><span data-stu-id="1a90a-141">**Create the email message in the wizard** : You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="1a90a-142">Шаг 1 (необязательно): Создание настраиваемого шаблона электронной почты</span><span class="sxs-lookup"><span data-stu-id="1a90a-142">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="1a90a-143">Если вы планируете использовать один из встроенных шаблонов или создать сообщение электронной почты непосредственно в мастере, вы можете пропустить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="1a90a-143">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="1a90a-144">В центре безопасности & соответствия требованиям перейдите к **Threat management** \> **симулятору атак** управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="1a90a-144">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="1a90a-145">На странице **имитация атак** : в разделах **спеар фишинг (учетные данные)** или **спеар фишинга (вложение)** нажмите **сведения об атаках**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-145">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="1a90a-146">Не имеет значения, где вы создаете шаблон.</span><span class="sxs-lookup"><span data-stu-id="1a90a-146">It doesn't matter where you create the template.</span></span> <span data-ttu-id="1a90a-147">Параметры, доступные в шаблоне, одинаковы для обоих типов фишинговых атак.</span><span class="sxs-lookup"><span data-stu-id="1a90a-147">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="1a90a-148">На открывшейся странице **сведения об атаке** в разделе **шаблоны фишинга** в области **Создание шаблонов** щелкните **новый шаблон**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-148">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="1a90a-149">Мастер **настройки шаблонов фишинга** запускается в новом всплывающем меню.</span><span class="sxs-lookup"><span data-stu-id="1a90a-149">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="1a90a-150">В разделе " **начать** " введите уникальное отображаемое имя для шаблона, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-150">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="1a90a-151">На шаге **Настройка сведений о сообщении электронной почты** настройте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="1a90a-151">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="1a90a-152">**From (имя)** : отображаемое имя, используемое для отправителя сообщения.</span><span class="sxs-lookup"><span data-stu-id="1a90a-152">**From (Name)** : The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="1a90a-153">**From (электронная почта)** : адрес электронной почты отправителя.</span><span class="sxs-lookup"><span data-stu-id="1a90a-153">**From (Email)** : The sender's email address.</span></span>

   - <span data-ttu-id="1a90a-154">**URL-адрес сервера входа с фишингом** : щелкните раскрывающийся список и выберите один из доступных URL-адресов из списка.</span><span class="sxs-lookup"><span data-stu-id="1a90a-154">**Phishing Login Server URL** : Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="1a90a-155">Это URL-адрес, по которому пользователи будут поддаваться своему щелчку.</span><span class="sxs-lookup"><span data-stu-id="1a90a-155">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="1a90a-156">Имеются следующие варианты.</span><span class="sxs-lookup"><span data-stu-id="1a90a-156">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > - <span data-ttu-id="1a90a-157">Все URL-адреса являются намеренно HTTP, а не HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1a90a-157">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="1a90a-158">Служба репутации URL-адресов может идентифицировать один или несколько из этих URL-адресов как небезопасные.</span><span class="sxs-lookup"><span data-stu-id="1a90a-158">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="1a90a-159">Прежде чем использовать URL-адрес в фишинговой кампании, проверьте доступность URL-адреса в поддерживаемых веб-браузерах.</span><span class="sxs-lookup"><span data-stu-id="1a90a-159">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="1a90a-160">**Настраиваемый URL-адрес начальной страницы** : Введите необязательную целевую страницу, на которой будут выполняться пользователи, если щелкнуть ссылку фишинга и ввести свои учетные данные.</span><span class="sxs-lookup"><span data-stu-id="1a90a-160">**Custom Landing Page URL** : Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="1a90a-161">Эта ссылка заменяет целевую страницу по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1a90a-161">This link replaces the default landing page.</span></span> <span data-ttu-id="1a90a-162">Например, если у вас есть внутреннее обучение, можно указать здесь URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="1a90a-162">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="1a90a-163">**Category** : в настоящее время этот параметр не используется (все введенные данные игнорируются).</span><span class="sxs-lookup"><span data-stu-id="1a90a-163">**Category** : Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="1a90a-164">**Тема** : поле **темы** сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1a90a-164">**Subject** : The **Subject** field of the email message.</span></span>

   <span data-ttu-id="1a90a-165">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-165">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="1a90a-166">На шаге создание **электронного** сообщения Создайте текст сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1a90a-166">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="1a90a-167">Вы можете использовать вкладку **Электронная почта** (ФОРМАТИРОВАННЫЙ HTML-редактор) или вкладку **источник** (HTML-код RAW).</span><span class="sxs-lookup"><span data-stu-id="1a90a-167">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="1a90a-168">Форматирование HTML может быть простым или сложным по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="1a90a-168">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="1a90a-169">Вы можете вставить изображения и текст, чтобы улучшить белиевабилити сообщения в почтовом клиенте получателя.</span><span class="sxs-lookup"><span data-stu-id="1a90a-169">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="1a90a-170">`${username}` Вставка имени получателя.</span><span class="sxs-lookup"><span data-stu-id="1a90a-170">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="1a90a-171">`${loginserverurl}` Вставляет значение **URL-адреса сервера фишингового входа** из предыдущего действия.</span><span class="sxs-lookup"><span data-stu-id="1a90a-171">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="1a90a-172">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-172">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="1a90a-173">На шаге **Подтверждение** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-173">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="1a90a-174">Шаг 2: создание и запуск антифишинговой кампании спеар</span><span class="sxs-lookup"><span data-stu-id="1a90a-174">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="1a90a-175">В центре безопасности & соответствия требованиям перейдите к **Threat management** \> **симулятору атак** управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="1a90a-175">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="1a90a-176">На странице **имитация атак** выберите один из следующих вариантов, в зависимости от типа кампании, которую вы хотите создать:</span><span class="sxs-lookup"><span data-stu-id="1a90a-176">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="1a90a-177">В разделе **спеар фишинг (учетные данные)** нажмите **запустить атаку** или " **сведения об атаке** ", чтобы \> **запустить атаку**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-177">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="1a90a-178">В разделе **спеар фишинг (вложение)** нажмите **запустить атаку** или " **сведения об атаке** ", чтобы \> **запустить атаку**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-178">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="1a90a-179">Мастер **настройки фишинговых атак** запускается в новом всплывающем меню.</span><span class="sxs-lookup"><span data-stu-id="1a90a-179">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="1a90a-180">На **начальном** этапе выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="1a90a-180">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="1a90a-181">В поле **имя** введите уникальное отображаемое имя для кампании.</span><span class="sxs-lookup"><span data-stu-id="1a90a-181">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="1a90a-182">Не щелкайте **шаблон использовать** , так как вы создадите сообщение электронной почты позже в мастере.</span><span class="sxs-lookup"><span data-stu-id="1a90a-182">Don't click **Use Template** , because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="1a90a-183">Щелкните **использовать шаблон** и выберите встроенный или настраиваемый шаблон электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1a90a-183">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="1a90a-184">После выбора шаблона поле **имя** автоматически заполняется на основе шаблона, но вы можете изменить его имя.</span><span class="sxs-lookup"><span data-stu-id="1a90a-184">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![Страница "начало фишинга"](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="1a90a-186">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-186">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="1a90a-187">На шаге **целевые получатели** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="1a90a-187">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="1a90a-188">Щелкните **Адресная книга** , чтобы выбрать получателей (пользователей или групп) для кампании.</span><span class="sxs-lookup"><span data-stu-id="1a90a-188">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="1a90a-189">У каждого целевого получателя должен быть почтовый ящик Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1a90a-189">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="1a90a-190">Если нажать кнопку **Фильтр** и **Применить** , не вводя условия поиска, все получатели возвращаются и добавляются в кампанию.</span><span class="sxs-lookup"><span data-stu-id="1a90a-190">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="1a90a-191">Нажмите кнопку **Импорт** и импорт **файлов** , чтобы импортировать значения с разделителями-запятыми (CSV) или файлы электронной почты с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="1a90a-191">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="1a90a-192">Каждая строка должна содержать адрес электронной почты получателя.</span><span class="sxs-lookup"><span data-stu-id="1a90a-192">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="1a90a-193">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-193">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="1a90a-194">На шаге **Настройка сведений о сообщении электронной почты** настройте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="1a90a-194">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="1a90a-195">Если вы выбрали шаблон на **начальном** этапе, большая часть этих значений уже настроена, но вы можете изменить их.</span><span class="sxs-lookup"><span data-stu-id="1a90a-195">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="1a90a-196">**From (имя)** : отображаемое имя, используемое для отправителя сообщения.</span><span class="sxs-lookup"><span data-stu-id="1a90a-196">**From (Name)** : The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="1a90a-197">**From (электронная почта)** : адрес электронной почты отправителя.</span><span class="sxs-lookup"><span data-stu-id="1a90a-197">**From (Email)** : The sender's email address.</span></span> <span data-ttu-id="1a90a-198">Вы можете ввести реальный или поддельный адрес электронной почты из почтового ящика организации или можно ввести реальный или фальшивый внешний адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1a90a-198">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="1a90a-199">Действительный адрес электронной почты отправителя в Организации будет фактически разрешаться в почтовом клиенте получателя.</span><span class="sxs-lookup"><span data-stu-id="1a90a-199">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="1a90a-200">**URL-адрес сервера входа с фишингом** : щелкните раскрывающийся список и выберите один из доступных URL-адресов из списка.</span><span class="sxs-lookup"><span data-stu-id="1a90a-200">**Phishing Login Server URL** : Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="1a90a-201">Это URL-адрес, по которому пользователи будут поддаваться своему щелчку.</span><span class="sxs-lookup"><span data-stu-id="1a90a-201">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="1a90a-202">Имеются следующие варианты.</span><span class="sxs-lookup"><span data-stu-id="1a90a-202">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > - <span data-ttu-id="1a90a-203">Все URL-адреса являются намеренно HTTP, а не HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1a90a-203">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="1a90a-204">Служба репутации URL-адресов может идентифицировать один или несколько из этих URL-адресов как небезопасные.</span><span class="sxs-lookup"><span data-stu-id="1a90a-204">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="1a90a-205">Прежде чем использовать URL-адрес в фишинговой кампании, проверьте доступность URL-адреса в поддерживаемых веб-браузерах.</span><span class="sxs-lookup"><span data-stu-id="1a90a-205">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="1a90a-206">Вам необходимо выбрать URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="1a90a-206">You are required to select a URL.</span></span> <span data-ttu-id="1a90a-207">Для кампаний с **фишингом (СПЕАР)** можно удалить ссылку из текста сообщения на следующем этапе (в противном случае сообщение будет содержать как ссылку **, так и** вложение).</span><span class="sxs-lookup"><span data-stu-id="1a90a-207">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="1a90a-208">**Тип вложения** : этот параметр доступен только для кампаний с **фишингом спеар (вложение)** .</span><span class="sxs-lookup"><span data-stu-id="1a90a-208">**Attachment Type** : This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="1a90a-209">Щелкните раскрывающийся список и выберите **. DOCX** или **. PDF** из списка.</span><span class="sxs-lookup"><span data-stu-id="1a90a-209">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="1a90a-210">**Имя вложения** : этот параметр доступен только для кампаний с **фишингом спеар (вложение)** .</span><span class="sxs-lookup"><span data-stu-id="1a90a-210">**Attachment Name** : This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="1a90a-211">Введите имя файла для DOCX-или PDF-вложения.</span><span class="sxs-lookup"><span data-stu-id="1a90a-211">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="1a90a-212">**Настраиваемый URL-адрес начальной страницы** : Введите необязательную целевую страницу, на которой будут выполняться пользователи, если щелкнуть ссылку фишинга и ввести свои учетные данные.</span><span class="sxs-lookup"><span data-stu-id="1a90a-212">**Custom Landing Page URL** : Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="1a90a-213">Эта ссылка заменяет целевую страницу по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1a90a-213">This link replaces the default landing page.</span></span> <span data-ttu-id="1a90a-214">Например, если у вас есть внутреннее обучение, можно указать здесь URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="1a90a-214">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="1a90a-215">**Тема** : поле **темы** сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1a90a-215">**Subject** : The **Subject** field of the email message.</span></span>

   <span data-ttu-id="1a90a-216">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-216">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="1a90a-217">На шаге создание **электронного** сообщения Создайте текст сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1a90a-217">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="1a90a-218">Если вы выбрали шаблон на **начальном** этапе, текст сообщения уже настроен, но его можно настроить.</span><span class="sxs-lookup"><span data-stu-id="1a90a-218">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="1a90a-219">Вы можете использовать вкладку **Электронная почта** (ФОРМАТИРОВАННЫЙ HTML-редактор) или вкладку **источник** (HTML-код RAW).</span><span class="sxs-lookup"><span data-stu-id="1a90a-219">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="1a90a-220">Форматирование HTML может быть простым или сложным по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="1a90a-220">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="1a90a-221">Вы можете вставить изображения и текст, чтобы улучшить белиевабилити сообщения в почтовом клиенте получателя.</span><span class="sxs-lookup"><span data-stu-id="1a90a-221">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="1a90a-222">`${username}` Вставка имени получателя.</span><span class="sxs-lookup"><span data-stu-id="1a90a-222">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="1a90a-223">`${loginserverurl}` Вставляет значение **URL-адреса сервера фишингового входа** .</span><span class="sxs-lookup"><span data-stu-id="1a90a-223">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="1a90a-224">Для кампаний с **фишингом спеар (вложение)** необходимо удалить ссылку из текста сообщения (в противном случае сообщение будет содержать **как ссылку, так и вложение** ), а ссылки, которые не отслеживаются в кампании вложения.</span><span class="sxs-lookup"><span data-stu-id="1a90a-224">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![Создание сообщения электронной почты](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="1a90a-226">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-226">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="1a90a-227">На шаге **Подтверждение** нажмите кнопку **Готово** , чтобы запустить кампанию.</span><span class="sxs-lookup"><span data-stu-id="1a90a-227">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="1a90a-228">Сообщение фишинга доставляется получателям.</span><span class="sxs-lookup"><span data-stu-id="1a90a-228">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="1a90a-229">Кампании по атакам паролей</span><span class="sxs-lookup"><span data-stu-id="1a90a-229">Password attack campaigns</span></span>

<span data-ttu-id="1a90a-230">*Атака* с помощью пароля пытается угадать пароли учетных записей пользователей в Организации, как правило, после того, как злоумышленник обнаружил одну или несколько действительных учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="1a90a-230">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="1a90a-231">В симуляторе атак можно проверить сложность паролей пользователей двумя различными типами кампаний по атакам паролей:</span><span class="sxs-lookup"><span data-stu-id="1a90a-231">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="1a90a-232">**Пароль принудительной силы (Словарная атака)** : при атаке *методом грубого* или *словаря* используется большой файл словаря паролей для учетной записи пользователя с тем, что один из них будет работать (многие пароли для одной учетной записи).</span><span class="sxs-lookup"><span data-stu-id="1a90a-232">**Brute force password (dictionary attack)** : A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="1a90a-233">Неправильные блокировки паролей помогают предотвратить атаки пароля методом прямого доступа.</span><span class="sxs-lookup"><span data-stu-id="1a90a-233">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="1a90a-234">Для атаки словаря можно указать один или несколько паролей, которые необходимо использовать (вручную или в отправленном файле), а также указать одного или нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="1a90a-234">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="1a90a-235">**Распыление паролей** : при атаке с помощью *распылителя пароля* такой же тщательно распознанный пароль используется для списка учетных записей пользователей (один пароль для многих учетных записей).</span><span class="sxs-lookup"><span data-stu-id="1a90a-235">**Password spray attack** : A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="1a90a-236">Не удается обнаружить пароли, которые трудно обнаружить, чем атаки методом грубой силы (вероятность успеха возрастает, когда злоумышленник пытается использовать один пароль в десятках или сотни учетных записей, не выполняя риск блокировки неправильного пароля пользователя).</span><span class="sxs-lookup"><span data-stu-id="1a90a-236">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="1a90a-237">Для атаки с помощью распылителя пароля можно указать только один пароль, а вы можете указать одного или нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="1a90a-237">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="1a90a-238">При атаке по паролю в симуляторе атак выполняется передача имени пользователя и пароля базовой авторизации в конечную точку, поэтому они также работают с другими методами проверки подлинности (AD FS, синхронизация хэша пароля, сквозной, Пингфедерате и т. д.).</span><span class="sxs-lookup"><span data-stu-id="1a90a-238">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="1a90a-239">Для пользователей с включенным MFA, даже если парольная атака пытается использовать действительный пароль, попытка всегда будет регистрироваться как сбой (другими словами, пользователи MFA никогда не будут отображаться в списке **успешных попыток** кампании).</span><span class="sxs-lookup"><span data-stu-id="1a90a-239">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="1a90a-240">Это ожидаемый результат.</span><span class="sxs-lookup"><span data-stu-id="1a90a-240">This is the expected result.</span></span> <span data-ttu-id="1a90a-241">MFA — это основной метод защиты от атак паролей.</span><span class="sxs-lookup"><span data-stu-id="1a90a-241">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="1a90a-242">Создание и запуск кампании по атаке паролей</span><span class="sxs-lookup"><span data-stu-id="1a90a-242">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="1a90a-243">В центре безопасности & соответствия требованиям перейдите к **Threat management** \> **симулятору атак** управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="1a90a-243">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="1a90a-244">На странице **имитация атак** выберите один из следующих вариантов, в зависимости от типа кампании, которую вы хотите создать:</span><span class="sxs-lookup"><span data-stu-id="1a90a-244">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="1a90a-245">В разделе @ @ **грубый пароль (атака с словарем)** нажмите кнопку **запустить атаку** или выберите пункт **сведения об атаке** \> **запустить атаку**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-245">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="1a90a-246">в разделе " **распыление пароли для паролей** " нажмите кнопку **запустить атаку** или " **сведения об атаке** ", чтобы \> **запустить атаку**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-246">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="1a90a-247">Мастер **настройки парольной атаки** запускается в новом всплывающем меню.</span><span class="sxs-lookup"><span data-stu-id="1a90a-247">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="1a90a-248">В разделе " **начать** " введите уникальное отображаемое имя кампании, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-248">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="1a90a-249">В шаге **Целевые пользователи** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="1a90a-249">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="1a90a-250">Щелкните **Адресная книга** , чтобы выбрать получателей (пользователей или групп) для кампании.</span><span class="sxs-lookup"><span data-stu-id="1a90a-250">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="1a90a-251">У каждого целевого получателя должен быть почтовый ящик Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1a90a-251">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="1a90a-252">Если нажать кнопку **Фильтр** и **Применить** , не вводя условия поиска, все получатели возвращаются и добавляются в кампанию.</span><span class="sxs-lookup"><span data-stu-id="1a90a-252">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="1a90a-253">Нажмите кнопку **Импорт** и импорт **файлов** , чтобы импортировать значения с разделителями-запятыми (CSV) или файлы электронной почты с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="1a90a-253">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="1a90a-254">Каждая строка должна содержать адрес электронной почты получателя.</span><span class="sxs-lookup"><span data-stu-id="1a90a-254">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="1a90a-255">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-255">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="1a90a-256">В разделе **Выбор параметров атаки** выберите действия, которые нужно выполнить, в зависимости от типа кампании:</span><span class="sxs-lookup"><span data-stu-id="1a90a-256">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="1a90a-257">**Пароль принудительной перебора (атака со словарем)** : выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="1a90a-257">**Brute Force Password (Dictionary Attack)** : Do either of the following steps:</span></span>

     - <span data-ttu-id="1a90a-258">**Введите пароли вручную** : в поле **нажмите клавишу ВВОД, чтобы добавить пароль** , введите пароль и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="1a90a-258">**Enter passwords manually** : In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="1a90a-259">Повторите этот шаг необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="1a90a-259">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="1a90a-260">**Отправьте пароли из файла словаря** : нажмите кнопку **Отправить** , чтобы импортировать существующий текстовый файл, который содержит один пароль в каждой строке, и пустую последнюю строку.</span><span class="sxs-lookup"><span data-stu-id="1a90a-260">**Upload passwords from a dictionary file** : Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="1a90a-261">Размер текстового файла должен быть не менее 10 МБ и не может содержать более 30000 паролей.</span><span class="sxs-lookup"><span data-stu-id="1a90a-261">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="1a90a-262">**Распыление паролей** : в поле **пароль (s) для атаки** введите один пароль.</span><span class="sxs-lookup"><span data-stu-id="1a90a-262">**Password spray attack** : In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="1a90a-263">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-263">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="1a90a-264">На шаге **Подтверждение** нажмите кнопку **Готово** , чтобы запустить кампанию.</span><span class="sxs-lookup"><span data-stu-id="1a90a-264">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="1a90a-265">Указанные пароли будут использоваться для указанных пользователей.</span><span class="sxs-lookup"><span data-stu-id="1a90a-265">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="1a90a-266">Просмотр результатов кампании</span><span class="sxs-lookup"><span data-stu-id="1a90a-266">View campaign results</span></span>

<span data-ttu-id="1a90a-267">После запуска кампании можно проверить ход выполнения и результаты на основной странице **имитации атак** .</span><span class="sxs-lookup"><span data-stu-id="1a90a-267">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="1a90a-268">В активных кампаниях будет отображаться строка состояния, процентное значение завершенного количества пользователей (количество пользователей).</span><span class="sxs-lookup"><span data-stu-id="1a90a-268">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="1a90a-269">Нажмите кнопку **Обновить** , чтобы обновить ход выполнения активных кампаний.</span><span class="sxs-lookup"><span data-stu-id="1a90a-269">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="1a90a-270">Вы также можете нажать кнопку **прекратить** , чтобы остановить активную кампанию.</span><span class="sxs-lookup"><span data-stu-id="1a90a-270">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="1a90a-271">По завершении кампании состояние "атака" будет изменено на " **атака завершена** ".</span><span class="sxs-lookup"><span data-stu-id="1a90a-271">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="1a90a-272">Результаты кампании можно просмотреть, выполнив одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="1a90a-272">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="1a90a-273">На главной странице **имитации атак** нажмите кнопку **Просмотреть отчет** под названием кампании.</span><span class="sxs-lookup"><span data-stu-id="1a90a-273">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="1a90a-274">На главной странице " **имитация атак** " в разделе **сведения о атаках** выберите тип атаки.</span><span class="sxs-lookup"><span data-stu-id="1a90a-274">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="1a90a-275">На открывшейся странице **сведения об атаке** выберите кампания в разделе **Журнал атак** .</span><span class="sxs-lookup"><span data-stu-id="1a90a-275">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="1a90a-276">При любом из предыдущих действий вы перейдете на страницу с именем " **сведения об атаке** ".</span><span class="sxs-lookup"><span data-stu-id="1a90a-276">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="1a90a-277">Сведения, доступные на этой странице для каждого типа кампании, описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="1a90a-277">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="1a90a-278">Результаты кампании фишинга спеар (Credential Credential)</span><span class="sxs-lookup"><span data-stu-id="1a90a-278">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="1a90a-279">Следующая информация доступна на странице **сведения о атаках** для каждой кампании:</span><span class="sxs-lookup"><span data-stu-id="1a90a-279">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="1a90a-280">Длительность кампании (Дата и время начала и Дата и время окончания).</span><span class="sxs-lookup"><span data-stu-id="1a90a-280">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="1a90a-281">**Общее количество целевых пользователей**</span><span class="sxs-lookup"><span data-stu-id="1a90a-281">**Total users targeted**</span></span>

- <span data-ttu-id="1a90a-282">**Успешных попыток** : количество пользователей, которые щелкают ссылку **и** ввели учетные данные ( *любое* имя пользователя и пароль).</span><span class="sxs-lookup"><span data-stu-id="1a90a-282">**Successful attempts** : The number of users who clicked the link **and** entered their credentials ( *any* username and password value).</span></span>

- <span data-ttu-id="1a90a-283">**Общая доля успешных** попыток: процент, рассчитанный на количество **успешных попыток** , для которых  /  **назначены пользователи**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-283">**Overall Success Rate** : A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="1a90a-284">**Самый быстрый щелчок** : сколько времени занял первый пользователь, щелкнув ссылку после запуска кампании.</span><span class="sxs-lookup"><span data-stu-id="1a90a-284">**Fastest Click** : How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="1a90a-285">**Среднее нажатие** : количество времени, в течение которого все потребовалось щелкнуть ссылку, деленную на количество пользователей, которые щелкают ссылку.</span><span class="sxs-lookup"><span data-stu-id="1a90a-285">**Average Click** : The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="1a90a-286">**Выберите процент успешных** действий: процент, вычисляемый (число пользователей, которые щелкают ссылку)/общее число **целевых пользователей**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-286">**Click Success Rate** : A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="1a90a-287">**Самые быстрые учетные данные** : время, в течение которого первый пользователь вводит свои учетные данные после запуска кампании.</span><span class="sxs-lookup"><span data-stu-id="1a90a-287">**Fastest Credentials** : How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="1a90a-288">**Средняя учетная** запись: сумма, на которую все пользователи могут вводить свои учетные данные, разделенные на количество пользователей, которые ввели свои учетные данные.</span><span class="sxs-lookup"><span data-stu-id="1a90a-288">**Average Credentials** : The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="1a90a-289">**Доля успешных учетных данных** : процентное отношение, вычисляемое (число пользователей, которые вводили свои учетные данные)/ **Общее число целевых пользователей**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-289">**Credential Success Rate** : A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="1a90a-290">Линейчатая диаграмма, показывающая, что **выбрана ссылка** , и число **предоставленных учетных данных** в день.</span><span class="sxs-lookup"><span data-stu-id="1a90a-290">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="1a90a-291">Граф круга, отображающий **выбранную ссылку** , **предоставленные учетные данные** **и процентные** значения для кампании.</span><span class="sxs-lookup"><span data-stu-id="1a90a-291">A circle graph that shows the **Link clicked** , **Credential supplied** , and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="1a90a-292">Раздел **скомпрометированные пользователи** : содержит сведения о пользователях, которые щелкают ссылку:</span><span class="sxs-lookup"><span data-stu-id="1a90a-292">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="1a90a-293">Адрес электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="1a90a-293">The user's email address</span></span>

  - <span data-ttu-id="1a90a-294">Дата и время щелчка ссылки.</span><span class="sxs-lookup"><span data-stu-id="1a90a-294">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="1a90a-295">IP-адрес клиента.</span><span class="sxs-lookup"><span data-stu-id="1a90a-295">The client IP address.</span></span>

  - <span data-ttu-id="1a90a-296">Сведения о версии Windows и веб-браузере пользователя.</span><span class="sxs-lookup"><span data-stu-id="1a90a-296">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="1a90a-297">Вы можете нажать кнопку **Экспорт** , чтобы экспортировать результаты в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="1a90a-297">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="1a90a-298">Результаты кампании фишинга спеар (вложение)</span><span class="sxs-lookup"><span data-stu-id="1a90a-298">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="1a90a-299">Следующая информация доступна на странице **сведения о атаках** для каждой кампании:</span><span class="sxs-lookup"><span data-stu-id="1a90a-299">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="1a90a-300">Длительность кампании (Дата и время начала и Дата и время окончания).</span><span class="sxs-lookup"><span data-stu-id="1a90a-300">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="1a90a-301">**Общее количество целевых пользователей**</span><span class="sxs-lookup"><span data-stu-id="1a90a-301">**Total users targeted**</span></span>

- <span data-ttu-id="1a90a-302">**Успешных попыток** : количество пользователей, которые открывали или открывали вложение (Предварительная версия не учитывается).</span><span class="sxs-lookup"><span data-stu-id="1a90a-302">**Successful attempts** : The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="1a90a-303">**Общая доля успешных** попыток: процент, рассчитанный на количество **успешных попыток** , для которых  /  **назначены пользователи**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-303">**Overall Success Rate** : A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="1a90a-304">**Самое быстрое время открытия вложения: время** , затрачиваемое первым пользователем на открытие вложения после запуска кампании.</span><span class="sxs-lookup"><span data-stu-id="1a90a-304">**Fastest attachment open time** : How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="1a90a-305">**Среднее время открытия вложения** : сумма, с которой все пользователи открывают вложение, разделенное на количество пользователей, открывающих вложение.</span><span class="sxs-lookup"><span data-stu-id="1a90a-305">**Average attachment open time** : The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="1a90a-306">**Доля успешных попыток открытия вложений** : процент, вычисляемый (число пользователей, открывших вложение)/ **Общее число целевых пользователей**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-306">**Attachment open success rate** : A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="1a90a-307">Результаты кампании с паролями грубой силы (Словарная атака)</span><span class="sxs-lookup"><span data-stu-id="1a90a-307">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="1a90a-308">Следующая информация доступна на странице **сведения о атаках** для каждой кампании:</span><span class="sxs-lookup"><span data-stu-id="1a90a-308">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="1a90a-309">Длительность кампании (Дата и время начала и Дата и время окончания).</span><span class="sxs-lookup"><span data-stu-id="1a90a-309">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="1a90a-310">**Общее количество целевых пользователей**</span><span class="sxs-lookup"><span data-stu-id="1a90a-310">**Total users targeted**</span></span>

- <span data-ttu-id="1a90a-311">**Успешных попыток** : количество пользователей, которые применялись к одному из указанных паролей.</span><span class="sxs-lookup"><span data-stu-id="1a90a-311">**Successful attempts** : The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="1a90a-312">**Общая доля успешных** попыток: процент, рассчитанный на количество **успешных попыток** , для которых  /  **назначены пользователи**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-312">**Overall Success Rate** : A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="1a90a-313">Раздел **скомпрометированные пользователи** содержит список адресов электронной почты затронутых пользователей.</span><span class="sxs-lookup"><span data-stu-id="1a90a-313">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="1a90a-314">Вы можете нажать кнопку **Экспорт** , чтобы экспортировать результаты в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="1a90a-314">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="1a90a-315">Результаты кампании для атаки на распылителя пароля</span><span class="sxs-lookup"><span data-stu-id="1a90a-315">Password spray attack campaign results</span></span>

<span data-ttu-id="1a90a-316">Следующая информация доступна на странице **сведения о атаках** для каждой кампании:</span><span class="sxs-lookup"><span data-stu-id="1a90a-316">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="1a90a-317">Длительность кампании (Дата и время начала и Дата и время окончания).</span><span class="sxs-lookup"><span data-stu-id="1a90a-317">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="1a90a-318">**Общее количество целевых пользователей**</span><span class="sxs-lookup"><span data-stu-id="1a90a-318">**Total users targeted**</span></span>

- <span data-ttu-id="1a90a-319">**Успешных попыток** : количество пользователей, которые были использованы с указанным паролем.</span><span class="sxs-lookup"><span data-stu-id="1a90a-319">**Successful attempts** : The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="1a90a-320">**Общая доля успешных** попыток: процент, рассчитанный на количество **успешных попыток** , для которых  /  **назначены пользователи**.</span><span class="sxs-lookup"><span data-stu-id="1a90a-320">**Overall Success Rate** : A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
