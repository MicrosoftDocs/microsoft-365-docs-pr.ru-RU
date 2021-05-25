---
title: Добавление записей DNS для подключения своего домена
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
description: Подключите домен любого поставщика услуг размещения DNS к Microsoft 365, проверив домен и обновив записи DNS в учетной записи регистратора.
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: 62b6793dd97e146b703c82e0ba23f4d7414025b6
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623981"
---
# <a name="add-dns-records-to-connect-your-domain"></a><span data-ttu-id="8ee13-103">Добавление записей DNS для подключения своего домена</span><span class="sxs-lookup"><span data-stu-id="8ee13-103">Add DNS records to connect your domain</span></span>

<span data-ttu-id="8ee13-104">Если вы приобрели домен у стороннего поставщика услуг размещения, вы можете подключить его к Microsoft 365, обновив записи DNS учетной записи регистратора.</span><span class="sxs-lookup"><span data-stu-id="8ee13-104">If you purchased a domain from a third-party hosting provider, you can connect it to Microsoft 365 by updating the DNS records in your registrar’s account.</span></span>

<span data-ttu-id="8ee13-105">После выполнения этих действий ваш домен останется зарегистрированным на узле, через который вы приобрели домен, но Microsoft 365 сможет использовать его для ваших адресов электронной почты (например, user@yourdomain.com) и других служб.</span><span class="sxs-lookup"><span data-stu-id="8ee13-105">At the end of these steps, your domain will stay registered with the host that you purchased the domain from, but Microsoft 365 can use it for your email addresses (like user@yourdomain.com) and other services.</span></span>

<span data-ttu-id="8ee13-106">Если вы не добавите домен, сотрудники вашей организации будут использовать домен onmicrosoft.com в своих адресах электронной почты до тех пор, пока вы не добавите домен.</span><span class="sxs-lookup"><span data-stu-id="8ee13-106">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="8ee13-107">Перед добавлением пользователей важно добавить свой домен, поэтому вам не нужно было настраивать их дважды.</span><span class="sxs-lookup"><span data-stu-id="8ee13-107">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="8ee13-108">Если вы не нашли то, что вы ищете, см. раздел [Вопросы и ответы по доменам](../setup/domains-faq.yml) ниже.</span><span class="sxs-lookup"><span data-stu-id="8ee13-108">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for below.</span></span>

## <a name="step-1-add-a-txt-or-mx-record-to-verify-you-own-the-domain"></a><span data-ttu-id="8ee13-109">Этап 1. Добавление записи типа TXT или MX для подтверждения права собственности на домен</span><span class="sxs-lookup"><span data-stu-id="8ee13-109">Step 1: Add a TXT or MX record to verify you own the domain</span></span>

### <a name="recommended-verify-with-a-txt-record"></a><span data-ttu-id="8ee13-110">Рекомендуется: Проверка с помощью записи TXT</span><span class="sxs-lookup"><span data-stu-id="8ee13-110">Recommended: Verify with a TXT record</span></span>

<span data-ttu-id="8ee13-111">Сначала необходимо подтвердить, что вы владеете доменом, который вы хотите добавить в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ee13-111">First, you need to prove you own the domain you want to add to Microsoft 365.</span></span>

1. <span data-ttu-id="8ee13-112">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com/), а затем выберите **Показать все** > **Настройки** > **Домены**.</span><span class="sxs-lookup"><span data-stu-id="8ee13-112">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="8ee13-113">В новой вкладке или окне браузера, войдите в свой поставщик услуг размещения DNS и найдите место, в котором вы управляете параметрами DNS (например, параметры файла зоны, управление доменами, диспетчер доменов, диспетчер DNS).</span><span class="sxs-lookup"><span data-stu-id="8ee13-113">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="8ee13-114">Перейдите на страницу диспетчера DNS поставщика, добавьте запись TXT, указанную в центре администрирования, в ваш домен.</span><span class="sxs-lookup"><span data-stu-id="8ee13-114">Go to your provider's DNS Manager page, and add the TXT record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="8ee13-115">Добавление этой записи не повлияет на ваши существующие сообщения электронной почты и другие службы, и вы можете безопасно удалить ее после подключения домена к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ee13-115">Adding this record won't affect your existing email or other services and you can safely remove it once your domain is connected to Microsoft 365.</span></span>

