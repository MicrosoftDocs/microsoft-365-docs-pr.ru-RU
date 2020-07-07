---
title: Добавление записей DNS для подключения своего домена
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
description: Узнайте, как проверить свой домен и создать записи DNS для Microsoft 365 у любого поставщика услуг размещения DNS.
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: d3a9e3787afc30b33122edf91c1cf9e3dd84b847
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049670"
---
# <a name="add-dns-records-to-connect-your-domain"></a><span data-ttu-id="b8408-103">Добавление записей DNS для подключения своего домена</span><span class="sxs-lookup"><span data-stu-id="b8408-103">Add DNS records to connect your domain</span></span>

<span data-ttu-id="b8408-104">Если вы приобрели домен у стороннего поставщика услуг размещения, вы можете подключить его к Microsoft 365, обновив записи DNS учетной записи регистратора.</span><span class="sxs-lookup"><span data-stu-id="b8408-104">If you purchased a domain from a third-party hosting provider, you can connect it to Microsoft 365 by updating the DNS records in your registrar’s account.</span></span>

<span data-ttu-id="b8408-105">После выполнения этих действий ваш домен останется зарегистрированным на узле, через который вы приобрели домен, но Microsoft 365 сможет использовать его для ваших адресов электронной почты (например, user@yourdomain.com) и других служб.</span><span class="sxs-lookup"><span data-stu-id="b8408-105">At the end of these steps, your domain will stay registered with the host that you purchased the domain from, but Microsoft 365 can use it for you email addresses (like user@yourdomain.com) and other services.</span></span>

<span data-ttu-id="b8408-106">Если вы не добавите домен, сотрудники вашей организации будут использовать домен onmicrosoft.com в своих адресах электронной почты до тех пор, пока вы не добавите домен.</span><span class="sxs-lookup"><span data-stu-id="b8408-106">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="b8408-107">Перед добавлением пользователей важно добавить свой домен, поэтому вам не нужно было настраивать их дважды.</span><span class="sxs-lookup"><span data-stu-id="b8408-107">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="b8408-108">Если вы не нашли то, что вы ищете, см. раздел [Вопросы и ответы по доменам](../setup/domains-faq.md) ниже.</span><span class="sxs-lookup"><span data-stu-id="b8408-108">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for below.</span></span>

## <a name="step-1-add-a-txt-record-to-verify-you-own-the-domain"></a><span data-ttu-id="b8408-109">Этап 1. Добавление записи TXT для подтверждения права собственности на домен</span><span class="sxs-lookup"><span data-stu-id="b8408-109">Step 1: Add a TXT record to verify you own the domain</span></span>

<span data-ttu-id="b8408-110">Сначала необходимо подтвердить, что вы владеете доменом, который вы хотите добавить в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b8408-110">First, you need to prove you own the domain you want to add to Microsoft 365.</span></span>

1. <span data-ttu-id="b8408-111">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com/), а затем выберите **Показать все** > **Настройки** > **Домены**.</span><span class="sxs-lookup"><span data-stu-id="b8408-111">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="b8408-112">В новой вкладке или окне браузера, войдите в свой поставщик услуг размещения DNS и найдите место, в котором вы управляете параметрами DNS (например, параметры файла зоны, управление доменами, диспетчер доменов, диспетчер DNS).</span><span class="sxs-lookup"><span data-stu-id="b8408-112">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="b8408-113">Перейдите на страницу диспетчера DNS поставщика, добавьте запись TXT, указанную в центре администрирования, в ваш домен.</span><span class="sxs-lookup"><span data-stu-id="b8408-113">Go to your provider's DNS Manager page, and add the TXT record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="b8408-114">Добавление этой записи не повлияет на ваши существующие сообщения электронной почты и другие службы, и вы можете безопасно удалить ее после подключения домена к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b8408-114">Adding this record won't affect your existing email or other services and you can safely remove it once your domain is connected to Microsoft 365.</span></span>

