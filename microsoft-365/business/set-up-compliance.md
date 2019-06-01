---
title: Повышение защиты от угроз для Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Настройка расширенной защиты от угроз для Office 365 и защита конфиденциальных данных.
ms.openlocfilehash: 53741a7726222bb32329a401953be72257df95cc
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668403"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="724b4-103">Настройка функций обеспечения соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="724b4-103">Set up compliance features</span></span>

<span data-ttu-id="724b4-104">Microsoft 365 бизнес поставляется с функциями для защиты ваших данных и устройств, а также для защиты конфиденциальной информации клиентов и ваших клиентов.</span><span class="sxs-lookup"><span data-stu-id="724b4-104">Your Microsoft 365 Business comes with features to protect your data and devices, and help you keep yours and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="724b4-105">Настройка функций DLP</span><span class="sxs-lookup"><span data-stu-id="724b4-105">Set up DLP features</span></span>

<span data-ttu-id="724b4-106">В разделе [Создание политики защиты от потери данных в шаблоне](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) приведен пример того, как настроить политику для защиты от персональных данных (PII).</span><span class="sxs-lookup"><span data-stu-id="724b4-106">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="724b4-107">DLP включает множество готовых шаблонов политик для множества разных языковых стандартов.</span><span class="sxs-lookup"><span data-stu-id="724b4-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="724b4-108">Например, финансовые данные Австралии, ACT персональной информации, финансовых данных США и т. д. Узнайте [, какие шаблоны политики защиты от потери данных входят в](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) полный список.</span><span class="sxs-lookup"><span data-stu-id="724b4-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="724b4-109">Все эти шаблоны можно включить аналогично примеру шаблона PII.</span><span class="sxs-lookup"><span data-stu-id="724b4-109">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="724b4-110">Настройка хранения электронной почты с помощью архивации на базе Exchange Online</span><span class="sxs-lookup"><span data-stu-id="724b4-110">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="724b4-111">Функции лицензии на архивацию на базе **Exchange Online** помогают поддерживать соответствие стандартам и нормативным требованиям, сохраняя содержимое электронной почты для обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="724b4-111">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="724b4-112">Кроме того, это помогает снизить риск возникновения судебного реагирования и предоставляет способ восстановления данных после нарушения безопасности или при необходимости восстановления удаленных элементов.</span><span class="sxs-lookup"><span data-stu-id="724b4-112">It also helps reduce your risk in the event of a lawsuit and provides a way to recover data after a security breach, or when you need to recover deleted items.</span></span> <span data-ttu-id="724b4-113">Вы можете использовать удержание для судебного разбирательства, чтобы сохранить все содержимое пользователя, или использовать политики хранения для настройки того, что нужно сохранить.</span><span class="sxs-lookup"><span data-stu-id="724b4-113">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="724b4-114">**Удержание для судебного разбирательства:** Вы можете сохранить все содержимое почтового ящика, включая удаленные элементы, поместив весь почтовый ящик пользователя на удержание для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="724b4-114">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="724b4-115">Чтобы поместить почтовый ящик на удержание для судебного разбирательства, в центре администрирования:</span><span class="sxs-lookup"><span data-stu-id="724b4-115">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="724b4-116">В левой панели навигации выберите **Пользователи** \> **Активные**пользователи.</span><span class="sxs-lookup"><span data-stu-id="724b4-116">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="724b4-117">Выберите пользователя, чей почтовый ящик вы хотите поместить на удержание для судебного разбирательства, а затем в области пользователя разверните **Параметры почты** и рядом с пунктом **Дополнительные параметры** выберите **изменить свойства Exchange**.</span><span class="sxs-lookup"><span data-stu-id="724b4-117">Select a user whose mailbox you want to place on litigation hold and in the user pane expand **Mail settings** and next to **More settings** choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="724b4-118">На странице почтовый ящик пользователя выберите \* \* функции почтовых ящиков \* \* в левой панели навигации, а затем щелкните ссылку **включить** в разделе **удержание для судебного разбирательства**.</span><span class="sxs-lookup"><span data-stu-id="724b4-118">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="724b4-119">В диалоговом окне **удержание** для судебного разбирательства вы можете указать срок хранения для судебного разбирательства в поле **Длительность хранения** для судебного разбирательства, оставьте поле пустым, если нужно помещать бесконечное удержание.</span><span class="sxs-lookup"><span data-stu-id="724b4-119">In the **litigation hold** dialog box you can specify the litigation hold duration in the **Litigation hold duration** field, leave field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="724b4-120">Вы также можете добавить заметки и направить владельца почтового ящика на веб-сайт, чтобы больше узнать больше о \> **сохранении**для хранения для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="724b4-120">You can also add notes and direct the mail box owner to a website you might have to explain more about the litigation hold \> **Save**.</span></span>
    
