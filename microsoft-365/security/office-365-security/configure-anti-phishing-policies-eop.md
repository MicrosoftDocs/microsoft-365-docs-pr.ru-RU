---
title: Настройка политики защиты от фишинга по умолчанию в EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как изменить параметры защиты от спуфинга, доступные в политике защиты от фишинга по умолчанию в организациях Office 365 с почтовыми ящиками Exchange Online.
ms.openlocfilehash: 1a8527a55796910e79fbf70b824de828ca48591b
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537537"
---
# <a name="configure-the-default-anti-phishing-policy-in-eop"></a><span data-ttu-id="f3c86-103">Настройка политики защиты от фишинга по умолчанию в EOP</span><span class="sxs-lookup"><span data-stu-id="f3c86-103">Configure the default anti-phishing policy in EOP</span></span>

<span data-ttu-id="f3c86-104">Организации Office 365 с почтовыми ящиками Exchange Online и отдельными организациями Exchange Online Protection (EOP) без почтовых ящиков Exchange Online имеют политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f3c86-104">Office 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes have a default anti-phishing policy.</span></span> <span data-ttu-id="f3c86-105">Эта политика содержит ограниченное число функций защиты от спуфинга, которые включены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f3c86-105">This policy contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="f3c86-106">Дополнительные сведения см в разделе [Параметры подделки в политиках защиты от фишинга](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="f3c86-106">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="f3c86-107">Организации Office 365 с почтовыми ящиками Exchange Online могут изменить политику защиты от фишинга по умолчанию в центре безопасности & безопасности Office 365 или в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f3c86-107">Office 365 organizations with Exchange Online mailboxes can modify the default anti-phishing policy in the Office 365 Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="f3c86-108">Автономные Организации EOP без почтовых ящиков Exchange Online не могут изменять политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f3c86-108">Standalone EOP organizations without Exchange Online mailboxes can't modify their default anti-phishing policy.</span></span>

<span data-ttu-id="f3c86-109">Сведения о создании и изменении дополнительных политик защиты от фишинга ATP, доступных в Office 365 Advanced Threat Protection, приведены в разделе [Настройка политик защиты от фишинга ATP в office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f3c86-109">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection, see [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f3c86-110">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="f3c86-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f3c86-111">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f3c86-111">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f3c86-112">Чтобы перейти непосредственно на страницу **защиты от фишинга** , используйте <https://protection.office.com/antiphishing>.</span><span class="sxs-lookup"><span data-stu-id="f3c86-112">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="f3c86-113">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f3c86-113">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="f3c86-114">Чтобы вы могли выполнить эти процедуры, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="f3c86-114">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="f3c86-115">Для добавления, изменения и удаления политик защиты от фишинга необходимо быть членом группы ролей " **Управление организацией** " или " **администратор безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="f3c86-115">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="f3c86-116">Для доступа только для чтения к политикам защиты от фишинга необходимо быть участником группы ролей " **читатель безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="f3c86-116">For read-only access to anti-phishing policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="f3c86-117">Дополнительные сведения о группах ролей в Центре безопасности и соответствия требованиям см. в статье [Разрешения в Центре безопасности и соответствия требованиям Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f3c86-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="f3c86-118">Рекомендуемые параметры политики защиты от фишинга по умолчанию приведены в статье [EOP по умолчанию](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="f3c86-118">For our recommended settings for the default anti-phishing policy, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="f3c86-119">Разрешить применение обновленной политики до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="f3c86-119">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="f3c86-120">Сведения о том, когда политики защиты от фишинга применяются в конвейере фильтрации, приведены в статье [порядок и приоритет защиты электронной почты в Office 365](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="f3c86-120">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection in Office 365](how-policies-and-protections-are-combined.md).</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="f3c86-121">Использование центра безопасности & соответствия требованиям для изменения политики защиты от фишинга по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f3c86-121">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="f3c86-122">По умолчанию политика защиты от фишинга называется Office365 по умолчанию и не отображается в списке политик.</span><span class="sxs-lookup"><span data-stu-id="f3c86-122">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="f3c86-123">Чтобы изменить политику защиты от фишинга по умолчанию, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f3c86-123">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="f3c86-124">В центре безопасности & соответствия требованиям перейдите к разделу \> **Политика** \> **управления угрозами** : **Защита от фишинга**.</span><span class="sxs-lookup"><span data-stu-id="f3c86-124">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f3c86-125">На странице **Защита от фишинга** щелкните **Политика по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="f3c86-125">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="f3c86-126">Откроется страница **изменение политики Office365 антифишинга по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="f3c86-126">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="f3c86-127">В разделе **подделка** нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="f3c86-127">In the **Spoof** section, click **Edit**.</span></span>

   <span data-ttu-id="f3c86-128">Обратите внимание, что эти параметры идентичны параметрам подделки, доступным в политиках защиты от фишинга ATP.</span><span class="sxs-lookup"><span data-stu-id="f3c86-128">Note that these settings are identical to the spoof settings that are available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="f3c86-129">**Параметры фильтра подделки**: значение по умолчанию — **включено**, и мы рекомендуем оставить его.</span><span class="sxs-lookup"><span data-stu-id="f3c86-129">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="f3c86-130">Чтобы отключить его, установите переключатель в значение **выкл**.</span><span class="sxs-lookup"><span data-stu-id="f3c86-130">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="f3c86-131">Дополнительные сведения см. [в статье Настройка логики анализа в Office 365](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="f3c86-131">For more information, see [Configure spoof intelligence in Office 365](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="f3c86-132">Отключение защиты от спуфинга не требуется, если запись MX не указывает на Office 365; Вместо этого вы включите расширенную фильтрацию для соединителей.</span><span class="sxs-lookup"><span data-stu-id="f3c86-132">You don't need to disable anti-spoofing protection if your MX record doesn't point to Office 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="f3c86-133">Инструкции см в разделе [Расширенная фильтрация соединителей в Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="f3c86-133">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="f3c86-134">**Включить функцию отправителя, не прошедший проверку подлинности**: добавляет вопросительный знак в фотографию отправителя, если сообщение не проходит проверку подлинности по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="f3c86-134">**Enable Unauthenticated Sender feature**: Adds a question mark to the sender's photo if the message fails email authentication checks.</span></span> <span data-ttu-id="f3c86-135">Дополнительные сведения см в разделе [Параметры подделки в политиках защиты от фишинга](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="f3c86-135">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span> <span data-ttu-id="f3c86-136">Значение по умолчанию — **Включено**.</span><span class="sxs-lookup"><span data-stu-id="f3c86-136">The default value is **On**.</span></span> <span data-ttu-id="f3c86-137">Чтобы отключить его, установите переключатель в значение **выкл**.</span><span class="sxs-lookup"><span data-stu-id="f3c86-137">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="f3c86-138">**Действия**: укажите действие, которое следует предпринять для сообщений, не прошедших анализ подделки:</span><span class="sxs-lookup"><span data-stu-id="f3c86-138">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="f3c86-139">**Если сообщение электронной почты отправлено пользователем, который не может подменить ваш домен**:</span><span class="sxs-lookup"><span data-stu-id="f3c86-139">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="f3c86-140">**Переместить сообщение в папку "Нежелательная почта" получателей** (это значение по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="f3c86-140">**Move message to the recipients' Junk Email folders** (This is the default value.)</span></span>
     - <span data-ttu-id="f3c86-141">**Помещать сообщение в карантин**</span><span class="sxs-lookup"><span data-stu-id="f3c86-141">**Quarantine the message**</span></span>

   - <span data-ttu-id="f3c86-142">**Проверьте параметры**: вместо того, чтобы щелкать каждый отдельный шаг, параметры отображаются в сводке.</span><span class="sxs-lookup"><span data-stu-id="f3c86-142">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="f3c86-143">Вы можете щелкнуть **изменить** в каждом разделе, чтобы вернуться на соответствующую страницу.</span><span class="sxs-lookup"><span data-stu-id="f3c86-143">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="f3c86-144">Вы можете включать и **отключать** следующие параметры **непосредственно на этой** странице:</span><span class="sxs-lookup"><span data-stu-id="f3c86-144">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="f3c86-145">**Включение защиты от спуфинга**</span><span class="sxs-lookup"><span data-stu-id="f3c86-145">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="f3c86-146">**Включение функции отправителя без проверки подлинности**</span><span class="sxs-lookup"><span data-stu-id="f3c86-146">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="f3c86-147">По завершении нажмите кнопку **сохранить** на любой странице.</span><span class="sxs-lookup"><span data-stu-id="f3c86-147">When you're finished, click **Save** on any page.</span></span>

4. <span data-ttu-id="f3c86-148">Вернувшись на страницу **изменение политики Office365 по умолчанию** , проверьте параметры и нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="f3c86-148">Back on the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-the-default-anti-phishing-policy"></a><span data-ttu-id="f3c86-149">Использование центра безопасности & соответствия требованиям для просмотра политики защиты от фишинга по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f3c86-149">Use the Security & Compliance Center to view the default anti-phishing policy</span></span>

1. <span data-ttu-id="f3c86-150">В центре безопасности & соответствия требованиям и перейдите к разделу \> **Политика** \> **управления угрозами** для **защиты от фишинга ATP**.</span><span class="sxs-lookup"><span data-stu-id="f3c86-150">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="f3c86-151">Щелкните **политику по умолчанию** , чтобы просмотреть политику защиты от фишинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f3c86-151">Click **Default policy** to view the default anti-phishing policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-the-default-anti-phishing-policy"></a><span data-ttu-id="f3c86-152">Настройка политики защиты от фишинга по умолчанию с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3c86-152">Use Exchange Online PowerShell to configure the default anti-phishing policy</span></span>

### <a name="use-powershell-to-view-the-default-anti-phish-policy"></a><span data-ttu-id="f3c86-153">Просмотр политики защиты от фишинга по умолчанию с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3c86-153">Use PowerShell to view the default anti-phish policy</span></span>

<span data-ttu-id="f3c86-154">Чтобы просмотреть политику защиты от фишинга по умолчанию, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f3c86-154">To view the default anti-phish policy, run the following command:</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
```

<span data-ttu-id="f3c86-155">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="f3c86-155">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-the-default-anti-phish-policy"></a><span data-ttu-id="f3c86-156">Изменение политики защиты от фишинга по умолчанию с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3c86-156">Use PowerShell to modify the default anti-phish policy</span></span>

<span data-ttu-id="f3c86-157">Чтобы изменить политику защиты от фишинга по умолчанию, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="f3c86-157">To modify the default anti-phish policy, use the following syntax:</span></span>

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableAntispoofEnforcement <$true | $false>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="f3c86-158">В этом примере показано изменение действия для поддельных сообщений, которые не прошли проверку подлинности на карантин.</span><span class="sxs-lookup"><span data-stu-id="f3c86-158">This example changes the action for spoofed messages that fail authentication checks to quarantine.</span></span>

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="f3c86-159">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="f3c86-159">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="f3c86-160">Как проверить, что эти процедуры выполнены?</span><span class="sxs-lookup"><span data-stu-id="f3c86-160">How do you know these procedures worked?</span></span>

<span data-ttu-id="f3c86-161">Чтобы убедиться, что политика защиты от фишинга по умолчанию успешно настроена, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="f3c86-161">To verify that you've successfully configured the default anti-phishing policy, do any of the following steps:</span></span>

- <span data-ttu-id="f3c86-162">В центре безопасности & соответствия требованиям перейдите **к разделу** \> **Политика** \> \> **управления угрозами** , щелкните **Политика по умолчанию** и просмотрите сведения в всплывающем меню.</span><span class="sxs-lookup"><span data-stu-id="f3c86-162">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing** \> click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="f3c86-163">В Exchange Online PowerShell выполните следующую команду и проверьте параметры:</span><span class="sxs-lookup"><span data-stu-id="f3c86-163">In Exchange Online PowerShell, run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
  ```
