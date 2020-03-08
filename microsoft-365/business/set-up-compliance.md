---
title: Повышение защиты от угроз для Microsoft 365 Business
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
search.appverid:
- BCS160
- MET150
description: Настройка функций соответствия требованиям для предотвращения потери данных и обеспечения безопасности конфиденциальной информации ваших клиентов.
ms.openlocfilehash: 6f4520b052c2e7acb8748d3c9d6e26777cb56d4b
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2020
ms.locfileid: "42561247"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="a74f0-103">Настройка функций обеспечения соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="a74f0-103">Set up compliance features</span></span>

<span data-ttu-id="a74f0-104">Microsoft 365 бизнес поставляется с функциями для защиты ваших данных и устройств, а также для обеспечения безопасности конфиденциальной информации клиентов.</span><span class="sxs-lookup"><span data-stu-id="a74f0-104">Your Microsoft 365 Business comes with features to protect your data and devices, and help you keep your and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="a74f0-105">Настройка функций DLP</span><span class="sxs-lookup"><span data-stu-id="a74f0-105">Set up DLP features</span></span>

<span data-ttu-id="a74f0-106">В разделе [Создание политики защиты от потери данных в шаблоне](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) приведен пример того, как настроить политику для защиты от персональных данных (PII).</span><span class="sxs-lookup"><span data-stu-id="a74f0-106">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="a74f0-107">DLP включает множество готовых шаблонов политик для множества разных языковых стандартов.</span><span class="sxs-lookup"><span data-stu-id="a74f0-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="a74f0-108">Например, финансовые данные для Австралии, персональные данные для Канады, финансовые данные США и т. д.</span><span class="sxs-lookup"><span data-stu-id="a74f0-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, and so on.</span></span> <span data-ttu-id="a74f0-109">Узнайте [, какие шаблоны политики защиты от потери данных входят в](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) полный список.</span><span class="sxs-lookup"><span data-stu-id="a74f0-109">See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="a74f0-110">Все эти шаблоны можно включить аналогично примеру шаблона PII.</span><span class="sxs-lookup"><span data-stu-id="a74f0-110">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="a74f0-111">Настройка хранения электронной почты с помощью архивации на базе Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a74f0-111">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="a74f0-112">Функции лицензии на **архивацию на базе Exchange Online** помогают поддерживать соответствие стандартам и нормативным требованиям, сохраняя содержимое электронной почты для обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="a74f0-112">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="a74f0-113">Это также способствует снижению риска при наличии судебного реагирования и способе восстановления данных после нарушения безопасности или при необходимости восстановления удаленных элементов.</span><span class="sxs-lookup"><span data-stu-id="a74f0-113">It also helps reduce your risk if there is a lawsuit, and provides a way to recover data after a security breach or when you need to recover deleted items.</span></span> <span data-ttu-id="a74f0-114">Вы можете использовать удержание для судебного разбирательства, чтобы сохранить все содержимое пользователя, или использовать политики хранения для настройки того, что нужно сохранить.</span><span class="sxs-lookup"><span data-stu-id="a74f0-114">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="a74f0-115">**Удержание для судебного разбирательства:** Вы можете сохранить все содержимое почтового ящика, включая удаленные элементы, поместив весь почтовый ящик пользователя на удержание для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="a74f0-115">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="a74f0-116">Чтобы поместить почтовый ящик на удержание для судебного разбирательства, в центре администрирования:</span><span class="sxs-lookup"><span data-stu-id="a74f0-116">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="a74f0-117">В левой панели навигации выберите **Пользователи** \> **Активные**пользователи.</span><span class="sxs-lookup"><span data-stu-id="a74f0-117">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="a74f0-118">Выберите пользователя, чей почтовый ящик вы хотите поместить на удержание для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="a74f0-118">Select a user whose mailbox you want to place on litigation hold.</span></span> <span data-ttu-id="a74f0-119">В области пользователя разверните узел **Параметры почты**и рядом с пунктом **Дополнительные параметры**выберите команду **изменить свойства Exchange**.</span><span class="sxs-lookup"><span data-stu-id="a74f0-119">In the user pane, expand **Mail settings**, and next to **More settings**, choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="a74f0-120">На странице почтовый ящик пользователя выберите \* \* функции почтовых ящиков \* \* в левой панели навигации, а затем щелкните ссылку **включить** в разделе **удержание для судебного разбирательства**.</span><span class="sxs-lookup"><span data-stu-id="a74f0-120">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="a74f0-121">В диалоговом окне " **удержание для судебного разбирательства** " можно указать продолжительность хранения для судебного разбирательства в поле **длительность удержания для судебного** разбирательства.</span><span class="sxs-lookup"><span data-stu-id="a74f0-121">In the **litigation hold** dialog box, you can specify the litigation hold duration in the **Litigation hold duration** field.</span></span> <span data-ttu-id="a74f0-122">Оставьте это поле пустым, если хотите разместить бесконечное удержание.</span><span class="sxs-lookup"><span data-stu-id="a74f0-122">Leave the field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="a74f0-123">Вы также можете добавить заметки и направить владельца почтового ящика на веб-сайт, который может пояснить дополнительные сведения о хранении для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="a74f0-123">You can also add notes and direct the mailbox owner to a website you might have to explain more about the litigation hold.</span></span> <span data-ttu-id="a74f0-124">\>**Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a74f0-124">\> **Save**.</span></span>
    
