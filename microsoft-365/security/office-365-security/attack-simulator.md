---
title: Симулятор атак в Microsoft Defender для Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как использовать симулятор атак для имитации фишинговых атак и атак паролей в Microsoft 365 E5 или Microsoft Defender для организаций Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 73ad3501ed9818261c9fbec6ba12b4dc884da84f
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624829"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="f1914-103">Симулятор атак в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="f1914-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f1914-104">**Применяется к** [Microsoft Defender для Office 365 плана 2](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="f1914-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="f1914-105">Если в вашей организации есть Microsoft Defender для Office 365 [](office-365-ti.md)Plan 2, который включает возможности расследования угроз и реагирования, вы можете использовать симулятор атак в Центре обеспечения безопасности & для выполнения реалистичных сценариев атак в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f1914-105">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="f1914-106">Эти смоделированные атаки помогут вам определить и найти уязвимых пользователей до того, как реальная атака сказывается на вашей нижней строке.</span><span class="sxs-lookup"><span data-stu-id="f1914-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="f1914-107">Подробнее читайте в этой статье.</span><span class="sxs-lookup"><span data-stu-id="f1914-107">Read this article to learn more.</span></span>

> [!NOTE]
>
> <span data-ttu-id="f1914-108">Симулятор атаки, как описано в этой статье, теперь  только для  чтения и заменен обучением имитации атаки в узле совместной & электронной почты в центре безопасности [Microsoft 365.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="f1914-108">Attack Simulator as described in this article is now read-only and has been replaced by **Attack simulation training** in the **Email & collaboration** node in the [Microsoft 365 security center](https://security.microsoft.com).</span></span> <span data-ttu-id="f1914-109">Дополнительные сведения см. в [дополнительных сведениях: Начало работы с обучением имитации атаки.](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="f1914-109">For more information, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>
>
> <span data-ttu-id="f1914-110">Отключена возможность запуска новых имитаций из этой версии симулятора атаки.</span><span class="sxs-lookup"><span data-stu-id="f1914-110">The ability to launch new simulations from this version of Attack Simulator has been disabled.</span></span> <span data-ttu-id="f1914-111">Однако с 24 января 2021 г. вы можете получать доступ к отчетам сроком до 90 дней.</span><span class="sxs-lookup"><span data-stu-id="f1914-111">However, you can still access reports for up to 90 days from January 24, 2021.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f1914-112">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="f1914-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f1914-113">Чтобы открыть Центр безопасности и соответствия требованиям, перейдите по ссылке <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f1914-113">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="f1914-114">Симулятор атаки доступен в **симуляторе атаки управления** \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="f1914-114">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="f1914-115">Чтобы перейти непосредственно к симулятору атаки, откройте <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="f1914-115">To go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="f1914-116">Дополнительные сведения о доступности симулятора атак для различных Microsoft 365 см. в описании [службы Microsoft Defender для Office 365.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="f1914-116">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="f1914-117">Необходимо быть членом групп ролей **"Управление организацией"** или **"Администратор** безопасности".</span><span class="sxs-lookup"><span data-stu-id="f1914-117">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="f1914-118">Дополнительные сведения о группах ролей в Центре безопасности и соответствия требованиям см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f1914-118">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="f1914-119">Ваша учетная запись должна быть настроена для многофакторной проверки подлинности (MFA) для создания и управления кампаниями в Симуляторе атак.</span><span class="sxs-lookup"><span data-stu-id="f1914-119">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="f1914-120">Инструкции см. [в инструкции Настройка многофакторной проверки подлинности.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="f1914-120">For instructions, see [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

- <span data-ttu-id="f1914-121">Симулятор атак работает только на облачных почтовых ящиках.</span><span class="sxs-lookup"><span data-stu-id="f1914-121">Attack Simulator only works on cloud-based mailboxes.</span></span>

- <span data-ttu-id="f1914-122">Фишинговые кампании будут собирать и обрабатывать события в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="f1914-122">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="f1914-123">Данные исторической кампании будут доступны в течение 90 дней после запуска кампании.</span><span class="sxs-lookup"><span data-stu-id="f1914-123">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="f1914-124">Имитация атаки и связанные с обучением данные хранятся с другими данными клиентов для Microsoft 365 служб.</span><span class="sxs-lookup"><span data-stu-id="f1914-124">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="f1914-125">Дополнительные сведения [см. в Microsoft 365 расположения данных.](../../enterprise/o365-data-locations.md)</span><span class="sxs-lookup"><span data-stu-id="f1914-125">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span>

- <span data-ttu-id="f1914-126">Для Симулятора атак нет соответствующих комлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1914-126">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="f1914-127">Фишинговые кампании с копьем</span><span class="sxs-lookup"><span data-stu-id="f1914-127">Spear phishing campaigns</span></span>

<span data-ttu-id="f1914-128">*Фишинг —* это общий термин для атак электронной почты, которые пытаются украсть конфиденциальные сведения в сообщениях, которые, как представляется, являются законными или доверенными отправителями.</span><span class="sxs-lookup"><span data-stu-id="f1914-128">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="f1914-129">*Фишинг* на копье — это целенаправленная фишинговая атака, которая использует сфокусированный и настраиваемый контент, специально адаптированный к целевым получателям (как правило, после разведки получателей злоумышленником).</span><span class="sxs-lookup"><span data-stu-id="f1914-129">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="f1914-130">В Симуляторе атак доступны два различных типа фишинговых кампаний копья:</span><span class="sxs-lookup"><span data-stu-id="f1914-130">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="f1914-131">**Фишинг для копей (сбор учетных данных).** Атака пытается убедить получателей щелкнуть URL-адрес в сообщении.</span><span class="sxs-lookup"><span data-stu-id="f1914-131">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="f1914-132">Если они щелкнуть ссылку, им будет предложено ввести свои учетные данные.</span><span class="sxs-lookup"><span data-stu-id="f1914-132">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="f1914-133">Если это так, они будут доставлены в одно из следующих мест:</span><span class="sxs-lookup"><span data-stu-id="f1914-133">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="f1914-134">Страница по умолчанию, которая объясняет, что это был просто тест, и дает советы по распознаванию фишинговых сообщений.</span><span class="sxs-lookup"><span data-stu-id="f1914-134">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Что видят пользователи, щелкнув фишинговую ссылку и введите учетные данные](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="f1914-136">Настраиваемая страница (URL-адрес), указанная вами.</span><span class="sxs-lookup"><span data-stu-id="f1914-136">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="f1914-137">**Фишинг (вложение)** копей: атака пытается убедить получателей открыть .docx или .pdf вложения в сообщении.</span><span class="sxs-lookup"><span data-stu-id="f1914-137">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="f1914-138">Вложение содержит тот же контент из фишинговой ссылки по умолчанию, но первое предложение начинается с ", вы видите это сообщение как недавнее сообщение электронной почты, которое вы \<Display Name\> открыли...".</span><span class="sxs-lookup"><span data-stu-id="f1914-138">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="f1914-139">В настоящее время срок действия фишинговых кампаний в Симуляторе атак не истекает.</span><span class="sxs-lookup"><span data-stu-id="f1914-139">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="f1914-140">Создание фишинговой кампании копья</span><span class="sxs-lookup"><span data-stu-id="f1914-140">Create a spear phishing campaign</span></span>

<span data-ttu-id="f1914-141">Важной частью любой кампании фишинга копья является внешний вид сообщения электронной почты, отправленного целевым получателям.</span><span class="sxs-lookup"><span data-stu-id="f1914-141">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="f1914-142">Чтобы создать и настроить сообщение электронной почты, у вас есть такие параметры:</span><span class="sxs-lookup"><span data-stu-id="f1914-142">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="f1914-143">**Используйте встроенный шаблон электронной** почты: доступны два встроенных шаблона: **Prize Giveaway** и **Payroll Update.**</span><span class="sxs-lookup"><span data-stu-id="f1914-143">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="f1914-144">При создании и запуске кампании можно дополнительно настроить некоторые, все или никакие свойства электронной почты из шаблона.</span><span class="sxs-lookup"><span data-stu-id="f1914-144">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="f1914-145">**Создайте многопользоваемый** шаблон электронной почты. После создания и сохранения шаблона электронной почты вы можете использовать его снова в будущих фишинговых кампаниях.</span><span class="sxs-lookup"><span data-stu-id="f1914-145">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="f1914-146">При создании и запуске кампании можно дополнительно настроить некоторые, все или никакие свойства электронной почты из шаблона.</span><span class="sxs-lookup"><span data-stu-id="f1914-146">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="f1914-147">**Создайте сообщение электронной** почты в мастере. Вы можете создать сообщение электронной почты непосредственно в мастере при создании и запуске кампании фишинга копья.</span><span class="sxs-lookup"><span data-stu-id="f1914-147">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="f1914-148">Шаг 1 (необязательный): создание настраиваемой шаблона электронной почты</span><span class="sxs-lookup"><span data-stu-id="f1914-148">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="f1914-149">Если вы собираетесь использовать один из встроенных шаблонов или создать сообщение электронной почты непосредственно в мастере, вы можете пропустить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="f1914-149">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="f1914-150">В Центре & безопасности перейдите к симулятору **атаки управления** \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="f1914-150">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="f1914-151">На странице **Имитация** атак в разделах "Фишинг на копье" (Сбор учетных **данных)** или "Фишинг для копей" **(Вложения)** щелкните **Сведения об атаке.**</span><span class="sxs-lookup"><span data-stu-id="f1914-151">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="f1914-152">Не важно, где вы создаете шаблон.</span><span class="sxs-lookup"><span data-stu-id="f1914-152">It doesn't matter where you create the template.</span></span> <span data-ttu-id="f1914-153">Доступные параметры в шаблоне одинаковы для обоих типов фишинговых атак.</span><span class="sxs-lookup"><span data-stu-id="f1914-153">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="f1914-154">На странице **Сведения о атаке,** открываемой в разделе **Шаблоны** фишинга в области **Создание** шаблонов, нажмите **кнопку Новый шаблон**.</span><span class="sxs-lookup"><span data-stu-id="f1914-154">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="f1914-155">Мастер **настройки шаблона фишинга** начинается с нового вылета.</span><span class="sxs-lookup"><span data-stu-id="f1914-155">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="f1914-156">На **шаге Начните** введите уникальное имя отображения шаблона и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f1914-156">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="f1914-157">В **шаге Настройка сведений электронной почты** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f1914-157">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="f1914-158">**From (Name)**: имя отображения, используемая для отправитель сообщения.</span><span class="sxs-lookup"><span data-stu-id="f1914-158">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="f1914-159">**From (Email)**: адрес электронной почты отправитель.</span><span class="sxs-lookup"><span data-stu-id="f1914-159">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="f1914-160">**Фишинговый URL-адрес login Server.** Щелкните выпадение вниз и выберите один из доступных URL-адресов из списка.</span><span class="sxs-lookup"><span data-stu-id="f1914-160">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="f1914-161">Это URL-адрес, который пользователи будут склонны щелкнуть.</span><span class="sxs-lookup"><span data-stu-id="f1914-161">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="f1914-162">Имеются следующие варианты.</span><span class="sxs-lookup"><span data-stu-id="f1914-162">The choices are:</span></span>

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
     > <span data-ttu-id="f1914-163">Служба репутации URL-адресов может определить один или несколько из этих URL-адресов как небезопасные.</span><span class="sxs-lookup"><span data-stu-id="f1914-163">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="f1914-164">Проверьте доступность URL-адреса в поддерживаемых веб-браузерах перед использованием URL-адреса в фишинговой кампании.</span><span class="sxs-lookup"><span data-stu-id="f1914-164">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="f1914-165">**Пользовательский URL-адрес** страницы для посадки. Введите необязательный посадочный лист, на котором будут приниматься пользователи, если они щелкнуть фишинговую ссылку и введите свои учетные данные.</span><span class="sxs-lookup"><span data-stu-id="f1914-165">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="f1914-166">Эта ссылка заменяет посадочную страницу по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f1914-166">This link replaces the default landing page.</span></span> <span data-ttu-id="f1914-167">Например, если у вас есть обучение внутренней осведомленности, вы можете указать этот URL-адрес здесь.</span><span class="sxs-lookup"><span data-stu-id="f1914-167">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="f1914-168">**Категория.** В настоящее время этот параметр не используется (все, что вы вводите, игнорируется).</span><span class="sxs-lookup"><span data-stu-id="f1914-168">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="f1914-169">**Тема.** **Поле Subject** сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f1914-169">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="f1914-170">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f1914-170">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="f1914-171">В **шаге Compose email** создайте текст сообщения сообщения.</span><span class="sxs-lookup"><span data-stu-id="f1914-171">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="f1914-172">Вы можете использовать вкладку **Email** (богатый редактор HTML) или вкладку **Source** (необработанные HTML-коды).</span><span class="sxs-lookup"><span data-stu-id="f1914-172">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="f1914-173">Форматирование HTML может быть таким же простым или сложным, как и нужно.</span><span class="sxs-lookup"><span data-stu-id="f1914-173">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="f1914-174">Вы можете вставить изображения и текст, чтобы повысить достоверность сообщения в клиенте электронной почты получателя.</span><span class="sxs-lookup"><span data-stu-id="f1914-174">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="f1914-175">`${username}` вставляет имя получателя.</span><span class="sxs-lookup"><span data-stu-id="f1914-175">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="f1914-176">`${loginserverurl}` вставляет **URL-адрес фишинг-сервера login Server** с предыдущего шага.</span><span class="sxs-lookup"><span data-stu-id="f1914-176">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="f1914-177">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f1914-177">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="f1914-178">На **шаге Подтверждение** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="f1914-178">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="f1914-179">Шаг 2. Создание и запуск кампании фишинга копья</span><span class="sxs-lookup"><span data-stu-id="f1914-179">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="f1914-180">В Центре & безопасности перейдите к симулятору **атаки управления** \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="f1914-180">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="f1914-181">На странице **Имитация атак** сделайте один из следующих выборов в зависимости от типа кампании, необходимой для создания:</span><span class="sxs-lookup"><span data-stu-id="f1914-181">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="f1914-182">В разделе **Фишинг для копей (Сбор учетных данных)** нажмите **кнопку Запуск атаки** или нажмите **кнопку Атака Сведения о** \> **запуске атаки**.</span><span class="sxs-lookup"><span data-stu-id="f1914-182">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="f1914-183">В разделе **Фишинг для копей (Вложения)** нажмите **кнопку Начать** атаку или нажмите **кнопку Атака Сведения о** \> **запуске атаки**.</span><span class="sxs-lookup"><span data-stu-id="f1914-183">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="f1914-184">Мастер **настройки фишинговых атак** запускается в новом вылете.</span><span class="sxs-lookup"><span data-stu-id="f1914-184">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="f1914-185">На **шаге Начните** делать один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f1914-185">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="f1914-186">В поле **Имя** введите уникальное имя отображения для кампании.</span><span class="sxs-lookup"><span data-stu-id="f1914-186">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="f1914-187">Не нажимайте **кнопку Использовать шаблон,** так как сообщение электронной почты будет создаваться позже в мастере.</span><span class="sxs-lookup"><span data-stu-id="f1914-187">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="f1914-188">Щелкните **Использовать шаблон** и выберите встроенный или настраиваемый шаблон электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f1914-188">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="f1914-189">После выбора шаблона поле **Имя** автоматически заполняется на основе шаблона, но можно изменить имя.</span><span class="sxs-lookup"><span data-stu-id="f1914-189">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f1914-190">![Страница "Запуск фишинга"](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span><span class="sxs-lookup"><span data-stu-id="f1914-190">![Phishing Start Page](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span></span>

   <span data-ttu-id="f1914-191">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f1914-191">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="f1914-192">На **шаге Целевые получатели** сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f1914-192">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="f1914-193">Нажмите **адресную** книгу, чтобы выбрать получателей (пользователей или групп) для кампании.</span><span class="sxs-lookup"><span data-stu-id="f1914-193">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="f1914-194">У каждого целевого получателя должен быть Exchange Online почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="f1914-194">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="f1914-195">Если щелкнуть **фильтр** и **применить** без ввода критериев поиска, все получатели возвращаются и добавляются в кампанию.</span><span class="sxs-lookup"><span data-stu-id="f1914-195">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="f1914-196">Щелкните **импортировать импорт файлов,** чтобы импортировать разделенное запятой значение (CSV) или файл адресов электронной почты, разделенный строками. </span><span class="sxs-lookup"><span data-stu-id="f1914-196">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="f1914-197">Каждая строка должна содержать адрес электронной почты получателя.</span><span class="sxs-lookup"><span data-stu-id="f1914-197">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="f1914-198">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f1914-198">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="f1914-199">В **шаге Настройка сведений электронной почты** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f1914-199">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="f1914-200">Если вы выбрали шаблон на шаге **Начните,** большинство из этих значений уже настроены, но их можно изменить.</span><span class="sxs-lookup"><span data-stu-id="f1914-200">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="f1914-201">**From (Name)**: имя отображения, используемая для отправитель сообщения.</span><span class="sxs-lookup"><span data-stu-id="f1914-201">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="f1914-202">**From (Email)**: адрес электронной почты отправитель.</span><span class="sxs-lookup"><span data-stu-id="f1914-202">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="f1914-203">Вы можете ввести реальный или поддельный адрес электронной почты из домена электронной почты организации или ввести реальный или поддельный внешний адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f1914-203">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="f1914-204">Допустимый адрес электронной почты отправитель из организации фактически будет решаться в клиенте электронной почты получателя.</span><span class="sxs-lookup"><span data-stu-id="f1914-204">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="f1914-205">**Фишинговый URL-адрес login Server.** Щелкните выпадение вниз и выберите один из доступных URL-адресов из списка.</span><span class="sxs-lookup"><span data-stu-id="f1914-205">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="f1914-206">Это URL-адрес, который пользователи будут склонны щелкнуть.</span><span class="sxs-lookup"><span data-stu-id="f1914-206">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="f1914-207">Имеются следующие варианты.</span><span class="sxs-lookup"><span data-stu-id="f1914-207">The choices are:</span></span>

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
     > - <span data-ttu-id="f1914-208">Все URL-адреса намеренно http, а не https.</span><span class="sxs-lookup"><span data-stu-id="f1914-208">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="f1914-209">Служба репутации URL-адресов может определить один или несколько из этих URL-адресов как небезопасные.</span><span class="sxs-lookup"><span data-stu-id="f1914-209">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="f1914-210">Проверьте доступность URL-адреса в поддерживаемых веб-браузерах перед использованием URL-адреса в фишинговой кампании.</span><span class="sxs-lookup"><span data-stu-id="f1914-210">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="f1914-211">Необходимо выбрать URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="f1914-211">You are required to select a URL.</span></span> <span data-ttu-id="f1914-212">Для **кампаний фишинга (вложения)** можно удалить ссылку из тела сообщения на следующем шаге (в противном случае сообщение будет содержать как ссылку, так **и** вложение).</span><span class="sxs-lookup"><span data-stu-id="f1914-212">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="f1914-213">**Тип вложения.** Этот параметр доступен только в кампаниях **по фишингу (вложениям).**</span><span class="sxs-lookup"><span data-stu-id="f1914-213">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="f1914-214">Нажмите кнопку drop down **и выберите**.DOCX **или.PDF** из списка.</span><span class="sxs-lookup"><span data-stu-id="f1914-214">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="f1914-215">**Имя вложения.** Этот параметр доступен только в кампаниях **по фишингу (вложениям).**</span><span class="sxs-lookup"><span data-stu-id="f1914-215">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="f1914-216">Введите имя файла для .docx или .pdf вложения.</span><span class="sxs-lookup"><span data-stu-id="f1914-216">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="f1914-217">**Пользовательский URL-адрес** страницы для посадки. Введите необязательный посадочный лист, на котором будут приниматься пользователи, если они щелкнуть фишинговую ссылку и введите свои учетные данные.</span><span class="sxs-lookup"><span data-stu-id="f1914-217">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="f1914-218">Эта ссылка заменяет посадочную страницу по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f1914-218">This link replaces the default landing page.</span></span> <span data-ttu-id="f1914-219">Например, если у вас есть обучение внутренней осведомленности, вы можете указать этот URL-адрес здесь.</span><span class="sxs-lookup"><span data-stu-id="f1914-219">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="f1914-220">**Тема.** **Поле Subject** сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f1914-220">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="f1914-221">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f1914-221">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="f1914-222">В **шаге Compose email** создайте текст сообщения сообщения.</span><span class="sxs-lookup"><span data-stu-id="f1914-222">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="f1914-223">Если вы выбрали шаблон на шаге **Начните,** тело сообщения уже настроено, но его можно настроить.</span><span class="sxs-lookup"><span data-stu-id="f1914-223">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="f1914-224">Вы можете использовать вкладку **Email** (богатый редактор HTML) или вкладку **Source** (необработанные HTML-коды).</span><span class="sxs-lookup"><span data-stu-id="f1914-224">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="f1914-225">Форматирование HTML может быть таким же простым или сложным, как и нужно.</span><span class="sxs-lookup"><span data-stu-id="f1914-225">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="f1914-226">Вы можете вставить изображения и текст, чтобы повысить достоверность сообщения в клиенте электронной почты получателя.</span><span class="sxs-lookup"><span data-stu-id="f1914-226">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="f1914-227">`${username}` вставляет имя получателя.</span><span class="sxs-lookup"><span data-stu-id="f1914-227">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="f1914-228">`${loginserverurl}`вставляет **URL-адрес фишинговых url-адресов login Server.**</span><span class="sxs-lookup"><span data-stu-id="f1914-228">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="f1914-229">Для кампаний фишинга **(вложения)** следует удалить ссылку из тела сообщения (в противном случае сообщение будет содержать ссылку и вложение, а щелчки ссылок не отслеживаются в кампании вложения). </span><span class="sxs-lookup"><span data-stu-id="f1914-229">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f1914-230">![Составить тело электронной почты](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span><span class="sxs-lookup"><span data-stu-id="f1914-230">![Compose Email Body](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span></span>

   <span data-ttu-id="f1914-231">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f1914-231">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="f1914-232">На **шаге Подтверждение** нажмите **кнопку Готово,** чтобы запустить кампанию.</span><span class="sxs-lookup"><span data-stu-id="f1914-232">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="f1914-233">Фишинговое сообщение доставляется целевым получателям.</span><span class="sxs-lookup"><span data-stu-id="f1914-233">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="f1914-234">Кампании атаки паролей</span><span class="sxs-lookup"><span data-stu-id="f1914-234">Password attack campaigns</span></span>

<span data-ttu-id="f1914-235">Атака *паролей* пытается угадать пароли для учетных записей пользователей в организации, как правило, после того, как злоумышленник идентифицировал одну или несколько допустимых учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="f1914-235">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="f1914-236">В Симуляторе атак доступны два различных типа кампаний атаки паролей для проверки сложности паролей пользователей:</span><span class="sxs-lookup"><span data-stu-id="f1914-236">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="f1914-237">**Грубый** пароль силы (атака словаря) :  атака грубой силы или словаря использует большой файл паролей словаря на учетной записи пользователя в надежде, что один из них будет работать (много паролей против одной учетной записи). </span><span class="sxs-lookup"><span data-stu-id="f1914-237">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="f1914-238">Неправильные блокировки паролей помогают отпугивать атаки грубого принудительного пароля.</span><span class="sxs-lookup"><span data-stu-id="f1914-238">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="f1914-239">При атаке словаря можно указать один или несколько паролей для проверки (вручную вложенный или в загруженный файл), а также указать одного или многих пользователей.</span><span class="sxs-lookup"><span data-stu-id="f1914-239">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="f1914-240">**Атака спрей** пароля. *Атака* спрей пароля использует тот же тщательно рассмотренный пароль против списка учетных записей пользователей (один пароль против многих учетных записей).</span><span class="sxs-lookup"><span data-stu-id="f1914-240">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="f1914-241">Атаки спрей паролей труднее обнаружить, чем атаки грубого принудительного пароля (вероятность успеха увеличивается, когда злоумышленник пытается один пароль на десятках или сотнях учетных записей без риска отключения блокировки неправильного пароля пользователя).</span><span class="sxs-lookup"><span data-stu-id="f1914-241">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="f1914-242">Для атаки спрей пароля можно указать только один пароль, чтобы попытаться, и вы можете указать одного или многих пользователей.</span><span class="sxs-lookup"><span data-stu-id="f1914-242">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="f1914-243">Атаки паролей в Симуляторе атак передают запросы имени пользователя и пароля Basic auth в конечную точку, поэтому они также работают с другими методами проверки подлинности (AD FS, синхронизация хеш-кодов паролей, сквозной доступ, PingFederate и т.д.).</span><span class="sxs-lookup"><span data-stu-id="f1914-243">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="f1914-244">Для пользователей с включенной поддержкой MFA, даже если атака пароля пытается использовать свой фактический пароль, попытка всегда  регистрируется как сбой (другими словами, пользователи MFA никогда не будут отображаться в графе Успешные попытки кампании).</span><span class="sxs-lookup"><span data-stu-id="f1914-244">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="f1914-245">Это ожидаемый результат.</span><span class="sxs-lookup"><span data-stu-id="f1914-245">This is the expected result.</span></span> <span data-ttu-id="f1914-246">MFA — это основной метод защиты от атак паролей.</span><span class="sxs-lookup"><span data-stu-id="f1914-246">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="f1914-247">Создание и запуск кампании атаки паролей</span><span class="sxs-lookup"><span data-stu-id="f1914-247">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="f1914-248">В Центре & безопасности перейдите к симулятору **атаки управления** \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="f1914-248">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="f1914-249">На странице **Имитация атак** сделайте один из следующих выборов в зависимости от типа кампании, необходимой для создания:</span><span class="sxs-lookup"><span data-stu-id="f1914-249">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="f1914-250">В разделе **Brute Force Password (Dictionary Attack)** нажмите **кнопку Запуск** атаки или нажмите **кнопку Атака Сведения о** \> **запуске атаки**.</span><span class="sxs-lookup"><span data-stu-id="f1914-250">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="f1914-251">в разделе **Атака спрей пароля** нажмите **кнопку Начать** атаку или нажмите **кнопку Атака Сведения о** \> **запуске атаки**.</span><span class="sxs-lookup"><span data-stu-id="f1914-251">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="f1914-252">Мастер **настройки атаки паролей** начинается с новой вылетной записи.</span><span class="sxs-lookup"><span data-stu-id="f1914-252">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="f1914-253">На **шаге Начните** введите уникальное имя отображения для кампании и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f1914-253">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="f1914-254">На **шаге Целевые** пользователи сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f1914-254">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="f1914-255">Нажмите **адресную** книгу, чтобы выбрать получателей (пользователей или групп) для кампании.</span><span class="sxs-lookup"><span data-stu-id="f1914-255">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="f1914-256">У каждого целевого получателя должен быть Exchange Online почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="f1914-256">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="f1914-257">Если щелкнуть **фильтр** и **применить** без ввода критериев поиска, все получатели возвращаются и добавляются в кампанию.</span><span class="sxs-lookup"><span data-stu-id="f1914-257">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="f1914-258">Щелкните **импортировать импорт файлов,** чтобы импортировать разделенное запятой значение (CSV) или файл адресов электронной почты, разделенный строками. </span><span class="sxs-lookup"><span data-stu-id="f1914-258">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="f1914-259">Каждая строка должна содержать адрес электронной почты получателя.</span><span class="sxs-lookup"><span data-stu-id="f1914-259">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="f1914-260">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f1914-260">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="f1914-261">В **шаге Выбор параметров атаки** выберите, что делать в зависимости от типа кампании:</span><span class="sxs-lookup"><span data-stu-id="f1914-261">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="f1914-262">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span><span class="sxs-lookup"><span data-stu-id="f1914-262">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="f1914-263">**Ввод паролей вручную.** Введите кнопку **Нажмите,** чтобы добавить пароль, введите пароль и нажмите кнопку ENTER.</span><span class="sxs-lookup"><span data-stu-id="f1914-263">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="f1914-264">Повторите этот шаг необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="f1914-264">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="f1914-265">**Upload** паролей из файла словаря: **щелкните** Upload, чтобы импортировать существующий текстовый файл, содержащий один пароль на каждой строке и пустую последнюю строку.</span><span class="sxs-lookup"><span data-stu-id="f1914-265">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="f1914-266">Размер текстового файла должен быть не более 10 МБ и не может содержать более 30000 паролей.</span><span class="sxs-lookup"><span data-stu-id="f1914-266">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="f1914-267">**Атака спрей пароля.** **В пароль(ы)** для использования в поле атаки введите один пароль.</span><span class="sxs-lookup"><span data-stu-id="f1914-267">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="f1914-268">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f1914-268">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="f1914-269">На **шаге Подтверждение** нажмите **кнопку Готово,** чтобы запустить кампанию.</span><span class="sxs-lookup"><span data-stu-id="f1914-269">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="f1914-270">Указанные пароли опробуются на указанных вами пользователях.</span><span class="sxs-lookup"><span data-stu-id="f1914-270">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="f1914-271">Просмотр результатов кампании</span><span class="sxs-lookup"><span data-stu-id="f1914-271">View campaign results</span></span>

<span data-ttu-id="f1914-272">После запуска кампании вы можете проверить ход и результаты на главной странице **Имитация атак.**</span><span class="sxs-lookup"><span data-stu-id="f1914-272">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="f1914-273">Активные кампании будут показывать планку состояния, завершенное процентное значение и количество "(завершенных пользователей) (всего пользователей)".</span><span class="sxs-lookup"><span data-stu-id="f1914-273">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="f1914-274">Нажатие **кнопки "Обновление"** позволит обновить ход активных кампаний.</span><span class="sxs-lookup"><span data-stu-id="f1914-274">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="f1914-275">Чтобы остановить активную **кампанию,** можно также нажать Кнопку Прекратить.</span><span class="sxs-lookup"><span data-stu-id="f1914-275">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="f1914-276">По завершению кампании состояние изменяется в **Attack.**</span><span class="sxs-lookup"><span data-stu-id="f1914-276">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="f1914-277">Результаты кампании можно просмотреть, выступая с одним из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f1914-277">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="f1914-278">На главной **странице Имитация атак** щелкните **Просмотр отчета** под именем кампании.</span><span class="sxs-lookup"><span data-stu-id="f1914-278">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="f1914-279">На главной **странице Имитация атак** щелкните **Сведения о** атаке в разделе для типа атаки.</span><span class="sxs-lookup"><span data-stu-id="f1914-279">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="f1914-280">На **открываемой странице** Сведения о атаке выберите кампанию в разделе **История атак.**</span><span class="sxs-lookup"><span data-stu-id="f1914-280">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="f1914-281">В любом из предыдущих действий вы будете перенабираться на страницу с именем **Attack details**.</span><span class="sxs-lookup"><span data-stu-id="f1914-281">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="f1914-282">Сведения, доступные на этой странице для каждого типа кампании, описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="f1914-282">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="f1914-283">Результаты кампании По борьбе с фишингом (сбор учетных данных)</span><span class="sxs-lookup"><span data-stu-id="f1914-283">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="f1914-284">На странице Сведения о **атаке** для каждой кампании доступны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="f1914-284">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="f1914-285">Продолжительность (дата начала,времени и конечной даты/времени) кампании.</span><span class="sxs-lookup"><span data-stu-id="f1914-285">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="f1914-286">**Всего пользователей, целевых**</span><span class="sxs-lookup"><span data-stu-id="f1914-286">**Total users targeted**</span></span>

- <span data-ttu-id="f1914-287">**Успешные** попытки: число пользователей,  которые нажали ссылку и ввели свои учетные данные *(любое* имя пользователя и значение пароля).</span><span class="sxs-lookup"><span data-stu-id="f1914-287">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="f1914-288">**Общая скорость успеха:** процент, который рассчитывается **по** успешным попыткам  /  **Всего целевых пользователей**.</span><span class="sxs-lookup"><span data-stu-id="f1914-288">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="f1914-289">**Быстрый щелчок:** Сколько времени потребовалось первому пользователю, чтобы щелкнуть ссылку после запуска кампании.</span><span class="sxs-lookup"><span data-stu-id="f1914-289">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="f1914-290">**Средний щелчок:** сумма времени, за который каждый щелкнуть ссылку, разделенную количеством пользователей, нажавших ссылку.</span><span class="sxs-lookup"><span data-stu-id="f1914-290">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="f1914-291">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted.**</span><span class="sxs-lookup"><span data-stu-id="f1914-291">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="f1914-292">**Быстрые учетные** данные. Сколько времени потребовалось первому пользователю, чтобы ввести свои учетные данные после запуска кампании.</span><span class="sxs-lookup"><span data-stu-id="f1914-292">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="f1914-293">**Средние учетные** данные: сумма времени ввода учетных данных каждого пользователя, разделенного на число пользователей, вступивших в свои учетные данные.</span><span class="sxs-lookup"><span data-stu-id="f1914-293">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="f1914-294">**Коэффициент успешности** учетных данных: процент, который рассчитывается по (число пользователей, вступивших в свои учетные данные) / **Общее количество целевых пользователей.**</span><span class="sxs-lookup"><span data-stu-id="f1914-294">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="f1914-295">Диаграмма панели, на которую показано **нажатие ссылки** и **предоставленные учетные данные** в день.</span><span class="sxs-lookup"><span data-stu-id="f1914-295">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="f1914-296">Круговой график, на который показано **нажатие ссылки,** предоставленные учетные данные, и **проценты none** для кампании.</span><span class="sxs-lookup"><span data-stu-id="f1914-296">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="f1914-297">В **разделе "Скомпрометированная** информация о пользователях" перечислены сведения пользователей, нажавших ссылку:</span><span class="sxs-lookup"><span data-stu-id="f1914-297">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="f1914-298">Адрес электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="f1914-298">The user's email address</span></span>

  - <span data-ttu-id="f1914-299">Дата и время, когда они щелкнули ссылку.</span><span class="sxs-lookup"><span data-stu-id="f1914-299">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="f1914-300">IP-адрес клиента.</span><span class="sxs-lookup"><span data-stu-id="f1914-300">The client IP address.</span></span>

  - <span data-ttu-id="f1914-301">Сведения о пользовательской версии веб-Windows и веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="f1914-301">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="f1914-302">Для экспорта **результатов** в CSV-файл можно нажать кнопку Экспорт.</span><span class="sxs-lookup"><span data-stu-id="f1914-302">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="f1914-303">Результаты кампании фишинга (вложения)</span><span class="sxs-lookup"><span data-stu-id="f1914-303">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="f1914-304">На странице Сведения о **атаке** для каждой кампании доступны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="f1914-304">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="f1914-305">Продолжительность (дата начала,времени и конечной даты/времени) кампании.</span><span class="sxs-lookup"><span data-stu-id="f1914-305">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="f1914-306">**Всего пользователей, целевых**</span><span class="sxs-lookup"><span data-stu-id="f1914-306">**Total users targeted**</span></span>

- <span data-ttu-id="f1914-307">**Успешные** попытки: количество пользователей, которые открыли или скачали и открыли вложение (предварительный просмотр не считается).</span><span class="sxs-lookup"><span data-stu-id="f1914-307">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="f1914-308">**Общая скорость успеха:** процент, который рассчитывается **по** успешным попыткам  /  **Всего целевых пользователей**.</span><span class="sxs-lookup"><span data-stu-id="f1914-308">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="f1914-309">**Самое быстрое время открытия** вложения: сколько времени потребовалось первому пользователю, чтобы открыть вложение после запуска кампании.</span><span class="sxs-lookup"><span data-stu-id="f1914-309">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="f1914-310">**Среднее время открытия** вложения: сумма, за которую каждый открыл вложение, разделенное на число пользователей, открывавших вложение.</span><span class="sxs-lookup"><span data-stu-id="f1914-310">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="f1914-311">**Показатель успешности** открытия вложения: процент, который рассчитывается по (число пользователей, открывавших вложение) / **Всего пользователей, целевых**.</span><span class="sxs-lookup"><span data-stu-id="f1914-311">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="f1914-312">Результаты кампании Brute Force Password (Dictionary Attack)</span><span class="sxs-lookup"><span data-stu-id="f1914-312">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="f1914-313">На странице Сведения о **атаке** для каждой кампании доступны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="f1914-313">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="f1914-314">Продолжительность (дата начала,времени и конечной даты/времени) кампании.</span><span class="sxs-lookup"><span data-stu-id="f1914-314">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="f1914-315">**Всего пользователей, целевых**</span><span class="sxs-lookup"><span data-stu-id="f1914-315">**Total users targeted**</span></span>

- <span data-ttu-id="f1914-316">**Успешные** попытки: число пользователей, у которых был обнаружен один из указанных паролей.</span><span class="sxs-lookup"><span data-stu-id="f1914-316">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="f1914-317">**Общая скорость успеха:** процент, который рассчитывается **по** успешным попыткам  /  **Всего целевых пользователей**.</span><span class="sxs-lookup"><span data-stu-id="f1914-317">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="f1914-318">В **разделе "Скомпрометированная** пользователи" перечислены адреса электронной почты затронутых пользователей.</span><span class="sxs-lookup"><span data-stu-id="f1914-318">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="f1914-319">Для экспорта **результатов** в CSV-файл можно нажать кнопку Экспорт.</span><span class="sxs-lookup"><span data-stu-id="f1914-319">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="f1914-320">Результаты кампании атаки спрей пароля</span><span class="sxs-lookup"><span data-stu-id="f1914-320">Password spray attack campaign results</span></span>

<span data-ttu-id="f1914-321">На странице Сведения о **атаке** для каждой кампании доступны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="f1914-321">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="f1914-322">Продолжительность (дата начала,времени и конечной даты/времени) кампании.</span><span class="sxs-lookup"><span data-stu-id="f1914-322">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="f1914-323">**Всего пользователей, целевых**</span><span class="sxs-lookup"><span data-stu-id="f1914-323">**Total users targeted**</span></span>

- <span data-ttu-id="f1914-324">**Успешные** попытки: число пользователей, у которых установлено использование указанного пароля.</span><span class="sxs-lookup"><span data-stu-id="f1914-324">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="f1914-325">**Общая скорость успеха:** процент, который рассчитывается **по** успешным попыткам  /  **Всего целевых пользователей**.</span><span class="sxs-lookup"><span data-stu-id="f1914-325">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