<span data-ttu-id="724b4-121">**Хранение:** Можно включить специальные политики хранения, например, для сохранения в течение определенного периода времени или окончательного удаления контента в конце периода хранения.</span><span class="sxs-lookup"><span data-stu-id="724b4-121">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="724b4-122">Чтобы узнать больше, ознакомьтесь [со статьей Обзор политик хранения](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="724b4-122">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="set-up-azure-information-protection-features"></a><span data-ttu-id="724b4-123">Настройка функций Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="724b4-123">Set up Azure Information Protection features</span></span>

<span data-ttu-id="724b4-124">Azure Information Protection (точка административной защиты) помогает классифицировать и дополнительно защищать документы и электронные письма, применяя метки.</span><span class="sxs-lookup"><span data-stu-id="724b4-124">Azure Information Protection (AIP) helps you classify and optionally, protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="724b4-125">Метки можно автоматически применять администраторы, которые определяют правила и условия, вручную или с помощью комбинации, в которой пользователи получают рекомендации.</span><span class="sxs-lookup"><span data-stu-id="724b4-125">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="724b4-126">В Outlook в Интернете можно применять следующие встроенные метки и ограничения к сообщениям электронной почты:</span><span class="sxs-lookup"><span data-stu-id="724b4-126">In Outlook on the web you can apply the following built-in labels and restrictions to your emails:</span></span>
  
- <span data-ttu-id="724b4-127">\*\*\*\* Не пересылать: получатели могут читать сообщение, но не могут пересылать, печатать или копировать содержимое.</span><span class="sxs-lookup"><span data-stu-id="724b4-127">**Do Not Forward**: Recipients can read the message, but they can't forward, print, or copy content</span></span>
    
- <span data-ttu-id="724b4-128">**Encrypt**: все сообщение зашифровано.</span><span class="sxs-lookup"><span data-stu-id="724b4-128">**Encrypt**: The entire message is encrypted.</span></span> <span data-ttu-id="724b4-129">Получатели должны подтвердить свою личность, прежде чем получать доступ к зашифрованному содержимому и не удается удалить шифрование.</span><span class="sxs-lookup"><span data-stu-id="724b4-129">Recipients must confirm their identity before accessing encrypted content and can't remove encryption.</span></span>
    
- <span data-ttu-id="724b4-130">**Конфиденциально**: предоставление сотрудникам Организации полных разрешений на контент и вложения электронной почты, но не на пользователей, не входящих в вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="724b4-130">**Confidential**: Gives the employees in your organization full permissions to the email content and attachments, but not to people outside your organization.</span></span> <span data-ttu-id="724b4-131">Владельцы данных могут отслеживать и отзывать контент в любой момент.</span><span class="sxs-lookup"><span data-stu-id="724b4-131">Data owners can track and revoke content at any point.</span></span>
    
- <span data-ttu-id="724b4-132">**Строго конфиденциально**: это ограничение можно применять к конфиденциальным данным, позволяя сотрудникам просматривать, редактировать и отвечать, но не пересылать, печатать или копировать данные.</span><span class="sxs-lookup"><span data-stu-id="724b4-132">**Highly Confidential**: This restriction can be applied to highly confidential data, allowing employees to view, edit, and reply, but not forward, print, or copy the data.</span></span> <span data-ttu-id="724b4-133">Владельцы данных могут отслеживать и отзывать контент в любой момент.</span><span class="sxs-lookup"><span data-stu-id="724b4-133">Data owners can track and revoke content at any point.</span></span>

### <a name="make-sure-azure-information-protection-is-activated"></a><span data-ttu-id="724b4-134">Убедитесь, что активна служба Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="724b4-134">Make sure Azure Information Protection is activated</span></span>

<span data-ttu-id="724b4-135">Чтобы убедиться, что точка административной установки активна:</span><span class="sxs-lookup"><span data-stu-id="724b4-135">To verify that AIP is activated :</span></span>

1. <span data-ttu-id="724b4-136">Войдите на [портал Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="724b4-136">Sign into [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="724b4-137">Выберите **все службы** и введите в **поле поиска** *Azure Information Protection* .</span><span class="sxs-lookup"><span data-stu-id="724b4-137">Select **All services** and type in *Azure Information Protection* in the **Search Box**.</span></span>

3. <span data-ttu-id="724b4-138">После отображения результатов нажмите кнопку начать рядом с элементом **Azure Information Protection** , чтобы сделать ее более удобной и удобной для дальнейшего поиска.</span><span class="sxs-lookup"><span data-stu-id="724b4-138">Once the results display, click the start next to **Azure Information Protection** to make it a favorite and easy to find later.</span></span>

4. <span data-ttu-id="724b4-139">Выберите **Активация** **Azure Information** \> Protection и убедитесь, что для параметра состояние установлено значение активировано.</span><span class="sxs-lookup"><span data-stu-id="724b4-139">Select **Azure Information Protection** \> **Protection activation** and make sure the status is set to activated.</span></span> 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a><span data-ttu-id="724b4-140">Просмотр политики Azure Information Protection и подписей по умолчанию</span><span class="sxs-lookup"><span data-stu-id="724b4-140">View the Azure Information Protection policy and default labels</span></span> 

<span data-ttu-id="724b4-141">Чтобы просмотреть и изменить существующие метки, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="724b4-141">To view, and modify, the existing labels:</span></span>

1. <span data-ttu-id="724b4-142">На панели мониторинга Azure Information Protection выберите метки **классификации** \> \*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="724b4-142">On the Azure Information Protection dashboard, select **Classifications** \> **Labels**.</span></span> <br/><span data-ttu-id="724b4-143">![Стандартные метки для Azure Information Protection.](media/AIPLabels.png)</span><span class="sxs-lookup"><span data-stu-id="724b4-143">![Standard labels for Azure Information Protection.](media/AIPLabels.png)</span></span>

2. <span data-ttu-id="724b4-144">Вы можете выбрать любую метку для просмотра параметров, вы можете изменить отображаемое имя, цвета и т. д.</span><span class="sxs-lookup"><span data-stu-id="724b4-144">You can choose any label to view options, you can change the display name, colors, etc.</span></span>
 
3. <span data-ttu-id="724b4-145">Если вы хотите создать собственные метки, ознакомьтесь с разметкой [изменение и создание новых меток](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) .</span><span class="sxs-lookup"><span data-stu-id="724b4-145">See  [Modify and create new labels](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) if you want to create your own.</span></span> 

### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="724b4-146">Установка клиента Azure Information Protection вручную</span><span class="sxs-lookup"><span data-stu-id="724b4-146">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="724b4-147">Для установки клиента АДМИНИСТРАТИВной установки вручную выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="724b4-147">To manually install the AIP client:</span></span>

1. <span data-ttu-id="724b4-148">Скачайте **азинфопротектион. exe** из [центра загрузки Майкрософт](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="724b4-148">Download **AzInfoProtection.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="724b4-149">Убедиться, что установка работала, можно, просмотрев документ Word и убедившись, что параметр **Защита** доступен на вкладке **Главная** .</span><span class="sxs-lookup"><span data-stu-id="724b4-149">You can verify that the installation worked by viewing a Word document and making sure that the **Protect** option is available on the **Home** tab.</span></span> <br/><span data-ttu-id="724b4-150">![Раскрывающийся список вкладок защита в документе Word.](media/Word_Protect.png)</span><span class="sxs-lookup"><span data-stu-id="724b4-150">![Protection tab drop-down in a Word document.](media/Word_Protect.png)</span></span>

<span data-ttu-id="724b4-151">Дополнительные сведения см. [в разделе Установка клиента](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="724b4-151">For more information see, [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
