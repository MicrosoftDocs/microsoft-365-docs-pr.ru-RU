---
title: Использование правил потока почты в SCL в сообщениях
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Узнайте, как создать правила потока почты (правила транспорта), чтобы определить сообщения и установить уровень доверия к нежелательной почте (SCL) сообщений в Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1d7d1de194d8529fd3cf3e2d1da68c1f928ffcfa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921136"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a><span data-ttu-id="2ceea-103">Используйте правила потока почты, чтобы установить уровень доверия к нежелательной почте (SCL) в сообщениях в EOP</span><span class="sxs-lookup"><span data-stu-id="2ceea-103">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2ceea-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="2ceea-104">**Applies to**</span></span>
- [<span data-ttu-id="2ceea-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2ceea-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2ceea-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="2ceea-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="2ceea-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ceea-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="2ceea-108">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online EOP использует политики защиты от нежелательной почты (также известные как политики фильтра спама или политики фильтрации контента) для проверки входящих сообщений на спам.</span><span class="sxs-lookup"><span data-stu-id="2ceea-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="2ceea-109">Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2ceea-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="2ceea-110">Если вы хотите отметить определенные сообщения в качестве нежелательной почты, прежде чем они даже будут отсканированы фильтрацией нежелательной почты, или пометить сообщения, чтобы они пропустили фильтрацию нежелательной почты, можно создать правила потока почты (также известные как правила транспорта), чтобы определить сообщения и установить уровень доверия к нежелательной почте (SCL).</span><span class="sxs-lookup"><span data-stu-id="2ceea-110">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="2ceea-111">Дополнительные сведения о SCL см. в сообщении уровня доверия к нежелательной почте [(SCL) в EOP.](spam-confidence-levels.md)</span><span class="sxs-lookup"><span data-stu-id="2ceea-111">For more information about the SCL, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2ceea-112">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="2ceea-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2ceea-113">Вам необходимо получить разрешения в Exchange Online или Exchange Online Protection, прежде чем вы сможете сделать процедуры в этой статье.</span><span class="sxs-lookup"><span data-stu-id="2ceea-113">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="2ceea-114">В частности, вам  нужна роль Правил транспорта, которая по умолчанию назначена группам  ролей **"Управление** организацией",  "Управление соответствием требованиям" (глобальные администраторы) и "Управление записями".</span><span class="sxs-lookup"><span data-stu-id="2ceea-114">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="2ceea-115">Дополнительную информацию см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="2ceea-115">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="2ceea-116">Разрешения в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2ceea-116">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="2ceea-117">Разрешения в автономном EOP</span><span class="sxs-lookup"><span data-stu-id="2ceea-117">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="2ceea-118">Использование EAC измените список участников в группах ролей</span><span class="sxs-lookup"><span data-stu-id="2ceea-118">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="2ceea-119">Чтобы открыть центр администрирования в Exchange Online, см. в центре [администрирования Exchange в Exchange Online.](/Exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="2ceea-119">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="2ceea-120">Чтобы открыть EAC в автономных EOP, см. в центре администрирования Exchange в режиме [автономный EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="2ceea-120">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="2ceea-121">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2ceea-121">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="2ceea-122">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="2ceea-122">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="2ceea-123">Дополнительные сведения о правилах потока почты в Exchange Online и Exchange Online Protection см. в дополнительных сведениях о правилах потока почты [(правила транспорта) в Exchange Online.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="2ceea-123">For more information about mail flow rules in Exchange Online and Exchange Online Protection, see [Mail flow rules (transport rules) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="2ceea-124">Используйте EAC для создания правила потока почты, которое задает SCL сообщения</span><span class="sxs-lookup"><span data-stu-id="2ceea-124">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="2ceea-125">В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.</span><span class="sxs-lookup"><span data-stu-id="2ceea-125">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="2ceea-126">Нажмите **кнопку Добавить** ![ значок Добавить, ](../../media/ITPro-EAC-AddIcon.png) а затем выберите Создать новое **правило**.</span><span class="sxs-lookup"><span data-stu-id="2ceea-126">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="2ceea-127">На открывшейся странице **Новое правило** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="2ceea-127">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="2ceea-128">**Имя.** Введите уникальное, описательное имя для правила.</span><span class="sxs-lookup"><span data-stu-id="2ceea-128">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="2ceea-129">Нажмите кнопку **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="2ceea-129">Click **More Options**.</span></span>

   - <span data-ttu-id="2ceea-130">**Примени это правило,** если выберите одно или несколько условий для идентификации сообщений.</span><span class="sxs-lookup"><span data-stu-id="2ceea-130">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="2ceea-131">Дополнительные сведения см. в рубрике Условия и исключения правил потока почты [(предикаты) в Exchange Online.](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)</span><span class="sxs-lookup"><span data-stu-id="2ceea-131">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="2ceea-132">**У следующих**: **Выберите Изменение свойств сообщения** установить уровень доверия нежелательной почты \> **(SCL).**</span><span class="sxs-lookup"><span data-stu-id="2ceea-132">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="2ceea-133">В **диалоговом окантовке Указать SCL** настройте одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="2ceea-133">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="2ceea-134">**Обход фильтрации нежелательной почты.** Сообщения будут пропускать фильтрацию нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="2ceea-134">**Bypass spam filtering**: The messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="2ceea-135">Будьте очень осторожны, разрешая сообщения пропускать фильтрацию нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="2ceea-135">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="2ceea-136">Злоумышленники могут использовать эту уязвимость для отправки фишинговых и других вредоносных сообщений в вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="2ceea-136">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="2ceea-137">Правила потока почты требуют большего, чем просто адрес электронной почты или домен отправитель.</span><span class="sxs-lookup"><span data-stu-id="2ceea-137">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="2ceea-138">Дополнительные сведения см. в [списке Создание безопасных списков](create-safe-sender-lists-in-office-365.md)отправитель в EOP.</span><span class="sxs-lookup"><span data-stu-id="2ceea-138">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="2ceea-139">**От 0 до 4.** Сообщение отправляется через фильтрацию нежелательной почты для дополнительной обработки.</span><span class="sxs-lookup"><span data-stu-id="2ceea-139">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="2ceea-140">**5 или 6**. Сообщение помечено как **спам**.</span><span class="sxs-lookup"><span data-stu-id="2ceea-140">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="2ceea-141">Действие, настроенное для вердиктов фильтрации нежелательной почты в политиках по борьбе со спамом, применяется к сообщению (по умолчанию значение **Move message to Junk Email folder).** </span><span class="sxs-lookup"><span data-stu-id="2ceea-141">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="2ceea-142">**От 7 до 9**: сообщение помечено как спам **с высокой уверенностью**.</span><span class="sxs-lookup"><span data-stu-id="2ceea-142">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="2ceea-143">Действие, настроенное для вердиктов о фильтрации нежелательной почты с высоким уровнем доверия в политиках по борьбе со спамом, применяется к сообщению (по умолчанию значение **Move message to Junk Email folder).** </span><span class="sxs-lookup"><span data-stu-id="2ceea-143">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="2ceea-144">Укажите дополнительные свойства, которые нужны для правила.</span><span class="sxs-lookup"><span data-stu-id="2ceea-144">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="2ceea-145">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2ceea-145">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="2ceea-146">Как проверить, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="2ceea-146">How do you know this worked?</span></span>

<span data-ttu-id="2ceea-147">Чтобы убедиться, что эта процедура работает правильно, отправьте сообщение одному из пользователей в вашей организации и убедитесь, что с сообщением выполняется ожидаемое действие.</span><span class="sxs-lookup"><span data-stu-id="2ceea-147">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="2ceea-148">Например, если вы **задали значение для вероятности нежелательной почты (SCL)** **Обход фильтрации нежелательной почты**, сообщение должно быть отправлено в папку "Входящие" указанного получателя.</span><span class="sxs-lookup"><span data-stu-id="2ceea-148">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="2ceea-149">Однако если вы установите уровень доверия к нежелательной почте  **(SCL)** до **9,** а действие высокой уверенности в нежелательной почте для применимых политик по борьбе со спамом должно переместить сообщение в папку нежелательной почты, то сообщение должно быть отправлено в папку нежелательной почты указанного получателя.</span><span class="sxs-lookup"><span data-stu-id="2ceea-149">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable anti-spam policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>