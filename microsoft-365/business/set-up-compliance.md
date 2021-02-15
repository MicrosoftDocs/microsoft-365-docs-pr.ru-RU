---
title: Повышение защиты от угроз для Microsoft 365 бизнес премиум
f1.keywords:
- NOCSH
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
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Настройка функций соответствия требованиям для предотвращения потери данных и обеспечения безопасности конфиденциальной информации ваших клиентов и ваших клиентов.
ms.openlocfilehash: 2c95ad3f36df28af2c68cd11192bcfe92dfe29e3
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841180"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="f8cad-103">Настройка функций обеспечения соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="f8cad-103">Set up compliance features</span></span>

<span data-ttu-id="f8cad-104">Microsoft 365 бизнес премиум включает функции для защиты данных и устройств, а также для защиты конфиденциальной информации ваших клиентов и ваших клиентов.</span><span class="sxs-lookup"><span data-stu-id="f8cad-104">Your Microsoft 365 Business Premium comes with features to protect your data and devices, and help you keep your and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="f8cad-105">Настройка функций DLP</span><span class="sxs-lookup"><span data-stu-id="f8cad-105">Set up DLP features</span></span>

<span data-ttu-id="f8cad-106">Пример [того,](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) как настроить политику защиты от потери персональных данных, см. в примере создания политики защиты от потери персональных данных.</span><span class="sxs-lookup"><span data-stu-id="f8cad-106">See [Create a DLP policy from a template](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) for an example on how to set up a policy to protect against protect loss of personal data.</span></span> 
  
<span data-ttu-id="f8cad-107">DLP поставляется с большим количеством готовых к использованию шаблонов политик для различных региональных es.</span><span class="sxs-lookup"><span data-stu-id="f8cad-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="f8cad-108">Например, "Финансовые данные Австралии", "Акт о персональных данных Для Канады", "Финансовые данные США" и так далее.</span><span class="sxs-lookup"><span data-stu-id="f8cad-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, and so on.</span></span> <span data-ttu-id="f8cad-109">Полный список см. в шаблонах политики [DLP.](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include)</span><span class="sxs-lookup"><span data-stu-id="f8cad-109">See [What the DLP policy templates include](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) for a full list.</span></span> <span data-ttu-id="f8cad-110">Все эти шаблоны можно включить аналогично примеру шаблона PII.</span><span class="sxs-lookup"><span data-stu-id="f8cad-110">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="f8cad-111">Настройка хранения электронной почты с помощью архивация на базе Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f8cad-111">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="f8cad-112">**архивация на базе Exchange Online** лицензии помогают поддерживать соответствие нормативным стандартам, сохраняя содержимое электронной почты для eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="f8cad-112">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="f8cad-113">Это также помогает снизить риск в случае судебных исков и предоставляет способ восстановления данных после нарушения безопасности или необходимости восстановления удаленных элементов.</span><span class="sxs-lookup"><span data-stu-id="f8cad-113">It also helps reduce your risk if there is a lawsuit, and provides a way to recover data after a security breach or when you need to recover deleted items.</span></span> <span data-ttu-id="f8cad-114">Можно использовать хранение для судебного разбирательства для сохранения всего содержимого пользователя или политики хранения для настройки того, что вы хотите сохранить.</span><span class="sxs-lookup"><span data-stu-id="f8cad-114">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="f8cad-115">**Судебное удержание:** Вы можете сохранить все содержимое почтового ящика, включая удаленные элементы, поключив весь почтовый ящик пользователя на судебное удержание.</span><span class="sxs-lookup"><span data-stu-id="f8cad-115">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="f8cad-116">Чтобы разместить почтовый ящик на удержании для судебного разбирательства, в Центре администрирования:</span><span class="sxs-lookup"><span data-stu-id="f8cad-116">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="f8cad-117">In the left nav, go to **Users** \> **Active users**.</span><span class="sxs-lookup"><span data-stu-id="f8cad-117">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="f8cad-118">Выберите пользователя, почтовый ящик которого необходимо разместить на удержании для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="f8cad-118">Select a user whose mailbox you want to place on litigation hold.</span></span> <span data-ttu-id="f8cad-119">В области пользователей разоберем параметры почты **и** рядом с параметрами "Больше" выберите "Изменить **свойства Exchange".**</span><span class="sxs-lookup"><span data-stu-id="f8cad-119">In the user pane, expand **Mail settings**, and next to **More settings**, choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="f8cad-120">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span><span class="sxs-lookup"><span data-stu-id="f8cad-120">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="f8cad-121">В **диалоговом окне** хранения для судебного разбирательства можно указать длительность хранения для судебного разбирательства в поле **"Длительность хранения для судебного** разбирательства".</span><span class="sxs-lookup"><span data-stu-id="f8cad-121">In the **litigation hold** dialog box, you can specify the litigation hold duration in the **Litigation hold duration** field.</span></span> <span data-ttu-id="f8cad-122">Оставьте поле пустым, если вы хотите разместить бесконечное удержание.</span><span class="sxs-lookup"><span data-stu-id="f8cad-122">Leave the field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="f8cad-123">Вы также можете добавлять заметки и направлять владельца почтового ящика на веб-сайт, на который может потребоваться объяснить больше о удержании для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="f8cad-123">You can also add notes and direct the mailbox owner to a website you might have to explain more about the litigation hold.</span></span> <span data-ttu-id="f8cad-124">\>**Сохраните**.</span><span class="sxs-lookup"><span data-stu-id="f8cad-124">\> **Save**.</span></span>
    
