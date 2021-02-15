---
title: Настройка пробной или пилотной среды Microsoft 365 Defender
description: Access Microsoft 365 Security Center then set up your Microsoft 365 Defender trial lab environment
keywords: Пробная настройка Защиты от угроз (Майкрософт), пилотная настройка Защиты от угроз (Майкрософт), попробуйте Microsoft Threat Protection, настройка лаборатории оценки Защиты от угроз (Майкрософт)
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 835adc5c2bf9fd1c9a14c2d53b17a032a89a6240
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932986"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="105cb-104">Настройка пробной лабораторной среды Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="105cb-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="105cb-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="105cb-105">**Applies to:**</span></span>
- <span data-ttu-id="105cb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="105cb-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="105cb-107">Создание пробной лабораторной или пилотной среды Microsoft 365 Defender и ее развертывание — это трех этапов:</span><span class="sxs-lookup"><span data-stu-id="105cb-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="105cb-108">[![Этап 1. Подготовка](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="105cb-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="105cb-109">Этап 1. Подготовка</span><span class="sxs-lookup"><span data-stu-id="105cb-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |![Этап 2. Настройка](../../media/phase-diagrams/setup.png)<br/><span data-ttu-id="105cb-111">Этап 2. Настройка</span><span class="sxs-lookup"><span data-stu-id="105cb-111">Phase 2: Set up</span></span> |<span data-ttu-id="105cb-112">[![Этап 3. Ветвь](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="105cb-112">[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span></span><br/>[<span data-ttu-id="105cb-113">Этап 3. Ветвь</span><span class="sxs-lookup"><span data-stu-id="105cb-113">Phase 3: Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="105cb-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="105cb-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="105cb-115">Вернуться к пилотной книге</span><span class="sxs-lookup"><span data-stu-id="105cb-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
||<span data-ttu-id="105cb-116">*Вы здесь!*</span><span class="sxs-lookup"><span data-stu-id="105cb-116">*You are here!*</span></span>  | | |


<span data-ttu-id="105cb-117">В настоящее время вы работаете на этапе настройка.</span><span class="sxs-lookup"><span data-stu-id="105cb-117">You're currently in the set up phase.</span></span> <span data-ttu-id="105cb-118">Сначала необходимо получить доступ к Центру безопасности Microsoft 365, а затем настроить пробную или пилотную среду.</span><span class="sxs-lookup"><span data-stu-id="105cb-118">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="105cb-119">Зарегистрируйте подписку на Office 365 или Azure Active Directory, чтобы создать клиент *.onmicrosoft.com,* который можно использовать для регистрации в вашей лицензии Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="105cb-119">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="105cb-120">Если у вас уже есть подписка на Office 365 или Azure Active Directory, вы можете пропустить этапы создания пробной или пилотной подписки на Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="105cb-120">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="105cb-121">На этом этапе вы получите руководство по:</span><span class="sxs-lookup"><span data-stu-id="105cb-121">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="105cb-122">Создание пробного клиента Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="105cb-122">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="105cb-123">Включить пробную подписку на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="105cb-123">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="105cb-124">Создание пробного клиента Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="105cb-124">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="105cb-125">Если у вас уже есть подписка на Office 365 или Azure Active Directory, вы можете пропустить действия по созданию пробного клиента Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="105cb-125">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="105cb-126">Перейдите на портал [продуктов Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) и выберите **бесплатную пробную версия.**</span><span class="sxs-lookup"><span data-stu-id="105cb-126">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Страница of_Office 365 E5](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="105cb-128">Завершите регистрацию пробной версия, введите свой адрес электронной почты (личный или корпоративный).</span><span class="sxs-lookup"><span data-stu-id="105cb-128">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="105cb-129">Щелкните **"Настройка учетной записи".**</span><span class="sxs-lookup"><span data-stu-id="105cb-129">Click **Set up account**.</span></span>

   ![Страница of_Office пробной регистрации E5 в 365 E5](../../media/mtp-eval-10.png)

