---
title: Имитатор атак в Microsoft Defender для Office 365
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
description: Администраторы могут научиться использовать имитатор атак для имитации фишинговых атак и атак с использованием паролей в организациях Microsoft 365 E5 или Microsoft Defender для Office 365 (план 2).
ms.openlocfilehash: a53ffee29ce928910b8c4add245c002ae6eb03da
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2021
ms.locfileid: "49788115"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="e5653-103">Имитатор атак в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="e5653-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e5653-104">Если в вашей организации есть Microsoft Defender для Office 365 (план 2), который включает возможности исследования угроз и реагирования на [них,](office-365-ti.md)вы можете использовать имитатор атак в Центре безопасности и соответствия требованиям & для выполнения реалистичных сценариев атак в организации.</span><span class="sxs-lookup"><span data-stu-id="e5653-104">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="e5653-105">Эти смоделированные атаки помогут вам определить и найти уязвимых пользователей, прежде чем реальные атаки поляв на вашу нижнюю часть.</span><span class="sxs-lookup"><span data-stu-id="e5653-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="e5653-106">Чтобы узнать больше, ознакомьтесь с этой статьей.</span><span class="sxs-lookup"><span data-stu-id="e5653-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="e5653-107">Имитация атак и учебные данные хранятся вместе с другими данными клиентов для служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e5653-107">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="e5653-108">Дополнительные сведения см. в [расположениях данных Microsoft 365.](/microsoft-365/enterprise/o365-data-locations)</span><span class="sxs-lookup"><span data-stu-id="e5653-108">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