<span data-ttu-id="8ee13-116">Пример.</span><span class="sxs-lookup"><span data-stu-id="8ee13-116">Example:</span></span>
- <span data-ttu-id="8ee13-117">Имя TXT: `@`</span><span class="sxs-lookup"><span data-stu-id="8ee13-117">TXT Name: `@`</span></span>
- <span data-ttu-id="8ee13-118">Значение TXT: MS=ms######## (уникальный идентификатор из центра администрирования);</span><span class="sxs-lookup"><span data-stu-id="8ee13-118">TXT Value: MS=ms######## (unique ID from the admin center)</span></span>
- <span data-ttu-id="8ee13-119">TTL: `3600‎` (или значение вашего поставщика по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8ee13-119">TTL: `3600‎` (or your provider default)</span></span>

4. <span data-ttu-id="8ee13-120">Сохраните запись, вернитесь в центр администрирования и выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="8ee13-120">Save the record, go back to the admin center, and then select **Verify**.</span></span> <span data-ttu-id="8ee13-121">Как правило, регистрация изменений занимает около 15 минут, но иногда это может занять больше времени.</span><span class="sxs-lookup"><span data-stu-id="8ee13-121">It typically takes around 15 minutes for record changes to register, but sometimes it can take longer.</span></span> <span data-ttu-id="8ee13-122">Предоставьте процессу некоторое время и выполните несколько попыток, чтобы изменение вступило в силу.</span><span class="sxs-lookup"><span data-stu-id="8ee13-122">Give it some time and a few tries to pick up the change.</span></span>

<span data-ttu-id="8ee13-123">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="8ee13-123">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

### <a name="verify-with-an-mx-record"></a><span data-ttu-id="8ee13-124">Проверка с помощью записи MX</span><span class="sxs-lookup"><span data-stu-id="8ee13-124">Verify with an MX record</span></span>

<span data-ttu-id="8ee13-125">Если регистратор не поддерживает добавление записей типа TXT, выполните проверку, добавив запись MX.</span><span class="sxs-lookup"><span data-stu-id="8ee13-125">If your registrar doesn't support adding TXT records, you can verify by adding an MX record.</span></span>

1. <span data-ttu-id="8ee13-126">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com/), а затем выберите **Показать все** > **Настройки** > **Домены**.</span><span class="sxs-lookup"><span data-stu-id="8ee13-126">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="8ee13-127">В новой вкладке или окне браузера, войдите в свой поставщик услуг размещения DNS и найдите место, в котором вы управляете параметрами DNS (например, параметры файла зоны, управление доменами, диспетчер доменов, диспетчер DNS).</span><span class="sxs-lookup"><span data-stu-id="8ee13-127">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="8ee13-128">Перейдите на страницу диспетчера DNS поставщика, добавьте запись MX, указанную в центре администрирования, в ваш домен.</span><span class="sxs-lookup"><span data-stu-id="8ee13-128">Go to your provider's DNS Manager page, and add the MX record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="8ee13-129">**Priority** (Приоритет) этой записи MX должен быть самым высоким из всех существующих записей MX для домена.</span><span class="sxs-lookup"><span data-stu-id="8ee13-129">This MX record's **Priority** must be the highest of all existing MX records for the domain.</span></span> <span data-ttu-id="8ee13-130">В противном случае она может помешать отправке и получению электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8ee13-130">Otherwise, it can interfere with sending and receiving email.</span></span> <span data-ttu-id="8ee13-131">Такие записи следует удалить сразу после завершения проверки домена.</span><span class="sxs-lookup"><span data-stu-id="8ee13-131">You should delete this records as soon as domain verification is complete.</span></span>

