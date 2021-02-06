---
title: Подключение домена к Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Узнайте, как проверить свой домен и создать записи DNS в Microsoft 365.
ms.custom:
- AdminSurgePortfolio
ms.openlocfilehash: c5c33af8a5635d1092aec2f1bffdfc942f2e4851
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126339"
---
# <a name="connect-your-domain-to-microsoft-365"></a><span data-ttu-id="dfefe-103">Подключение домена к Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dfefe-103">Connect your domain to Microsoft 365</span></span>

> [!NOTE]
> <span data-ttu-id="dfefe-104">Если вы не добавите домен, сотрудники вашей организации будут использовать домен onmicrosoft.com в своих адресах электронной почты до тех пор, пока вы не добавите домен.</span><span class="sxs-lookup"><span data-stu-id="dfefe-104">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="dfefe-105">Перед добавлением пользователей важно добавить свой домен, поэтому вам не нужно было настраивать их дважды.</span><span class="sxs-lookup"><span data-stu-id="dfefe-105">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="dfefe-106">Если вы не нашли то, что вы ищете, см. раздел [Вопросы и ответы по доменам](../setup/domains-faq.yml) ниже.</span><span class="sxs-lookup"><span data-stu-id="dfefe-106">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for below.</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="dfefe-107">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="dfefe-107">Add an MX record so email for your domain will come to Microsoft</span></span>

<span data-ttu-id="dfefe-108">Информация для записи MX будет выводится в мастере настройки домена центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="dfefe-108">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="dfefe-109">На веб-сайте своего поставщика услуг размещения добавьте новую MX-запись.</span><span class="sxs-lookup"><span data-stu-id="dfefe-109">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="dfefe-110">Убедитесь, что значения полей точно соответствуют указанным ниже.</span><span class="sxs-lookup"><span data-stu-id="dfefe-110">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="dfefe-111">Record Type (Тип записи): `MX`</span><span class="sxs-lookup"><span data-stu-id="dfefe-111">Record Type: `MX`</span></span>
- <span data-ttu-id="dfefe-112">Приоритет: установите максимальное доступное значение, обычно `0`.</span><span class="sxs-lookup"><span data-stu-id="dfefe-112">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="dfefe-113">Host Name (Имя узла): `@`</span><span class="sxs-lookup"><span data-stu-id="dfefe-113">Host Name: `@`</span></span>
- <span data-ttu-id="dfefe-114">Указывает на адрес: скопируйте значение из центра администрирования и вставьте его сюда.</span><span class="sxs-lookup"><span data-stu-id="dfefe-114">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="dfefe-115">TTL: `3600‎` (или значение вашего поставщика по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="dfefe-115">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="dfefe-116">Сохраните запись, а затем удалите все остальные записи MX.</span><span class="sxs-lookup"><span data-stu-id="dfefe-116">Save the record, and then remove any other MX records.</span></span>

## <a name="add-a-cname-record-to-connect-users-to-their-mailboxes"></a><span data-ttu-id="dfefe-117">Добавьте запись CNAME, чтобы подключить пользователей к их почтовым ящикам</span><span class="sxs-lookup"><span data-stu-id="dfefe-117">Add a CNAME record to connect users to their mailboxes</span></span>
<span data-ttu-id="dfefe-118">Информация для записей CNAME будет выводится в мастере настройки домена центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="dfefe-118">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="dfefe-119">На веб-сайте своего поставщика услуг размещения добавьте следующую запись CNAME.</span><span class="sxs-lookup"><span data-stu-id="dfefe-119">On your hosting provider's website, add the following CNAME record.</span></span> <span data-ttu-id="dfefe-120">Убедитесь, что значения полей точно соответствуют каждым из указанных ниже.</span><span class="sxs-lookup"><span data-stu-id="dfefe-120">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="dfefe-121">Record Type (Тип записи): `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="dfefe-121">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="dfefe-122">Host (Узел): вставьте значения, скопированные из центра администрирования, здесь.</span><span class="sxs-lookup"><span data-stu-id="dfefe-122">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="dfefe-123">Указывает на адрес: скопируйте значение из центра администрирования и вставьте его сюда.</span><span class="sxs-lookup"><span data-stu-id="dfefe-123">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="dfefe-124">TTL: `3600‎` (или значение вашего поставщика по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="dfefe-124">TTL: `3600‎` (or your provider default)</span></span>

## <a name="add-a-txt-record-to-help-prevent-spam"></a><span data-ttu-id="dfefe-125">Добавьте запись TXT, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="dfefe-125">Add a TXT record to help prevent spam</span></span>
<span data-ttu-id="dfefe-126">**Прежде чем начать:** если вы уже указали запись SPF для домена, не создавайте еще одну для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dfefe-126">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="dfefe-127">Вместо этого добавьте необходимые значения Microsoft 365 в текущую запись по веб-сайту вашего поставщика услуг размещения, таким образом, в *одной* записи SPF будут указаны оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="dfefe-127">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="dfefe-128">На веб-сайте вашего поставщика услуг размещения измените имеющуюся запись SPF или создайте новую запись SPF.</span><span class="sxs-lookup"><span data-stu-id="dfefe-128">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="dfefe-129">Убедитесь, что значения полей точно соответствуют указанным ниже.</span><span class="sxs-lookup"><span data-stu-id="dfefe-129">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="dfefe-130">Record Type (Тип записи): `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="dfefe-130">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="dfefe-131">Host (Узел): `@`</span><span class="sxs-lookup"><span data-stu-id="dfefe-131">Host: `@`</span></span>
- <span data-ttu-id="dfefe-132">TXT Value (Значение TXT): `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="dfefe-132">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="dfefe-133">TTL: `3600‎` (или значение вашего поставщика по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="dfefe-133">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="dfefe-134">Сохраните запись.</span><span class="sxs-lookup"><span data-stu-id="dfefe-134">Save the record.</span></span>

<span data-ttu-id="dfefe-135">Проверьте запись SPF, используя одно из этих [средств проверки SPF](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain).</span><span class="sxs-lookup"><span data-stu-id="dfefe-135">Validate your SPF record by using one of these [SPF validation tools](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="dfefe-136">Инфраструктура политики отправителей (SPF) призвана предотвратить спуфинг, но существуют некоторые методики, позволяющие обойти ее.</span><span class="sxs-lookup"><span data-stu-id="dfefe-136">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="dfefe-137">Чтобы защититься от таких атак, по завершении настройки SPF необходимо настроить DKIM и DMARC для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dfefe-137">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span>

<span data-ttu-id="dfefe-138">Чтобы начать, см. статьи [Проверка исходящей электронной почты, отправляемой со своего домена в Microsoft 365, с помощью DKIM](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) и [Использование DMARC для проверки электронной почты в Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="dfefe-138">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) and [Use DMARC to validate email in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="dfefe-139">Затем вернитесь в мастер настройки домена центра администрирования, чтобы завершить настройку.</span><span class="sxs-lookup"><span data-stu-id="dfefe-139">Finally, head back to the admin center domain setup wizard to complete your setup.</span></span>
