---
title: Настройка пробной лабораторной среды Майкрософт для защиты от угроз
description: Доступ к центру обеспечения безопасности Microsoft 365 и Настройка лабораторной среды лаборатории Майкрософт по защите от угроз
keywords: Пробная версия системы защиты от угроз Майкрософт, проверка Microsoft Threat Protection, Настройка лаборатории оценки защиты от угроз Майкрософт
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 6cba773d0c4bea259db151d5a8f1d8e03954a045
ms.sourcegitcommit: f80c6c52e5b08290f74baec1d64c4070046c32e4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2020
ms.locfileid: "44717299"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="96da7-104">Настройка пробной лабораторной среды Майкрософт для защиты от угроз</span><span class="sxs-lookup"><span data-stu-id="96da7-104">Set up your Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="96da7-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="96da7-105">**Applies to:**</span></span>
- <span data-ttu-id="96da7-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="96da7-106">Microsoft Threat Protection</span></span> 


<span data-ttu-id="96da7-107">Создание пробной лабораторной среды Майкрософт для защиты от угроз и развертывание выполняется в три этапа:</span><span class="sxs-lookup"><span data-stu-id="96da7-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Подготовка лаборатории оценки Microsoft Threat protection" />
      <br/><span data-ttu-id="96da7-109">Этап 1: подготовка</a></span><span class="sxs-lookup"><span data-stu-id="96da7-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Настройка лаборатории оценки Microsoft Threat protection" />
      <br/><span data-ttu-id="96da7-111">Этап 2: Настройка</a></span><span class="sxs-lookup"><span data-stu-id="96da7-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints" title="
Настройте каждый из принципов защиты от угроз Майкрософт для лаборатории пробной среды Майкрософт по защите от угроз и конечных точек." />
      <br/><span data-ttu-id="96da7-113">Этап 3: Настройка встроенного &</a></span><span class="sxs-lookup"><span data-stu-id="96da7-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="96da7-114">В данный момент вы настраиваете этап настройки.</span><span class="sxs-lookup"><span data-stu-id="96da7-114">You are currently in the set up phase.</span></span> <span data-ttu-id="96da7-115">Выполните начальные действия, чтобы получить доступ к центру безопасности Microsoft 365, а затем настройте свою лабораторную среду.</span><span class="sxs-lookup"><span data-stu-id="96da7-115">Take the initial steps to access Microsoft 365 Security Center then setup your trial lab environment.</span></span>

<span data-ttu-id="96da7-116">Подпишитесь на Office 365 или Azure Active Directory, чтобы создать клиент *. onmicrosoft.com* , который вы можете использовать для подписки на лицензию Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="96da7-116">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="96da7-117">Если у вас уже есть подписка на Office 365 или Azure Active Directory, вы можете пропустить этапы создания пробных клиентов Office 365</span><span class="sxs-lookup"><span data-stu-id="96da7-117">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

<span data-ttu-id="96da7-118">На этом этапе вы найдете следующие руководства:</span><span class="sxs-lookup"><span data-stu-id="96da7-118">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="96da7-119">Создание пробного клиента Office 365</span><span class="sxs-lookup"><span data-stu-id="96da7-119">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="96da7-120">Включение пробной подписки на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="96da7-120">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="96da7-121">Создание пробного клиента Office 365</span><span class="sxs-lookup"><span data-stu-id="96da7-121">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="96da7-122">Если у вас уже есть подписка на Office 365 или Azure Active Directory, вы можете пропустить этапы создания пробных клиентов Office 365</span><span class="sxs-lookup"><span data-stu-id="96da7-122">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="96da7-123">Перейдите на [портал продуктов Office 365](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) и выберите **бесплатную пробную версию**.</span><span class="sxs-lookup"><span data-stu-id="96da7-123">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>
<span data-ttu-id="96da7-124">![Страница "изображение of_Office 365 и бесплатная пробная версия"](../../media/mtp-eval-9.png)</span><span class="sxs-lookup"><span data-stu-id="96da7-124">![Image of_Office 365 E5 free trial page](../../media/mtp-eval-9.png)</span></span> <br>
  