<span data-ttu-id="8ee13-132">Убедитесь, что значения полей точно соответствуют указанным ниже.</span><span class="sxs-lookup"><span data-stu-id="8ee13-132">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="8ee13-133">Record Type (Тип записи): `MX`</span><span class="sxs-lookup"><span data-stu-id="8ee13-133">Record Type: `MX`</span></span>
- <span data-ttu-id="8ee13-134">Приоритет: установите максимальное доступное значение, обычно `0`.</span><span class="sxs-lookup"><span data-stu-id="8ee13-134">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="8ee13-135">Host Name (Имя узла): `@`</span><span class="sxs-lookup"><span data-stu-id="8ee13-135">Host Name: `@`</span></span>
- <span data-ttu-id="8ee13-136">Указывает на адрес: скопируйте значение из центра администрирования и вставьте его сюда.</span><span class="sxs-lookup"><span data-stu-id="8ee13-136">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="8ee13-137">TTL: `3600‎` (или значение вашего поставщика по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8ee13-137">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="8ee13-138">Когда продукт корпорации Майкрософт обнаружит правильную запись MX, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="8ee13-138">When Microsoft finds the correct MX record, your domain is verified.</span></span>

## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a><span data-ttu-id="8ee13-139">Шаг 2. Добавление записей DNS для подключения служб Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8ee13-139">Step 2: Add DNS records to connect Microsoft services</span></span>

<span data-ttu-id="8ee13-140">В новой вкладке или окне браузера, войдите в свой поставщик услуг размещения DNS, а затем найдите место, в котором вы управляете параметрами DNS (например, параметры файла зоны, управление доменами, диспетчер доменов, диспетчер DNS).</span><span class="sxs-lookup"><span data-stu-id="8ee13-140">In a new browser tab or window, sign in to your DNS hosting provider, and find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>

<span data-ttu-id="8ee13-141">В зависимости от служб, которые вы хотите включить, потребуется добавить несколько записей DNS различных типов.</span><span class="sxs-lookup"><span data-stu-id="8ee13-141">You'll be adding several different types of DNS records depending on the services you want to enable.</span></span> 

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a><span data-ttu-id="8ee13-142">Добавление записи MX для электронной почты (Outlook, Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="8ee13-142">Add an MX record for email (Outlook, Exchange Online)</span></span>
<span data-ttu-id="8ee13-143">**Прежде чем начать, выполните указанные ниже действия**. Если у пользователей уже есть электронная почта в вашем домене (например, user@yourdomain.com), перед настройкой записей MX создайте их учетные записи в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="8ee13-143">**Before you begin:** If users already have email with your domain (such as user@yourdomain.com), create their accounts in the admin center before you set up your MX records.</span></span> <span data-ttu-id="8ee13-144">Таким образом, они будут продолжать получать электронную почту.</span><span class="sxs-lookup"><span data-stu-id="8ee13-144">That way, they’ll continue to receive email.</span></span> <span data-ttu-id="8ee13-145">После обновления записи MX вашего домена все новые сообщения, адресованные его пользователям, будут поступать в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ee13-145">When you update your domain's MX record, all new email for anyone who uses your domain will now come to Microsoft 365.</span></span> <span data-ttu-id="8ee13-146">Ранее полученные сообщения останутся на текущем узле электронной почты, если вы не решите [перенести сообщения и контакты в Microsoft 365](../setup/migrate-email-and-contacts-admin.md).</span><span class="sxs-lookup"><span data-stu-id="8ee13-146">Any email you already have will stay at your current email host, unless you decide to [migrate email and contacts to Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)</span></span>

<span data-ttu-id="8ee13-147">Информация для записи MX будет выводится в мастере настройки домена центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="8ee13-147">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="8ee13-148">На веб-сайте своего поставщика услуг размещения добавьте новую MX-запись.</span><span class="sxs-lookup"><span data-stu-id="8ee13-148">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="8ee13-149">Убедитесь, что значения полей точно соответствуют указанным ниже.</span><span class="sxs-lookup"><span data-stu-id="8ee13-149">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="8ee13-150">Record Type (Тип записи): `MX`</span><span class="sxs-lookup"><span data-stu-id="8ee13-150">Record Type: `MX`</span></span>
- <span data-ttu-id="8ee13-151">Приоритет: установите максимальное доступное значение, обычно `0`.</span><span class="sxs-lookup"><span data-stu-id="8ee13-151">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="8ee13-152">Host Name (Имя узла): `@`</span><span class="sxs-lookup"><span data-stu-id="8ee13-152">Host Name: `@`</span></span>
- <span data-ttu-id="8ee13-153">Указывает на адрес: скопируйте значение из центра администрирования и вставьте его сюда.</span><span class="sxs-lookup"><span data-stu-id="8ee13-153">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="8ee13-154">TTL: `3600‎` (или значение вашего поставщика по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8ee13-154">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="8ee13-155">Сохраните запись, а затем удалите все остальные записи MX.</span><span class="sxs-lookup"><span data-stu-id="8ee13-155">Save the record, and then remove any other MX records.</span></span>

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a><span data-ttu-id="8ee13-156">Добавление записей CNAME для подключения к другим службам (Teams, Exchange Online, AAD, MDM)</span><span class="sxs-lookup"><span data-stu-id="8ee13-156">Add CNAME records to connect other services (Teams, Exchange Online, AAD, MDM)</span></span>
<span data-ttu-id="8ee13-157">Информация для записей CNAME будет выводится в мастере настройки домена центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="8ee13-157">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="8ee13-158">На веб-сайте поставщика услуг размещения добавьте записи CNAME для каждой службы, которую вы хотите подключить.</span><span class="sxs-lookup"><span data-stu-id="8ee13-158">On your hosting provider's website, add CNAME records for each service that you want to connect.</span></span>
<span data-ttu-id="8ee13-159">Убедитесь, что значения полей точно соответствуют каждым из указанных ниже.</span><span class="sxs-lookup"><span data-stu-id="8ee13-159">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="8ee13-160">Record Type (Тип записи): `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="8ee13-160">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="8ee13-161">Host (Узел): вставьте значения, скопированные из центра администрирования, здесь.</span><span class="sxs-lookup"><span data-stu-id="8ee13-161">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="8ee13-162">Указывает на адрес: скопируйте значение из центра администрирования и вставьте его сюда.</span><span class="sxs-lookup"><span data-stu-id="8ee13-162">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="8ee13-163">TTL: `3600‎` (или значение вашего поставщика по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8ee13-163">TTL: `3600‎` (or your provider default)</span></span>


### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a><span data-ttu-id="8ee13-164">Добавление или изменение записи SPF, которая помогает предотвратить нежелательную почту (Outlook, Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="8ee13-164">Add or edit an SPF TXT record to help prevent email spam (Outlook, Exchange Online)</span></span>
<span data-ttu-id="8ee13-165">**Прежде чем начать:** если вы уже указали запись SPF для домена, не создавайте еще одну для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ee13-165">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="8ee13-166">Вместо этого добавьте необходимые значения Microsoft 365 в текущую запись по веб-сайту вашего поставщика услуг размещения, таким образом, в *одной* записи SPF будут указаны оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="8ee13-166">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="8ee13-167">На веб-сайте вашего поставщика услуг размещения измените имеющуюся запись SPF или создайте новую запись SPF.</span><span class="sxs-lookup"><span data-stu-id="8ee13-167">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="8ee13-168">Убедитесь, что значения полей точно соответствуют указанным ниже.</span><span class="sxs-lookup"><span data-stu-id="8ee13-168">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="8ee13-169">Record Type (Тип записи): `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="8ee13-169">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="8ee13-170">Host (Узел): `@`</span><span class="sxs-lookup"><span data-stu-id="8ee13-170">Host: `@`</span></span>
- <span data-ttu-id="8ee13-171">TXT Value (Значение TXT): `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="8ee13-171">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="8ee13-172">TTL: `3600‎` (или значение вашего поставщика по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8ee13-172">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="8ee13-173">Сохраните запись.</span><span class="sxs-lookup"><span data-stu-id="8ee13-173">Save the record.</span></span>

<span data-ttu-id="8ee13-174">Проверьте запись SPF, используя одно из этих [средств проверки SPF](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain).</span><span class="sxs-lookup"><span data-stu-id="8ee13-174">Validate your SPF record by using one of these [SPF validation tools](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="8ee13-175">Инфраструктура политики отправителей (SPF) призвана предотвратить спуфинг, но существуют некоторые методики, позволяющие обойти ее.</span><span class="sxs-lookup"><span data-stu-id="8ee13-175">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="8ee13-176">Чтобы защититься от таких атак, по завершении настройки SPF необходимо настроить DKIM и DMARC для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8ee13-176">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span> 

<span data-ttu-id="8ee13-177">Чтобы начать, см. статьи [Проверка исходящей электронной почты, отправляемой со своего домена в Microsoft 365, с помощью DKIM](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) и [Использование DMARC для проверки электронной почты в Microsoft 365](../../security/office-365-security/use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="8ee13-177">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) and [Use DMARC to validate email in Microsoft 365](../../security/office-365-security/use-dmarc-to-validate-email.md).</span></span>

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a><span data-ttu-id="8ee13-178">Добавление записей SRV для служб связи (Teams, Skype для бизнеса)</span><span class="sxs-lookup"><span data-stu-id="8ee13-178">Add SRV records for communications services (Teams, Skype for Business)</span></span>

<span data-ttu-id="8ee13-179">На веб-сайте поставщика услуг размещения добавьте записи SRV для каждой службы, которую вы хотите подключить.</span><span class="sxs-lookup"><span data-stu-id="8ee13-179">On your hosting provider's website, add SRV records for each service you want to connect.</span></span>
<span data-ttu-id="8ee13-180">Убедитесь, что значения полей точно соответствуют каждым из указанных ниже.</span><span class="sxs-lookup"><span data-stu-id="8ee13-180">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="8ee13-181">Record Type (Тип записи): `SRV (Service)`</span><span class="sxs-lookup"><span data-stu-id="8ee13-181">Record Type: `SRV (Service)`</span></span>
- <span data-ttu-id="8ee13-182">Имя: `@`</span><span class="sxs-lookup"><span data-stu-id="8ee13-182">Name: `@`</span></span>
- <span data-ttu-id="8ee13-183">Цель: скопируйте значение из центра администрирования и вставьте его сюда.</span><span class="sxs-lookup"><span data-stu-id="8ee13-183">Target: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="8ee13-184">Протокол: скопируйте значение из центра администрирования и вставьте его сюда.</span><span class="sxs-lookup"><span data-stu-id="8ee13-184">Protocol: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="8ee13-185">Служба: скопируйте значение из центра администрирования и вставьте его сюда.</span><span class="sxs-lookup"><span data-stu-id="8ee13-185">Service: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="8ee13-186">Приоритет: `100`</span><span class="sxs-lookup"><span data-stu-id="8ee13-186">Priority: `100`</span></span>
- <span data-ttu-id="8ee13-187">Weight (Вес):`1`</span><span class="sxs-lookup"><span data-stu-id="8ee13-187">Weight: `1`</span></span>
- <span data-ttu-id="8ee13-188">Порт: скопируйте значение из центра администрирования и вставьте его сюда.</span><span class="sxs-lookup"><span data-stu-id="8ee13-188">Port: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="8ee13-189">TTL: `3600‎` (или значение вашего поставщика по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8ee13-189">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="8ee13-190">Сохраните запись.</span><span class="sxs-lookup"><span data-stu-id="8ee13-190">Save the record.</span></span>

#### <a name="srv-record-field-restrictions-and-workarounds"></a><span data-ttu-id="8ee13-191">Ограничения и обходные пути для полей записи SRV</span><span class="sxs-lookup"><span data-stu-id="8ee13-191">SRV record field restrictions and workarounds</span></span>
<span data-ttu-id="8ee13-192">Некоторые поставщики услуг размещения накладывают ограничения на значения полей в записях SRV.</span><span class="sxs-lookup"><span data-stu-id="8ee13-192">Some hosting providers impose restrictions on field values within SRV records.</span></span> <span data-ttu-id="8ee13-193">Ниже приведены некоторые распространенные временные решения для этих ограничений.</span><span class="sxs-lookup"><span data-stu-id="8ee13-193">Here are some common workarounds for these restrictions.</span></span>

##### <a name="name"></a><span data-ttu-id="8ee13-194">Имя</span><span class="sxs-lookup"><span data-stu-id="8ee13-194">Name</span></span>
<span data-ttu-id="8ee13-195">Если ваш поставщик услуг размещения не позволяет задать для этого поля **@**, оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="8ee13-195">If your hosting provider doesn't allow setting this field to **@**, leave it blank.</span></span> <span data-ttu-id="8ee13-196">Следуйте этим инструкциям *только* в том случае, если вашим поставщиком услуг размещения предусмотрены отдельные поля для значений "Service" (Служба) и "Protocol" (Протокол).</span><span class="sxs-lookup"><span data-stu-id="8ee13-196">Use this approach *only* when your hosting provider has separate fields for the Service and Protocol values.</span></span> <span data-ttu-id="8ee13-197">В противном случае см. примечания о соответствующих параметрах ниже.</span><span class="sxs-lookup"><span data-stu-id="8ee13-197">Otherwise, see the Service and Protocol notes below.</span></span>

##### <a name="service-and-protocol"></a><span data-ttu-id="8ee13-198">Поля Service (Служба) и Protocol (Протокол)</span><span class="sxs-lookup"><span data-stu-id="8ee13-198">Service and Protocol</span></span>
<span data-ttu-id="8ee13-199">Если у вашего поставщика услуг размещения нет соответствующих полей для записей SRV, параметры **Service (Служба)** и **Protocol (Протокол)** задаются в поле **Name (Имя)** данной записи.</span><span class="sxs-lookup"><span data-stu-id="8ee13-199">If your hosting provider doesn't provide these fields for SRV records, you must specify the **Service** and **Protocol** values in the record's **Name** field.</span></span> <span data-ttu-id="8ee13-200">(Примечание. В зависимости от поставщика услуг размещения, поле **Name (Имя)** может называться иначе, например, **Host**, **Hostname** или **Subdomain**.) Чтобы добавить эти значения, укажите их в одной строке, разделив значения точкой.</span><span class="sxs-lookup"><span data-stu-id="8ee13-200">(Note: Depending on your hosting provider, the **Name** field might be called something else, like: **Host**, **Hostname**, or **Subdomain**.) To add these values, you create a single string, separating the values with a dot.</span></span> 

<span data-ttu-id="8ee13-201">Пример: `_sip._tls`</span><span class="sxs-lookup"><span data-stu-id="8ee13-201">Example: `_sip._tls`</span></span>

##### <a name="priority-weight-and-port-br"></a><span data-ttu-id="8ee13-202">Поля Priority (Приоритет), Weight (Вес) и Port (Порт)</span><span class="sxs-lookup"><span data-stu-id="8ee13-202">Priority, Weight, and Port</span></span> <br>
<span data-ttu-id="8ee13-203">Если у вашего поставщика услуг размещения нет необходимых полей для записей SRV, соответствующие параметры задаются в поле **Target (Цель)** данной записи.</span><span class="sxs-lookup"><span data-stu-id="8ee13-203">If your hosting provider doesn't provide these fields for SRV records, you must specify them in the record's **Target** field.</span></span> <span data-ttu-id="8ee13-204">(Примечание. В зависимости от поставщика услуг размещения поле **Target (Цель)** может называться иначе, например, **Content (Содержимое)**, **IP Address (IP-адрес)** или **Target Host (Целевой узел**.)</span><span class="sxs-lookup"><span data-stu-id="8ee13-204">(Note: Depending on your hosting provider, the **Target** field might be called something else, like: **Content**, **IP Address**, or **Target Host**.)</span></span> 

<span data-ttu-id="8ee13-205">Чтобы добавить эти значения, укажите их в одной строке, разделив значения пробелами, и *иногда строка может заканчиваться точкой* (если вы не уверены, обратитесь к поставщику.)</span><span class="sxs-lookup"><span data-stu-id="8ee13-205">To add these values, create a single string, separating the values with spaces and *sometimes ending with a dot* (check with your provider if you are unsure).</span></span> <span data-ttu-id="8ee13-206">Значения указываются в следующем порядке: Priority, Weight, Port, Target.</span><span class="sxs-lookup"><span data-stu-id="8ee13-206">The values must be included in this order: Priority, Weight, Port, Target.</span></span> 

- <span data-ttu-id="8ee13-207">Пример 1:`100 1 443 sipdir.online.lync.com.`</span><span class="sxs-lookup"><span data-stu-id="8ee13-207">Example 1: `100 1 443 sipdir.online.lync.com.`</span></span>
- <span data-ttu-id="8ee13-208">Пример 2: `100 1 443 sipdir.online.lync.com`</span><span class="sxs-lookup"><span data-stu-id="8ee13-208">Example 2: `100 1 443 sipdir.online.lync.com`</span></span>

## <a name="related-content"></a><span data-ttu-id="8ee13-209">См. также:</span><span class="sxs-lookup"><span data-stu-id="8ee13-209">Related content</span></span>

<span data-ttu-id="8ee13-210">[Изменение серверов доменных имен для настройки Microsoft 365 с любым регистратором доменных имен](change-nameservers-at-any-domain-registrar.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="8ee13-210">[Change nameservers to set up Microsoft 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md) (article)</span></span>\
<span data-ttu-id="8ee13-211">[Поиск и устранение неполадок после добавления домена и записей DNS](find-and-fix-issues.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="8ee13-211">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="8ee13-212">[Управление доменами](index.yml) (страница ссылки)</span><span class="sxs-lookup"><span data-stu-id="8ee13-212">[Manage domains](index.yml) (link page)</span></span>