<span data-ttu-id="f8cad-125">**Хранение:** Можно включить настраиваемые политики хранения, например, для сохранения в течение определенного периода времени или окончательно удалить содержимое в конце периода хранения.</span><span class="sxs-lookup"><span data-stu-id="f8cad-125">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="f8cad-126">Дополнительные сведения [см. в обзоре политик хранения.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)</span><span class="sxs-lookup"><span data-stu-id="f8cad-126">To learn more, see [Overview of retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="f8cad-127">Настройка меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="f8cad-127">Set up Sensitivity labels</span></span>

<span data-ttu-id="f8cad-128">Метки конфиденциальности вместе с Azure Information Protection (AIP) (план 1) помогают классифицировать и при желании защищать документы и сообщения электронной почты, применяя метки.</span><span class="sxs-lookup"><span data-stu-id="f8cad-128">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify, and optionally protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="f8cad-129">Метки могут применяться автоматически администраторами, которые определяют правила и условия, вручную пользователями или с помощью сочетания, в котором пользователям даются рекомендации.</span><span class="sxs-lookup"><span data-stu-id="f8cad-129">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="f8cad-130">Чтобы настроить метки конфиденциальности, просматривайте видео о создании меток [конфиденциальности и управлении ими.](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)</span><span class="sxs-lookup"><span data-stu-id="f8cad-130">To set up Sensitivity labels, view [create and manage sensitivity labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="f8cad-131">Установка клиента Azure Information Protection вручную</span><span class="sxs-lookup"><span data-stu-id="f8cad-131">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="f8cad-132">Чтобы вручную установить клиент AIP:</span><span class="sxs-lookup"><span data-stu-id="f8cad-132">To manually install the AIP client:</span></span>

1. <span data-ttu-id="f8cad-133">Скачайте **AzinfoProtection_UL.exe** [из Центра загрузки Майкрософт.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="f8cad-133">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="f8cad-134">Чтобы убедиться, что установка сработала, просмотрев  документ Word и убедившись, что параметр "Конфиденциальность" доступен на вкладке **"Главная".**</span><span class="sxs-lookup"><span data-stu-id="f8cad-134">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="f8cad-135">![Вкладки "Защита" в документе Word.](../media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="f8cad-135">![Protection tab drop-down in a Word document.](../media/word-sensitivity.png)</span></span>

<span data-ttu-id="f8cad-136">Дополнительные сведения см. в [под вопросе "Установка клиента".](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)</span><span class="sxs-lookup"><span data-stu-id="f8cad-136">For more information, see [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
