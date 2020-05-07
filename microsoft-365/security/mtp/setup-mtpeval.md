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
ms.openlocfilehash: 50557b0824999f0220af4d12b906b0274db4471e
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049619"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="d9e1f-104">Настройка пробной лабораторной среды Майкрософт для защиты от угроз</span><span class="sxs-lookup"><span data-stu-id="d9e1f-104">Set up your Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="d9e1f-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d9e1f-105">**Applies to:**</span></span>
- <span data-ttu-id="d9e1f-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="d9e1f-106">Microsoft Threat Protection</span></span> 


<span data-ttu-id="d9e1f-107">Создание пробной лабораторной среды Майкрософт для защиты от угроз и развертывание выполняется в три этапа:</span><span class="sxs-lookup"><span data-stu-id="d9e1f-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Подготовка лаборатории оценки Microsoft Threat protection" />
      <br/><span data-ttu-id="d9e1f-109">Этап 1: подготовка</a></span><span class="sxs-lookup"><span data-stu-id="d9e1f-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Настройка лаборатории оценки Microsoft Threat protection" />
      <br/><span data-ttu-id="d9e1f-111">Этап 2: Настройка</a></span><span class="sxs-lookup"><span data-stu-id="d9e1f-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints" title="
Настройте каждый из принципов защиты от угроз Майкрософт для лаборатории пробной среды Майкрософт по защите от угроз и конечных точек." />
      <br/><span data-ttu-id="d9e1f-113">Этап 3: Настройка встроенного &</a></span><span class="sxs-lookup"><span data-stu-id="d9e1f-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="d9e1f-114">В данный момент вы настраиваете этап настройки.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-114">You are currently in the set up phase.</span></span> <span data-ttu-id="d9e1f-115">Выполните начальные действия, чтобы получить доступ к центру безопасности Microsoft 365, а затем настройте свою лабораторную среду.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-115">Take the initial steps to access Microsoft 365 Security Center then setup your trial lab environment.</span></span>

<span data-ttu-id="d9e1f-116">Подпишитесь на Office 365 или Azure Active Directory, чтобы создать клиент *. onmicrosoft.com* , который вы можете использовать для подписки на лицензию Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-116">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="d9e1f-117">Если у вас уже есть подписка на Office 365 или Azure Active Directory, вы можете пропустить этапы создания пробных клиентов Office 365</span><span class="sxs-lookup"><span data-stu-id="d9e1f-117">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

<span data-ttu-id="d9e1f-118">На этом этапе вы найдете следующие руководства:</span><span class="sxs-lookup"><span data-stu-id="d9e1f-118">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="d9e1f-119">Создание пробного клиента Office 365</span><span class="sxs-lookup"><span data-stu-id="d9e1f-119">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="d9e1f-120">Включение пробной подписки на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d9e1f-120">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="d9e1f-121">Создание пробного клиента Office 365</span><span class="sxs-lookup"><span data-stu-id="d9e1f-121">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="d9e1f-122">Если у вас уже есть подписка на Office 365 или Azure Active Directory, вы можете пропустить этапы создания пробных клиентов Office 365</span><span class="sxs-lookup"><span data-stu-id="d9e1f-122">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="d9e1f-123">Перейдите на [портал продуктов Office 365](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) и выберите **бесплатную пробную версию**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-123">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>
<span data-ttu-id="d9e1f-124">![Of_page изображений](../../media/mtp-eval-9.png)</span><span class="sxs-lookup"><span data-stu-id="d9e1f-124">![Image of_page](../../media/mtp-eval-9.png)</span></span> <br>
  
2. <span data-ttu-id="d9e1f-125">Выполните пробную регистрацию, указав свой адрес электронной почты (персональный или корпоративный).</span><span class="sxs-lookup"><span data-stu-id="d9e1f-125">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="d9e1f-126">Нажмите кнопку **Настройка учетной записи**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-126">Click **Set up account**.</span></span>
<span data-ttu-id="d9e1f-127">![Of_page изображений](../../media/mtp-eval-10.png)</span><span class="sxs-lookup"><span data-stu-id="d9e1f-127">![Image of_page](../../media/mtp-eval-10.png)</span></span> <br> 

