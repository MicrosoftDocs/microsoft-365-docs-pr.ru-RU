---
title: Использование правил обработки почтового процесса для нежелательной почты в сообщениях
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Узнайте, как создавать правила для поток обработки почты (правила транспорта) для идентификации сообщений и установки ВЕРОЯТНОсти нежелательной почты для сообщений в Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 791e6747e1ffa92d54e7d4f4a6c257c3aad4c0d9
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195859"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a><span data-ttu-id="e311b-103">Установка вероятности нежелательной почты (SCL) в сообщениях в EOP с помощью правил для почтового процесса</span><span class="sxs-lookup"><span data-stu-id="e311b-103">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e311b-104">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или Exchange Online Protection (EOP) без почтовых ящиков Exchange Online, EOP использует политики защиты от нежелательной почты (также называемые политиками фильтрации нежелательной почты или фильтрами содержимого) для сканирования входящих сообщений для спама</span><span class="sxs-lookup"><span data-stu-id="e311b-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="e311b-105">Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e311b-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="e311b-106">Если вы хотите пометить определенные сообщения как нежелательные, прежде чем они будут проверены при фильтрации нежелательной почты или помечать сообщения таким образом, чтобы они пропустили фильтрацию нежелательной почты, можно создать правила для обработки сообщений (также называемые правилами транспорта), чтобы определить сообщения и установить уровень вероятности нежелательной почты (SCL).</span><span class="sxs-lookup"><span data-stu-id="e311b-106">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="e311b-107">Для получения дополнительных сведений о ВЕРОЯТНОсти нежелательной почты [(SCL) в EOP](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="e311b-107">For more information about the SCL, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e311b-108">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="e311b-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e311b-109">Прежде чем выполнять эти процедуры, вам необходимо назначить разрешения в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e311b-109">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="e311b-110">В частности, необходимо назначить роль " **правила транспорта** ", которая назначается для ролей управления **организацией**, **управления соответствием требованиям**и управления **записями** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e311b-110">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="e311b-111">Дополнительные сведения см. в статье [Управление группами ролей в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="e311b-111">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="e311b-112">Чтобы открыть центр администрирования Exchange в Exchange Online, обратитесь к [центру администрирования Exchange в Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="e311b-112">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="e311b-113">Дополнительные сведения о правилах обработки почты в Exchange Online см. [правила для обработки почтового ящика (правила транспорта) в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="e311b-113">For more information about mail flow rules in Exchange Online, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="e311b-114">Использование центра администрирования Exchange для создания правила обработки почтового ящика, которое задает значение вероятности нежелательной почты для сообщения</span><span class="sxs-lookup"><span data-stu-id="e311b-114">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="e311b-115">В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.</span><span class="sxs-lookup"><span data-stu-id="e311b-115">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="e311b-116">Щелкните **Добавить** ![ значок Добавить ](../../media/ITPro-EAC-AddIcon.png) , а затем выберите **создать новое правило**.</span><span class="sxs-lookup"><span data-stu-id="e311b-116">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="e311b-117">На открывшейся странице **Новое правило** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e311b-117">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="e311b-118">**Name**: введите уникальное описательное имя правила.</span><span class="sxs-lookup"><span data-stu-id="e311b-118">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="e311b-119">Нажмите кнопку **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="e311b-119">Click **More Options**.</span></span>

   - <span data-ttu-id="e311b-120">**Применять это правило, если**: выберите одно или несколько условий для идентификации сообщений.</span><span class="sxs-lookup"><span data-stu-id="e311b-120">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="e311b-121">Дополнительные сведения см. [в статье условия и исключения правила обработки почты (предикаты) в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span><span class="sxs-lookup"><span data-stu-id="e311b-121">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="e311b-122">**Выполните следующие**действия: выберите **изменить свойства сообщения** \> **установите уровень вероятности нежелательной почты (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="e311b-122">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="e311b-123">В появившемся диалоговом окне **Указание вероятности** настройте одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="e311b-123">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="e311b-124">**Обход фильтрации нежелательной почты**: сообщения будут пропускать фильтрацию нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="e311b-124">**Bypass spam filtering**: The messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="e311b-125">Будьте внимательны, разрешая сообщениям пропускать фильтрацию нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="e311b-125">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="e311b-126">Злоумышленники могут использовать эту уязвимость для отправки фишинговых сообщений и других вредоносных сообщений в организацию.</span><span class="sxs-lookup"><span data-stu-id="e311b-126">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="e311b-127">Для правил почтового процесса требуется больше, чем просто адрес электронной почты отправителя или домен.</span><span class="sxs-lookup"><span data-stu-id="e311b-127">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="e311b-128">Дополнительные сведения см. [в статье Создание списков надежных отправителей в EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="e311b-128">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="e311b-129">от **0 до 4**: сообщение отправляется при фильтрации нежелательной почты для дополнительной обработки.</span><span class="sxs-lookup"><span data-stu-id="e311b-129">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="e311b-130">**5 или 6**: сообщение помечено как **Нежелательная почта**.</span><span class="sxs-lookup"><span data-stu-id="e311b-130">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="e311b-131">Действие, настроенное для фильтрации **нежелательной почты** вердиктс в политиках защиты от нежелательной почты, применяется к сообщению (значение по умолчанию — **переместить сообщение в папку "Нежелательная почта**").</span><span class="sxs-lookup"><span data-stu-id="e311b-131">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="e311b-132">**7 – 9**: сообщение помечено как **Нежелательная почта высокой достоверности**.</span><span class="sxs-lookup"><span data-stu-id="e311b-132">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="e311b-133">Действие, настроенное для фильтрации нежелательной **почты высокой надежности** , вердиктс в политиках защиты от нежелательной почты применяется к сообщению (значение по умолчанию: **переместить сообщение в папку "Нежелательная почта**").</span><span class="sxs-lookup"><span data-stu-id="e311b-133">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="e311b-134">Укажите дополнительные свойства, которые требуется использовать для правила.</span><span class="sxs-lookup"><span data-stu-id="e311b-134">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="e311b-135">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e311b-135">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="e311b-136">Как проверить, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="e311b-136">How do you know this worked?</span></span>

<span data-ttu-id="e311b-137">Чтобы убедиться, что эта процедура работает правильно, отправьте сообщение одному из пользователей в вашей организации и убедитесь, что с сообщением выполняется ожидаемое действие.</span><span class="sxs-lookup"><span data-stu-id="e311b-137">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="e311b-138">Например, если вы **задали значение для вероятности нежелательной почты (SCL)** **Обход фильтрации нежелательной почты**, сообщение должно быть отправлено в папку "Входящие" указанного получателя.</span><span class="sxs-lookup"><span data-stu-id="e311b-138">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="e311b-139">Тем не менее, если **установить** для вероятности нежелательной почты **9**, а для соответствующих политик защиты от нежелательной **почты —** переместить сообщение в папку нежелательной почты, сообщение должно быть отправлено в указанную папку нежелательной почты получателя.</span><span class="sxs-lookup"><span data-stu-id="e311b-139">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable anti-spam policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>
