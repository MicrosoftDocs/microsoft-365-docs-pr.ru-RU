---
title: Настройка пробной Microsoft 365 Defender или пилотной среды
description: Затем Microsoft 365 центр безопасности установите среду Microsoft 365 Defender пробной лаборатории
keywords: Microsoft 365 Defender пробной установки, Microsoft 365 Defender экспериментальной установки, попробуйте Microsoft 365 Defender, Microsoft 365 Defender лаборатории оценки
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6db3003aa6465df90a3d2e4af55b28ccccf44100
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454737"
---
# <a name="set-up-your-microsoft-365-defender-trial-in-a-lab-environment"></a><span data-ttu-id="091db-104">Настройка пробной Microsoft 365 Defender в лабораторных условиях</span><span class="sxs-lookup"><span data-stu-id="091db-104">Set up your Microsoft 365 Defender trial in a lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="091db-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="091db-105">**Applies to:**</span></span>
- <span data-ttu-id="091db-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="091db-106">Microsoft 365 Defender</span></span> 

<span data-ttu-id="091db-107">В этом разделе вы можете настроить специальную лабораторную среду.</span><span class="sxs-lookup"><span data-stu-id="091db-107">This topic guides you to set up a dedicated lab environment.</span></span> <span data-ttu-id="091db-108">Сведения о настройке пробной оценки см. в новом руководстве по оценке [и Microsoft 365 Defender.](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="091db-108">For information on setting up a trial in production, see the new [Evaluate and pilot Microsoft 365 Defender](eval-overview.md) guide.</span></span> 

## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="091db-109">Создание клиента Office 365 E5 пробного клиента</span><span class="sxs-lookup"><span data-stu-id="091db-109">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="091db-110">Если у вас уже есть Office 365 или Azure Active Directory подписка, можно пропустить этапы создания Office 365 E5 клиента.</span><span class="sxs-lookup"><span data-stu-id="091db-110">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="091db-111">Перейдите на [портал Office 365 E5 продукта и](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) выберите **бесплатную пробную версия**.</span><span class="sxs-lookup"><span data-stu-id="091db-111">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Страница of_Office 365 E5](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="091db-113">Завершите пробную регистрацию, введите свой адрес электронной почты (личный или корпоративный).</span><span class="sxs-lookup"><span data-stu-id="091db-113">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="091db-114">Нажмите **кнопку Настройка учетной записи**.</span><span class="sxs-lookup"><span data-stu-id="091db-114">Click **Set up account**.</span></span>

   ![Страница of_Office 365 E5 для пробной регистрации](../../media/mtp-eval-10.png)

3. <span data-ttu-id="091db-116">Заполните имя, фамилию, номер бизнес-телефона, имя компании, размер компании и страну или регион.</span><span class="sxs-lookup"><span data-stu-id="091db-116">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![Страница of_Office 365 E5 для установки пробной регистрации с запросом имен, телефонов и сведений о компании](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="091db-118">Страна или регион, который вы здесь застроили, определяет регион центра обработки данных, в Office 365 будет организован ваш центр обработки данных.</span><span class="sxs-lookup"><span data-stu-id="091db-118">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="091db-119">Выберите свое предпочтение проверки: через текстовое сообщение или вызов.</span><span class="sxs-lookup"><span data-stu-id="091db-119">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="091db-120">Нажмите **кнопку Отправить код проверки**.</span><span class="sxs-lookup"><span data-stu-id="091db-120">Click **Send Verification Code**.</span></span> 

   ![Страница of_Office 365 E5 для установки пробной регистрации с запросом на проверку](../../media/mtp-eval-12.png)

5. <span data-ttu-id="091db-122">Установите настраиваемую доменную фамилию для клиента, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="091db-122">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Страница of_Office 365 E5 пробной регистрации, на которой можно настроить настраиваемую доменную фамилию](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="091db-124">Настройка первого удостоверения, которое будет глобальным администратором для клиента.</span><span class="sxs-lookup"><span data-stu-id="091db-124">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="091db-125">Заполните **имя и** **пароль.**</span><span class="sxs-lookup"><span data-stu-id="091db-125">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="091db-126">Нажмите кнопку **Зарегистрироваться**.</span><span class="sxs-lookup"><span data-stu-id="091db-126">Click **Sign up**.</span></span>

   ![Страница of_Office 365 E5 для установки пробной регистрации, на которой можно установить свою бизнес-идентичность](../../media/mtp-eval-14.png)

7. <span data-ttu-id="091db-128">Нажмите **кнопку Перейти** к установке, чтобы завершить Office 365 E5 предварительного клиента.</span><span class="sxs-lookup"><span data-stu-id="091db-128">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Изображение страницы Office 365 E5 настройки пробной регистрации с запросом на кнопку Go Setup](../../media/mtp-eval-15.png)

8. <span data-ttu-id="091db-130">Подключение корпоративного домена Office 365 клиента.</span><span class="sxs-lookup"><span data-stu-id="091db-130">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="091db-131">[Необязательный] Выберите Подключение домен, который вы **уже владеете,** и введите в доменное имя.</span><span class="sxs-lookup"><span data-stu-id="091db-131">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="091db-132">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="091db-132">Click **Next**.</span></span>

   ![Страница of_Office 365 E5, на которой необходимо персонализировать вход и электронную почту](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="091db-134">Добавьте запись TXT или MX для проверки владения доменом.</span><span class="sxs-lookup"><span data-stu-id="091db-134">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="091db-135">После того как вы добавите запись TXT или MX в свой домен, выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="091db-135">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![Страница of_Office 365 E5, на которой необходимо добавить TXT записи MX для проверки домена](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="091db-137">[Необязательный] Создайте дополнительные учетные записи пользователей для клиента.</span><span class="sxs-lookup"><span data-stu-id="091db-137">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="091db-138">Этот шаг можно пропустить, нажав **кнопку Далее.**</span><span class="sxs-lookup"><span data-stu-id="091db-138">You can skip this step by clicking **Next**.</span></span>

    ![Страница of_Office 365 E5, на которой можно добавить больше пользователей](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="091db-140">[Необязательный] Скачайте Office приложения.</span><span class="sxs-lookup"><span data-stu-id="091db-140">[Optional] Download Office apps.</span></span> <span data-ttu-id="091db-141">Нажмите **кнопку Далее,** чтобы пропустить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="091db-141">Click **Next** to skip this step.</span></span> 

    ![Страница of_Office 365 E5, на которой можно установить Office приложения](../../media/mtp-eval-19.png)

12. <span data-ttu-id="091db-143">[Необязательный] Перенос сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="091db-143">[Optional] Migrate email messages.</span></span> <span data-ttu-id="091db-144">Опять же, вы можете пропустить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="091db-144">Again, you can skip this step.</span></span>

    ![Изображение of_Office 365 E5, где можно определить, следует ли перенести сообщения электронной почты или нет](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="091db-146">Выберите онлайн-службы.</span><span class="sxs-lookup"><span data-stu-id="091db-146">Choose online services.</span></span> <span data-ttu-id="091db-147">Выберите **Exchange** и нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="091db-147">Select **Exchange** and click **Next**.</span></span> 

    ![Изображение of_Office 365 E5, где вы можете выбрать онлайн-службы](../../media/mtp-eval-21.png)

14. <span data-ttu-id="091db-149">Добавьте записи MX, CNAME и TXT в домен.</span><span class="sxs-lookup"><span data-stu-id="091db-149">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="091db-150">После завершения выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="091db-150">When completed, select **Verify**.</span></span>

    ![Изображение of_Office 365 E5 здесь можно добавить записи DNS](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="091db-152">Поздравляем, вы завершили подготовка Office 365 клиента.</span><span class="sxs-lookup"><span data-stu-id="091db-152">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Страница of_Office 365 E5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="091db-154">Включить Microsoft 365 пробную подписку</span><span class="sxs-lookup"><span data-stu-id="091db-154">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="091db-155">Регистрация для пробной пробной записи дает вам 25 лицензий пользователей, которые можно использовать в течение месяца.</span><span class="sxs-lookup"><span data-stu-id="091db-155">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="091db-156">Дополнительные [сведения см. в материале Try or Buy an M365 subscription.](../../commerce/try-or-buy-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="091db-156">See [Try or Buy an M365 subscription](../../commerce/try-or-buy-microsoft-365.md) for details.</span></span>

1. <span data-ttu-id="091db-157">Из [Microsoft 365 Admin Центра](https://admin.microsoft.com/)щелкните **Биллинг** и перейдите к **службам покупки.**</span><span class="sxs-lookup"><span data-stu-id="091db-157">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="091db-158">Выберите **Microsoft 365 E5** и нажмите **кнопку Начните бесплатную пробную версия**.</span><span class="sxs-lookup"><span data-stu-id="091db-158">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Страница of_Microsoft 365 E5 Начните бесплатную пробную страницу](../../media/mtp-eval-24.png)

3. <span data-ttu-id="091db-160">Выберите свое предпочтение проверки: через текстовое сообщение или вызов.</span><span class="sxs-lookup"><span data-stu-id="091db-160">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="091db-161">После того как вы решили, введите номер телефона, выберите **текст меня** или **позвоните** мне в зависимости от выбора.</span><span class="sxs-lookup"><span data-stu-id="091db-161">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Страница of_Microsoft 365 E5 Start бесплатная пробная страница с запросом контактных данных для отправки кода, чтобы доказать, что вы не робот](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="091db-163">Введите код проверки и **нажмите кнопку Начните бесплатную пробную проверку.**</span><span class="sxs-lookup"><span data-stu-id="091db-163">Enter the verification code and click **Start your free trial**.</span></span>

   ![Страница of_Microsoft 365 E5 Start бесплатная пробная страница, на которой можно заполнить код проверки, отправленный системой, чтобы доказать, что вы не робот](../../media/mtp-eval-26.png)

5. <span data-ttu-id="091db-165">Нажмите **кнопку Попробуйте** сейчас, чтобы подтвердить Microsoft 365 E5 пробную попытку.</span><span class="sxs-lookup"><span data-stu-id="091db-165">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Изображение of_Microsoft 365 E5 Начало бесплатной пробной страницы, где вы должны часы кнопку Попробуйте сейчас, чтобы начать](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="091db-167">Перейдите в **центр Microsoft 365 Admin**  >    >  **активных пользователей**.</span><span class="sxs-lookup"><span data-stu-id="091db-167">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="091db-168">Выберите учетную запись пользователя, **выберите Управление лицензиями** на продукты, а затем обмен лицензией с Office 365 E5 на **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="091db-168">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="091db-169">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="091db-169">Click **Save**.</span></span>

   ![Страница of_Microsoft центра администрирования 365, на которой можно выбрать Microsoft 365 E5 лицензию](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="091db-171">Выберите глобальную учетную запись администратора и нажмите **кнопку Управление иным пользователем.**</span><span class="sxs-lookup"><span data-stu-id="091db-171">Select the global administrator account again then click **Manage username**.</span></span>

   ![Страница of_Microsoft центра администрирования 365, на которой можно выбрать учетную запись, а затем управлять иным иным пользователем](../../media/mtp-eval-29.png)

8. <span data-ttu-id="091db-173">[Необязательный] Измените домен с *onmicrosoft.com* на собственный домен в зависимости от того, что вы выбрали на предыдущих действиях.</span><span class="sxs-lookup"><span data-stu-id="091db-173">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="091db-174">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="091db-174">Click **Save changes**.</span></span>

   ![Страница of_Microsoft 365 Admin Center, на которой можно изменить предпочтения домена](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="091db-176">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="091db-176">Next step</span></span>
|[<span data-ttu-id="091db-177">Этап 3. Настройка & на борту</span><span class="sxs-lookup"><span data-stu-id="091db-177">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="091db-178">Настройте каждый столб Microsoft 365 Defender для Microsoft 365 Defender пробной лаборатории или пилотной среды и на борту конечных точек.</span><span class="sxs-lookup"><span data-stu-id="091db-178">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