3. <span data-ttu-id="d9e1f-128">Введите имя, фамилию, номер рабочего телефона, название компании, размер и страну или регион.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-128">Fill in your first name, last name, business phone number, company name, company size and country or region.</span></span>  
<br>![Of_page изображений](../../media/mtp-eval-11.png) <br>
>[!NOTE]
><span data-ttu-id="d9e1f-130">Страна или регион, которые вы настроили, определяет регион центра обработки данных, в котором будет размещаться Office 365.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-130">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="d9e1f-131">Выберите предпочтения проверки: в текстовом сообщении или вызове.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-131">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="d9e1f-132">Нажмите кнопку **Отправить проверочный код**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-132">Click **Send Verification Code**.</span></span> 
<span data-ttu-id="d9e1f-133">![Of_page изображений](../../media/mtp-eval-12.png)</span><span class="sxs-lookup"><span data-stu-id="d9e1f-133">![Image of_page](../../media/mtp-eval-12.png)</span></span> <br>

5. <span data-ttu-id="d9e1f-134">Задайте имя пользовательского домена для клиента, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-134">Set the custom domain name for your tenant, then click **Next**.</span></span>
<br><span data-ttu-id="d9e1f-135">![Of_page изображений](../../media/mtp-eval-13.png)</span><span class="sxs-lookup"><span data-stu-id="d9e1f-135">![Image of_page](../../media/mtp-eval-13.png)</span></span> <br>
 
6. <span data-ttu-id="d9e1f-136">Настройте первое удостоверение, которое будет глобальным администратором клиента.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-136">Set up the first identity which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="d9e1f-137">Введите **имя** и **пароль**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-137">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="d9e1f-138">Нажмите кнопку **Зарегистрироваться**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-138">Click **Sign up**.</span></span>
<span data-ttu-id="d9e1f-139">![Of_page изображений](../../media/mtp-eval-14.png)</span><span class="sxs-lookup"><span data-stu-id="d9e1f-139">![Image of_page](../../media/mtp-eval-14.png)</span></span> <br>
<span data-ttu-id="d9e1f-140">c</span><span class="sxs-lookup"><span data-stu-id="d9e1f-140">c</span></span>
7. <span data-ttu-id="d9e1f-141">Нажмите кнопку **Перейти к программе установки** , чтобы завершить подготовку пробного клиента Office 365 в Office.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-141">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>
<br><span data-ttu-id="d9e1f-142">![Of_page изображений](../../media/mtp-eval-15.png)</span><span class="sxs-lookup"><span data-stu-id="d9e1f-142">![Image of_page](../../media/mtp-eval-15.png)</span></span> <br>

8. <span data-ttu-id="d9e1f-143">Подключите корпоративный домен к клиенту Office 365.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-143">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="d9e1f-144">Необязательно Выберите **подключить домен, который вы уже владеете** , и введите имя своего домена.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-144">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="d9e1f-145">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-145">Click **Next**.</span></span>
<br><span data-ttu-id="d9e1f-146">![Of_page изображений](../../media/mtp-eval-16.png)</span><span class="sxs-lookup"><span data-stu-id="d9e1f-146">![Image of_page](../../media/mtp-eval-16.png)</span></span> <br>
 
9. <span data-ttu-id="d9e1f-147">Чтобы проверить владение доменом, необходимо добавить запись TXT или MX.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-147">You will need to add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="d9e1f-148">Добавив запись TXT или MX в свой домен, нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-148">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>
<br><span data-ttu-id="d9e1f-149">![Of_page изображений](../../media/mtp-eval-17.png)</span><span class="sxs-lookup"><span data-stu-id="d9e1f-149">![Image of_page](../../media/mtp-eval-17.png)</span></span> <br>
 