<span data-ttu-id="a74f0-125">**Хранение:** Можно включить специальные политики хранения, например, для сохранения в течение определенного периода времени или окончательного удаления контента в конце периода хранения.</span><span class="sxs-lookup"><span data-stu-id="a74f0-125">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="a74f0-126">Чтобы узнать больше, ознакомьтесь [со статьей Обзор политик хранения](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="a74f0-126">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="a74f0-127">Настройка меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="a74f0-127">Set up Sensitivity labels</span></span>

<span data-ttu-id="a74f0-128">Метки конфиденциальности поставляются с планом 1 Azure Information Protection (точка административной защиты) и помогают классифицировать и дополнительно защищать документы и электронные письма, применяя метки.</span><span class="sxs-lookup"><span data-stu-id="a74f0-128">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify, and optionally protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="a74f0-129">Метки можно автоматически применять администраторы, которые определяют правила и условия, вручную или с помощью комбинации, в которой пользователи получают рекомендации.</span><span class="sxs-lookup"><span data-stu-id="a74f0-129">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="a74f0-130">Чтобы настроить метки конфиденциальности, просмотрите видео [Создание меток о конфиденциальности и управление ими](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) .</span><span class="sxs-lookup"><span data-stu-id="a74f0-130">To set up Sensitivity labels, view [create and manage sensitivity labels](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="a74f0-131">Установка клиента Azure Information Protection вручную</span><span class="sxs-lookup"><span data-stu-id="a74f0-131">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="a74f0-132">Для установки клиента АДМИНИСТРАТИВной установки вручную выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a74f0-132">To manually install the AIP client:</span></span>

1. <span data-ttu-id="a74f0-133">Скачайте **AzinfoProtection_UL. exe** из [центра загрузки Майкрософт](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="a74f0-133">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="a74f0-134">Чтобы убедиться, что установка проработала, просмотрите документ Word и убедитесь, что параметр " **чувствительность** " доступен на вкладке " **Главная** ".</span><span class="sxs-lookup"><span data-stu-id="a74f0-134">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="a74f0-135">![Раскрывающийся список вкладок защита в документе Word.](../media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="a74f0-135">![Protection tab drop-down in a Word document.](../media/word-sensitivity.png)</span></span>

<span data-ttu-id="a74f0-136">Для получения дополнительных сведений обратитесь [к разделу Установка клиента](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="a74f0-136">For more information, see [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