3. <span data-ttu-id="105cb-131">Уполномойте имя, фамилию, номер телефона, название компании, размер компании, страну или регион.</span><span class="sxs-lookup"><span data-stu-id="105cb-131">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![Изображение of_Office 365 E5: страница настройки пробной регистрации E5 с запросом имени, телефона и сведений о компании](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="105cb-133">Страна или регион, которые вы здесь настроили, определяет регион центра обработки данных, в который будет работать Office 365.</span><span class="sxs-lookup"><span data-stu-id="105cb-133">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="105cb-134">Выберите параметр проверки: с помощью текстового сообщения или звонка.</span><span class="sxs-lookup"><span data-stu-id="105cb-134">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="105cb-135">Щелкните **"Отправить код проверки".**</span><span class="sxs-lookup"><span data-stu-id="105cb-135">Click **Send Verification Code**.</span></span> 

   ![Изображение of_Office 365 E5: страница настройки пробной регистрации с запросом подтверждения](../../media/mtp-eval-12.png)

5. <span data-ttu-id="105cb-137">Задайте имя пользовательского домена для клиента, а затем нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="105cb-137">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Страница of_Office пробной регистрации E5 365, на которой можно настроить пользовательское доменное имя](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="105cb-139">Настроить первое удостоверение, которое будет глобальным администратором клиента.</span><span class="sxs-lookup"><span data-stu-id="105cb-139">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="105cb-140">В заполните **имя** и **пароль.**</span><span class="sxs-lookup"><span data-stu-id="105cb-140">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="105cb-141">Нажмите кнопку **Зарегистрироваться**.</span><span class="sxs-lookup"><span data-stu-id="105cb-141">Click **Sign up**.</span></span>

   ![Изображение of_Office 365 E5: страница настройки пробной регистрации E5, на которой можно настроить бизнес-удостоверение](../../media/mtp-eval-14.png)

7. <span data-ttu-id="105cb-143">Нажмите **кнопку "Перейти к** установке", чтобы завершить настройку пробного клиента Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="105cb-143">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Изображение страницы настройки пробной регистрации Office 365 E5 с запросом на кнопку "Перейти к установке"](../../media/mtp-eval-15.png)