> [!TIP]
> <span data-ttu-id="e5653-109">Обучение моделированию атак доступно для предварительной версии в Центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e5653-109">Attack simulation training is available for public preview in the Microsoft 365 security center.</span></span> <span data-ttu-id="e5653-110">Чтобы узнать больше, ознакомьтесь с имитацией фишинговой атаки с [помощью Microsoft Defender для Office 365.](attack-simulation-training.md)</span><span class="sxs-lookup"><span data-stu-id="e5653-110">Check out [Simulate a phishing attack with Microsoft Defender for Office 365](attack-simulation-training.md) to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e5653-111">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="e5653-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e5653-112">Чтобы открыть Центр безопасности и соответствия требованиям, перейдите по ссылке <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="e5653-112">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="e5653-113">Имитатор атак доступен в **имитаторе атак** \> **управления угрозами.**</span><span class="sxs-lookup"><span data-stu-id="e5653-113">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="e5653-114">Перейдите непосредственно в имитатор атак, откройте <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="e5653-114">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="e5653-115">Дополнительные сведения о доступности имитатора атак в различных подписках Microsoft 365 см. в описании службы [Microsoft Defender для Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="e5653-115">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="e5653-116">Необходимо быть членом группы  ролей "Управление организацией" или **"Администратор** безопасности".</span><span class="sxs-lookup"><span data-stu-id="e5653-116">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="e5653-117">Дополнительные сведения о группах ролей в Центре безопасности и соответствия требованиям см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e5653-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="e5653-118">Ваша учетная запись должна быть настроена для многофакторной проверки подлинности (MFA) для создания кампаний и управления имитатором атак.</span><span class="sxs-lookup"><span data-stu-id="e5653-118">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="e5653-119">Инструкции см. в [настройках многофакторной проверки подлинности.](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)</span><span class="sxs-lookup"><span data-stu-id="e5653-119">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="e5653-120">Фишинговые кампании собирают и обрабатывает события в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="e5653-120">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="e5653-121">Данные истории кампании будут доступны в течение 90 дней после запуска кампании.</span><span class="sxs-lookup"><span data-stu-id="e5653-121">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="e5653-122">Для имитатора атак нет соответствующих cmdlets PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5653-122">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="e5653-123">Фишинговые кампании</span><span class="sxs-lookup"><span data-stu-id="e5653-123">Spear phishing campaigns</span></span>

<span data-ttu-id="e5653-124">*Фишинг —* это универсальный термин для атак электронной почты, которые пытаются украсть конфиденциальную информацию в сообщениях, которые кажутся надежными или надежными отправителями.</span><span class="sxs-lookup"><span data-stu-id="e5653-124">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="e5653-125">*Целевой* фишинг — это целевая фишинговая атака, использующая сфокусированное и настроенное содержимое, специально адаптированное для целевых получателей (как правило, после погруженого применения злоумышленником к получателям).</span><span class="sxs-lookup"><span data-stu-id="e5653-125">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="e5653-126">В имитаторе атак доступны два различных типа фишинговых кампаний:</span><span class="sxs-lookup"><span data-stu-id="e5653-126">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="e5653-127">**Фишинговое фишинговое письмо (сбор** учетных данных): атака пытается убедить получателей в том, что нужно щелкнуть URL-адрес в сообщении.</span><span class="sxs-lookup"><span data-stu-id="e5653-127">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="e5653-128">Если щелкнуть ссылку, им будет предложено ввести свои учетные данные.</span><span class="sxs-lookup"><span data-stu-id="e5653-128">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="e5653-129">В этом случае они будут доставлены в одно из следующих мест:</span><span class="sxs-lookup"><span data-stu-id="e5653-129">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="e5653-130">Страница по умолчанию, объясняя, что это всего лишь тест, и дает советы по распознаванию фишинговых сообщений.</span><span class="sxs-lookup"><span data-stu-id="e5653-130">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Что видят пользователи, щелкнув фишинговую ссылку и введите свои учетные данные](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="e5653-132">Настраиваемая страница (URL-адрес), которую вы указываете.</span><span class="sxs-lookup"><span data-stu-id="e5653-132">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="e5653-133">**Фишинговое письмо (вложение):** атака пытается убедить получателей в том, что в сообщении открывается вложение DOCX или PDF.</span><span class="sxs-lookup"><span data-stu-id="e5653-133">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="e5653-134">Вложение содержит то же содержимое из фишинговой ссылки по умолчанию, но первое предложение начинается с ", вы видите это сообщение как недавнее сообщение электронной \<Display Name\> почты, которое вы открыли...".</span><span class="sxs-lookup"><span data-stu-id="e5653-134">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="e5653-135">В настоящее время срок действия фишинговых кампаний в имитаторе атак не истекает.</span><span class="sxs-lookup"><span data-stu-id="e5653-135">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="e5653-136">Создание антифишинговой кампании</span><span class="sxs-lookup"><span data-stu-id="e5653-136">Create a spear phishing campaign</span></span>

<span data-ttu-id="e5653-137">Важной частью любой целевой фишинговой кампании является внешний вид сообщения электронной почты, которое отправляется целевым получателям.</span><span class="sxs-lookup"><span data-stu-id="e5653-137">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="e5653-138">Чтобы создать и настроить сообщение электронной почты, у вас есть указанные здесь параметры.</span><span class="sxs-lookup"><span data-stu-id="e5653-138">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="e5653-139">**Используйте встроенный шаблон электронной** почты: доступны два встроенных шаблона: **"Обновление** оплаты" и "Обновление **зарплаты".**</span><span class="sxs-lookup"><span data-stu-id="e5653-139">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="e5653-140">При создании и запуске кампании вы можете дополнительно настроить некоторые, все или никакие свойства электронной почты из шаблона.</span><span class="sxs-lookup"><span data-stu-id="e5653-140">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="e5653-141">**Создайте шаблон электронной** почты для повторного использования: после создания и сохранения шаблона электронной почты вы сможете использовать его снова в будущих фишинговых кампаниях.</span><span class="sxs-lookup"><span data-stu-id="e5653-141">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="e5653-142">При создании и запуске кампании вы можете дополнительно настроить некоторые, все или никакие свойства электронной почты из шаблона.</span><span class="sxs-lookup"><span data-stu-id="e5653-142">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="e5653-143">**Создайте сообщение электронной** почты в мастере: вы можете создать сообщение электронной почты непосредственно в мастере при создании и запуске фишинговой кампании.</span><span class="sxs-lookup"><span data-stu-id="e5653-143">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="e5653-144">Шаг 1 (необязательно). Создание пользовательского шаблона электронной почты</span><span class="sxs-lookup"><span data-stu-id="e5653-144">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="e5653-145">Если вы собираетесь использовать один из встроенных шаблонов или создать сообщение электронной почты непосредственно в мастере, вы можете пропустить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="e5653-145">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="e5653-146">В Центре безопасности & соответствия требованиям перейдите в имитатор **атак** \> **управления угрозами.**</span><span class="sxs-lookup"><span data-stu-id="e5653-146">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="e5653-147">На странице **"Имитация**  **атак"** щелкните "Сведения о атаке". </span><span class="sxs-lookup"><span data-stu-id="e5653-147">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="e5653-148">Не имеет значения, где вы создаете шаблон.</span><span class="sxs-lookup"><span data-stu-id="e5653-148">It doesn't matter where you create the template.</span></span> <span data-ttu-id="e5653-149">Доступные варианты в шаблоне одинаковы для обоих типов фишинговых атак.</span><span class="sxs-lookup"><span data-stu-id="e5653-149">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="e5653-150">На **открываемой** странице сведений о атаке в  разделе "Фишинговые шаблоны" в области "Создание шаблонов" щелкните **"Создать шаблон".** </span><span class="sxs-lookup"><span data-stu-id="e5653-150">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="e5653-151">Мастер **настройки фишинговых шаблонов** запускается в новом flyout.</span><span class="sxs-lookup"><span data-stu-id="e5653-151">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="e5653-152">На **шаге** "Начните" введите уникальное отображаемое имя шаблона и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="e5653-152">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="e5653-153">На **этапе настройки сведений электронной** почты настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e5653-153">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="e5653-154">**From (Name)**— отображаемая фамилия, используемая для отправитель сообщения.</span><span class="sxs-lookup"><span data-stu-id="e5653-154">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="e5653-155">**From (Email)**: адрес электронной почты отправитель.</span><span class="sxs-lookup"><span data-stu-id="e5653-155">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="e5653-156">**URL-адрес фишинговой учетной** записи сервера входа: щелкните в выпадаемом списке и выберите один из доступных URL-адресов в списке.</span><span class="sxs-lookup"><span data-stu-id="e5653-156">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="e5653-157">Это URL-адрес, который пользователи смогут щелкнуть.</span><span class="sxs-lookup"><span data-stu-id="e5653-157">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="e5653-158">Имеются следующие варианты.</span><span class="sxs-lookup"><span data-stu-id="e5653-158">The choices are:</span></span>

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
     > <span data-ttu-id="e5653-159">Служба репутации URL-адресов может определить один или несколько таких URL-адресов как небезопасные.</span><span class="sxs-lookup"><span data-stu-id="e5653-159">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="e5653-160">Перед использованием URL-адреса в фишинговой кампании проверьте доступность URL-адреса в поддерживаемых веб-браузерах.</span><span class="sxs-lookup"><span data-stu-id="e5653-160">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="e5653-161">**URL-адрес настраиваемой** страницы: введите необязательные страницы, на которых пользователи будут переходить по фишинговой ссылке и вводить свои учетные данные.</span><span class="sxs-lookup"><span data-stu-id="e5653-161">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="e5653-162">Эта ссылка заменяет тесную страницу по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e5653-162">This link replaces the default landing page.</span></span> <span data-ttu-id="e5653-163">Например, если у вас есть обучение внутренней осведомленности, вы можете указать этот URL-адрес здесь.</span><span class="sxs-lookup"><span data-stu-id="e5653-163">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="e5653-164">**Категория:** в настоящее время этот параметр не используется (все, что вы вводите, игнорируется).</span><span class="sxs-lookup"><span data-stu-id="e5653-164">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="e5653-165">**Тема:** поле **темы** сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e5653-165">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="e5653-166">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e5653-166">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="e5653-167">На **этапе создания сообщения** создайте текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="e5653-167">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="e5653-168">Вы можете использовать вкладку **"Электронная** почта" (редактор ФОРМАТ HTML) или вкладку **"Источник"** (необработанные HTML-коды).</span><span class="sxs-lookup"><span data-stu-id="e5653-168">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="e5653-169">Форматирование HTML может быть простым или сложным.</span><span class="sxs-lookup"><span data-stu-id="e5653-169">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="e5653-170">Вы можете вставлять изображения и текст, чтобы улучшить надежность сообщения в почтовом клиенте получателя.</span><span class="sxs-lookup"><span data-stu-id="e5653-170">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="e5653-171">`${username}` вставляет имя получателя.</span><span class="sxs-lookup"><span data-stu-id="e5653-171">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="e5653-172">`${loginserverurl}` вставляет **URL-адрес сервера фишинга для входа** в систему из предыдущего шага.</span><span class="sxs-lookup"><span data-stu-id="e5653-172">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="e5653-173">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e5653-173">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="e5653-174">На **шаге "Подтверждение"** нажмите кнопку **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="e5653-174">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="e5653-175">Шаг 2. Создание и запуск первой фишинговой кампании</span><span class="sxs-lookup"><span data-stu-id="e5653-175">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="e5653-176">В Центре безопасности & соответствия требованиям перейдите в имитатор **атак** \> **управления угрозами.**</span><span class="sxs-lookup"><span data-stu-id="e5653-176">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="e5653-177">На странице **"Имитация атак"** сделайте одно из следующих выбором в зависимости от типа создаемой кампании:</span><span class="sxs-lookup"><span data-stu-id="e5653-177">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="e5653-178">В разделе **"Копирошение фишинга (сбор** учетных данных") щелкните **"Атака при** запуске" или **"Атака с** подробными \> **сведениями о атаке при запуске".**</span><span class="sxs-lookup"><span data-stu-id="e5653-178">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="e5653-179">В разделе **"Вложение" выберите**  "Атака при запуске" или **"Атака с** подробными \> **сведениями о запуске атаки".**</span><span class="sxs-lookup"><span data-stu-id="e5653-179">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="e5653-180">Мастер **настройки фишинговых атак** запускается в новом окле.</span><span class="sxs-lookup"><span data-stu-id="e5653-180">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="e5653-181">На **шаге** "Начните" сделайте одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="e5653-181">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="e5653-182">В поле **"Имя"** введите уникальное отображаемое имя кампании.</span><span class="sxs-lookup"><span data-stu-id="e5653-182">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="e5653-183">Не нажимайте кнопку **"Использовать шаблон",** так как вы создадим сообщение электронной почты позже в мастере.</span><span class="sxs-lookup"><span data-stu-id="e5653-183">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="e5653-184">Щелкните **"Использовать шаблон"** и выберите встроенный или настраиваемый шаблон электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e5653-184">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="e5653-185">После выбора шаблона поле **"Имя"** заполняется автоматически на основе шаблона, но вы можете изменить имя.</span><span class="sxs-lookup"><span data-stu-id="e5653-185">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![Начальная страница фишинга](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="e5653-187">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e5653-187">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="e5653-188">На **шаге "Получатели"** сделайте одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="e5653-188">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="e5653-189">Щелкните **адресную** книгу, чтобы выбрать получателей (пользователей или группы) для кампании.</span><span class="sxs-lookup"><span data-stu-id="e5653-189">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="e5653-190">У каждого целевого получателя должен быть почтовый ящик Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e5653-190">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="e5653-191">Если нажать **кнопку "Фильтр"** и **"Применить"** без ввода условия поиска, все получатели будут возвращены и добавлены в кампанию.</span><span class="sxs-lookup"><span data-stu-id="e5653-191">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="e5653-192">Нажмите **кнопку** **"Импорт** и импорт файла", чтобы импортировать CSV-файл или файл адресов электронной почты, разделенный запятой.</span><span class="sxs-lookup"><span data-stu-id="e5653-192">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="e5653-193">Каждая строка должна содержать адрес электронной почты получателя.</span><span class="sxs-lookup"><span data-stu-id="e5653-193">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="e5653-194">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e5653-194">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="e5653-195">На **этапе настройки сведений электронной** почты настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e5653-195">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="e5653-196">Если вы выбрали шаблон  на шаге "Начните", большинство из этих значений уже настроены, но их можно изменить.</span><span class="sxs-lookup"><span data-stu-id="e5653-196">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="e5653-197">**From (Name)**— отображаемая фамилия, используемая для отправитель сообщения.</span><span class="sxs-lookup"><span data-stu-id="e5653-197">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="e5653-198">**From (Email)**: адрес электронной почты отправитель.</span><span class="sxs-lookup"><span data-stu-id="e5653-198">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="e5653-199">Вы можете ввести реальный или поддельный адрес электронной почты из домена электронной почты вашей организации или ввести реальный или поддельный внешний адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e5653-199">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="e5653-200">Допустимый адрес электронной почты отправитель из вашей организации фактически будет разрешаться в почтовом клиенте получателя.</span><span class="sxs-lookup"><span data-stu-id="e5653-200">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="e5653-201">**URL-адрес фишинговой учетной** записи сервера входа: щелкните в выпадаемом списке и выберите один из доступных URL-адресов в списке.</span><span class="sxs-lookup"><span data-stu-id="e5653-201">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="e5653-202">Это URL-адрес, который пользователи смогут щелкнуть.</span><span class="sxs-lookup"><span data-stu-id="e5653-202">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="e5653-203">Имеются следующие варианты.</span><span class="sxs-lookup"><span data-stu-id="e5653-203">The choices are:</span></span>

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
     > - <span data-ttu-id="e5653-204">Все URL-адреса намеренно являются http, а не https.</span><span class="sxs-lookup"><span data-stu-id="e5653-204">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="e5653-205">Служба репутации URL-адресов может определить один или несколько таких URL-адресов как небезопасные.</span><span class="sxs-lookup"><span data-stu-id="e5653-205">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="e5653-206">Перед использованием URL-адреса в фишинговой кампании проверьте доступность URL-адреса в поддерживаемых веб-браузерах.</span><span class="sxs-lookup"><span data-stu-id="e5653-206">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="e5653-207">Необходимо выбрать URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="e5653-207">You are required to select a URL.</span></span> <span data-ttu-id="e5653-208">Для кампаний по борьбе с фишингом **(вложениями)** ссылку можно удалить из тела сообщения на следующем шаге (в противном случае сообщение будет содержать как ссылку, так **и** вложение).</span><span class="sxs-lookup"><span data-stu-id="e5653-208">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="e5653-209">**Тип вложения:** этот параметр доступен только в кампаниях **по фишингу** с вложениями.</span><span class="sxs-lookup"><span data-stu-id="e5653-209">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="e5653-210">Щелкните в этом выпадаемом окте и выберите **. DOCX** или **. PDF** из списка.</span><span class="sxs-lookup"><span data-stu-id="e5653-210">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="e5653-211">**Имя вложения:** этот параметр доступен только в кампаниях **по фишингу** с вложениями.</span><span class="sxs-lookup"><span data-stu-id="e5653-211">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="e5653-212">Введите имя файла для вложения DOCX или PDF.</span><span class="sxs-lookup"><span data-stu-id="e5653-212">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="e5653-213">**URL-адрес настраиваемой** страницы: введите необязательные страницы, на которых пользователи будут переходить по фишинговой ссылке и вводить свои учетные данные.</span><span class="sxs-lookup"><span data-stu-id="e5653-213">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="e5653-214">Эта ссылка заменяет тесную страницу по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e5653-214">This link replaces the default landing page.</span></span> <span data-ttu-id="e5653-215">Например, если у вас есть обучение внутренней осведомленности, вы можете указать этот URL-адрес здесь.</span><span class="sxs-lookup"><span data-stu-id="e5653-215">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="e5653-216">**Тема:** поле **темы** сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e5653-216">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="e5653-217">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e5653-217">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="e5653-218">На **этапе создания сообщения** создайте текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="e5653-218">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="e5653-219">Если вы выбрали шаблон  на шаге "Начните", текст сообщения уже настроен, но его можно настроить.</span><span class="sxs-lookup"><span data-stu-id="e5653-219">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="e5653-220">Вы можете использовать вкладку **"Электронная** почта" (редактор ФОРМАТ HTML) или вкладку **"Источник"** (необработанные HTML-коды).</span><span class="sxs-lookup"><span data-stu-id="e5653-220">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="e5653-221">Форматирование HTML может быть простым или сложным.</span><span class="sxs-lookup"><span data-stu-id="e5653-221">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="e5653-222">Вы можете вставлять изображения и текст, чтобы улучшить надежность сообщения в почтовом клиенте получателя.</span><span class="sxs-lookup"><span data-stu-id="e5653-222">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="e5653-223">`${username}` вставляет имя получателя.</span><span class="sxs-lookup"><span data-stu-id="e5653-223">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="e5653-224">`${loginserverurl}` вставляет **URL-адрес сервера фишинга для** входа в систему.</span><span class="sxs-lookup"><span data-stu-id="e5653-224">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="e5653-225">Для кампаний по борьбе с фишингом **(вложениями)** следует удалить ссылку из тела  сообщения (в противном случае сообщение будет содержать как ссылку, так и вложение, а щелчки по ссылкам не отслеживаются в кампании вложения).</span><span class="sxs-lookup"><span data-stu-id="e5653-225">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![Тело сообщения электронной почты для составить](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="e5653-227">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e5653-227">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="e5653-228">На **шаге "Подтверждение"** нажмите кнопку **"Готово",** чтобы запустить кампанию.</span><span class="sxs-lookup"><span data-stu-id="e5653-228">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="e5653-229">Фишинговое сообщение доставляется целевым получателям.</span><span class="sxs-lookup"><span data-stu-id="e5653-229">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="e5653-230">Атаки с помощью паролей</span><span class="sxs-lookup"><span data-stu-id="e5653-230">Password attack campaigns</span></span>

