---
title: Настройка доставки сторонних фишинговых симуляций пользователям и неотображемых сообщений в почтовые ящики SecOps
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
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Администраторы могут узнать, как использовать передовую политику доставки в Exchange Online Protection (EOP) для идентификации сообщений, которые не должны фильтроваться в определенных поддерживаемых сценариях (сторонние фишинговые симуляции и сообщения, доставленные в почтовые ящики операций безопасности (SecOps).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b989b11739b5418ad14e147f76dde0e0dd7b1b1a
ms.sourcegitcommit: 233989a02a3fc6db33c995ad06b1f820f08f8f0a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53383454"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a><span data-ttu-id="afdff-103">Настройка доставки сторонних фишинговых симуляций пользователям и неотображемых сообщений в почтовые ящики SecOps</span><span class="sxs-lookup"><span data-stu-id="afdff-103">Configure the delivery of third-party phishing simulations to users and unfiltered messages to SecOps mailboxes</span></span>

<span data-ttu-id="afdff-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="afdff-104">**Applies to**</span></span>
- [<span data-ttu-id="afdff-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="afdff-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="afdff-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="afdff-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="afdff-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="afdff-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="afdff-108">Функция, описанная в этой статье, доступна не всем и подлежит изменениям.</span><span class="sxs-lookup"><span data-stu-id="afdff-108">The feature that's described in this article is in Preview, isn't available to everyone, and is subject to change.</span></span>

<span data-ttu-id="afdff-109">Чтобы обеспечить безопасность организации по [умолчанию,](secure-by-default.md)Exchange Online Protection (EOP) не разрешает безопасные списки или обход фильтрации для сообщений, которые определены как вредоносные программы или высокой достоверности фишинга.</span><span class="sxs-lookup"><span data-stu-id="afdff-109">To keep your organization [secure by default](secure-by-default.md), Exchange Online Protection (EOP) does not allow safe lists or filtering bypass for messages that are identified as malware or high confidence phishing.</span></span> <span data-ttu-id="afdff-110">Но существуют определенные сценарии, которые требуют доставки неотобраченных сообщений.</span><span class="sxs-lookup"><span data-stu-id="afdff-110">But, there are specific scenarios that require the delivery of unfiltered messages.</span></span> <span data-ttu-id="afdff-111">Пример:</span><span class="sxs-lookup"><span data-stu-id="afdff-111">For example:</span></span>

- <span data-ttu-id="afdff-112">**Сторонние имитации фишинга.** Имитация атак может помочь вам идентифицировать уязвимых пользователей до того, как реальная атака ударит по организации.</span><span class="sxs-lookup"><span data-stu-id="afdff-112">**Third-party phishing simulations**: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="afdff-113">Почтовые ящики операций безопасности **(SecOps)**— выделенные почтовые ящики, используемые группами безопасности для сбора и анализа неотобраченных сообщений (как хороших, так и плохих).</span><span class="sxs-lookup"><span data-stu-id="afdff-113">**Security operations (SecOps) mailboxes**: Dedicated mailboxes that are used by security teams to collect and analyze unfiltered messages (both good and bad).</span></span>

<span data-ttu-id="afdff-114">Для _предотвращения_ фильтрации этих сообщений в Microsoft 365  в этих конкретных сценариях используется усовершенствованая политика доставки в Microsoft 365. <sup>\*</sup> Продвинутая политика доставки гарантирует, что сообщения в этих сценариях будут достигать следующих результатов:</span><span class="sxs-lookup"><span data-stu-id="afdff-114">You use the _advanced delivery policy_ in Microsoft 365 to prevent these messages _in these specific scenarios_ from being filtered.<sup>\*</sup> The advanced delivery policy ensures that messages in these scenarios achieve the following results:</span></span>

- <span data-ttu-id="afdff-115">Фильтры в EOP и Microsoft Defender для Office 365 не принимают никаких действий по этим сообщениям.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="afdff-115">Filters in EOP and Microsoft Defender for Office 365 take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="afdff-116">Очистка от нежелательной почты и фишинга с нулевой часовой очисткой [(ZAP)](zero-hour-auto-purge.md) не принимает никаких действий по этим сообщениям.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="afdff-116">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="afdff-117">[Для этих сценариев](alerts.md) системные оповещения по умолчанию не запускаются.</span><span class="sxs-lookup"><span data-stu-id="afdff-117">[Default system alerts](alerts.md) aren't triggered for these scenarios.</span></span>
- <span data-ttu-id="afdff-118">[Air и кластеризация в Defender для Office 365](office-365-air.md) игнорирует эти сообщения.</span><span class="sxs-lookup"><span data-stu-id="afdff-118">[AIR and clustering in Defender for Office 365](office-365-air.md) ignores these messages.</span></span>
- <span data-ttu-id="afdff-119">В частности, для сторонних имитаций фишинга:</span><span class="sxs-lookup"><span data-stu-id="afdff-119">Specifically for third-party phishing simulations:</span></span>
  - <span data-ttu-id="afdff-120">[Отправки администратора](admin-submission.md) создают автоматический ответ, который говорит, что сообщение является частью фишинговой кампании моделирования и не представляет реальной угрозы.</span><span class="sxs-lookup"><span data-stu-id="afdff-120">[Admin submissions](admin-submission.md) generates an automatic response saying that the message is part of a phishing simulation campaign and isn't a real threat.</span></span> <span data-ttu-id="afdff-121">Оповещения и AIR не будут запускаться.</span><span class="sxs-lookup"><span data-stu-id="afdff-121">Alerts and AIR will not be triggered.</span></span>
  - <span data-ttu-id="afdff-122">[Сейф ссылки в Defender для Office 365](safe-links.md) не блокируют или не взрывают указанные URL-адреса в этих сообщениях.</span><span class="sxs-lookup"><span data-stu-id="afdff-122">[Safe Links in Defender for Office 365](safe-links.md) doesn't block or detonate the specifically identified URLs in these messages.</span></span>
  - <span data-ttu-id="afdff-123">[Сейф Вложения в Defender для Office 365](safe-attachments.md) не детонировать вложения в этих сообщениях.</span><span class="sxs-lookup"><span data-stu-id="afdff-123">[Safe Attachments in Defender for Office 365](safe-attachments.md) doesn't detonate attachments in these messages.</span></span>

<span data-ttu-id="afdff-124"><sup>\*</sup> Вы не можете обойти фильтрацию вредоносных программ или ZAP для вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="afdff-124"><sup>\*</sup> You can't bypass malware filtering or ZAP for malware.</span></span>

<span data-ttu-id="afdff-125">Сообщения, идентифицированные в продвинутой политике доставки, не являются угрозами безопасности, поэтому сообщения помечены как переопределения системы.</span><span class="sxs-lookup"><span data-stu-id="afdff-125">Messages that are identified by the advanced delivery policy aren't security threats, so the messages are marked as system overrides.</span></span> <span data-ttu-id="afdff-126">Администраторы могут фильтровать и анализировать эти переопределения системы в следующих интерфейсах:</span><span class="sxs-lookup"><span data-stu-id="afdff-126">Admins can filter and analyze these system overrides in the following experiences:</span></span>

- [<span data-ttu-id="afdff-127">Обнаружение обозревателя угроз и обнаружения в режиме реального времени в Defender для Office 365 плана 2</span><span class="sxs-lookup"><span data-stu-id="afdff-127">Threat Explorer/Real-time detections in Defender for Office 365 plan 2</span></span>](threat-explorer.md)
- <span data-ttu-id="afdff-128">Страница [сущности электронной почты в обнаружении обозревателя угроз и обнаружения в режиме реального времени](mdo-email-entity-page.md)</span><span class="sxs-lookup"><span data-stu-id="afdff-128">The [Email entity Page in Threat Explorer/Real-time detections](mdo-email-entity-page.md)</span></span>
- <span data-ttu-id="afdff-129">Отчет [о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="afdff-129">The [Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="afdff-130">Расширенный поиск в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="afdff-130">Advanced hunting in Microsoft Defender for Endpoint</span></span>](../defender-endpoint/advanced-hunting-overview.md)
- [<span data-ttu-id="afdff-131">Представления кампании</span><span class="sxs-lookup"><span data-stu-id="afdff-131">Campaign Views</span></span>](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="afdff-132">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="afdff-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="afdff-133">Чтобы открыть портал Microsoft 365 Defender, перейдите на сайт <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="afdff-133">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="afdff-134">Чтобы перейти непосредственно на **страницу advanced delivery,** откройте <https://security.microsoft.com/advanceddelivery> .</span><span class="sxs-lookup"><span data-stu-id="afdff-134">To go directly to the **Advanced delivery** page, open <https://security.microsoft.com/advanceddelivery>.</span></span>

- <span data-ttu-id="afdff-135">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="afdff-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="afdff-136">Прежде чем делать процедуры в этой статье, необходимо получить соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="afdff-136">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="afdff-137">Чтобы создать, изменить или удалить настроенные параметры в продвинутой политике доставки,  необходимо быть членом группы ролей администратора безопасности  на портале **Microsoft 365 Defender** и членом группы ролей управления организацией в **Exchange Online**.</span><span class="sxs-lookup"><span data-stu-id="afdff-137">To create, modify, or remove configured settings in the advanced delivery policy, you need to be a member of the **Security Administrator** role group in the **Microsoft 365 Defender portal** and a member of the **Organization Management** role group in **Exchange Online**.</span></span>
  - <span data-ttu-id="afdff-138">Для доступа только для чтения к продвинутой политике доставки необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="afdff-138">For read-only access to the advanced delivery policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="afdff-139">Дополнительные сведения см. [в Microsoft 365 Defender](permissions-microsoft-365-security-center.md) и [разрешениях](/exchange/permissions-exo/permissions-exo)в Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="afdff-139">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > <span data-ttu-id="afdff-140">Добавление пользователей к соответствующей роли Azure Active Directory дает пользователям необходимые разрешения на  портале Microsoft 365 Defender и разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="afdff-140">Adding users to the corresponding Azure Active Directory role gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="afdff-141">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="afdff-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="afdff-142">Используйте портал Microsoft 365 Defender для настройки почтовых ящиков SecOps в продвинутой политике доставки</span><span class="sxs-lookup"><span data-stu-id="afdff-142">Use the Microsoft 365 Defender portal to configure SecOps mailboxes in the advanced delivery policy</span></span>

1. <span data-ttu-id="afdff-143">На портале Microsoft 365 Defender перейдите на страницу Политики **совместной &** электронной почты & Правила правила \>  \>  \>  \> доставки.</span><span class="sxs-lookup"><span data-stu-id="afdff-143">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="afdff-144">На странице **Advanced delivery** убедитесь, что выбрана вкладка почтовых ящиков **SecOps,** а затем сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="afdff-144">On the **Advanced delivery** page, verify that the **SecOps mailbox** tab is selected, and then do one of the following steps:</span></span>
   - <span data-ttu-id="afdff-145">Нажмите ![ кнопку Изменить ](../../media/m365-cc-sc-edit-icon.png) **значок Изменить**.</span><span class="sxs-lookup"><span data-stu-id="afdff-145">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="afdff-146">Если нет настроенных имитаций фишинга, нажмите **кнопку Добавить**.</span><span class="sxs-lookup"><span data-stu-id="afdff-146">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="afdff-147">В открываемом флажке Изменить почтовые ящики SecOps введите существующий Exchange Online почтовый ящик, который необходимо назначить почтовым ящиком **SecOps,** предприняв один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="afdff-147">On the **Edit SecOps mailboxes** flyout that opens, enter an existing Exchange Online mailbox that you want to designate as SecOps mailbox by doing one of the following steps:</span></span>
   - <span data-ttu-id="afdff-148">Щелкните в поле, дайте список почтовых ящиков разрешить, а затем выберите почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="afdff-148">Click in the box, let the list of mailboxes resolve, and then select the mailbox.</span></span>
   - <span data-ttu-id="afdff-149">Щелкните в поле начало ввода идентификатора для почтового ящика (имя, имя отображения, псевдоним, адрес электронной почты, имя учетной записи и т.д.) и выберите почтовый ящик (имя отображения) из результатов.</span><span class="sxs-lookup"><span data-stu-id="afdff-149">Click in the box start typing an identifier for the mailbox (name, display name, alias, email address, account name, etc.), and select the mailbox (display name) from the results.</span></span>

     <span data-ttu-id="afdff-150">Повторите этот шаг нужное количество раз.</span><span class="sxs-lookup"><span data-stu-id="afdff-150">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="afdff-151">Группы рассылки запрещены.</span><span class="sxs-lookup"><span data-stu-id="afdff-151">Distribution groups are not allowed.</span></span>

     <span data-ttu-id="afdff-152">Чтобы удалить существующее значение, нажмите "Удалить".</span><span class="sxs-lookup"><span data-stu-id="afdff-152">To remove an existing value, click remove</span></span> ![Значок "Удалить"](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="afdff-154">рядом со значением.</span><span class="sxs-lookup"><span data-stu-id="afdff-154">next to the value.</span></span>

4. <span data-ttu-id="afdff-155">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="afdff-155">When you're finished, click **Save**.</span></span>

<span data-ttu-id="afdff-156">Настроенные записи почтовых ящиков SecOps отображаются на вкладке **почтовый ящик SecOps.** Чтобы внести изменения, нажмите ![ кнопку Изменить ](../../media/m365-cc-sc-edit-icon.png) **значок Изменить** на вкладке.</span><span class="sxs-lookup"><span data-stu-id="afdff-156">The SecOps mailbox entries that you configured are displayed on the **SecOps mailbox** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="afdff-157">Используйте портал Microsoft 365 Defender для настройки сторонних фишинговых симуляций в продвинутой политике доставки</span><span class="sxs-lookup"><span data-stu-id="afdff-157">Use the Microsoft 365 Defender portal to configure third-party phishing simulations in the advanced delivery policy</span></span>

1. <span data-ttu-id="afdff-158">На портале Microsoft 365 Defender перейдите на страницу Политики **совместной &** электронной почты & Правила правила \>  \>  \>  \> доставки.</span><span class="sxs-lookup"><span data-stu-id="afdff-158">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="afdff-159">На странице **Advanced delivery** выберите вкладку **фишинг-моделирования** и сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="afdff-159">On the **Advanced delivery** page, select the **Phishing simulation** tab, and then do one of the following steps:</span></span>
   - <span data-ttu-id="afdff-160">Нажмите ![ кнопку Изменить ](../../media/m365-cc-sc-edit-icon.png) **значок Изменить**.</span><span class="sxs-lookup"><span data-stu-id="afdff-160">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="afdff-161">Если нет настроенных имитаций фишинга, нажмите **кнопку Добавить**.</span><span class="sxs-lookup"><span data-stu-id="afdff-161">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="afdff-162">В **открываемом вылете** редактирования сторонних фишинговых симуляций настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="afdff-162">On the **Edit third-party phishing simulation** flyout that opens, configure the following settings:</span></span>

   - <span data-ttu-id="afdff-163">**Отправка** домена. Разведите этот параметр и введите по крайней мере один домен электронной почты (например, contoso.com) щелкнув в поле, введите значение, а затем нажмите кнопку Введите или выберите значение, отображаемую ниже окна.</span><span class="sxs-lookup"><span data-stu-id="afdff-163">**Sending domain**: Expand this setting and enter at least one email address domain (for example, contoso.com) by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="afdff-164">Повторите этот шаг нужное количество раз.</span><span class="sxs-lookup"><span data-stu-id="afdff-164">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="afdff-165">Можно добавить до 10 записей.</span><span class="sxs-lookup"><span data-stu-id="afdff-165">You can add up to 10 entries.</span></span>
   - <span data-ttu-id="afdff-166">**Отправка IP.** Разведите этот параметр и введите хотя бы один допустимый адрес IPv4, щелкнув в поле, введите значение, а затем нажав кнопку Ввод или выбрав значение, отображаемую ниже окна.</span><span class="sxs-lookup"><span data-stu-id="afdff-166">**Sending IP**: Expand this setting and enter at least one valid IPv4 address is required by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="afdff-167">Повторите этот шаг нужное количество раз.</span><span class="sxs-lookup"><span data-stu-id="afdff-167">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="afdff-168">Можно добавить до 10 записей.</span><span class="sxs-lookup"><span data-stu-id="afdff-168">You can add up to 10 entries.</span></span> <span data-ttu-id="afdff-169">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="afdff-169">Valid values are:</span></span>
     - <span data-ttu-id="afdff-170">Один IP. Например, 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="afdff-170">Single IP: For example, 192.168.1.1.</span></span>
     - <span data-ttu-id="afdff-171">Диапазон IP: Например, 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="afdff-171">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
     - <span data-ttu-id="afdff-172">IP CIDR. Например, 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="afdff-172">CIDR IP: For example, 192.168.0.1/25.</span></span>
   - <span data-ttu-id="afdff-173">URL-адреса моделирования, позволяющие: расширить этот параметр и дополнительно ввести определенные URL-адреса, которые являются частью вашей кампании фишинг-моделирования, которые не должны быть заблокированы или детонировать, щелкнув в поле, введите значение, а затем нажатие ввода или выбора значения, отображаемого ниже окна.</span><span class="sxs-lookup"><span data-stu-id="afdff-173">**Simulation URLs to allow**: Expand this setting and optionally enter specific URLs that are part of your phishing simulation campaign that should not be blocked or detonated by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="afdff-174">Можно добавить до 10 записей.</span><span class="sxs-lookup"><span data-stu-id="afdff-174">You can add up to 10 entries.</span></span> <span data-ttu-id="afdff-175">В формате синтаксиса URL-адресов см. [синтаксис URL-адреса](/microsoft-365/security/office-365-security/tenant-allow-block-list#url-syntax-for-the-tenant-allowblock-list)для списка разрешить или блокировать клиента.</span><span class="sxs-lookup"><span data-stu-id="afdff-175">For the URL syntax format, see [URL syntax for the Tenant Allow/Block List](/microsoft-365/security/office-365-security/tenant-allow-block-list#url-syntax-for-the-tenant-allowblock-list).</span></span>

   <span data-ttu-id="afdff-176">Чтобы удалить существующее значение, нажмите "Удалить".</span><span class="sxs-lookup"><span data-stu-id="afdff-176">To remove an existing value, click remove</span></span> ![Значок "Удалить"](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="afdff-178">рядом со значением.</span><span class="sxs-lookup"><span data-stu-id="afdff-178">next to the value.</span></span>

4. <span data-ttu-id="afdff-179">По завершению сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="afdff-179">When you're finished, do one of the following steps:</span></span>
   - <span data-ttu-id="afdff-180">**Первый раз:** **Нажмите добавить,** а затем нажмите **кнопку Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="afdff-180">**First time**: Click **Add**, and then click **Close**.</span></span>
   - <span data-ttu-id="afdff-181">**Изменение существующего:** **Щелкните Сохранить** и нажмите **кнопку Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="afdff-181">**Edit existing**: Click **Save** and then click **Close**.</span></span>

<span data-ttu-id="afdff-182">Настроенные сторонние записи моделирования фишинга отображаются на вкладке **Имитация** фишинга. Чтобы внести изменения, нажмите ![ кнопку Изменить ](../../media/m365-cc-sc-edit-icon.png) **значок Изменить** на вкладке.</span><span class="sxs-lookup"><span data-stu-id="afdff-182">The third-party phishing simulation entries that you configured are displayed on the **Phishing simulation** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="additional-scenarios-that-require-filtering-bypass"></a><span data-ttu-id="afdff-183">Дополнительные сценарии, которые требуют обхода фильтрации</span><span class="sxs-lookup"><span data-stu-id="afdff-183">Additional scenarios that require filtering bypass</span></span>

<span data-ttu-id="afdff-184">В дополнение к двум сценариям, которые может помочь вам усовершенствовать политика доставки, существуют и другие сценарии, которые могут потребовать обхода фильтрации:</span><span class="sxs-lookup"><span data-stu-id="afdff-184">In addition to the two scenarios that the advanced delivery policy can help you with, there are other scenarios that might require you bypass filtering:</span></span>

- <span data-ttu-id="afdff-185">**Сторонние фильтры.** Если запись MX  вашего домена не означает Office 365 (сообщения сначала перенаписыются где-то [еще),](secure-by-default.md) безопасность по умолчанию *недоступна.*</span><span class="sxs-lookup"><span data-stu-id="afdff-185">**Third-party filters**: If your domain's MX record *doesn't* point to Office 365 (messages are routed somewhere else first), [secure by default](secure-by-default.md) *is not available*.</span></span> <span data-ttu-id="afdff-186">Если вы хотите добавить защиту, необходимо включить усиленную фильтрацию для соединители (также известной как *пропустить перечисление).*</span><span class="sxs-lookup"><span data-stu-id="afdff-186">If you'd like to add protection, you'll need to enable Enhanced Filtering for Connectors (also known as *skip listing*).</span></span> <span data-ttu-id="afdff-187">Дополнительные сведения см. в [ссылке Управление потоком почты с](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud)помощью стороннее облачной службы с Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="afdff-187">For more information, see [Manage mail flow using a third-party cloud service with Exchange Online](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud).</span></span> <span data-ttu-id="afdff-188">Если вы не хотите расширенной фильтрации для соединители, используйте правила потока почты (также известные как правила транспорта), чтобы обойти фильтрацию Microsoft для сообщений, которые уже были оценены сторонним фильтрацией.</span><span class="sxs-lookup"><span data-stu-id="afdff-188">If you don't want Enhanced Filtering for Connectors,use mail flow rules (also known as transport rules) to bypass Microsoft filtering for messages that have already been evaluated by third-party filtering.</span></span> <span data-ttu-id="afdff-189">Дополнительные сведения см. в тексте Правила потока почты для [набора SCL в сообщениях.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)</span><span class="sxs-lookup"><span data-stu-id="afdff-189">For more information, see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).</span></span>

- <span data-ttu-id="afdff-190">**Ложные** срабатываки, которые рассматриваются в настоящее время. Вы [](admin-submission.md) можете временно разрешить некоторым сообщениям, которые по-прежнему анализируются Корпорацией Майкрософт с помощью представлений администратора, сообщать о известных хороших сообщениях, которые неправильно помечены как плохие для Microsoft (ложные срабатываки).</span><span class="sxs-lookup"><span data-stu-id="afdff-190">**False positives under review**: You might want to temporarily allow certain messages that are still being analyzed by Microsoft via [admin submissions](admin-submission.md) to report known good messages that are incorrectly being marked as bad to Microsoft (false positives).</span></span> <span data-ttu-id="afdff-191">Как и во всех переопределениях, мы **_настоятельно рекомендуем,_** чтобы эти надбавки были временными.</span><span class="sxs-lookup"><span data-stu-id="afdff-191">As with all overrides, we **_highly recommended_** that these allowances are temporary.</span></span>

## <a name="exchange-online-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="afdff-192">Exchange Online Процедуры PowerShell для почтовых ящиков SecOps в продвинутой политике доставки</span><span class="sxs-lookup"><span data-stu-id="afdff-192">Exchange Online PowerShell procedures for SecOps mailboxes in the advanced delivery policy</span></span>

<span data-ttu-id="afdff-193">В Exchange Online PowerShell основными элементами почтовых ящиков SecOps в продвинутой политике доставки являются:</span><span class="sxs-lookup"><span data-stu-id="afdff-193">In Exchange Online PowerShell, the basic elements of SecOps mailboxes in the advanced delivery policy are:</span></span>

- <span data-ttu-id="afdff-194">**Политика переопределения SecOps:** управляется с помощью **\* кодлетов -SecOpsOverridePolicy.**</span><span class="sxs-lookup"><span data-stu-id="afdff-194">**The SecOps override policy**: Controlled by the **\*-SecOpsOverridePolicy** cmdlets.</span></span>
- <span data-ttu-id="afdff-195">**Правило переопределения SecOps.** Управляется с помощью **\* кодлетов -SecOpsOverrideRule.**</span><span class="sxs-lookup"><span data-stu-id="afdff-195">**The SecOps override rule**: Controlled by the **\*-SecOpsOverrideRule** cmdlets.</span></span>

<span data-ttu-id="afdff-196">Это поведение приводит к следующим результатам:</span><span class="sxs-lookup"><span data-stu-id="afdff-196">This behavior has the following results:</span></span>

- <span data-ttu-id="afdff-197">Сначала создается политика, а затем создается правило, определя которое определяет политику, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="afdff-197">You create the policy first, then you create the rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="afdff-198">При удалении политики из PowerShell соответствующее правило также удаляется.</span><span class="sxs-lookup"><span data-stu-id="afdff-198">When you remove a policy from PowerShell, the corresponding rule is also removed.</span></span>
- <span data-ttu-id="afdff-199">При удалении правила из PowerShell соответствующая политика не удаляется.</span><span class="sxs-lookup"><span data-stu-id="afdff-199">When you remove a rule from PowerShell, the corresponding policy is not removed.</span></span> <span data-ttu-id="afdff-200">Соответствующую политику необходимо удалить вручную.</span><span class="sxs-lookup"><span data-stu-id="afdff-200">You need to remove the corresponding policy manually.</span></span>

### <a name="use-powershell-to-configure-secops-mailboxes"></a><span data-ttu-id="afdff-201">Использование PowerShell для настройки почтовых ящиков SecOps</span><span class="sxs-lookup"><span data-stu-id="afdff-201">Use PowerShell to configure SecOps mailboxes</span></span>

<span data-ttu-id="afdff-202">Настройка почтового ящика SecOps в продвинутой политике доставки в PowerShell — это двухшаговая процедура:</span><span class="sxs-lookup"><span data-stu-id="afdff-202">Configuring a SecOps mailbox in the advanced delivery policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="afdff-203">Создание политики переопределения SecOps.</span><span class="sxs-lookup"><span data-stu-id="afdff-203">Create the SecOps override policy.</span></span>
2. <span data-ttu-id="afdff-204">Создайте правило переопределения SecOps, которое указывает политику, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="afdff-204">Create the SecOps override rule that specifies the policy that the rule applies to.</span></span>

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a><span data-ttu-id="afdff-205">Шаг 1. Использование PowerShell для создания политики переопределения SecOps</span><span class="sxs-lookup"><span data-stu-id="afdff-205">Step 1: Use PowerShell to create the SecOps override policy</span></span>

<span data-ttu-id="afdff-206">Чтобы создать политику переопределения SecOps, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="afdff-206">To create the SecOps override policy, use the following syntax:</span></span>

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

<span data-ttu-id="afdff-207">**Примечание.** Независимо от значения Имя, которое вы указываете, имя политики будет SecOpsOverridePolicy, поэтому вы также можете использовать это значение.</span><span class="sxs-lookup"><span data-stu-id="afdff-207">**Note**: Regardless of the Name value you specify, the policy name will be SecOpsOverridePolicy, so you might as well use that value.</span></span>

<span data-ttu-id="afdff-208">В этом примере создается политика почтовых ящиков SecOps.</span><span class="sxs-lookup"><span data-stu-id="afdff-208">This example creates the SecOps mailbox policy.</span></span>

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo secops@contoso.com
```

<span data-ttu-id="afdff-209">Подробные сведения о синтаксисах и параметрах см. в [обзоре New-SecOpsOverridePolicy.](/powershell/module/exchange/new-secopsoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="afdff-209">For detailed syntax and parameter information, see [New-SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a><span data-ttu-id="afdff-210">Шаг 2. Использование PowerShell для создания правила переопределения SecOps</span><span class="sxs-lookup"><span data-stu-id="afdff-210">Step 2: Use PowerShell to create the SecOps override rule</span></span>

<span data-ttu-id="afdff-211">В этом примере создается правило почтовых ящиков SecOps с указанными настройками.</span><span class="sxs-lookup"><span data-stu-id="afdff-211">This example creates the SecOps mailbox rule with the specified settings.</span></span>

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

<span data-ttu-id="afdff-212">\*\*Примечание.\*\*\*\*Независимо от значения Имя, которое вы указываете, имя правила будет SecOpsOverrideRule, где имеется уникальное значение \<GUID\> \<GUID\> GUID (например, 6fed4b63-3563-495d-a481-b24a311f8329).</span><span class="sxs-lookup"><span data-stu-id="afdff-212">**Note**: \*\*Regardless of the Name value you specify, the rule name will be SecOpsOverrideRule\<GUID\> where \<GUID\> is a unique GUID value (for example, 6fed4b63-3563-495d-a481-b24a311f8329).</span></span>

<span data-ttu-id="afdff-213">Подробные сведения о синтаксисах и параметрах см. [в обзоре New-SecOpsOverrideRule.](/powershell/module/exchange/new-secopsoverriderule)</span><span class="sxs-lookup"><span data-stu-id="afdff-213">For detailed syntax and parameter information, see [New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule).</span></span>

### <a name="use-powershell-to-view-the-secops-override-policy"></a><span data-ttu-id="afdff-214">Использование PowerShell для просмотра политики переопределения SecOps</span><span class="sxs-lookup"><span data-stu-id="afdff-214">Use PowerShell to view the SecOps override policy</span></span>

<span data-ttu-id="afdff-215">В этом примере возвращаются подробные сведения о политике почтовых ящиков SecOps.</span><span class="sxs-lookup"><span data-stu-id="afdff-215">This example returns detailed information about the one and only SecOps mailbox policy.</span></span>

```powershell
Get-SecOpsOverridePolicy
```

<span data-ttu-id="afdff-216">Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-SecOpsOverridePolicy.](/powershell/module/exchange/get-secopsoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="afdff-216">For detailed syntax and parameter information, see [Get-SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-view-secops-override-rules"></a><span data-ttu-id="afdff-217">Использование PowerShell для просмотра правил переопределения SecOps</span><span class="sxs-lookup"><span data-stu-id="afdff-217">Use PowerShell to view SecOps override rules</span></span>

<span data-ttu-id="afdff-218">В этом примере возвращаются подробные сведения о правилах переопределения SecOps.</span><span class="sxs-lookup"><span data-stu-id="afdff-218">This example returns detailed information about SecOps override rules.</span></span>

```powershell
Get-SecOpsOverrideRule
```

<span data-ttu-id="afdff-219">Хотя предыдущая команда должна возвращать только одно правило, все правила, ожидающих удаления, также могут быть включены в результаты.</span><span class="sxs-lookup"><span data-stu-id="afdff-219">Although the previous command should return only one rule, any rules that are pending deletion might also be included in the results.</span></span>

<span data-ttu-id="afdff-220">В этом примере определяются допустимые правила (одно) и все недействительные правила.</span><span class="sxs-lookup"><span data-stu-id="afdff-220">This example identifies the valid rule (one) and any invalid rules.</span></span>

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

<span data-ttu-id="afdff-221">После определения недействительных правил их можно удалить с помощью **cmdlet Remove-SecOpsOverrideRule,** как описано ниже [в этой статье.](#use-powershell-to-remove-secops-override-rules)</span><span class="sxs-lookup"><span data-stu-id="afdff-221">After you identify the invalid rules, you can remove them by using the **Remove-SecOpsOverrideRule** cmdlet as described [later in this article](#use-powershell-to-remove-secops-override-rules).</span></span>

<span data-ttu-id="afdff-222">Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-SecOpsOverrideRule.](/powershell/module/exchange/get-secopsoverriderule)</span><span class="sxs-lookup"><span data-stu-id="afdff-222">For detailed syntax and parameter information, see [Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)</span></span>

### <a name="use-powershell-to-modify-the-secops-override-policy"></a><span data-ttu-id="afdff-223">Использование PowerShell для изменения политики переопределения SecOps</span><span class="sxs-lookup"><span data-stu-id="afdff-223">Use PowerShell to modify the SecOps override policy</span></span>

<span data-ttu-id="afdff-224">Чтобы изменить политику переопределения SecOps, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="afdff-224">To modify the SecOps override policy, use the following syntax:</span></span>

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

<span data-ttu-id="afdff-225">В этом примере secops2@contoso.com политики переопределения SecOps.</span><span class="sxs-lookup"><span data-stu-id="afdff-225">This example adds secops2@contoso.com to the SecOps override policy.</span></span>

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

<span data-ttu-id="afdff-226">**Примечание.** Если существует связанное, допустимые правила переопределения SecOps, адреса электронной почты в правиле также будут обновлены.</span><span class="sxs-lookup"><span data-stu-id="afdff-226">**Note**: If an associated, valid SecOps override rule exists, the email addresses in the rule will also be updated.</span></span>

<span data-ttu-id="afdff-227">Подробные сведения о синтаксисах и параметрах см. в [обзоре Set-SecOpsOverridePolicy.](/powershell/module/exchange/set-secopsoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="afdff-227">For detailed syntax and parameter information, see [Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-modify-a-secops-override-rule"></a><span data-ttu-id="afdff-228">Использование PowerShell для изменения правила переопределения SecOps</span><span class="sxs-lookup"><span data-stu-id="afdff-228">Use PowerShell to modify a SecOps override rule</span></span>

<span data-ttu-id="afdff-229">Кодлет **Set-SecOpsOverrideRule** не изменит адреса электронной почты в правиле переопределения SecOps.</span><span class="sxs-lookup"><span data-stu-id="afdff-229">The **Set-SecOpsOverrideRule** cmdlet does not modify the email addresses in the SecOps override rule.</span></span> <span data-ttu-id="afdff-230">Чтобы изменить адреса электронной почты в правиле переопределения SecOps, используйте **cmdlet Set-SecOpsOverridePolicy.**</span><span class="sxs-lookup"><span data-stu-id="afdff-230">To modify the email addresses in the SecOps override rule, use the **Set-SecOpsOverridePolicy** cmdlet.</span></span>

<span data-ttu-id="afdff-231">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-SecOpsOverrideRule.](/powershell/module/exchange/set-secopsoverriderule)</span><span class="sxs-lookup"><span data-stu-id="afdff-231">For detailed syntax and parameter information, see [Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule).</span></span>

### <a name="use-powershell-to-remove-the-secops-override-policy"></a><span data-ttu-id="afdff-232">Использование PowerShell для удаления политики переопределения SecOps</span><span class="sxs-lookup"><span data-stu-id="afdff-232">Use PowerShell to remove the SecOps override policy</span></span>

<span data-ttu-id="afdff-233">В этом примере удаляется политика почтовых ящиков SecOps и соответствующее правило.</span><span class="sxs-lookup"><span data-stu-id="afdff-233">This example removes the SecOps Mailbox policy and the corresponding rule.</span></span>

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

<span data-ttu-id="afdff-234">Подробные сведения о синтаксисе и параметрах см. в этой ссылке [Remove-SecOpsOverridePolicy.](/powershell/module/exchange/remove-secopsoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="afdff-234">For detailed syntax and parameter information, see [Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-remove-secops-override-rules"></a><span data-ttu-id="afdff-235">Использование PowerShell для удаления правил переопределения SecOps</span><span class="sxs-lookup"><span data-stu-id="afdff-235">Use PowerShell to remove SecOps override rules</span></span>

<span data-ttu-id="afdff-236">Чтобы удалить правило переопределения SecOps, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="afdff-236">To remove a SecOps override rule, use the following syntax:</span></span>

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

<span data-ttu-id="afdff-237">В этом примере удаляется указанное правило переопределения SecOps.</span><span class="sxs-lookup"><span data-stu-id="afdff-237">This example removes the specified SecOps override rule.</span></span>

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

<span data-ttu-id="afdff-238">Подробные сведения о синтаксисах и параметрах см. в этой ссылке [Remove-SecOpsOverrideRule.](/powershell/module/exchange/remove-secopsoverriderule)</span><span class="sxs-lookup"><span data-stu-id="afdff-238">For detailed syntax and parameter information, see [Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule).</span></span>

## <a name="exchange-online-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="afdff-239">Exchange Online Процедуры PowerShell для сторонних имитаций фишинга в продвинутой политике доставки</span><span class="sxs-lookup"><span data-stu-id="afdff-239">Exchange Online PowerShell procedures for third-party phishing simulations in the advanced delivery policy</span></span>

<span data-ttu-id="afdff-240">В Exchange Online PowerShell основными элементами сторонних имитаций фишинга в продвинутой политике доставки являются:</span><span class="sxs-lookup"><span data-stu-id="afdff-240">In Exchange Online PowerShell, the basic elements of third-party phishing simulations in the advanced delivery policy are:</span></span>

- <span data-ttu-id="afdff-241">**Политика** переопределения фишингового моделирования: управляется с помощью **\* кодлетов -PhishSimOverridePolicy.**</span><span class="sxs-lookup"><span data-stu-id="afdff-241">**The phishing simulation override policy**: Controlled by the **\*-PhishSimOverridePolicy** cmdlets.</span></span>
- <span data-ttu-id="afdff-242">**Правило переопределения фишингового** моделирования: управляется с помощью **\* кодлетов -PhishSimOverrideRule.**</span><span class="sxs-lookup"><span data-stu-id="afdff-242">**The phishing simulation override rule**: Controlled by the **\*-PhishSimOverrideRule** cmdlets.</span></span>

<span data-ttu-id="afdff-243">Это поведение приводит к следующим результатам:</span><span class="sxs-lookup"><span data-stu-id="afdff-243">This behavior has the following results:</span></span>

- <span data-ttu-id="afdff-244">Сначала создается политика, а затем создается правило, определя которое определяет политику, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="afdff-244">You create the policy first, then you create the rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="afdff-245">Параметры политики и правила изменяются отдельно.</span><span class="sxs-lookup"><span data-stu-id="afdff-245">You modify the settings in the policy and the rule separately.</span></span>
- <span data-ttu-id="afdff-246">При удалении политики из PowerShell соответствующее правило также удаляется.</span><span class="sxs-lookup"><span data-stu-id="afdff-246">When you remove a policy from PowerShell, the corresponding rule is also removed.</span></span>
- <span data-ttu-id="afdff-247">При удалении правила из PowerShell соответствующая политика не удаляется.</span><span class="sxs-lookup"><span data-stu-id="afdff-247">When you remove a rule from PowerShell, the corresponding policy is not removed.</span></span> <span data-ttu-id="afdff-248">Соответствующую политику необходимо удалить вручную.</span><span class="sxs-lookup"><span data-stu-id="afdff-248">You need to remove the corresponding policy manually.</span></span>

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a><span data-ttu-id="afdff-249">Использование PowerShell для настройки сторонних фишинговых симуляций</span><span class="sxs-lookup"><span data-stu-id="afdff-249">Use PowerShell to configure third-party phishing simulations</span></span>

<span data-ttu-id="afdff-250">Настройка сторонних имитаций фишинга в продвинутой политике доставки в PowerShell — это двухшаговая процедура:</span><span class="sxs-lookup"><span data-stu-id="afdff-250">Configuring a third-party phishing simulation in the advanced delivery policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="afdff-251">Создайте политику переопределения имитации фишинга.</span><span class="sxs-lookup"><span data-stu-id="afdff-251">Create the phishing simulation override policy.</span></span>
2. <span data-ttu-id="afdff-252">Создайте правило переопределения фишинговых симуляций, которое указывает политику, к которую применяется правило.</span><span class="sxs-lookup"><span data-stu-id="afdff-252">Create the phishing simulation override rule that specifies the policy that the rule applies to.</span></span>

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a><span data-ttu-id="afdff-253">Шаг 1. Использование PowerShell для создания политики переопределения фишинговых симуляций</span><span class="sxs-lookup"><span data-stu-id="afdff-253">Step 1: Use PowerShell to create the phishing simulation override policy</span></span>

<span data-ttu-id="afdff-254">В этом примере создается политика переопределения фишинговых симуляций.</span><span class="sxs-lookup"><span data-stu-id="afdff-254">This example creates the phishing simulation override policy.</span></span>

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

<span data-ttu-id="afdff-255">**Примечание.** Независимо от значения Имя, которое вы указываете, имя политики будет PhishSimOverridePolicy, поэтому вы также можете использовать это значение.</span><span class="sxs-lookup"><span data-stu-id="afdff-255">**Note**: Regardless of the Name value you specify, the policy name will be PhishSimOverridePolicy, so you might as well use that value.</span></span>

<span data-ttu-id="afdff-256">Подробные сведения о синтаксисах и параметрах см. в [обзоре New-PhishSimOverridePolicy.](/powershell/module/exchange/new-phishsimoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="afdff-256">For detailed syntax and parameter information, see [New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a><span data-ttu-id="afdff-257">Шаг 2. Использование PowerShell для создания правила переопределения фишинговых симуляций</span><span class="sxs-lookup"><span data-stu-id="afdff-257">Step 2: Use PowerShell to create the phishing simulation override rule</span></span>

<span data-ttu-id="afdff-258">Используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="afdff-258">Use the following syntax:</span></span>

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs <Domain1>,<Domain2>,...<DomainN> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>
```

<span data-ttu-id="afdff-259">Независимо от значения Имя, которое вы указываете, имя правила будет PhishSimOverrideRule, где имеется уникальное значение \<GUID\> \<GUID\> GUID (например, a0eae53e-d755-4a42-9320-b9c6b55c5011).</span><span class="sxs-lookup"><span data-stu-id="afdff-259">Regardless of the Name value you specify, the rule name will be PhishSimOverrideRule\<GUID\> where \<GUID\> is a unique GUID value (for example, a0eae53e-d755-4a42-9320-b9c6b55c5011).</span></span>

<span data-ttu-id="afdff-260">Допустимая запись IP-адреса — это одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="afdff-260">A valid IP address entry is one of the following values:</span></span>

- <span data-ttu-id="afdff-261">Один IP. Например, 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="afdff-261">Single IP: For example, 192.168.1.1.</span></span>
- <span data-ttu-id="afdff-262">Диапазон IP: Например, 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="afdff-262">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
- <span data-ttu-id="afdff-263">IP CIDR. Например, 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="afdff-263">CIDR IP: For example, 192.168.0.1/25.</span></span>

<span data-ttu-id="afdff-264">В этом примере создается правило переопределения фишинговых симуляций с указанными настройками.</span><span class="sxs-lookup"><span data-stu-id="afdff-264">This example creates the phishing simulation override rule with the specified settings.</span></span>

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

<span data-ttu-id="afdff-265">Подробные сведения о синтаксисах и параметрах см. в [обзоре New-PhishSimOverrideRule.](/powershell/module/exchange/new-phishsimoverriderule)</span><span class="sxs-lookup"><span data-stu-id="afdff-265">For detailed syntax and parameter information, see [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a><span data-ttu-id="afdff-266">Использование PowerShell для просмотра политики переопределения фишинговых симуляций</span><span class="sxs-lookup"><span data-stu-id="afdff-266">Use PowerShell to view the phishing simulation override policy</span></span>

<span data-ttu-id="afdff-267">В этом примере возвращается подробная информация об одной и единственной политике переопределения имитации фишинга.</span><span class="sxs-lookup"><span data-stu-id="afdff-267">This example returns detailed information about the one and only phishing simulation override policy.</span></span>

```powershell
Get-PhishSimOverridePolicy
```

<span data-ttu-id="afdff-268">Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-PhishSimOverridePolicy.](/powershell/module/exchange/get-phishsimoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="afdff-268">For detailed syntax and parameter information, see [Get-PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a><span data-ttu-id="afdff-269">Использование PowerShell для просмотра правил переопределения имитации фишинга</span><span class="sxs-lookup"><span data-stu-id="afdff-269">Use PowerShell to view phishing simulation override rules</span></span>

<span data-ttu-id="afdff-270">В этом примере возвращаются подробные сведения о правилах переопределения имитации фишинга.</span><span class="sxs-lookup"><span data-stu-id="afdff-270">This example returns detailed information about phishing simulation override rules.</span></span>

```powershell
Get-PhishSimOverrideRule
```

<span data-ttu-id="afdff-271">Хотя предыдущая команда должна возвращать только одно правило, все правила, ожидающих удаления, также могут быть включены в результаты.</span><span class="sxs-lookup"><span data-stu-id="afdff-271">Although the previous command should return only one rule, any rules that are pending deletion might also be included in the results.</span></span>

<span data-ttu-id="afdff-272">В этом примере определяются допустимые правила (одно) и все недействительные правила.</span><span class="sxs-lookup"><span data-stu-id="afdff-272">This example identifies the valid rule (one) and any invalid rules.</span></span>

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

<span data-ttu-id="afdff-273">После определения недействительных правил их можно удалить с помощью **cmdlet Remove-PhisSimOverrideRule,** как описано ниже [в этой статье.](#use-powershell-to-remove-phishing-simulation-override-rules)</span><span class="sxs-lookup"><span data-stu-id="afdff-273">After you identify the invalid rules, you can remove them by using the **Remove-PhisSimOverrideRule** cmdlet as described [later in this article](#use-powershell-to-remove-phishing-simulation-override-rules).</span></span>

<span data-ttu-id="afdff-274">Подробные сведения о синтаксисах и параметрах см. в [ссылке Get-PhishSimOverrideRule.](/powershell/module/exchange/get-phishsimoverriderule)</span><span class="sxs-lookup"><span data-stu-id="afdff-274">For detailed syntax and parameter information, see [Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a><span data-ttu-id="afdff-275">Использование PowerShell для изменения политики переопределения фишинговых симуляций</span><span class="sxs-lookup"><span data-stu-id="afdff-275">Use PowerShell to modify the phishing simulation override policy</span></span>

<span data-ttu-id="afdff-276">Чтобы изменить политику переопределения имитации фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="afdff-276">To modify the phishing simulation override policy, use the following syntax:</span></span>

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="afdff-277">В этом примере отключает политику переопределения фишинговых симуляций.</span><span class="sxs-lookup"><span data-stu-id="afdff-277">This example disables the phishing simulation override policy.</span></span>

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

<span data-ttu-id="afdff-278">Подробные сведения о синтаксисах и параметрах см. в [обзоре Set-PhishSimOverridePolicy.](/powershell/module/exchange/set-phishsimoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="afdff-278">For detailed syntax and parameter information, see [Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-modify-a-phishing-simulation-override-rule"></a><span data-ttu-id="afdff-279">Использование PowerShell для изменения правила переопределения фишинговых симуляций</span><span class="sxs-lookup"><span data-stu-id="afdff-279">Use PowerShell to modify a phishing simulation override rule</span></span>

<span data-ttu-id="afdff-280">Чтобы изменить правило переопределения фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="afdff-280">To modify the phishing simulation override rule, use the following syntax:</span></span>

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

<span data-ttu-id="afdff-281">В этом примере изменяется указанное правило переопределения имитации фишинга со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="afdff-281">This example modifies the specified phishing simulation override rule with the following settings:</span></span>

- <span data-ttu-id="afdff-282">Добавьте запись домена blueyonderairlines.com.</span><span class="sxs-lookup"><span data-stu-id="afdff-282">Add the domain entry blueyonderairlines.com.</span></span>
- <span data-ttu-id="afdff-283">Удалите запись IP-адреса 192.168.1.55.</span><span class="sxs-lookup"><span data-stu-id="afdff-283">Remove the IP address entry 192.168.1.55.</span></span>

<span data-ttu-id="afdff-284">Обратите внимание, что эти изменения не влияют на существующие записи.</span><span class="sxs-lookup"><span data-stu-id="afdff-284">Note that these changes don't affect existing entries.</span></span>

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

<span data-ttu-id="afdff-285">Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-PhishSimOverrideRule.](/powershell/module/exchange/set-phishsimoverriderule)</span><span class="sxs-lookup"><span data-stu-id="afdff-285">For detailed syntax and parameter information, see [Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a><span data-ttu-id="afdff-286">Использование PowerShell для удаления политики переопределения фишинговых симуляций</span><span class="sxs-lookup"><span data-stu-id="afdff-286">Use PowerShell to remove a phishing simulation override policy</span></span>

<span data-ttu-id="afdff-287">В этом примере удаляется политика переопределения имитации фишинга и соответствующее правило.</span><span class="sxs-lookup"><span data-stu-id="afdff-287">This example removes the phishing simulation override policy and the corresponding rule.</span></span>

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

<span data-ttu-id="afdff-288">Подробные сведения о синтаксисах и параметрах см. в [ссылке Remove-PhishSimOverridePolicy.](/powershell/module/exchange/remove-phishsimoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="afdff-288">For detailed syntax and parameter information, see [Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a><span data-ttu-id="afdff-289">Использование PowerShell для удаления правил переопределения фишинговых симуляций</span><span class="sxs-lookup"><span data-stu-id="afdff-289">Use PowerShell to remove phishing simulation override rules</span></span>

<span data-ttu-id="afdff-290">Чтобы удалить правило переопределения имитации фишинга, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="afdff-290">To remove a phishing simulation override rule, use the following syntax:</span></span>

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

<span data-ttu-id="afdff-291">В этом примере удаляется указанное правило переопределения имитации фишинга.</span><span class="sxs-lookup"><span data-stu-id="afdff-291">This example removes the specified phishing simulation override rule.</span></span>

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

<span data-ttu-id="afdff-292">Подробные сведения о синтаксисах и параметрах см. в [ссылке Remove-PhishSimOverrideRule.](/powershell/module/exchange/remove-phishsimoverriderule)</span><span class="sxs-lookup"><span data-stu-id="afdff-292">For detailed syntax and parameter information, see [Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule).</span></span>