8. <span data-ttu-id="105cb-145">Подключите корпоративный домен к клиенту Office 365.</span><span class="sxs-lookup"><span data-stu-id="105cb-145">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="105cb-146">[Необязательно] Choose **Connect a domain you already own** and type in your domain name.</span><span class="sxs-lookup"><span data-stu-id="105cb-146">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="105cb-147">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="105cb-147">Click **Next**.</span></span>

   ![Изображение of_Office 365 E5, где необходимо персонализировать вход и электронную почту](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="105cb-149">Добавьте запись TXT или MX, чтобы проверить владение доменом.</span><span class="sxs-lookup"><span data-stu-id="105cb-149">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="105cb-150">После того как вы добавите запись TXT или MX в свой домен, выберите **"Проверить".**</span><span class="sxs-lookup"><span data-stu-id="105cb-150">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![Изображение of_Office 365 E5, где необходимо добавить TXT записи MX для проверки домена](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="105cb-152">[Необязательно] Создайте дополнительные учетные записи пользователей для своего клиента.</span><span class="sxs-lookup"><span data-stu-id="105cb-152">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="105cb-153">Вы можете пропустить этот шаг, нажав кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="105cb-153">You can skip this step by clicking **Next**.</span></span>

    ![Страница of_Office 365 E5, на которой можно добавить дополнительных пользователей](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="105cb-155">[Необязательно] Скачайте приложения Office.</span><span class="sxs-lookup"><span data-stu-id="105cb-155">[Optional] Download Office apps.</span></span> <span data-ttu-id="105cb-156">Нажмите **кнопку** "Далее", чтобы пропустить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="105cb-156">Click **Next** to skip this step.</span></span> 

    ![Изображение of_Office 365 E5, на которой можно установить приложения Office](../../media/mtp-eval-19.png)

12. <span data-ttu-id="105cb-158">[Необязательно] Перенос сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="105cb-158">[Optional] Migrate email messages.</span></span> <span data-ttu-id="105cb-159">Опять же, этот шаг можно пропустить.</span><span class="sxs-lookup"><span data-stu-id="105cb-159">Again, you can skip this step.</span></span>

    ![Изображение of_Office 365 E5, где можно настроить перенос сообщений электронной почты](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="105cb-161">Выберите веб-службы.</span><span class="sxs-lookup"><span data-stu-id="105cb-161">Choose online services.</span></span> <span data-ttu-id="105cb-162">Выберите **Exchange** и нажмите **кнопку "Далее".**</span><span class="sxs-lookup"><span data-stu-id="105cb-162">Select **Exchange** and click **Next**.</span></span> 

    ![Изображение of_Office 365 E5, где можно выбрать веб-службы](../../media/mtp-eval-21.png)

14. <span data-ttu-id="105cb-164">Добавьте записи MX, CNAME и TXT в свой домен.</span><span class="sxs-lookup"><span data-stu-id="105cb-164">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="105cb-165">По завершению выберите **"Проверить".**</span><span class="sxs-lookup"><span data-stu-id="105cb-165">When completed, select **Verify**.</span></span>

    ![Изображение of_Office 365 E5 здесь можно добавить записи DNS](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="105cb-167">Поздравляем, вы завершили подготовка клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="105cb-167">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Страница of_Office завершения установки 365 E5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="105cb-169">Включить пробную подписку на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="105cb-169">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="105cb-170">При регистрации на пробной подписке вы можете использовать 25 пользовательских лицензий в течение месяца.</span><span class="sxs-lookup"><span data-stu-id="105cb-170">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="105cb-171">Дополнительные сведения см. в сведениях о подписке [На M365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) try или Buy.</span><span class="sxs-lookup"><span data-stu-id="105cb-171">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="105cb-172">В [Центре администрирования Microsoft 365](https://admin.microsoft.com/)щелкните **"Выставление счета",** а затем перейдите в **"Приобретение служб".**</span><span class="sxs-lookup"><span data-stu-id="105cb-172">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="105cb-173">Выберите **Microsoft 365 E5 и** нажмите кнопку **"Начать бесплатную пробную версия".**</span><span class="sxs-lookup"><span data-stu-id="105cb-173">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Изображение of_Microsoft 365 E5 : начальная бесплатная пробная страница](../../media/mtp-eval-24.png)

3. <span data-ttu-id="105cb-175">Выберите параметр проверки: с помощью текстового сообщения или звонка.</span><span class="sxs-lookup"><span data-stu-id="105cb-175">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="105cb-176">После того как вы решили, введите номер телефона, выберите **"Текст"** или **"Позвонить мне"** в зависимости от выбранного вами выбора.</span><span class="sxs-lookup"><span data-stu-id="105cb-176">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Изображение of_Microsoft 365 E5 Start free trial page asking for contact details to send code to prove you are not a robot](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="105cb-178">Введите код проверки и нажмите **кнопку "Начать бесплатную пробную проверку".**</span><span class="sxs-lookup"><span data-stu-id="105cb-178">Enter the verification code and click **Start your free trial**.</span></span>

   ![Изображение of_Microsoft 365 E5 Start free trial page where you can fill out verification code the system sent to prove you are not a robot](../../media/mtp-eval-26.png)

5. <span data-ttu-id="105cb-180">Нажмите **кнопку "Попробовать",** чтобы подтвердить пробную версия Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="105cb-180">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Изображение of_Microsoft 365 E5 Начать бесплатную пробную страницу, на которой следует нажать кнопку "Попробовать сейчас", чтобы начать](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="105cb-182">Перейдите к активным пользователям Центра администрирования **Microsoft 365.**  >    >  </span><span class="sxs-lookup"><span data-stu-id="105cb-182">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="105cb-183">Выберите свою учетную запись пользователя, **выберите**"Управление лицензиями на продукты" и замените лицензию с Office 365 E5 на **Microsoft 365 E5.**</span><span class="sxs-lookup"><span data-stu-id="105cb-183">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="105cb-184">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="105cb-184">Click **Save**.</span></span>

   ![Страница of_Microsoft Центра администрирования 365, на которой можно выбрать лицензию Microsoft 365 E5](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="105cb-186">Снова выберите учетную запись глобального администратора, а затем нажмите кнопку **"Управление иным пользователем".**</span><span class="sxs-lookup"><span data-stu-id="105cb-186">Select the global administrator account again then click **Manage username**.</span></span>

   ![Страница of_Microsoft Центра администрирования 365, на которой можно выбрать учетную запись, а затем управление иным пользователем](../../media/mtp-eval-29.png)

8. <span data-ttu-id="105cb-188">[Необязательно] Измените домен с *onmicrosoft.com* на собственный домен в зависимости от того, что вы выбрали на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="105cb-188">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="105cb-189">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="105cb-189">Click **Save changes**.</span></span>

   ![Страница of_Microsoft Центра администрирования 365, на которой можно изменить настройки домена](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="105cb-191">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="105cb-191">Next step</span></span>
|[<span data-ttu-id="105cb-192">Этап 3. Настройка & в &</span><span class="sxs-lookup"><span data-stu-id="105cb-192">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="105cb-193">Настройте каждый компонент Microsoft 365 Defender для пробной или пилотной среды Защитника Microsoft 365, а также подстройте конечные точки.</span><span class="sxs-lookup"><span data-stu-id="105cb-193">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