<span data-ttu-id="e5653-231">Атака *с паролем* пытается угадать пароли для учетных записей пользователей в организации, как правило, после того, как злоумышленник определил одну или несколько допустимых учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="e5653-231">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="e5653-232">В имитаторе атак доступны два различных типа кампаний по атаке с помощью паролей для проверки сложности паролей пользователей:</span><span class="sxs-lookup"><span data-stu-id="e5653-232">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="e5653-233">Пароль для атак с использованием  словаря,  в которых используется большой файл словаря паролей для учетной записи пользователя в расчете на то, что один из них будет работать (много паролей для одной учетной записи). </span><span class="sxs-lookup"><span data-stu-id="e5653-233">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="e5653-234">Неправильные блокировки паролей помогают предотвратить атаки с помощью атак с помощью перенастраховки.</span><span class="sxs-lookup"><span data-stu-id="e5653-234">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="e5653-235">Для атаки с помощью словаря можно указать один или несколько паролей для проверки (вручную или в добавленный файл), а также указать одного или несколько пользователей.</span><span class="sxs-lookup"><span data-stu-id="e5653-235">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="e5653-236">**Атака распыления пароля:** при атаке *распыления* пароля используется тот же тщательно просмотряный пароль для списка учетных записей пользователей (один пароль для многих учетных записей).</span><span class="sxs-lookup"><span data-stu-id="e5653-236">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="e5653-237">Атаки с распылением пароля обнаруживать сложнее, чем атаки с помощью атак злоумышленника.</span><span class="sxs-lookup"><span data-stu-id="e5653-237">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="e5653-238">Для атаки распыления пароля можно указать только один пароль, который необходимо попробовать, и указать одного или несколько пользователей.</span><span class="sxs-lookup"><span data-stu-id="e5653-238">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="e5653-239">Атаки с паролями в симуляторе атак передают запросы проверки подлинности пользователя и пароля Basic конечной точке, поэтому они также работают с другими методами проверки подлинности (AD FS, синхронизация хеш-функций паролей, сквозной доступ, PingFederate и т. д.).</span><span class="sxs-lookup"><span data-stu-id="e5653-239">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="e5653-240">Для пользователей, для пользователей с включенной многофаксной многофаксной поддержкой, даже если атака с паролем пытается  использовать их фактический пароль, попытка всегда регистрируется как ошибка (другими словами, пользователи MFA никогда не будут отображаться в подсчете успешных попыток кампании).</span><span class="sxs-lookup"><span data-stu-id="e5653-240">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="e5653-241">Это ожидаемый результат.</span><span class="sxs-lookup"><span data-stu-id="e5653-241">This is the expected result.</span></span> <span data-ttu-id="e5653-242">MFA — это основной способ защиты от атак с помощью паролей.</span><span class="sxs-lookup"><span data-stu-id="e5653-242">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="e5653-243">Создание и запуск кампании по атаке с помощью паролей</span><span class="sxs-lookup"><span data-stu-id="e5653-243">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="e5653-244">В Центре безопасности & соответствия требованиям перейдите в имитатор **атак** \> **управления угрозами.**</span><span class="sxs-lookup"><span data-stu-id="e5653-244">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="e5653-245">На странице **"Имитация атак"** сделайте одно из следующих выбором в зависимости от типа создаемой кампании:</span><span class="sxs-lookup"><span data-stu-id="e5653-245">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="e5653-246">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** Launch \> **Attack**.</span><span class="sxs-lookup"><span data-stu-id="e5653-246">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="e5653-247">в разделе **"Атака с распылением** пароля" щелкните **"Атака при запуске"** или **"Атака с** подробными \> **сведениями о атаке при запуске".**</span><span class="sxs-lookup"><span data-stu-id="e5653-247">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="e5653-248">Мастер **настройки атаки паролем** запускается в новом окле.</span><span class="sxs-lookup"><span data-stu-id="e5653-248">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="e5653-249">На **шаге** "Начните" введите уникальное отображаемое имя для кампании и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="e5653-249">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="e5653-250">На **шаге "Целевые** пользователи" сделайте одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="e5653-250">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="e5653-251">Щелкните **адресную** книгу, чтобы выбрать получателей (пользователей или группы) для кампании.</span><span class="sxs-lookup"><span data-stu-id="e5653-251">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="e5653-252">У каждого целевого получателя должен быть почтовый ящик Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e5653-252">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="e5653-253">Если нажать **кнопку "Фильтр"** и **"Применить"** без ввода условия поиска, все получатели будут возвращены и добавлены в кампанию.</span><span class="sxs-lookup"><span data-stu-id="e5653-253">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="e5653-254">Нажмите **кнопку** **"Импорт** и импорт файла", чтобы импортировать CSV-файл или файл адресов электронной почты, разделенный запятой.</span><span class="sxs-lookup"><span data-stu-id="e5653-254">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="e5653-255">Каждая строка должна содержать адрес электронной почты получателя.</span><span class="sxs-lookup"><span data-stu-id="e5653-255">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="e5653-256">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e5653-256">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="e5653-257">На **шаге "Выбор параметров атаки"** выберите, что делать в зависимости от типа кампании:</span><span class="sxs-lookup"><span data-stu-id="e5653-257">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="e5653-258">**Пароль при атаке** по словарю: сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="e5653-258">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="e5653-259">**Введите пароли** вручную:  введите пароль в поле "Нажмите ввод", чтобы добавить пароль, а затем нажмите ввод.</span><span class="sxs-lookup"><span data-stu-id="e5653-259">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="e5653-260">Повторите этот шаг необходимое количество раз.</span><span class="sxs-lookup"><span data-stu-id="e5653-260">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="e5653-261">**Отправка паролей из файла словаря:** нажмите кнопку **"Отправить",** чтобы импортировать существующий текстовый файл, содержащий один пароль в каждой строке и пустую последнюю строку.</span><span class="sxs-lookup"><span data-stu-id="e5653-261">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="e5653-262">Размер текстового файла не должен быть меньше 10 МБ и не может содержать более 30 000 паролей.</span><span class="sxs-lookup"><span data-stu-id="e5653-262">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="e5653-263">**Атака распылением пароля:** в поле атаки введите один пароль. </span><span class="sxs-lookup"><span data-stu-id="e5653-263">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="e5653-264">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e5653-264">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="e5653-265">На **шаге "Подтверждение"** нажмите кнопку **"Готово",** чтобы запустить кампанию.</span><span class="sxs-lookup"><span data-stu-id="e5653-265">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="e5653-266">Указанные пароли пытаются использовать для указанных пользователей.</span><span class="sxs-lookup"><span data-stu-id="e5653-266">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="e5653-267">Просмотр результатов кампании</span><span class="sxs-lookup"><span data-stu-id="e5653-267">View campaign results</span></span>

