---
title: Имитатор атак в ATP
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
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как с помощью имитатора атак запускать имитированный фишинг и атаки с паролем в организациях Microsoft 365 E5 или ATP с планом 2.
ms.openlocfilehash: 017376d8002811398fe3ce2d94f7c207cd718a78
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825837"
---
# <a name="attack-simulator-in-atp"></a><span data-ttu-id="d5beb-103">Имитатор атак в ATP</span><span class="sxs-lookup"><span data-stu-id="d5beb-103">Attack Simulator in ATP</span></span>

<span data-ttu-id="d5beb-104">Если в вашей организации используется план 2 Office 365 Advanced Threat Protection (ATP) (план 2), который включает в себя средства анализа угроз и [реагирования на них,](office-365-ti.md)вы можете использовать эмулятор атак в Центре соответствия требованиям безопасности & для запуска реализованных атак в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d5beb-104">If your organization has Office 365 Advanced Threat Protection (ATP) Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="d5beb-105">Эти смоделированные атаки помогают идентифицировать и находить уязвивых пользователей, прежде чем на снизу вы не сможете взломать на вашу снизу.</span><span class="sxs-lookup"><span data-stu-id="d5beb-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="d5beb-106">Прочитайте эту статью для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="d5beb-106">Read this article to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d5beb-107">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="d5beb-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d5beb-108">Чтобы открыть Центр безопасности и соответствия требованиям, перейдите по ссылке <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="d5beb-108">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="d5beb-109">Имитатор атак доступен в **имитаторе атак на** \> **управлении угрозами.**</span><span class="sxs-lookup"><span data-stu-id="d5beb-109">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="d5beb-110">Перейдите непосредственно к имитатору атак, <https://protection.office.com/attacksimulator> откройте.</span><span class="sxs-lookup"><span data-stu-id="d5beb-110">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="d5beb-111">Дополнительные сведения о доступности имитатора атак в различных подписках на Microsoft 365 см. в [описании службы Office 365 Advanced Threat Protection.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="d5beb-111">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="d5beb-112">Вы должны быть членом группы **ролей "Управление организацией"** **или "Администратор** безопасности".</span><span class="sxs-lookup"><span data-stu-id="d5beb-112">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="d5beb-113">Дополнительные сведения о группах ролей в Центре безопасности и соответствия требованиям см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d5beb-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="d5beb-114">Для создания кампаний и управления ими в симуляторе атак ваша учетная запись должна быть настроена для использования многофакторной проверки подлинности (MFA).</span><span class="sxs-lookup"><span data-stu-id="d5beb-114">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="d5beb-115">Инструкции см. в статье ["Настройка многофакторной проверки подлинности".](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)</span><span class="sxs-lookup"><span data-stu-id="d5beb-115">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="d5beb-116">Фишинговые кампании собирают и обрабатывают события в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="d5beb-116">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="d5beb-117">Данные исторических кампаний будут доступны в течение 90 дней после запуска кампании.</span><span class="sxs-lookup"><span data-stu-id="d5beb-117">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="d5beb-118">Соответствующих командлетов PowerShell для имитатора атак не существует.</span><span class="sxs-lookup"><span data-stu-id="d5beb-118">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="d5beb-119">Развитые фишинговые кампании</span><span class="sxs-lookup"><span data-stu-id="d5beb-119">Spear phishing campaigns</span></span>

