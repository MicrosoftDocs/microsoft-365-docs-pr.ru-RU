---
title: Повышение защиты от Microsoft 365 бизнес премиум
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Настройка функций соответствия требованиям для предотвращения потери данных и обеспечения безопасности конфиденциальной информации ваших клиентов и ваших клиентов.
ms.openlocfilehash: 945f8a283b90b89da2fbe67a073e0807b80d198f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245091"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="ebbfa-103">Настройка функций обеспечения соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="ebbfa-103">Set up compliance features</span></span>

<span data-ttu-id="ebbfa-104">В Microsoft 365 бизнес премиум есть функции для защиты данных и устройств, а также для обеспечения безопасности конфиденциальной информации ваших клиентов и ваших клиентов.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-104">Your Microsoft 365 Business Premium comes with features to protect your data and devices, and help you keep your and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="ebbfa-105">Настройка функций DLP</span><span class="sxs-lookup"><span data-stu-id="ebbfa-105">Set up DLP features</span></span>

<span data-ttu-id="ebbfa-106">Пример [создания политики DLP см.](../compliance/create-a-dlp-policy-from-a-template.md) в примере создания политики защиты от потери персональных данных.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-106">See [Create a DLP policy from a template](../compliance/create-a-dlp-policy-from-a-template.md) for an example on how to set up a policy to protect against protect loss of personal data.</span></span> 
  
<span data-ttu-id="ebbfa-107">DLP поставляется с множеством готовых к использованию шаблонов политик для различных локализов.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="ebbfa-108">Например, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data и так далее.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, and so on.</span></span> <span data-ttu-id="ebbfa-109">Узнайте, [какие шаблоны политики DLP включают](../compliance/what-the-dlp-policy-templates-include.md) в полный список.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-109">See [What the DLP policy templates include](../compliance/what-the-dlp-policy-templates-include.md) for a full list.</span></span> <span data-ttu-id="ebbfa-110">Все эти шаблоны можно включить аналогично примеру шаблона PII.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-110">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="ebbfa-111">Настройка хранения электронной почты с помощью Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="ebbfa-111">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="ebbfa-112">**Exchange Online Archiving** функции лицензии помогают поддерживать соответствие требованиям и нормативные стандарты, сохраняя содержимое электронной почты для проверки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-112">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="ebbfa-113">Это также помогает снизить риск в случае судебного разбирательства и позволяет восстановить данные после нарушения безопасности или при необходимости восстановления удаленных элементов.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-113">It also helps reduce your risk if there is a lawsuit, and provides a way to recover data after a security breach or when you need to recover deleted items.</span></span> <span data-ttu-id="ebbfa-114">Вы можете использовать удержание для судебного разбирательства, чтобы сохранить все содержимое пользователя, или использовать политики хранения для настройки того, что необходимо сохранить.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-114">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="ebbfa-115">**Удержание судебного разбирательства:** Вы можете сохранить все содержимое почтовых ящиков, включая удаленные элементы, поставив весь почтовый ящик пользователя на удержание судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-115">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="ebbfa-116">Чтобы разместить почтовый ящик на удержание судебного разбирательства, в центре администрирования:</span><span class="sxs-lookup"><span data-stu-id="ebbfa-116">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="ebbfa-117">В левом nav перейдите к **Пользователям** \> **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-117">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="ebbfa-118">Выберите пользователя, почтовый ящик которого необходимо разместить на удержании судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-118">Select a user whose mailbox you want to place on litigation hold.</span></span> <span data-ttu-id="ebbfa-119">В области пользователя развявем параметры  **Почты,** а рядом с дополнительными **настройками** выберите изменить Exchange свойства .</span><span class="sxs-lookup"><span data-stu-id="ebbfa-119">In the user pane, expand **Mail settings**, and next to **More settings**, choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="ebbfa-120">На странице почтового ящика для пользователя выберите \*\* функции почтового ящика \*\* в левом nav, а затем выберите ссылку **Включить** в удержании **Litigation.**</span><span class="sxs-lookup"><span data-stu-id="ebbfa-120">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="ebbfa-121">В **диалоговом** окне удержания судебного разбирательства можно указать продолжительность хранения судебного разбирательства в поле **длительность хранения судебного** разбирательства.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-121">In the **litigation hold** dialog box, you can specify the litigation hold duration in the **Litigation hold duration** field.</span></span> <span data-ttu-id="ebbfa-122">Оставьте поле пустым, если вы хотите разместить бесконечное удержание.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-122">Leave the field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="ebbfa-123">Вы также можете добавить заметки и направить владельца почтовых ящиков на веб-сайт, который может потребовать дополнительных объяснений о проведении судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-123">You can also add notes and direct the mailbox owner to a website you might have to explain more about the litigation hold.</span></span> <span data-ttu-id="ebbfa-124">\>**Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-124">\> **Save**.</span></span>
    
<span data-ttu-id="ebbfa-125">**Хранение:** Можно включить настраиваемые политики хранения, например, для сохранения определенного количества времени или удаления контента навсегда по окончании периода хранения.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-125">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="ebbfa-126">Дополнительные сведения см. [в обзоре политик хранения.](../compliance/retention.md)</span><span class="sxs-lookup"><span data-stu-id="ebbfa-126">To learn more, see [Overview of retention policies](../compliance/retention.md).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="ebbfa-127">Настройка меток "Чувствительность"</span><span class="sxs-lookup"><span data-stu-id="ebbfa-127">Set up Sensitivity labels</span></span>

<span data-ttu-id="ebbfa-128">Метки конфиденциальности приходят с планом 1 Azure Information Protection (AIP) и помогают классифицировать и необязательно защищать документы и электронные почты, применяя метки.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-128">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify, and optionally protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="ebbfa-129">Метки могут применяться автоматически администраторами, которые определяют правила и условия вручную пользователями или с помощью комбинации, в которой пользователям даются рекомендации.</span><span class="sxs-lookup"><span data-stu-id="ebbfa-129">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="ebbfa-130">Чтобы настроить метки "Чувствительность", просматривайте видео создания и управления [метами конфиденциальности.](../business-video/create-sensitivity-labels.md)</span><span class="sxs-lookup"><span data-stu-id="ebbfa-130">To set up Sensitivity labels, view [create and manage sensitivity labels](../business-video/create-sensitivity-labels.md) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="ebbfa-131">Установка клиента Azure Information Protection вручную</span><span class="sxs-lookup"><span data-stu-id="ebbfa-131">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="ebbfa-132">Чтобы вручную установить клиент AIP:</span><span class="sxs-lookup"><span data-stu-id="ebbfa-132">To manually install the AIP client:</span></span>

1. <span data-ttu-id="ebbfa-133">Скачайте **AzinfoProtection_UL.exe** [из центра загрузки Майкрософт.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="ebbfa-133">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="ebbfa-134">Вы можете убедиться, что установка работала, просмотрев документ Word и убедившись, что параметр **Sensitivity** доступен на вкладке **Home.**</span><span class="sxs-lookup"><span data-stu-id="ebbfa-134">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="ebbfa-135">![Вкладка защита в документе Word.](../media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="ebbfa-135">![Protection tab drop-down in a Word document.](../media/word-sensitivity.png)</span></span>

<span data-ttu-id="ebbfa-136">Дополнительные сведения см. в [дополнительных сведениях Install the client.](/azure/information-protection/infoprotect-tutorial-step3)</span><span class="sxs-lookup"><span data-stu-id="ebbfa-136">For more information, see [Install the client](/azure/information-protection/infoprotect-tutorial-step3).</span></span>