2. <span data-ttu-id="96da7-125">Выполните пробную регистрацию, указав свой адрес электронной почты (персональный или корпоративный).</span><span class="sxs-lookup"><span data-stu-id="96da7-125">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="96da7-126">Нажмите кнопку **Настройка учетной записи**.</span><span class="sxs-lookup"><span data-stu-id="96da7-126">Click **Set up account**.</span></span>
<span data-ttu-id="96da7-127">![Страница "Настройка of_Office образа 365 для пробной регистрации](../../media/mtp-eval-10.png)</span><span class="sxs-lookup"><span data-stu-id="96da7-127">![Image of_Office 365 E5 trial registration setup page](../../media/mtp-eval-10.png)</span></span> <br> 

3. <span data-ttu-id="96da7-128">Введите имя, фамилию, номер рабочего телефона, название компании, размер и страну или регион.</span><span class="sxs-lookup"><span data-stu-id="96da7-128">Fill in your first name, last name, business phone number, company name, company size and country or region.</span></span>  
<br>![Of_Office изображений — страница настройки регистрации 365 для пробной регистрации с запросом имени, телефона и сведений о компании](../../media/mtp-eval-11.png) <br>
>[!NOTE]
><span data-ttu-id="96da7-130">Страна или регион, которые вы настроили, определяет регион центра обработки данных, в котором будет размещаться Office 365.</span><span class="sxs-lookup"><span data-stu-id="96da7-130">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="96da7-131">Выберите предпочтения проверки: в текстовом сообщении или вызове.</span><span class="sxs-lookup"><span data-stu-id="96da7-131">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="96da7-132">Нажмите кнопку **Отправить проверочный код**.</span><span class="sxs-lookup"><span data-stu-id="96da7-132">Click **Send Verification Code**.</span></span> 
<span data-ttu-id="96da7-133">![Страница "Настройка of_Office изображений с пробной проверкой 365](../../media/mtp-eval-12.png)</span><span class="sxs-lookup"><span data-stu-id="96da7-133">![Image of_Office 365 E5 trial registration setup page asking for verification preference](../../media/mtp-eval-12.png)</span></span> <br>

5. <span data-ttu-id="96da7-134">Задайте имя пользовательского домена для клиента, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="96da7-134">Set the custom domain name for your tenant, then click **Next**.</span></span>
<br><span data-ttu-id="96da7-135">![Страница "Настройка образа of_Office 365 для пробной регистрации", где можно настроить собственное доменное имя.](../../media/mtp-eval-13.png)</span><span class="sxs-lookup"><span data-stu-id="96da7-135">![Image of_Office 365 E5 trial registration setup page where you can set up your custom domain name](../../media/mtp-eval-13.png)</span></span> <br>
 
6. <span data-ttu-id="96da7-136">Настройте первое удостоверение, которое будет глобальным администратором клиента.</span><span class="sxs-lookup"><span data-stu-id="96da7-136">Set up the first identity which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="96da7-137">Введите **имя** и **пароль**.</span><span class="sxs-lookup"><span data-stu-id="96da7-137">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="96da7-138">Нажмите кнопку **Зарегистрироваться**.</span><span class="sxs-lookup"><span data-stu-id="96da7-138">Click **Sign up**.</span></span>
<span data-ttu-id="96da7-139">![Страница "Настройка образа of_Office 365", на которой можно задать бизнес-идентификатор](../../media/mtp-eval-14.png)</span><span class="sxs-lookup"><span data-stu-id="96da7-139">![Image of_Office 365 E5 trial registration setup page where you can set your business identity](../../media/mtp-eval-14.png)</span></span> <br>

7. <span data-ttu-id="96da7-140">Нажмите кнопку **Перейти к программе установки** , чтобы завершить подготовку пробного клиента Office 365 в Office.</span><span class="sxs-lookup"><span data-stu-id="96da7-140">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>
<br><span data-ttu-id="96da7-141">![Изображение страницы настройки Office 365 в пробной регистрационной записи с запросом кнопки "установить"](../../media/mtp-eval-15.png)</span><span class="sxs-lookup"><span data-stu-id="96da7-141">![Image of Office 365 E5 trial registration setup page prompting to click Go Setup button](../../media/mtp-eval-15.png)</span></span> <br>

8. <span data-ttu-id="96da7-142">Подключите корпоративный домен к клиенту Office 365.</span><span class="sxs-lookup"><span data-stu-id="96da7-142">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="96da7-143">Необязательно Выберите **подключить домен, который вы уже владеете** , и введите имя своего домена.</span><span class="sxs-lookup"><span data-stu-id="96da7-143">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="96da7-144">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="96da7-144">Click **Next**.</span></span>
<br><span data-ttu-id="96da7-145">![Image of_Office страницу установки 365 для настройки входа и электронной почты](../../media/mtp-eval-16.png)</span><span class="sxs-lookup"><span data-stu-id="96da7-145">![Image of_Office 365 E5 Setup page where you should personalize your sign-in and email](../../media/mtp-eval-16.png)</span></span> <br>
 
9. <span data-ttu-id="96da7-146">Чтобы проверить владение доменом, необходимо добавить запись TXT или MX.</span><span class="sxs-lookup"><span data-stu-id="96da7-146">You will need to add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="96da7-147">Добавив запись TXT или MX в свой домен, нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="96da7-147">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>
<br><span data-ttu-id="96da7-148">![Image of_Office 365, где необходимо добавить TXT записи MX для проверки домена](../../media/mtp-eval-17.png)</span><span class="sxs-lookup"><span data-stu-id="96da7-148">![Image of_Office 365 E5 setup page where you should add a TXT of MX record to verify your domain](../../media/mtp-eval-17.png)</span></span> <br>
 
10. <span data-ttu-id="96da7-149">Необязательно Создайте дополнительные учетные записи пользователей для клиента.</span><span class="sxs-lookup"><span data-stu-id="96da7-149">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="96da7-150">Вы можете пропустить этот шаг, нажав кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="96da7-150">You can skip this step by clicking **Next**.</span></span>
<span data-ttu-id="96da7-151">![Изображение of_Office страницу установки 365 для добавления пользователей](../../media/mtp-eval-18.png)</span><span class="sxs-lookup"><span data-stu-id="96da7-151">![Image of_Office 365 E5 setup page where you can add more users](../../media/mtp-eval-18.png)</span></span> <br>
 
11. <span data-ttu-id="96da7-152">Необязательно Скачайте приложения Office.</span><span class="sxs-lookup"><span data-stu-id="96da7-152">[Optional] Download Office apps.</span></span> <span data-ttu-id="96da7-153">Нажмите кнопку **Далее** , чтобы пропустить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="96da7-153">Click **Next** to skip this step.</span></span> 
<br><span data-ttu-id="96da7-154">![Image of_Office 365, где можно установить приложения Office](../../media/mtp-eval-19.png)</span><span class="sxs-lookup"><span data-stu-id="96da7-154">![Image of_Office 365 E5 page where you can install your Office apps](../../media/mtp-eval-19.png)</span></span> <br>

12. <span data-ttu-id="96da7-155">Необязательно Перенос сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="96da7-155">[Optional] Migrate email messages.</span></span> <span data-ttu-id="96da7-156">Опять же, вы можете пропустить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="96da7-156">Again, you can skip this step.</span></span>
<br><span data-ttu-id="96da7-157">![Image of_Office 365, где можно указать, следует ли переносить сообщения электронной почты или нет](../../media/mtp-eval-20.png)</span><span class="sxs-lookup"><span data-stu-id="96da7-157">![Image of_Office 365 E5 where you can set whether to migrate email messages or not](../../media/mtp-eval-20.png)</span></span> <br>
 
13. <span data-ttu-id="96da7-158">Выберите веб-службы.</span><span class="sxs-lookup"><span data-stu-id="96da7-158">Choose online services.</span></span> <span data-ttu-id="96da7-159">Выберите **Exchange** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="96da7-159">Select **Exchange** and click **Next**.</span></span> 
<br><span data-ttu-id="96da7-160">![Image of_Office 365, где можно выбрать Интернет-службы](../../media/mtp-eval-21.png)</span><span class="sxs-lookup"><span data-stu-id="96da7-160">![Image of_Office 365 E5 where you can choose your online services](../../media/mtp-eval-21.png)</span></span> <br>

14. <span data-ttu-id="96da7-161">Добавьте записи MX, CNAME и TXT в свой домен.</span><span class="sxs-lookup"><span data-stu-id="96da7-161">Add MX, CNAME and TXT records to your domain.</span></span> <span data-ttu-id="96da7-162">По завершении нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="96da7-162">When completed, select **Verify**.</span></span>
<br><span data-ttu-id="96da7-163">![Изображение of_Office 365 в ~ можно добавить записи DNS](../../media/mtp-eval-22.png)</span><span class="sxs-lookup"><span data-stu-id="96da7-163">![Image of_Office 365 E5 here you can add your DNS records](../../media/mtp-eval-22.png)</span></span> <br>
 
15. <span data-ttu-id="96da7-164">Поздравляем, вы завершили подготовку клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="96da7-164">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>
<br><span data-ttu-id="96da7-165">![Страница подтверждения завершения установки of_Office "изображение" 365](../../media/mtp-eval-23.png)</span><span class="sxs-lookup"><span data-stu-id="96da7-165">![Image of_Office 365 E5 setup completion confirmation page](../../media/mtp-eval-23.png)</span></span> <br>

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="96da7-166">Включение пробной подписки на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="96da7-166">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="96da7-167">При регистрации пробной версии вы получите 25 пользовательских лицензий, которые будут использоваться в течение месяца.</span><span class="sxs-lookup"><span data-stu-id="96da7-167">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="96da7-168">Сведения о том, [как испытать или приобрести подписку на M365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) .</span><span class="sxs-lookup"><span data-stu-id="96da7-168">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="96da7-169">В [центре администрирования Microsoft 365](https://admin.microsoft.com/)щелкните **выставление счетов** , а затем перейдите к разделу **Услуги по приобретению**.</span><span class="sxs-lookup"><span data-stu-id="96da7-169">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="96da7-170">Выберите **Microsoft 365** и щелкните **начать бесплатную пробную версию**.</span><span class="sxs-lookup"><span data-stu-id="96da7-170">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 
<span data-ttu-id="96da7-171">![Изображение of_Microsoft странице Загрузка бесплатной пробной версии 365](../../media/mtp-eval-24.png)</span><span class="sxs-lookup"><span data-stu-id="96da7-171">![Image of_Microsoft 365 E5 Start free trial page](../../media/mtp-eval-24.png)</span></span> <br>

3. <span data-ttu-id="96da7-172">Выберите предпочтения проверки: в текстовом сообщении или вызове.</span><span class="sxs-lookup"><span data-stu-id="96da7-172">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="96da7-173">После того как вы решили, введите номер телефона, выберите пункт **текстовые** или **позвонить мне** в зависимости от выбранного варианта.</span><span class="sxs-lookup"><span data-stu-id="96da7-173">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>
<span data-ttu-id="96da7-174">![Image of_Microsoft 365: начало бесплатной пробной страницы с запросом контактных сведений для отправки кода на доказательства, что вы не робот](../../media/mtp-eval-25.png)</span><span class="sxs-lookup"><span data-stu-id="96da7-174">![Image of_Microsoft 365 E5 Start free trial page asking for contact details to send code to prove you are not a robot](../../media/mtp-eval-25.png)</span></span> <br>
 
4. <span data-ttu-id="96da7-175">Введите код проверки и нажмите кнопку **начать бесплатную пробную версию**.</span><span class="sxs-lookup"><span data-stu-id="96da7-175">Enter the verification code and click **Start your free trial**.</span></span> 
<br><span data-ttu-id="96da7-176">![Image of_Microsoft 365: страница "Загрузка бесплатной пробной версии", на которой вы можете заполнить проверочный код система, отправленная на доказательства, что вы не робот](../../media/mtp-eval-26.png)</span><span class="sxs-lookup"><span data-stu-id="96da7-176">![Image of_Microsoft 365 E5 Start free trial page where you can fill out verification code the system sent to prove you are not a robot](../../media/mtp-eval-26.png)</span></span> <br>

5. <span data-ttu-id="96da7-177">Нажмите кнопку **проверить** , чтобы подтвердить пробную версию Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="96da7-177">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>
<br><span data-ttu-id="96da7-178">![Image of_Microsoft 365, перейдите на страницу Загрузка бесплатной пробной версии, где следует запустить кнопку Try Now](../../media/mtp-eval-27.png)</span><span class="sxs-lookup"><span data-stu-id="96da7-178">![Image of_Microsoft 365 E5 Start free trial page where you should clock the Try now button to start](../../media/mtp-eval-27.png)</span></span> <br>
 
6. <span data-ttu-id="96da7-179">Перейдите в раздел **центр администрирования Microsoft 365**  >  **Users**  >  **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="96da7-179">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="96da7-180">Выберите свою учетную запись пользователя, выберите **Управление лицензиями на продукты**, затем замените лицензию из Office 365 в ~ на **Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="96da7-180">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="96da7-181">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="96da7-181">Click **Save**.</span></span>
<span data-ttu-id="96da7-182">![Image of_Microsoft 365. страница центра администрирования, на которой можно выбрать лицензию Майкрософт 365](../../media/mtp-eval-28.png)</span><span class="sxs-lookup"><span data-stu-id="96da7-182">![Image of_Microsoft 365 Admin Center page where you can select Microsoft 365 E5 license](../../media/mtp-eval-28.png)</span></span> <br>
 
7. <span data-ttu-id="96da7-183">Снова выберите учетную запись глобального администратора и нажмите кнопку **Управление именем пользователя**.</span><span class="sxs-lookup"><span data-stu-id="96da7-183">Select the global administrator account again then click **Manage username**.</span></span>
<br><span data-ttu-id="96da7-184">![Image of_Microsoft 365 страница центра администрирования, на которой можно выбрать учетную запись и затем управлять именем пользователя.](../../media/mtp-eval-29.png)</span><span class="sxs-lookup"><span data-stu-id="96da7-184">![Image of_Microsoft 365 Admin Center page where you can select Account and then Manage username](../../media/mtp-eval-29.png)</span></span> <br>

8. <span data-ttu-id="96da7-185">Необязательно Замените домен с *onmicrosoft.com* на свой домен в зависимости от того, что было выбрано на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="96da7-185">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="96da7-186">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="96da7-186">Click **Save changes**.</span></span>
<br><span data-ttu-id="96da7-187">![Image of_Microsoft 365 страница центра администрирования, на которой можно изменить параметры домена](../../media/mtp-eval-30.png)</span><span class="sxs-lookup"><span data-stu-id="96da7-187">![Image of_Microsoft 365 Admin Center page where you can change your domain preference](../../media/mtp-eval-30.png)</span></span> <br>



## <a name="next-step"></a><span data-ttu-id="96da7-188">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="96da7-188">Next step</span></span>
|||
|:-------|:-----|
|<span data-ttu-id="96da7-189">![Этап 3: Настройка встроенного &](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="96da7-189">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="96da7-190">Этап 3: Настройка встроенного &</span><span class="sxs-lookup"><span data-stu-id="96da7-190">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="96da7-191">Настройте каждый из принципов защиты от угроз Майкрософт для лаборатории оценки Microsoft Threat Protection и входящей конечной точки.</span><span class="sxs-lookup"><span data-stu-id="96da7-191">Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection evaluation lab and onboard your endpoints.</span></span>