<span data-ttu-id="d5beb-120">*Фишинг — это общий* термин атак, которые старались украсть конфиденциальную информацию в сообщениях, кажущихся как надежных, так и доверенных отправителей.</span><span class="sxs-lookup"><span data-stu-id="d5beb-120">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="d5beb-121">*Зеркальные фишинг —* это целевая фишинговая атака, использующая сфокусированное и настраиваемое содержимое, специально подобранное указанным получателям (обычно после получения получателей злоумышленником).</span><span class="sxs-lookup"><span data-stu-id="d5beb-121">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="d5beb-122">В симуляторе атак доступны два различных типа специализированных фишинговых кампаний:</span><span class="sxs-lookup"><span data-stu-id="d5beb-122">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="d5beb-123">**Земление от радозии (свяжение**с учетными данными).Атака пытается синхронизировать получателей для перехода по URL-адресу в сообщении.</span><span class="sxs-lookup"><span data-stu-id="d5beb-123">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="d5beb-124">Если пользователь перейдет по ссылке, ему будет отображен запрос на ввод учетных данных.</span><span class="sxs-lookup"><span data-stu-id="d5beb-124">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="d5beb-125">В этом случае нужно перенестись в одно из следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="d5beb-125">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="d5beb-126">Страница по умолчанию, в которой описывается, что это всего лишь тест и ее внимание раскрыто.</span><span class="sxs-lookup"><span data-stu-id="d5beb-126">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Что пользователь видит, щелкнут ссылку для фишинга, и вводят свои учетные данные](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="d5beb-128">Указанная пользовательская страница (URL-адрес).</span><span class="sxs-lookup"><span data-stu-id="d5beb-128">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="d5beb-129">**Проверка с ветвления фишинга (вложение).** Атака пытается сообщить получателям, чтобы открыть в сообщении вложение DOCX или PDF.</span><span class="sxs-lookup"><span data-stu-id="d5beb-129">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="d5beb-130">Вложение содержит то же содержимое, которое содержит стандартную фишинговую ссылку, но первое предложение начинается с " , вы видите это сообщение как недавнее сообщение электронной почты, которое \<Display Name\> вы открывали...".</span><span class="sxs-lookup"><span data-stu-id="d5beb-130">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="d5beb-131">В настоящее время срок действия разностных фишинговых кампаний в имитаторе атак не ограничен.</span><span class="sxs-lookup"><span data-stu-id="d5beb-131">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="d5beb-132">Создание спектральной фишинг-кампании</span><span class="sxs-lookup"><span data-stu-id="d5beb-132">Create a spear phishing campaign</span></span>

<span data-ttu-id="d5beb-133">Важной частью любой из злоумышленников является внешний вид и функции сообщения, отправляемого целевым получателям.</span><span class="sxs-lookup"><span data-stu-id="d5beb-133">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="d5beb-134">При создании и настройке электронного сообщения можно использовать следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="d5beb-134">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="d5beb-135">**Используйте встроенный шаблон электронной почты:** доступны два встроенных шаблона: **Prize Inaway (Высота и** **обновление зарплаты).**</span><span class="sxs-lookup"><span data-stu-id="d5beb-135">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="d5beb-136">Вы можете дополнительно настраивать некоторые, все или не вообще ни одного из свойств электронной почты из шаблона при создании и запуске кампании.</span><span class="sxs-lookup"><span data-stu-id="d5beb-136">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="d5beb-137">**Создайте повторно используемый шаблон электронной почты:** после создания и сохранения шаблона электронной почты можно снова использовать его в последующих кампаниях с фишинговыми кампаниями.</span><span class="sxs-lookup"><span data-stu-id="d5beb-137">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="d5beb-138">Вы можете дополнительно настраивать некоторые, все или не вообще ни одного из свойств электронной почты из шаблона при создании и запуске кампании.</span><span class="sxs-lookup"><span data-stu-id="d5beb-138">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="d5beb-139">**Создайте электронное сообщение с помощью мастера:** вы можете создать сообщение электронной почты прямо в мастере при создании и запуске специальной фишинга.</span><span class="sxs-lookup"><span data-stu-id="d5beb-139">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="d5beb-140">Шаг 1 (необязательно). Создание настраиваемого шаблона электронной почты</span><span class="sxs-lookup"><span data-stu-id="d5beb-140">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="d5beb-141">Если вы собираетесь использовать один из встроенных шаблонов или создать сообщение электронной почты непосредственно в мастере, этот шаг можно пропустить.</span><span class="sxs-lookup"><span data-stu-id="d5beb-141">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="d5beb-142">В Центре безопасности & требованиям откройте **эмулятор атак на** \> **управление угрозами.**</span><span class="sxs-lookup"><span data-stu-id="d5beb-142">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="d5beb-143">На странице **"Имитация атак"** в разделе "Отраженный **фишинг" ("Варанттрафик учетных данных")** или "Спецификация" **выберите** "Сведения об **атаке".**</span><span class="sxs-lookup"><span data-stu-id="d5beb-143">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="d5beb-144">Неважно, где создавать шаблон.</span><span class="sxs-lookup"><span data-stu-id="d5beb-144">It doesn't matter where you create the template.</span></span> <span data-ttu-id="d5beb-145">Доступные в шаблоне параметры одинаковы для обоих типов фишинговых атак.</span><span class="sxs-lookup"><span data-stu-id="d5beb-145">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="d5beb-146">На **открывшейся странице** "Сведения об атаке" в разделе **"Фишинговые** шаблоны" в **области "Создание шаблонов"** выберите **"Новый шаблон".**</span><span class="sxs-lookup"><span data-stu-id="d5beb-146">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="d5beb-147">Мастер **настройки шаблона фишинга** запускается в новом всплывающем элементе.</span><span class="sxs-lookup"><span data-stu-id="d5beb-147">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="d5beb-148">На **начальном** этапе введите уникальное отображаемое имя шаблона и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="d5beb-148">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="d5beb-149">В разделе **"Настройка сведений электронной** почты" настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="d5beb-149">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="d5beb-150">**От (имя)**— отображаемое имя, используемое для отправителя сообщения.</span><span class="sxs-lookup"><span data-stu-id="d5beb-150">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="d5beb-151">**From (Электронная почта):** электронный адрес отправителя.</span><span class="sxs-lookup"><span data-stu-id="d5beb-151">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="d5beb-152">**URL-адрес фишингового сервера**входа. Щелкните раскрывающийся список и выберите один из доступных URL-адресов из списка.</span><span class="sxs-lookup"><span data-stu-id="d5beb-152">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="d5beb-153">Этот URL-адрес, который будет запоминаться для перехода пользователей.</span><span class="sxs-lookup"><span data-stu-id="d5beb-153">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="d5beb-154">Имеются следующие варианты.</span><span class="sxs-lookup"><span data-stu-id="d5beb-154">The choices are:</span></span>

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
     > - <span data-ttu-id="d5beb-155">Все URL-адреса намеренно являются http, а не https.</span><span class="sxs-lookup"><span data-stu-id="d5beb-155">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="d5beb-156">Служба репутации URL-адресов может определить один или несколько из них как небезопасные.</span><span class="sxs-lookup"><span data-stu-id="d5beb-156">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="d5beb-157">Проверьте доступность URL-адреса в поддерживаемых веб-браузерах, прежде чем использовать его URL-адрес в фишинговой кампании.</span><span class="sxs-lookup"><span data-stu-id="d5beb-157">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="d5beb-158">**URL-адрес пользовательской страницы: введите**дополнительную страницу, на которой пользователи берутся, если щелкнут ссылку для фишинга и введите свои учетные данные.</span><span class="sxs-lookup"><span data-stu-id="d5beb-158">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="d5beb-159">Эта ссылка заменяет только страницу с фирнантной страницей по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d5beb-159">This link replaces the default landing page.</span></span> <span data-ttu-id="d5beb-160">Например, если у вас есть внутреннее обучение по информированию, здесь можно указать этот URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="d5beb-160">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="d5beb-161">**Category**: этот параметр в настоящее время не используется (вводимые элементы игнорируются).</span><span class="sxs-lookup"><span data-stu-id="d5beb-161">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="d5beb-162">**Subject**( **Поле Тема** сообщения электронной почты).</span><span class="sxs-lookup"><span data-stu-id="d5beb-162">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="d5beb-163">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d5beb-163">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="d5beb-164">На **составлении** электронного письма создайте текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="d5beb-164">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="d5beb-165">Вкладку **"Электронная почта"** можно использовать на вкладке электронной почты (формат HTML) или **вкладке "Источник"** (необработанный HTML-код).</span><span class="sxs-lookup"><span data-stu-id="d5beb-165">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="d5beb-166">Форматирование HTML может быть так же простой или сложной, как и нужно.</span><span class="sxs-lookup"><span data-stu-id="d5beb-166">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="d5beb-167">Чтобы повысить надежность сообщения в почтовом клиенте получателя, вы можете вставлять изображения и текст.</span><span class="sxs-lookup"><span data-stu-id="d5beb-167">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="d5beb-168">`${username}` вставляет имя получателя.</span><span class="sxs-lookup"><span data-stu-id="d5beb-168">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="d5beb-169">`${loginserverurl}` Вставляет из **предыдущего шага URL-адрес** фишингового сервера для входа.</span><span class="sxs-lookup"><span data-stu-id="d5beb-169">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="d5beb-170">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d5beb-170">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="d5beb-171">В шаге **подтверждения** нажмите кнопку **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="d5beb-171">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="d5beb-172">Шаг 2. Создание и запуск специальной фишинг-кампании</span><span class="sxs-lookup"><span data-stu-id="d5beb-172">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="d5beb-173">В Центре безопасности & требованиям откройте **эмулятор атак на** \> **управление угрозами.**</span><span class="sxs-lookup"><span data-stu-id="d5beb-173">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="d5beb-174">На странице **"Имитация атак"** выберите один из следующих вариантов в зависимости от типа создаваемой кампании.</span><span class="sxs-lookup"><span data-stu-id="d5beb-174">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="d5beb-175">В разделе **"Снижение фишинга " ("Восприятие учетных данных")** щелкните команду **Запускаа** атаки или щелкните **"Сведения об** \> **атаке запуска".**</span><span class="sxs-lookup"><span data-stu-id="d5beb-175">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="d5beb-176">В разделе **"Свободный фишинг "Вложение")** выберите команду запуска **атаки** или щелкните **«Сведения об атаке** \> **на запуск атаки».**</span><span class="sxs-lookup"><span data-stu-id="d5beb-176">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="d5beb-177">Мастер **настройки фишинговых атак** запускается в новом всплывающем элементе.</span><span class="sxs-lookup"><span data-stu-id="d5beb-177">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="d5beb-178">На **начальном** этапе выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="d5beb-178">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="d5beb-179">В поле **"Имя"** введите уникальное отображаемое имя кампании.</span><span class="sxs-lookup"><span data-stu-id="d5beb-179">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="d5beb-180">Не нажимайте **кнопку "Использовать**шаблон", так как вы создадите сообщение электронной почты позднее в мастере.</span><span class="sxs-lookup"><span data-stu-id="d5beb-180">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="d5beb-181">Щелкните **"Использовать шаблон"** и выберите встроенный или настраиваемый шаблон сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d5beb-181">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="d5beb-182">После выбора шаблона поле **"Имя" автоматически** заполняется на основе шаблона, но вы можете изменить имя.</span><span class="sxs-lookup"><span data-stu-id="d5beb-182">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![Начальная страница фишинга](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="d5beb-184">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d5beb-184">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="d5beb-185">В **действии получателей "Конечные** пользователи" выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="d5beb-185">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="d5beb-186">Щелкните **адресную** книгу, чтобы выбрать получателей (пользователей или группы) для кампании.</span><span class="sxs-lookup"><span data-stu-id="d5beb-186">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="d5beb-187">У каждого получателя должен быть почтовый ящик Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d5beb-187">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="d5beb-188">Если **щелкнуть Filter** **и применить без** ввода критериев поиска, все получатели возвращаются и добавляются в кампанию.</span><span class="sxs-lookup"><span data-stu-id="d5beb-188">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="d5beb-189">**Нажмите** **кнопку "Импорт файла",** чтобы импортировать файл с разделителями-запятыми или электронные адреса, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="d5beb-189">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="d5beb-190">Каждая строка должна содержать электронный адрес получателя.</span><span class="sxs-lookup"><span data-stu-id="d5beb-190">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="d5beb-191">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d5beb-191">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="d5beb-192">В разделе **"Настройка сведений электронной** почты" настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="d5beb-192">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="d5beb-193">Если шаблон был выбран на **начальном этапе,** большинство из этих значений уже настроены, но их можно изменить.</span><span class="sxs-lookup"><span data-stu-id="d5beb-193">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="d5beb-194">**От (имя)**— отображаемое имя, используемое для отправителя сообщения.</span><span class="sxs-lookup"><span data-stu-id="d5beb-194">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="d5beb-195">**From (Электронная почта):** электронный адрес отправителя.</span><span class="sxs-lookup"><span data-stu-id="d5beb-195">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="d5beb-196">Вы можете ввести реальный или накопительный адрес электронной почты из домена электронной почты организации или ввести реальный или подсказки внешнего адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d5beb-196">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="d5beb-197">Допустимый адрес электронной почты отправителя в вашей организации фактически будет разрешен в почтовом клиенте получателя.</span><span class="sxs-lookup"><span data-stu-id="d5beb-197">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="d5beb-198">**URL-адрес фишингового сервера**входа. Щелкните раскрывающийся список и выберите один из доступных URL-адресов из списка.</span><span class="sxs-lookup"><span data-stu-id="d5beb-198">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="d5beb-199">Этот URL-адрес, который будет запоминаться для перехода пользователей.</span><span class="sxs-lookup"><span data-stu-id="d5beb-199">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="d5beb-200">Имеются следующие варианты.</span><span class="sxs-lookup"><span data-stu-id="d5beb-200">The choices are:</span></span>

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
     > - <span data-ttu-id="d5beb-201">Все URL-адреса намеренно являются http, а не https.</span><span class="sxs-lookup"><span data-stu-id="d5beb-201">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="d5beb-202">Служба репутации URL-адресов может определить один или несколько из них как небезопасные.</span><span class="sxs-lookup"><span data-stu-id="d5beb-202">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="d5beb-203">Проверьте доступность URL-адреса в поддерживаемых веб-браузерах, прежде чем использовать его URL-адрес в фишинговой кампании.</span><span class="sxs-lookup"><span data-stu-id="d5beb-203">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="d5beb-204">Необходимо выбрать URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="d5beb-204">You are required to select a URL.</span></span> <span data-ttu-id="d5beb-205">Для **кампаний На** основе земли можно удалить ссылку из текста сообщения на следующем шаге (в противном случае сообщение будет содержать как **ссылку,** так и вложение).</span><span class="sxs-lookup"><span data-stu-id="d5beb-205">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="d5beb-206">**Тип вложения.** Этот параметр доступен только **для проводных** кампаний (Ориентироваться)</span><span class="sxs-lookup"><span data-stu-id="d5beb-206">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="d5beb-207">Щелкните раскрывающийся список и **выберите.. DOCX или** **. PDF-файл** из списка.</span><span class="sxs-lookup"><span data-stu-id="d5beb-207">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="d5beb-208">**Имя вложения**— этот параметр доступен только в кампаниях **(Ориентироваться)**</span><span class="sxs-lookup"><span data-stu-id="d5beb-208">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="d5beb-209">Введите имя файла для вложения DOCX или PDF.</span><span class="sxs-lookup"><span data-stu-id="d5beb-209">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="d5beb-210">**URL-адрес пользовательской страницы: введите**дополнительную страницу, на которой пользователи берутся, если щелкнут ссылку для фишинга и введите свои учетные данные.</span><span class="sxs-lookup"><span data-stu-id="d5beb-210">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="d5beb-211">Эта ссылка заменяет только страницу с фирнантной страницей по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d5beb-211">This link replaces the default landing page.</span></span> <span data-ttu-id="d5beb-212">Например, если у вас есть внутреннее обучение по информированию, здесь можно указать этот URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="d5beb-212">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="d5beb-213">**Subject**( **Поле Тема** сообщения электронной почты).</span><span class="sxs-lookup"><span data-stu-id="d5beb-213">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="d5beb-214">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d5beb-214">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="d5beb-215">На **составлении** электронного письма создайте текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="d5beb-215">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="d5beb-216">Если на начальном этапе **вы** выбрали шаблон, текст сообщения уже настроен, но его можно настроить.</span><span class="sxs-lookup"><span data-stu-id="d5beb-216">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="d5beb-217">Вкладку **"Электронная почта"** можно использовать на вкладке электронной почты (формат HTML) или **вкладке "Источник"** (необработанный HTML-код).</span><span class="sxs-lookup"><span data-stu-id="d5beb-217">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="d5beb-218">Форматирование HTML может быть так же простой или сложной, как и нужно.</span><span class="sxs-lookup"><span data-stu-id="d5beb-218">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="d5beb-219">Чтобы повысить надежность сообщения в почтовом клиенте получателя, вы можете вставлять изображения и текст.</span><span class="sxs-lookup"><span data-stu-id="d5beb-219">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="d5beb-220">`${username}` вставляет имя получателя.</span><span class="sxs-lookup"><span data-stu-id="d5beb-220">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="d5beb-221">`${loginserverurl}`Вставляет значение **URL-адреса фишингового сервера входа.**</span><span class="sxs-lookup"><span data-stu-id="d5beb-221">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="d5beb-222">Для **кампаний (в** том случае, если кампании на основе вложений) необходимо удалить ссылку из **and** текста сообщения (в противном случае сообщение будет содержать ссылку и вложение, а переходы по ссылкам не отслеживаются в кампании вложений).</span><span class="sxs-lookup"><span data-stu-id="d5beb-222">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![Составление текста сообщения](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="d5beb-224">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d5beb-224">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="d5beb-225">В **Confirm** шаге подтверждения **нажмите кнопку** "Готово", чтобы запустить кампанию.</span><span class="sxs-lookup"><span data-stu-id="d5beb-225">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="d5beb-226">Фишинговое сообщение доставляется получателям.</span><span class="sxs-lookup"><span data-stu-id="d5beb-226">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="d5beb-227">Кампании по атакам паролей</span><span class="sxs-lookup"><span data-stu-id="d5beb-227">Password attack campaigns</span></span>

<span data-ttu-id="d5beb-228">*Атака с* паролями пытается угадать пароли учетных записей пользователей в организации (как правило, после идентификации одной или нескольких допустимых учетных записей пользователя злоумышленником).</span><span class="sxs-lookup"><span data-stu-id="d5beb-228">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="d5beb-229">В симуляторе атак для проверки сложности паролей пользователей доступны два различных типа кампаний, указанных в специальности паролей.</span><span class="sxs-lookup"><span data-stu-id="d5beb-229">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="d5beb-230">**Метод подбора пароля (атака перебором по словарю):** *атака методом* подбора или атака перебором по словарю использует большой файл словаря паролей на учетной записи пользователя с надежностью, что один из них будет работать (множество паролей для одной учетной записи). *dictionary*</span><span class="sxs-lookup"><span data-stu-id="d5beb-230">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="d5beb-231">Неправильная блокировка пароля помогает проводить атаки методом подбора пароля.</span><span class="sxs-lookup"><span data-stu-id="d5beb-231">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="d5beb-232">Для атак с словарем можно указать один или несколько паролей для проверки подлинности (вручную введенных или введенных в выгрузку файлах), а также одного или нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="d5beb-232">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="d5beb-233">**Атака распыления пароля:** *атаки распыления* пароля используют тот же пароль, что и в списке учетных записей пользователей (один пароль для многих учетных записей).</span><span class="sxs-lookup"><span data-stu-id="d5beb-233">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="d5beb-234">Обнаружение атак методом подбора пароля усложняется обнаружение, чем подбор пароля (вероятность успешной резки при попыток перебора пароля злоумышленнику на несколько десятков или сотен учетных записей без риска неправильноблокировки пароля пользователя).</span><span class="sxs-lookup"><span data-stu-id="d5beb-234">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="d5beb-235">Для атаки с распылежением пароля можно указать только один пароль, который можно попробовать, и можно указать одного или нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="d5beb-235">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="d5beb-236">Атаки на пароли в Имитаторе атак передают запросы имени пользователя и сложную проверку подлинности пароля в конечную точку, поэтому они также работают с другими методами проверки подлинности (AD FS, синхронизация хэша паролей, сквозная проверка, PingFederate и т. д.).</span><span class="sxs-lookup"><span data-stu-id="d5beb-236">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="d5beb-237">Для пользователей, для которых включена многофакторная идентификация, даже если атака пароля повторит попытку фактического пароля, эта попытка всегда будет регистрироваться как ошибка (другими словами, пользователи MFA никогда не будут отображаться в **подсчете** успешных попыток кампании).</span><span class="sxs-lookup"><span data-stu-id="d5beb-237">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="d5beb-238">Это ожидаемый результат.</span><span class="sxs-lookup"><span data-stu-id="d5beb-238">This is the expected result.</span></span> <span data-ttu-id="d5beb-239">MFA — это основной метод защиты от атак с паролем.</span><span class="sxs-lookup"><span data-stu-id="d5beb-239">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="d5beb-240">Создание и запуск кампании по атаке пароля</span><span class="sxs-lookup"><span data-stu-id="d5beb-240">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="d5beb-241">В Центре безопасности & требованиям откройте **эмулятор атак на** \> **управление угрозами.**</span><span class="sxs-lookup"><span data-stu-id="d5beb-241">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="d5beb-242">На странице **"Имитация атак"** выберите один из следующих вариантов в зависимости от типа создаваемой кампании.</span><span class="sxs-lookup"><span data-stu-id="d5beb-242">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="d5beb-243">В разделе **"Пароль перебора брюзов "Перебор пароля" (Атака перебором по словарю)** щелкните команду **Запускать атаки** или щелкните **"Сведения об** \> **атаке запуска".**</span><span class="sxs-lookup"><span data-stu-id="d5beb-243">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="d5beb-244">в разделе **атака с распылежением** пароля щелкните "Запуск **атаки"** или щелкните "Сведения **об атаке** \> **запуска".**</span><span class="sxs-lookup"><span data-stu-id="d5beb-244">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="d5beb-245">Мастер **настройки атак нановнова** запустится с новым всплывающим элементом.</span><span class="sxs-lookup"><span data-stu-id="d5beb-245">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="d5beb-246">На **начальном этапе** введите уникальное отображаемое имя кампании и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="d5beb-246">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="d5beb-247">В **шаге "Конечные** пользователи" выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="d5beb-247">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="d5beb-248">Щелкните **адресную** книгу, чтобы выбрать получателей (пользователей или группы) для кампании.</span><span class="sxs-lookup"><span data-stu-id="d5beb-248">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="d5beb-249">У каждого получателя должен быть почтовый ящик Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d5beb-249">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="d5beb-250">Если **щелкнуть Filter** **и применить без** ввода критериев поиска, все получатели возвращаются и добавляются в кампанию.</span><span class="sxs-lookup"><span data-stu-id="d5beb-250">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="d5beb-251">**Нажмите** **кнопку "Импорт файла",** чтобы импортировать файл с разделителями-запятыми или электронные адреса, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="d5beb-251">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="d5beb-252">Каждая строка должна содержать электронный адрес получателя.</span><span class="sxs-lookup"><span data-stu-id="d5beb-252">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="d5beb-253">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d5beb-253">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="d5beb-254">В **шаге "Выбор параметров атак"** выберите, что делать, в зависимости от типа кампании:</span><span class="sxs-lookup"><span data-stu-id="d5beb-254">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="d5beb-255">**Брюксор ное перебор пароля (Атака перебором по словарю):** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="d5beb-255">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="d5beb-256">**Введите пароли вручную:** в **поле ввода пароля** введите пароль и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="d5beb-256">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="d5beb-257">Повторите этот шаг необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="d5beb-257">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="d5beb-258">**Загрузите пароли из файла словаря:** нажмите "Отправить", чтобы импортировать существующий текстовый файл, содержащий по одному паролю в каждой строке, и пустая последняя строка. **Upload**</span><span class="sxs-lookup"><span data-stu-id="d5beb-258">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="d5beb-259">Размер текстового файла не должен превышать 10 МБ и не может содержать более 30000 паролей.</span><span class="sxs-lookup"><span data-stu-id="d5beb-259">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="d5beb-260">**Атака с распылежением**пароля: **в паролях, которые необходимо использовать в атаке,** введите один пароль.</span><span class="sxs-lookup"><span data-stu-id="d5beb-260">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="d5beb-261">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d5beb-261">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="d5beb-262">В **Confirm** шаге подтверждения **нажмите кнопку** "Готово", чтобы запустить кампанию.</span><span class="sxs-lookup"><span data-stu-id="d5beb-262">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="d5beb-263">Указанные пароли применятся к указанным пользователям.</span><span class="sxs-lookup"><span data-stu-id="d5beb-263">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="d5beb-264">Просмотр результатов кампании</span><span class="sxs-lookup"><span data-stu-id="d5beb-264">View campaign results</span></span>

<span data-ttu-id="d5beb-265">После запуска кампании можно проверить ход выполнения и результаты на главной странице **атак** "Смоделирование".</span><span class="sxs-lookup"><span data-stu-id="d5beb-265">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="d5beb-266">В активных кампаниях отображается строка состояния, выполненное значение процента и "(количество завершенных пользователей) количество пользователей)" (всего пользователей).</span><span class="sxs-lookup"><span data-stu-id="d5beb-266">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="d5beb-267">При нажатии **кнопки** "Обновить" будет обновляться ход выполнения всех активных кампаний.</span><span class="sxs-lookup"><span data-stu-id="d5beb-267">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="d5beb-268">Вы также можете **нажать кнопку "Завершение",** чтобы остановить активную кампанию.</span><span class="sxs-lookup"><span data-stu-id="d5beb-268">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="d5beb-269">После завершения кампании состояние "Атака **завершена".**</span><span class="sxs-lookup"><span data-stu-id="d5beb-269">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="d5beb-270">Чтобы просмотреть результаты кампании, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="d5beb-270">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="d5beb-271">На главной **странице "Смоделирование атак"** нажмите кнопку **"Просмотреть отчет"** под именем кампании.</span><span class="sxs-lookup"><span data-stu-id="d5beb-271">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="d5beb-272">На главной странице **моделировании атак щелкните** **"Сведения об атаке"** в разделе для типа атаки.</span><span class="sxs-lookup"><span data-stu-id="d5beb-272">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="d5beb-273">На **открывшейся странице** "Сведения об атаке" выберите кампанию в разделе **"История атак".**</span><span class="sxs-lookup"><span data-stu-id="d5beb-273">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="d5beb-274">Любое из описанных выше действий позволит перенагуть страницу под названием "Сведения об **атаке".**</span><span class="sxs-lookup"><span data-stu-id="d5beb-274">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="d5beb-275">Сведения, доступные на этой странице для каждого типа кампании, описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="d5beb-275">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="d5beb-276">Результаты кампании от радостивания отражения (Phishing)</span><span class="sxs-lookup"><span data-stu-id="d5beb-276">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="d5beb-277">Следующие сведения доступны на странице **сведений об атаке** для каждой кампании:</span><span class="sxs-lookup"><span data-stu-id="d5beb-277">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="d5beb-278">Длительность кампании (дата/время начала и дата и время окончания).</span><span class="sxs-lookup"><span data-stu-id="d5beb-278">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="d5beb-279">**Всего пользователей, нацеленных на**</span><span class="sxs-lookup"><span data-stu-id="d5beb-279">**Total users targeted**</span></span>

- <span data-ttu-id="d5beb-280">**Число пользователей,** которые щелкнули **and** ссылку и ввели свои учетные данные *(любое значение* имени пользователя и пароля).</span><span class="sxs-lookup"><span data-stu-id="d5beb-280">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="d5beb-281">**Общая доля успешности:** процент, вычисленный успешными **попытками, идентифицированным**  /  **total users.**</span><span class="sxs-lookup"><span data-stu-id="d5beb-281">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="d5beb-282">**Быстрый щелчок:** время, которое первый пользователь потребовал нажать на ссылку после запуска кампании.</span><span class="sxs-lookup"><span data-stu-id="d5beb-282">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="d5beb-283">**Среднее число переходов:** сумма времени, деленная на количество пользователей, щелкнувших ссылку.</span><span class="sxs-lookup"><span data-stu-id="d5beb-283">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="d5beb-284">**Показатель количества переходов:** процент, рассчитанный (количество пользователей, щелкнувших по ссылке) / **Всего пользователей, указанных.**</span><span class="sxs-lookup"><span data-stu-id="d5beb-284">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="d5beb-285">**Быстрые учетные данные:** время, которое первый пользователь ввел свои учетные данные после запуска кампании.</span><span class="sxs-lookup"><span data-stu-id="d5beb-285">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="d5beb-286">**Среднее количество учетных данных:** сумма времени, которое потребовалось всем ввести свои учетные данные на количество пользователей, которые ввели свои учетные данные.</span><span class="sxs-lookup"><span data-stu-id="d5beb-286">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="d5beb-287">**Показатель успешности данных:** процент, рассчитанный по (числу пользователей, введенных в учетные данные) / **Общее количество пользователей, ориентированных на пользователей.**</span><span class="sxs-lookup"><span data-stu-id="d5beb-287">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="d5beb-288">Линейчатая диаграмма, на которой **показаны нажатые параметры** **ссылки и указанные** числа ежедневно.</span><span class="sxs-lookup"><span data-stu-id="d5beb-288">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="d5beb-289">График кругов, на котором показаны нажатая **ссылка,** **введенные**учетные данные и не **доли** этих процентов.</span><span class="sxs-lookup"><span data-stu-id="d5beb-289">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="d5beb-290">В **разделе "Скомпрометированные** пользователи" перечислены сведения о пользователях, которые щелкнули ссылку:</span><span class="sxs-lookup"><span data-stu-id="d5beb-290">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="d5beb-291">Адрес электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="d5beb-291">The user's email address</span></span>

  - <span data-ttu-id="d5beb-292">Дата и время перехода по ссылке.</span><span class="sxs-lookup"><span data-stu-id="d5beb-292">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="d5beb-293">IP-адрес клиента.</span><span class="sxs-lookup"><span data-stu-id="d5beb-293">The client IP address.</span></span>

  - <span data-ttu-id="d5beb-294">Сведения о версии Windows и веб-браузере пользователя.</span><span class="sxs-lookup"><span data-stu-id="d5beb-294">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="d5beb-295">Вы можете **щелкнуть** "Экспорт", чтобы экспортировать результаты в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="d5beb-295">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="d5beb-296">Результаты кампании от радостив (вложений)</span><span class="sxs-lookup"><span data-stu-id="d5beb-296">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="d5beb-297">Следующие сведения доступны на странице **сведений об атаке** для каждой кампании:</span><span class="sxs-lookup"><span data-stu-id="d5beb-297">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="d5beb-298">Длительность кампании (дата/время начала и дата и время окончания).</span><span class="sxs-lookup"><span data-stu-id="d5beb-298">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="d5beb-299">**Всего пользователей, нацеленных на**</span><span class="sxs-lookup"><span data-stu-id="d5beb-299">**Total users targeted**</span></span>

- <span data-ttu-id="d5beb-300">**Успешных**попыток: количество пользователей, открывавших или скачавших и открывших вложение (предварительная версия не учитывается).</span><span class="sxs-lookup"><span data-stu-id="d5beb-300">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="d5beb-301">**Общая доля успешности:** процент, вычисленный успешными **попытками, идентифицированным**  /  **total users.**</span><span class="sxs-lookup"><span data-stu-id="d5beb-301">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="d5beb-302">**Самое быстрое открытие вложения:** сколько времени потребовалось первому пользователю открыть вложение после запуска кампании.</span><span class="sxs-lookup"><span data-stu-id="d5beb-302">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="d5beb-303">**Среднее время открытия вложения:** сумма времени, спомощьтельная продолжительность открытия вложения на количество пользователей, открывших вложение.</span><span class="sxs-lookup"><span data-stu-id="d5beb-303">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="d5beb-304">**Частота успешности открытия**вложений: процент, рассчитанный (количество пользователей, открывших вложение) / **общее количество прогнозированных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="d5beb-304">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="d5beb-305">Результаты кампании пароля (атаки перебором по словарю)</span><span class="sxs-lookup"><span data-stu-id="d5beb-305">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="d5beb-306">Следующие сведения доступны на странице **сведений об атаке** для каждой кампании:</span><span class="sxs-lookup"><span data-stu-id="d5beb-306">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="d5beb-307">Длительность кампании (дата/время начала и дата и время окончания).</span><span class="sxs-lookup"><span data-stu-id="d5beb-307">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="d5beb-308">**Всего пользователей, нацеленных на**</span><span class="sxs-lookup"><span data-stu-id="d5beb-308">**Total users targeted**</span></span>

- <span data-ttu-id="d5beb-309">**Успешные**попытки: количество пользователей, которые были найдены по паролям.</span><span class="sxs-lookup"><span data-stu-id="d5beb-309">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="d5beb-310">**Общая доля успешности:** процент, вычисленный успешными **попытками, идентифицированным**  /  **total users.**</span><span class="sxs-lookup"><span data-stu-id="d5beb-310">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="d5beb-311">В **разделе "Скомпрометированные** пользователи" перечислены адреса электронной почты затронутых пользователей.</span><span class="sxs-lookup"><span data-stu-id="d5beb-311">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="d5beb-312">Вы можете **щелкнуть** "Экспорт", чтобы экспортировать результаты в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="d5beb-312">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="d5beb-313">Результаты противодействия атакам, распыления пароля</span><span class="sxs-lookup"><span data-stu-id="d5beb-313">Password spray attack campaign results</span></span>

<span data-ttu-id="d5beb-314">Следующие сведения доступны на странице **сведений об атаке** для каждой кампании:</span><span class="sxs-lookup"><span data-stu-id="d5beb-314">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="d5beb-315">Длительность кампании (дата/время начала и дата и время окончания).</span><span class="sxs-lookup"><span data-stu-id="d5beb-315">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="d5beb-316">**Всего пользователей, нацеленных на**</span><span class="sxs-lookup"><span data-stu-id="d5beb-316">**Total users targeted**</span></span>

- <span data-ttu-id="d5beb-317">**Успешные**попытки: количество пользователей, которые обнаружили, используя указанный пароль.</span><span class="sxs-lookup"><span data-stu-id="d5beb-317">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="d5beb-318">**Общая доля успешности:** процент, вычисленный успешными **попытками, идентифицированным**  /  **total users.**</span><span class="sxs-lookup"><span data-stu-id="d5beb-318">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