10. <span data-ttu-id="d9e1f-150">Необязательно Создайте дополнительные учетные записи пользователей для клиента.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-150">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="d9e1f-151">Вы можете пропустить этот шаг, нажав кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-151">You can skip this step by clicking **Next**.</span></span>
<span data-ttu-id="d9e1f-152">![Of_page изображений](../../media/mtp-eval-18.png)</span><span class="sxs-lookup"><span data-stu-id="d9e1f-152">![Image of_page](../../media/mtp-eval-18.png)</span></span> <br>
 
11. <span data-ttu-id="d9e1f-153">Необязательно Скачайте приложения Office.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-153">[Optional] Download Office apps.</span></span> <span data-ttu-id="d9e1f-154">Нажмите кнопку **Далее** , чтобы пропустить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-154">Click **Next** to skip this step.</span></span> 
<br><span data-ttu-id="d9e1f-155">![Of_page изображений](../../media/mtp-eval-19.png)</span><span class="sxs-lookup"><span data-stu-id="d9e1f-155">![Image of_page](../../media/mtp-eval-19.png)</span></span> <br>

12. <span data-ttu-id="d9e1f-156">Необязательно Перенос сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-156">[Optional] Migrate email messages.</span></span> <span data-ttu-id="d9e1f-157">Опять же, вы можете пропустить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-157">Again, you can skip this step.</span></span>
<br><span data-ttu-id="d9e1f-158">![Of_page изображений](../../media/mtp-eval-20.png)</span><span class="sxs-lookup"><span data-stu-id="d9e1f-158">![Image of_page](../../media/mtp-eval-20.png)</span></span> <br>
 
13. <span data-ttu-id="d9e1f-159">Выберите веб-службы.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-159">Choose online services.</span></span> <span data-ttu-id="d9e1f-160">Выберите **Exchange** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-160">Select **Exchange** and click **Next**.</span></span> 
<br><span data-ttu-id="d9e1f-161">![Of_page изображений](../../media/mtp-eval-21.png)</span><span class="sxs-lookup"><span data-stu-id="d9e1f-161">![Image of_page](../../media/mtp-eval-21.png)</span></span> <br>

14. <span data-ttu-id="d9e1f-162">Добавьте записи MX, CNAME и TXT в свой домен.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-162">Add MX, CNAME and TXT records to your domain.</span></span> <span data-ttu-id="d9e1f-163">По завершении нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-163">When completed, select **Verify**.</span></span>
<br><span data-ttu-id="d9e1f-164">![Of_page изображений](../../media/mtp-eval-22.png)</span><span class="sxs-lookup"><span data-stu-id="d9e1f-164">![Image of_page](../../media/mtp-eval-22.png)</span></span> <br>
 
