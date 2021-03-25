---
title: Настройка пробной лаборатории или пилотной среды Microsoft 365 Defender
description: Доступ к Центру безопасности Microsoft 365 затем настройка среды пробной лаборатории Защитника Microsoft 365
keywords: Установка пробной установки Microsoft Threat Protection, пилотная установка Microsoft Threat Protection, настройка лаборатории оценки Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 976f6a1ec010348e8a281c251064acdd7a26748b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074774"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="aae45-104">Настройка среды пробной лаборатории Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aae45-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="aae45-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="aae45-105">**Applies to:**</span></span>
- <span data-ttu-id="aae45-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aae45-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="aae45-107">Создание пробной лаборатории или пилотной среды Microsoft 365 Defender и ее развертывание — это трех этапный процесс:</span><span class="sxs-lookup"><span data-stu-id="aae45-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="aae45-108">[![Этап 1. Подготовка](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="aae45-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="aae45-109">Этап 1. Подготовка</span><span class="sxs-lookup"><span data-stu-id="aae45-109">Phase 1: Prepare</span></span>](prepare-m365d-eval.md) |![Этап 2. Настройка](../../media/phase-diagrams/setup.png)<br/><span data-ttu-id="aae45-111">Этап 2. Настройка</span><span class="sxs-lookup"><span data-stu-id="aae45-111">Phase 2: Set up</span></span> |<span data-ttu-id="aae45-112">[![Этап 3. На борту](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="aae45-112">[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)</span></span><br/>[<span data-ttu-id="aae45-113">Этап 3. На борту</span><span class="sxs-lookup"><span data-stu-id="aae45-113">Phase 3: Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="aae45-114">[![Назад к пилоту](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="aae45-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span></span><br/>[<span data-ttu-id="aae45-115">Вернуться к экспериментальной книге воспроизведения</span><span class="sxs-lookup"><span data-stu-id="aae45-115">Back to pilot playbook</span></span>](m365d-pilot.md) |
|--|--|--|--|
||<span data-ttu-id="aae45-116">*Вы здесь!*</span><span class="sxs-lookup"><span data-stu-id="aae45-116">*You are here!*</span></span>  | | |


<span data-ttu-id="aae45-117">Вы в настоящее время на этапе настройка.</span><span class="sxs-lookup"><span data-stu-id="aae45-117">You're currently in the set up phase.</span></span> <span data-ttu-id="aae45-118">Сначала необходимо получить доступ к Центру безопасности Microsoft 365, а затем настроить пробную лабораторию или пилотную среду.</span><span class="sxs-lookup"><span data-stu-id="aae45-118">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="aae45-119">Зарегистрируйся для подписки На Office 365 или Azure Active Directory, чтобы создать *клиент .onmicrosoft.com,* который можно использовать для регистрации на лицензию Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="aae45-119">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="aae45-120">Если у вас уже есть существующая подписка На Office 365 или Azure Active Directory, вы можете пропустить пробные или пилотные этапы создания клиента Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="aae45-120">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="aae45-121">На этом этапе вы будете руководствоваться:</span><span class="sxs-lookup"><span data-stu-id="aae45-121">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="aae45-122">Создание клиентского пробного клиента Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="aae45-122">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="aae45-123">Включить пробную подписку Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aae45-123">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="aae45-124">Создание клиентского пробного клиента Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="aae45-124">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="aae45-125">Если у вас уже есть существующая подписка На Office 365 или Azure Active Directory, можно пропустить этапы создания пробных клиентов Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="aae45-125">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="aae45-126">Перейдите на [портал продуктов Office 365 E5 и](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) выберите **бесплатную пробную версия**.</span><span class="sxs-lookup"><span data-stu-id="aae45-126">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Страница of_Office 365 E5](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="aae45-128">Завершите пробную регистрацию, введите свой адрес электронной почты (личный или корпоративный).</span><span class="sxs-lookup"><span data-stu-id="aae45-128">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="aae45-129">Нажмите **кнопку Настройка учетной записи**.</span><span class="sxs-lookup"><span data-stu-id="aae45-129">Click **Set up account**.</span></span>

   ![Страница of_Office 365 E5 для пробной регистрации](../../media/mtp-eval-10.png)

3. <span data-ttu-id="aae45-131">Заполните имя, фамилию, номер бизнес-телефона, имя компании, размер компании и страну или регион.</span><span class="sxs-lookup"><span data-stu-id="aae45-131">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![Страница of_Office 365 E5 для установки пробной регистрации с запросом имен, телефонов и сведений о компании](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="aae45-133">Страна или регион, который вы здесь застроили, определяет регион центра обработки данных, в который будет хозяйно работать Office 365.</span><span class="sxs-lookup"><span data-stu-id="aae45-133">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="aae45-134">Выберите свое предпочтение проверки: через текстовое сообщение или вызов.</span><span class="sxs-lookup"><span data-stu-id="aae45-134">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="aae45-135">Нажмите **кнопку Отправить код проверки**.</span><span class="sxs-lookup"><span data-stu-id="aae45-135">Click **Send Verification Code**.</span></span> 

   ![Страница of_Office 365 E5 для установки пробной регистрации с запросом на проверку](../../media/mtp-eval-12.png)

5. <span data-ttu-id="aae45-137">Установите настраиваемую доменную фамилию для клиента, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="aae45-137">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Страница of_Office 365 E5 пробной регистрации, на которой можно настроить настраиваемую доменную фамилию](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="aae45-139">Настройка первого удостоверения, которое будет глобальным администратором для клиента.</span><span class="sxs-lookup"><span data-stu-id="aae45-139">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="aae45-140">Заполните **имя и** **пароль.**</span><span class="sxs-lookup"><span data-stu-id="aae45-140">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="aae45-141">Нажмите кнопку **Зарегистрироваться**.</span><span class="sxs-lookup"><span data-stu-id="aae45-141">Click **Sign up**.</span></span>

   ![Страница of_Office 365 E5 для установки пробной регистрации, на которой можно установить свою бизнес-идентичность](../../media/mtp-eval-14.png)

7. <span data-ttu-id="aae45-143">Нажмите **кнопку Перейти к настройке,** чтобы завершить подготовка клиента для пробного клиента Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="aae45-143">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Изображение страницы установки пробной регистрации Office 365 E5 с запросом на кнопку Go Setup](../../media/mtp-eval-15.png)

8. <span data-ttu-id="aae45-145">Подключите корпоративный домен к клиенту Office 365.</span><span class="sxs-lookup"><span data-stu-id="aae45-145">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="aae45-146">[Необязательный] Выберите **Подключение домена, который вы уже имеете,** и введите в доменном имени.</span><span class="sxs-lookup"><span data-stu-id="aae45-146">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="aae45-147">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="aae45-147">Click **Next**.</span></span>

   ![Страница of_Office 365 E5, на которой необходимо персонализировать вход и электронную почту](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="aae45-149">Добавьте запись TXT или MX для проверки владения доменом.</span><span class="sxs-lookup"><span data-stu-id="aae45-149">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="aae45-150">После того как вы добавите запись TXT или MX в свой домен, выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="aae45-150">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![Страница of_Office 365 E5, на которой необходимо добавить TXT записи MX для проверки домена](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="aae45-152">[Необязательный] Создайте дополнительные учетные записи пользователей для клиента.</span><span class="sxs-lookup"><span data-stu-id="aae45-152">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="aae45-153">Этот шаг можно пропустить, нажав **кнопку Далее.**</span><span class="sxs-lookup"><span data-stu-id="aae45-153">You can skip this step by clicking **Next**.</span></span>

    ![Страница of_Office 365 E5, на которой можно добавить больше пользователей](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="aae45-155">[Необязательный] Скачайте приложения Office.</span><span class="sxs-lookup"><span data-stu-id="aae45-155">[Optional] Download Office apps.</span></span> <span data-ttu-id="aae45-156">Нажмите **кнопку Далее,** чтобы пропустить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="aae45-156">Click **Next** to skip this step.</span></span> 

    ![Страница of_Office 365 E5, на которой можно установить приложения Office](../../media/mtp-eval-19.png)

12. <span data-ttu-id="aae45-158">[Необязательный] Перенос сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="aae45-158">[Optional] Migrate email messages.</span></span> <span data-ttu-id="aae45-159">Опять же, вы можете пропустить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="aae45-159">Again, you can skip this step.</span></span>

    ![Изображение of_Office 365 E5, где можно определить, следует ли перенести сообщения электронной почты или нет](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="aae45-161">Выберите онлайн-службы.</span><span class="sxs-lookup"><span data-stu-id="aae45-161">Choose online services.</span></span> <span data-ttu-id="aae45-162">Выберите **Exchange** и нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="aae45-162">Select **Exchange** and click **Next**.</span></span> 

    ![Изображение of_Office 365 E5, где вы можете выбрать онлайн-службы](../../media/mtp-eval-21.png)

14. <span data-ttu-id="aae45-164">Добавьте записи MX, CNAME и TXT в домен.</span><span class="sxs-lookup"><span data-stu-id="aae45-164">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="aae45-165">После завершения выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="aae45-165">When completed, select **Verify**.</span></span>

    ![Изображение of_Office 365 E5 здесь можно добавить записи DNS](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="aae45-167">Поздравляем, вы завершили подготовка клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="aae45-167">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Страница of_Office 365 E5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="aae45-169">Включить пробную подписку Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aae45-169">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="aae45-170">Регистрация для пробной пробной записи дает вам 25 лицензий пользователей, которые можно использовать в течение месяца.</span><span class="sxs-lookup"><span data-stu-id="aae45-170">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="aae45-171">Дополнительные [сведения см. в материале Try or Buy an M365 subscription.](../../commerce/try-or-buy-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="aae45-171">See [Try or Buy an M365 subscription](../../commerce/try-or-buy-microsoft-365.md) for details.</span></span>

1. <span data-ttu-id="aae45-172">Из [Центра администрирования Microsoft 365](https://admin.microsoft.com/)щелкните **Биллинг** и перейдите к **службам покупки.**</span><span class="sxs-lookup"><span data-stu-id="aae45-172">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="aae45-173">Выберите **Microsoft 365 E5** и нажмите **кнопку Начните бесплатную пробную версия**.</span><span class="sxs-lookup"><span data-stu-id="aae45-173">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Страница of_Microsoft 365 E5 Начните бесплатную пробную страницу](../../media/mtp-eval-24.png)

3. <span data-ttu-id="aae45-175">Выберите свое предпочтение проверки: через текстовое сообщение или вызов.</span><span class="sxs-lookup"><span data-stu-id="aae45-175">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="aae45-176">После того как вы решили, введите номер телефона, выберите **текст меня** или **позвоните** мне в зависимости от выбора.</span><span class="sxs-lookup"><span data-stu-id="aae45-176">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Страница of_Microsoft 365 E5 Start бесплатная пробная страница с запросом контактных данных для отправки кода, чтобы доказать, что вы не робот](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="aae45-178">Введите код проверки и **нажмите кнопку Начните бесплатную пробную проверку.**</span><span class="sxs-lookup"><span data-stu-id="aae45-178">Enter the verification code and click **Start your free trial**.</span></span>

   ![Страница of_Microsoft 365 E5 Start бесплатная пробная страница, на которой можно заполнить код проверки, отправленный системой, чтобы доказать, что вы не робот](../../media/mtp-eval-26.png)

5. <span data-ttu-id="aae45-180">Нажмите **кнопку Попробуйте** сейчас подтвердить пробную запись Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="aae45-180">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Изображение of_Microsoft 365 E5 Начало бесплатной пробной страницы, где вы должны часы кнопку Попробуйте сейчас, чтобы начать](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="aae45-182">Перейдите к **активным пользователям Центра администрирования Microsoft 365.**  >    >  </span><span class="sxs-lookup"><span data-stu-id="aae45-182">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="aae45-183">Выберите учетную запись пользователя, **выберите управление** лицензиями на продукты, а затем смените лицензию с Office 365 E5 на **Microsoft 365 E5.**</span><span class="sxs-lookup"><span data-stu-id="aae45-183">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="aae45-184">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="aae45-184">Click **Save**.</span></span>

   ![Страница of_Microsoft центра администрирования 365, на которой можно выбрать лицензию Microsoft 365 E5](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="aae45-186">Выберите глобальную учетную запись администратора и нажмите **кнопку Управление иным пользователем.**</span><span class="sxs-lookup"><span data-stu-id="aae45-186">Select the global administrator account again then click **Manage username**.</span></span>

   ![Страница of_Microsoft центра администрирования 365, на которой можно выбрать учетную запись, а затем управлять иным иным пользователем](../../media/mtp-eval-29.png)

8. <span data-ttu-id="aae45-188">[Необязательный] Измените домен с *onmicrosoft.com* на собственный домен в зависимости от того, что вы выбрали на предыдущих действиях.</span><span class="sxs-lookup"><span data-stu-id="aae45-188">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="aae45-189">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="aae45-189">Click **Save changes**.</span></span>

   ![Страница of_Microsoft 365 Admin Center, на которой можно изменить предпочтения домена](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="aae45-191">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="aae45-191">Next step</span></span>
|[<span data-ttu-id="aae45-192">Этап 3. Настройка & на борту</span><span class="sxs-lookup"><span data-stu-id="aae45-192">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="aae45-193">Настройте каждый столб Microsoft 365 Defender для пробной лаборатории Или пилотной среды Защитника Microsoft 365 и на борту конечных точек.</span><span class="sxs-lookup"><span data-stu-id="aae45-193">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