<span data-ttu-id="b8408-115">Пример.</span><span class="sxs-lookup"><span data-stu-id="b8408-115">Example:</span></span>
- <span data-ttu-id="b8408-116">Имя TXT: `@`</span><span class="sxs-lookup"><span data-stu-id="b8408-116">TXT Name: `@`</span></span>
- <span data-ttu-id="b8408-117">Значение TXT: MS=ms######## (уникальный идентификатор из центра администрирования);</span><span class="sxs-lookup"><span data-stu-id="b8408-117">TXT Value: MS=ms######## (unique ID from the admin center)</span></span>
- <span data-ttu-id="b8408-118">TTL: `3600‎` (или значение вашего поставщика по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b8408-118">TTL: `3600‎` (or your provider default)</span></span>

4. <span data-ttu-id="b8408-119">Сохраните запись, вернитесь в центр администрирования и выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="b8408-119">Save the record, go back to the admin center, and then select **Verify**.</span></span> <span data-ttu-id="b8408-120">Как правило, регистрация изменений занимает около 15 минут, но иногда это может занять больше времени.</span><span class="sxs-lookup"><span data-stu-id="b8408-120">It typically takes around 15 minutes for record changes to register, but sometimes it can take longer.</span></span> <span data-ttu-id="b8408-121">Предоставьте процессу некоторое время и выполните несколько попыток, чтобы изменение вступило в силу.</span><span class="sxs-lookup"><span data-stu-id="b8408-121">Give it some time and a few tries to pick up the change.</span></span>

<span data-ttu-id="b8408-122">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="b8408-122">When Microsoft finds the correct TXT record, your domain is verified.</span></span>


## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a><span data-ttu-id="b8408-123">Шаг 2. Добавление записей DNS для подключения служб Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b8408-123">Step 2: Add DNS records to connect Microsoft services</span></span>

<span data-ttu-id="b8408-124">В новой вкладке или окне браузера, войдите в свой поставщик услуг размещения DNS, а затем найдите место, в котором вы управляете параметрами DNS (например, параметры файла зоны, управление доменами, диспетчер доменов, диспетчер DNS).</span><span class="sxs-lookup"><span data-stu-id="b8408-124">In a new browser tab or window, sign in to your DNS hosting provider, and find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>

<span data-ttu-id="b8408-125">В зависимости от служб, которые вы хотите включить, потребуется добавить несколько записей DNS различных типов.</span><span class="sxs-lookup"><span data-stu-id="b8408-125">You'll be adding several different types of DNS records depending on the services you want to enable.</span></span> 

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a><span data-ttu-id="b8408-126">Добавление записи MX для электронной почты (Outlook, Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="b8408-126">Add an MX record for email (Outlook, Exchange Online)</span></span>
<span data-ttu-id="b8408-127">**Прежде чем начать, выполните указанные ниже действия**. Если у пользователей уже есть электронная почта в вашем домене (например, user@yourdomain.com), перед настройкой записей MX создайте их учетные записи в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="b8408-127">**Before you begin:** If users already have email with your domain (such as user@yourdomain.com), create their accounts in the admin center before you set up your MX records.</span></span> <span data-ttu-id="b8408-128">Таким образом, они будут продолжать получать электронную почту.</span><span class="sxs-lookup"><span data-stu-id="b8408-128">That way, they’ll continue to receive email.</span></span> <span data-ttu-id="b8408-129">После обновления записи MX вашего домена все новые сообщения, адресованные его пользователям, будут поступать в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b8408-129">When you update your domain's MX record, all new email for anyone who uses your domain will now come to Microsoft 365.</span></span> <span data-ttu-id="b8408-130">Ранее полученные сообщения останутся на текущем узле электронной почты, если вы не решите [перенести сообщения и контакты в Microsoft 365](../setup/migrate-email-and-contacts-admin.md).</span><span class="sxs-lookup"><span data-stu-id="b8408-130">Any email you already have will stay at your current email host, unless you decide to [migrate email and contacts to Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)</span></span>

<span data-ttu-id="b8408-131">Информация для записи MX будет выводится в мастере настройки домена центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="b8408-131">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="b8408-132">На веб-сайте своего поставщика услуг размещения добавьте новую MX-запись.</span><span class="sxs-lookup"><span data-stu-id="b8408-132">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="b8408-133">Убедитесь, что значения полей точно соответствуют указанным ниже.</span><span class="sxs-lookup"><span data-stu-id="b8408-133">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="b8408-134">Record Type (Тип записи): `MX`</span><span class="sxs-lookup"><span data-stu-id="b8408-134">Record Type: `MX`</span></span>
- <span data-ttu-id="b8408-135">Приоритет: установите максимальное доступное значение, обычно `0`.</span><span class="sxs-lookup"><span data-stu-id="b8408-135">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="b8408-136">Host Name (Имя узла): `@`</span><span class="sxs-lookup"><span data-stu-id="b8408-136">Host Name: `@`</span></span>
- <span data-ttu-id="b8408-137">Указывает на адрес: скопируйте значение из центра администрирования и вставьте его сюда.</span><span class="sxs-lookup"><span data-stu-id="b8408-137">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="b8408-138">TTL: `3600‎` (или значение вашего поставщика по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b8408-138">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="b8408-139">Сохраните запись, а затем удалите все остальные записи MX.</span><span class="sxs-lookup"><span data-stu-id="b8408-139">Save the record, and then remove any other MX records.</span></span>

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a><span data-ttu-id="b8408-140">Добавление записей CNAME для подключения к другим службам (Teams, Exchange Online, AAD, MDM)</span><span class="sxs-lookup"><span data-stu-id="b8408-140">Add CNAME records to connect other services (Teams, Exchange Online, AAD, MDM)</span></span>
<span data-ttu-id="b8408-141">Информация для записей CNAME будет выводится в мастере настройки домена центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="b8408-141">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="b8408-142">На веб-сайте поставщика услуг размещения добавьте записи CNAME для каждой службы, которую вы хотите подключить.</span><span class="sxs-lookup"><span data-stu-id="b8408-142">On your hosting provider's website, add CNAME records for each service that you want to connect.</span></span>
<span data-ttu-id="b8408-143">Убедитесь, что значения полей точно соответствуют каждым из указанных ниже.</span><span class="sxs-lookup"><span data-stu-id="b8408-143">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="b8408-144">Record Type (Тип записи): `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="b8408-144">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="b8408-145">Host (Узел): вставьте значения, скопированные из центра администрирования, здесь.</span><span class="sxs-lookup"><span data-stu-id="b8408-145">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="b8408-146">Указывает на адрес: скопируйте значение из центра администрирования и вставьте его сюда.</span><span class="sxs-lookup"><span data-stu-id="b8408-146">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="b8408-147">TTL: `3600‎` (или значение вашего поставщика по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b8408-147">TTL: `3600‎` (or your provider default)</span></span>


### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a><span data-ttu-id="b8408-148">Добавление или изменение записи SPF, которая помогает предотвратить нежелательную почту (Outlook, Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="b8408-148">Add or edit an SPF TXT record to help prevent email spam (Outlook, Exchange Online)</span></span>
<span data-ttu-id="b8408-149">**Прежде чем начать:** если вы уже указали запись SPF для домена, не создавайте еще одну для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b8408-149">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="b8408-150">Вместо этого добавьте необходимые значения Microsoft 365 в текущую запись по веб-сайту вашего поставщика услуг размещения, таким образом, в *одной* записи SPF будут указаны оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="b8408-150">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="b8408-151">На веб-сайте вашего поставщика услуг размещения измените имеющуюся запись SPF или создайте новую запись SPF.</span><span class="sxs-lookup"><span data-stu-id="b8408-151">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="b8408-152">Убедитесь, что значения полей точно соответствуют указанным ниже.</span><span class="sxs-lookup"><span data-stu-id="b8408-152">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="b8408-153">Record Type (Тип записи): `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="b8408-153">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="b8408-154">Host (Узел): `@`</span><span class="sxs-lookup"><span data-stu-id="b8408-154">Host: `@`</span></span>
- <span data-ttu-id="b8408-155">TXT Value (Значение TXT): `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="b8408-155">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="b8408-156">TTL: `3600‎` (или значение вашего поставщика по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b8408-156">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="b8408-157">Сохраните запись.</span><span class="sxs-lookup"><span data-stu-id="b8408-157">Save the record.</span></span>

<span data-ttu-id="b8408-158">Проверьте запись SPF, используя одно из этих [средств проверки SPF](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain).</span><span class="sxs-lookup"><span data-stu-id="b8408-158">Validate your SPF record by using one of these [SPF validation tools](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="b8408-159">Инфраструктура политики отправителей (SPF) призвана предотвратить спуфинг, но существуют некоторые методики, позволяющие обойти ее.</span><span class="sxs-lookup"><span data-stu-id="b8408-159">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="b8408-160">Чтобы защититься от таких атак, по завершении настройки SPF необходимо настроить DKIM и DMARC для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b8408-160">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span> 

<span data-ttu-id="b8408-161">Чтобы начать, см. статьи [Проверка исходящей электронной почты, отправляемой со своего домена в Microsoft 365, с помощью DKIM](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) и [Использование DMARC для проверки электронной почты в Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="b8408-161">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) and [Use DMARC to validate email in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a><span data-ttu-id="b8408-162">Добавление записей SRV для служб связи (Teams, Skype для бизнеса)</span><span class="sxs-lookup"><span data-stu-id="b8408-162">Add SRV records for communications services (Teams, Skype for Business)</span></span>

<span data-ttu-id="b8408-163">На веб-сайте поставщика услуг размещения добавьте записи SRV для каждой службы, которую вы хотите подключить.</span><span class="sxs-lookup"><span data-stu-id="b8408-163">On your hosting provider's website, add SRV records for each service you want to connect.</span></span>
<span data-ttu-id="b8408-164">Убедитесь, что значения полей точно соответствуют каждым из указанных ниже.</span><span class="sxs-lookup"><span data-stu-id="b8408-164">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="b8408-165">Record Type (Тип записи): `SRV (Service)`</span><span class="sxs-lookup"><span data-stu-id="b8408-165">Record Type: `SRV (Service)`</span></span>
- <span data-ttu-id="b8408-166">Имя: `@`</span><span class="sxs-lookup"><span data-stu-id="b8408-166">Name: `@`</span></span>
- <span data-ttu-id="b8408-167">Цель: скопируйте значение из центра администрирования и вставьте его сюда.</span><span class="sxs-lookup"><span data-stu-id="b8408-167">Target: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="b8408-168">Протокол: скопируйте значение из центра администрирования и вставьте его сюда.</span><span class="sxs-lookup"><span data-stu-id="b8408-168">Protocol: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="b8408-169">Служба: скопируйте значение из центра администрирования и вставьте его сюда.</span><span class="sxs-lookup"><span data-stu-id="b8408-169">Service: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="b8408-170">Приоритет: `100`</span><span class="sxs-lookup"><span data-stu-id="b8408-170">Priority: `100`</span></span>
- <span data-ttu-id="b8408-171">Weight (Вес):`1`</span><span class="sxs-lookup"><span data-stu-id="b8408-171">Weight: `1`</span></span>
- <span data-ttu-id="b8408-172">Порт: скопируйте значение из центра администрирования и вставьте его сюда.</span><span class="sxs-lookup"><span data-stu-id="b8408-172">Port: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="b8408-173">TTL: `3600‎` (или значение вашего поставщика по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b8408-173">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="b8408-174">Сохраните запись.</span><span class="sxs-lookup"><span data-stu-id="b8408-174">Save the record.</span></span>

#### <a name="srv-record-field-restrictions-and-workarounds"></a><span data-ttu-id="b8408-175">Ограничения и обходные пути для полей записи SRV</span><span class="sxs-lookup"><span data-stu-id="b8408-175">SRV record field restrictions and workarounds</span></span>
<span data-ttu-id="b8408-176">Некоторые поставщики услуг размещения накладывают ограничения на значения полей в записях SRV.</span><span class="sxs-lookup"><span data-stu-id="b8408-176">Some hosting providers impose restrictions on field values within SRV records.</span></span> <span data-ttu-id="b8408-177">Ниже приведены некоторые распространенные временные решения для этих ограничений.</span><span class="sxs-lookup"><span data-stu-id="b8408-177">Here are some common workarounds for these restrictions.</span></span>

##### <a name="name"></a><span data-ttu-id="b8408-178">Имя</span><span class="sxs-lookup"><span data-stu-id="b8408-178">Name</span></span>
<span data-ttu-id="b8408-179">Если ваш поставщик услуг размещения не позволяет задать для этого поля **@**, оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="b8408-179">If your hosting provider doesn't allow setting this field to **@**, leave it blank.</span></span> <span data-ttu-id="b8408-180">Следуйте этим инструкциям *только* в том случае, если вашим поставщиком услуг размещения предусмотрены отдельные поля для значений "Service" (Служба) и "Protocol" (Протокол).</span><span class="sxs-lookup"><span data-stu-id="b8408-180">Use this approach *only* when your hosting provider has separate fields for the Service and Protocol values.</span></span> <span data-ttu-id="b8408-181">В противном случае см. примечания о соответствующих параметрах ниже.</span><span class="sxs-lookup"><span data-stu-id="b8408-181">Otherwise, see the Service and Protocol notes below.</span></span>

##### <a name="service-and-protocol"></a><span data-ttu-id="b8408-182">Поля Service (Служба) и Protocol (Протокол)</span><span class="sxs-lookup"><span data-stu-id="b8408-182">Service and Protocol</span></span>
<span data-ttu-id="b8408-183">Если у вашего поставщика услуг размещения нет соответствующих полей для записей SRV, параметры **Service (Служба)** и **Protocol (Протокол)** задаются в поле **Name (Имя)** данной записи.</span><span class="sxs-lookup"><span data-stu-id="b8408-183">If your hosting provider doesn't provide these fields for SRV records, you must specify the **Service** and **Protocol** values in the record's **Name** field.</span></span> <span data-ttu-id="b8408-184">(Примечание. В зависимости от поставщика услуг размещения, поле **Name (Имя)** может называться иначе, например, **Host**, **Hostname** или **Subdomain**.) Чтобы добавить эти значения, укажите их в одной строке, разделив значения точкой.</span><span class="sxs-lookup"><span data-stu-id="b8408-184">(Note: Depending on your hosting provider, the **Name** field might be called something else, like: **Host**, **Hostname**, or **Subdomain**.) To add these values, you create a single string, separating the values with a dot.</span></span> 

<span data-ttu-id="b8408-185">Пример: `_sip._tls`</span><span class="sxs-lookup"><span data-stu-id="b8408-185">Example: `_sip._tls`</span></span>

##### <a name="priority-weight-and-port-br"></a><span data-ttu-id="b8408-186">Поля Priority (Приоритет), Weight (Вес) и Port (Порт)</span><span class="sxs-lookup"><span data-stu-id="b8408-186">Priority, Weight, and Port</span></span> <br>
<span data-ttu-id="b8408-187">Если у вашего поставщика услуг размещения нет необходимых полей для записей SRV, соответствующие параметры задаются в поле **Target (Цель)** данной записи.</span><span class="sxs-lookup"><span data-stu-id="b8408-187">If your hosting provider doesn't provide these fields for SRV records, you must specify them in the record's **Target** field.</span></span> <span data-ttu-id="b8408-188">(Примечание. В зависимости от поставщика услуг размещения поле **Target (Цель)** может называться иначе, например, **Content (Содержимое)**, **IP Address (IP-адрес)** или **Target Host (Целевой узел**.)</span><span class="sxs-lookup"><span data-stu-id="b8408-188">(Note: Depending on your hosting provider, the **Target** field might be called something else, like: **Content**, **IP Address**, or **Target Host**.)</span></span> 

<span data-ttu-id="b8408-189">Чтобы добавить эти значения, укажите их в одной строке, разделив значения пробелами, и *иногда строка может заканчиваться точкой* (если вы не уверены, обратитесь к поставщику.)</span><span class="sxs-lookup"><span data-stu-id="b8408-189">To add these values, create a single string, separating the values with spaces and *sometimes ending with a dot* (check with your provider if you are unsure).</span></span> <span data-ttu-id="b8408-190">Значения указываются в следующем порядке: Priority, Weight, Port, Target.</span><span class="sxs-lookup"><span data-stu-id="b8408-190">The values must be included in this order: Priority, Weight, Port, Target.</span></span> 

- <span data-ttu-id="b8408-191">Пример 1:`100 1 443 sipdir.online.lync.com.`</span><span class="sxs-lookup"><span data-stu-id="b8408-191">Example 1: `100 1 443 sipdir.online.lync.com.`</span></span>
- <span data-ttu-id="b8408-192">Пример 2: `100 1 443 sipdir.online.lync.com`</span><span class="sxs-lookup"><span data-stu-id="b8408-192">Example 2: `100 1 443 sipdir.online.lync.com`</span></span>