15. <span data-ttu-id="d9e1f-165">Поздравляем, вы завершили подготовку клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-165">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>
<br><span data-ttu-id="d9e1f-166">![Of_page изображений](../../media/mtp-eval-23.png)</span><span class="sxs-lookup"><span data-stu-id="d9e1f-166">![Image of_page](../../media/mtp-eval-23.png)</span></span> <br>

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="d9e1f-167">Включение пробной подписки на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d9e1f-167">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="d9e1f-168">При регистрации пробной версии вы получите 25 пользовательских лицензий, которые будут использоваться в течение месяца.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-168">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="d9e1f-169">Сведения о том, [как испытать или приобрести подписку на M365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) .</span><span class="sxs-lookup"><span data-stu-id="d9e1f-169">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="d9e1f-170">В [центре администрирования Microsoft 365](https://admin.microsoft.com/)щелкните **выставление счетов** , а затем перейдите к разделу **Услуги по приобретению**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-170">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="d9e1f-171">Выберите **Microsoft 365** и щелкните **начать бесплатную пробную версию**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-171">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 
<span data-ttu-id="d9e1f-172">![Of_page изображений](../../media/mtp-eval-24.png)</span><span class="sxs-lookup"><span data-stu-id="d9e1f-172">![Image of_page](../../media/mtp-eval-24.png)</span></span> <br>

3. <span data-ttu-id="d9e1f-173">Выберите предпочтения проверки: в текстовом сообщении или вызове.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-173">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="d9e1f-174">После того как вы решили, введите номер телефона, выберите пункт **текстовые** или **позвонить мне** в зависимости от выбранного варианта.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-174">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>
<span data-ttu-id="d9e1f-175">![Of_page изображений](../../media/mtp-eval-25.png)</span><span class="sxs-lookup"><span data-stu-id="d9e1f-175">![Image of_page](../../media/mtp-eval-25.png)</span></span> <br>
 
4. <span data-ttu-id="d9e1f-176">Введите код проверки и нажмите кнопку **начать бесплатную пробную версию**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-176">Enter the verification code and click **Start your free trial**.</span></span> 
<br><span data-ttu-id="d9e1f-177">![Of_page изображений](../../media/mtp-eval-26.png)</span><span class="sxs-lookup"><span data-stu-id="d9e1f-177">![Image of_page](../../media/mtp-eval-26.png)</span></span> <br>

5. <span data-ttu-id="d9e1f-178">Нажмите кнопку **проверить** , чтобы подтвердить пробную версию Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-178">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>
<br><span data-ttu-id="d9e1f-179">![Of_page изображений](../../media/mtp-eval-27.png)</span><span class="sxs-lookup"><span data-stu-id="d9e1f-179">![Image of_page](../../media/mtp-eval-27.png)</span></span> <br>
 
6. <span data-ttu-id="d9e1f-180">Перейдите в**Users** > раздел >  **центр администрирования Microsoft 365\*\*\*\*Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-180">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="d9e1f-181">Выберите свою учетную запись пользователя, выберите **Управление лицензиями на продукты**, затем замените лицензию из Office 365 в ~ на **Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-181">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="d9e1f-182">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-182">Click **Save**.</span></span>
<span data-ttu-id="d9e1f-183">![Of_page изображений](../../media/mtp-eval-28.png)</span><span class="sxs-lookup"><span data-stu-id="d9e1f-183">![Image of_page](../../media/mtp-eval-28.png)</span></span> <br>
 
7. <span data-ttu-id="d9e1f-184">Снова выберите учетную запись глобального администратора и нажмите кнопку **Управление именем пользователя**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-184">Select the global administrator account again then click **Manage username**.</span></span>
<br><span data-ttu-id="d9e1f-185">![Of_page изображений](../../media/mtp-eval-29.png)</span><span class="sxs-lookup"><span data-stu-id="d9e1f-185">![Image of_page](../../media/mtp-eval-29.png)</span></span> <br>

8. <span data-ttu-id="d9e1f-186">Необязательно Замените домен с *onmicrosoft.com* на свой домен в зависимости от того, что было выбрано на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-186">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="d9e1f-187">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-187">Click **Save changes**.</span></span>
<br><span data-ttu-id="d9e1f-188">![Of_page изображений](../../media/mtp-eval-30.png)</span><span class="sxs-lookup"><span data-stu-id="d9e1f-188">![Image of_page](../../media/mtp-eval-30.png)</span></span> <br>



## <a name="next-step"></a><span data-ttu-id="d9e1f-189">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="d9e1f-189">Next step</span></span>
<span data-ttu-id="d9e1f-190">||| |:-------|:-----| конфиг-онбоард. png)</span><span class="sxs-lookup"><span data-stu-id="d9e1f-190">||| |:-------|:-----|config-onboard.png)</span></span> <br><span data-ttu-id="d9e1f-191">[Этап 3: настройка & Onboard](config-mtpeval.md) | Настройте каждый из принципов защиты от угроз Майкрософт для испытательной лаборатории Microsoft Threat Protection и встроенных конечных точек.</span><span class="sxs-lookup"><span data-stu-id="d9e1f-191">[Phase 3: Configure & Onboard](config-mtpeval.md) | Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints.</span></span>