<span data-ttu-id="e5653-268">После запуска кампании вы можете проверить ход выполнения и результаты на главной странице **имитации атак.**</span><span class="sxs-lookup"><span data-stu-id="e5653-268">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="e5653-269">Активные кампании будут показывать планку состояния, завершенное процентное значение и количество "(завершенных пользователей) (всего пользователей)".</span><span class="sxs-lookup"><span data-stu-id="e5653-269">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="e5653-270">Нажатие **кнопки "Обновить"** обножит ход выполнения всех активных кампаний.</span><span class="sxs-lookup"><span data-stu-id="e5653-270">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="e5653-271">Вы также можете нажать **кнопку "Завершить",** чтобы остановить активную кампанию.</span><span class="sxs-lookup"><span data-stu-id="e5653-271">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="e5653-272">После завершения кампании состояние "Атака" изменится на **"Атака завершена".**</span><span class="sxs-lookup"><span data-stu-id="e5653-272">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="e5653-273">Чтобы просмотреть результаты кампании, с помощью одного из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="e5653-273">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="e5653-274">На главной **странице "Имитация атак"** щелкните **"Просмотреть отчет"** под именем кампании.</span><span class="sxs-lookup"><span data-stu-id="e5653-274">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="e5653-275">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span><span class="sxs-lookup"><span data-stu-id="e5653-275">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="e5653-276">На **открывскойся** странице сведений о атаке выберите кампанию в разделе **"История атак".**</span><span class="sxs-lookup"><span data-stu-id="e5653-276">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="e5653-277">При любом из предыдущих действий вы будете перенабираться на страницу с именем **"Сведения о атаке".**</span><span class="sxs-lookup"><span data-stu-id="e5653-277">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="e5653-278">Сведения, доступные на этой странице для каждого типа кампании, описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="e5653-278">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="e5653-279">Результаты кампании по фишингу (сбор учетных данных)</span><span class="sxs-lookup"><span data-stu-id="e5653-279">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="e5653-280">На странице сведений о атаке для каждой **кампании** доступны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="e5653-280">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="e5653-281">Продолжительность кампании (дата и время начала, время и дата окончания).</span><span class="sxs-lookup"><span data-stu-id="e5653-281">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="e5653-282">**Общее количество целевых пользователей**</span><span class="sxs-lookup"><span data-stu-id="e5653-282">**Total users targeted**</span></span>

- <span data-ttu-id="e5653-283">**Успешные попытки:** количество пользователей, которые щелкнули ссылку и **ввели** свои учетные данные *(любое* имя пользователя и пароль).</span><span class="sxs-lookup"><span data-stu-id="e5653-283">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="e5653-284">**Общий показатель успешности**: процент, который рассчитывается по **успешным попыткам**  /  **Всего целевых пользователей.**</span><span class="sxs-lookup"><span data-stu-id="e5653-284">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="e5653-285">**Самый быстрый щелчок:** сколько времени потребовалось первому пользователю, чтобы щелкнуть ссылку после запуска кампании.</span><span class="sxs-lookup"><span data-stu-id="e5653-285">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="e5653-286">**Средний щелчок**: сумма времени, за который все щелкнули ссылку, разделенную на количество пользователей, щелкнув ссылку.</span><span class="sxs-lookup"><span data-stu-id="e5653-286">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="e5653-287">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span><span class="sxs-lookup"><span data-stu-id="e5653-287">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="e5653-288">**Самые быстрые учетные** данные: сколько времени потребовалось первому пользователю, чтобы ввести свои учетные данные после запуска кампании.</span><span class="sxs-lookup"><span data-stu-id="e5653-288">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="e5653-289">**Средние учетные данные**: сумма времени, за который все ввели свои учетные данные, разделенные на количество пользователей, введвших свои учетные данные.</span><span class="sxs-lookup"><span data-stu-id="e5653-289">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="e5653-290">**Показатель успешности учетных** данных : процент, который рассчитывается на 1 процент (количество пользователей, ввели свои учетные данные) / **Общее количество целевых пользователей.**</span><span class="sxs-lookup"><span data-stu-id="e5653-290">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="e5653-291">Диаграмма с **нажатием** ссылки и предоставленными учетными **данными** номерами в день.</span><span class="sxs-lookup"><span data-stu-id="e5653-291">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="e5653-292">Круговой график, на который показаны щелчок ссылки, предоставленные учетные данные **и** процентные соотношения **"Нет"** для кампании.</span><span class="sxs-lookup"><span data-stu-id="e5653-292">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="e5653-293">В **разделе "Скомпрометированная** пользователи" перечислены сведения о пользователях, щелкнув ссылку:</span><span class="sxs-lookup"><span data-stu-id="e5653-293">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="e5653-294">Адрес электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="e5653-294">The user's email address</span></span>

  - <span data-ttu-id="e5653-295">Дата и время щелчка по ссылке.</span><span class="sxs-lookup"><span data-stu-id="e5653-295">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="e5653-296">IP-адрес клиента.</span><span class="sxs-lookup"><span data-stu-id="e5653-296">The client IP address.</span></span>

  - <span data-ttu-id="e5653-297">Сведения о версии Windows и веб-браузере пользователя.</span><span class="sxs-lookup"><span data-stu-id="e5653-297">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="e5653-298">Можно нажать **кнопку "Экспорт",** чтобы экспортировать результаты в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="e5653-298">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="e5653-299">Результаты кампании по фишингу (вложениям)</span><span class="sxs-lookup"><span data-stu-id="e5653-299">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="e5653-300">На странице сведений о атаке для каждой **кампании** доступны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="e5653-300">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="e5653-301">Продолжительность кампании (дата и время начала, время и дата окончания).</span><span class="sxs-lookup"><span data-stu-id="e5653-301">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="e5653-302">**Общее количество целевых пользователей**</span><span class="sxs-lookup"><span data-stu-id="e5653-302">**Total users targeted**</span></span>

- <span data-ttu-id="e5653-303">**Успешные** попытки: количество пользователей, открывавших или скачавших и открывавших вложение (предварительная версия не учитывается).</span><span class="sxs-lookup"><span data-stu-id="e5653-303">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="e5653-304">**Общий показатель успешности**: процент, который рассчитывается по **успешным попыткам**  /  **Всего целевых пользователей.**</span><span class="sxs-lookup"><span data-stu-id="e5653-304">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="e5653-305">**Самое быстрое время открытия** вложения: сколько времени потребовалось первому пользователю, чтобы открыть вложение после запуска кампании.</span><span class="sxs-lookup"><span data-stu-id="e5653-305">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="e5653-306">**Среднее время открытия вложения:** сумма времени, за который все открывали вложение, разделив его на количество пользователей, открывавших вложение.</span><span class="sxs-lookup"><span data-stu-id="e5653-306">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="e5653-307">**Показатель успешности** открытия вложения: процент, который рассчитывается на долю (количество пользователей, открывавших вложение) / общее количество пользователей, на **которые нацелено.**</span><span class="sxs-lookup"><span data-stu-id="e5653-307">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="e5653-308">Результаты кампании по выбору принудительного пароля (атака по словарю)</span><span class="sxs-lookup"><span data-stu-id="e5653-308">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="e5653-309">На странице сведений о атаке для каждой **кампании** доступны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="e5653-309">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="e5653-310">Продолжительность кампании (дата и время начала, время и дата окончания).</span><span class="sxs-lookup"><span data-stu-id="e5653-310">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="e5653-311">**Общее количество целевых пользователей**</span><span class="sxs-lookup"><span data-stu-id="e5653-311">**Total users targeted**</span></span>

- <span data-ttu-id="e5653-312">**Успешные** попытки: количество пользователей, которые использовали один из указанных паролей.</span><span class="sxs-lookup"><span data-stu-id="e5653-312">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="e5653-313">**Общий показатель успешности**: процент, который рассчитывается по **успешным попыткам**  /  **Всего целевых пользователей.**</span><span class="sxs-lookup"><span data-stu-id="e5653-313">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="e5653-314">В **разделе "Скомпрометированная** пользователи" перечислены адреса электронной почты затронутых пользователей.</span><span class="sxs-lookup"><span data-stu-id="e5653-314">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="e5653-315">Можно нажать **кнопку "Экспорт",** чтобы экспортировать результаты в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="e5653-315">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="e5653-316">Результаты кампании по распылку пароля</span><span class="sxs-lookup"><span data-stu-id="e5653-316">Password spray attack campaign results</span></span>

<span data-ttu-id="e5653-317">На странице сведений о атаке для каждой **кампании** доступны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="e5653-317">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="e5653-318">Продолжительность кампании (дата и время начала, время и дата окончания).</span><span class="sxs-lookup"><span data-stu-id="e5653-318">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="e5653-319">**Общее количество целевых пользователей**</span><span class="sxs-lookup"><span data-stu-id="e5653-319">**Total users targeted**</span></span>

- <span data-ttu-id="e5653-320">**Успешные** попытки: количество пользователей, которые были найдены с использованием указанного пароля.</span><span class="sxs-lookup"><span data-stu-id="e5653-320">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="e5653-321">**Общий показатель успешности**: процент, который рассчитывается по **успешным попыткам**  /  **Всего целевых пользователей.**</span><span class="sxs-lookup"><span data-stu-id="e5653-321">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
