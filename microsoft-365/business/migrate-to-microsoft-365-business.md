---
title: Перенос в Microsoft 365 бизнеса с Office 365 бизнеса расширенный
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Узнайте, как для перемещения бизнеса Microsoft 365 для бизнеса.
ms.openlocfilehash: fd6f18c02453e6751d6163ab79e726eae9c951a9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870916"
---
# <a name="migrate-to-microsoft-365-business-from-office-365-business-premium"></a><span data-ttu-id="a9778-103">Перенос в Microsoft 365 бизнеса с Office 365 бизнеса расширенный</span><span class="sxs-lookup"><span data-stu-id="a9778-103">Migrate to Microsoft 365 Business from Office 365 Business Premium</span></span>

<span data-ttu-id="a9778-104">Если у вас уже есть Office 365 для бизнеса подписки, например, Office 365 бизнеса расширенный, можно легко добавить лицензии Майкрософт 365 для бизнеса и назначить их для некоторых или всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="a9778-104">If you already have an Office 365 for business subscription, for example, Office 365 Business Premium, you can easily add licenses to Microsoft 365 Business, and assign them to some, or all users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a9778-105">Кнопка [планы переключатель](https://support.office.com/article/73318661-8f33-478b-bcc7-fb8d69dbb22a?.aspx#switchbutton) нельзя использовать для обновления до Microsoft 365 Business еще.</span><span class="sxs-lookup"><span data-stu-id="a9778-105">You can't use the [Switch plans](https://support.office.com/article/73318661-8f33-478b-bcc7-fb8d69dbb22a?.aspx#switchbutton) button to upgrade to Microsoft 365 Business yet.</span></span> 
  
## <a name="add-microsoft-365-business-licenses"></a><span data-ttu-id="a9778-106">Добавить лицензии Майкрософт 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a9778-106">Add Microsoft 365 Business licenses</span></span>

<span data-ttu-id="a9778-p101">У вас есть два способа для получения Microsoft 365 Business. Если у вас есть партнер, он или она можно приобрести 365 Microsoft Business для вас центра [партнера корпорации Майкрософт](get-microsoft-365-business.md). Ваш партнер также помогает перехода на Microsoft 365 для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a9778-p101">You have two ways to get Microsoft 365 Business. If you have a partner, he or she can purchase Microsoft 365 Business for you from [Microsoft Partner Center](get-microsoft-365-business.md). Your partner can also help you transition to Microsoft 365 Business.</span></span>
  
<span data-ttu-id="a9778-110">Если вы управляете свои собственные подписки, можно [Сотрудники отдела продаж](https://www.microsoft.com/microsoft-365/business) , чтобы приобрести лицензии Майкрософт 365 для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a9778-110">If you manage your own subscription, you can [contact sales](https://www.microsoft.com/microsoft-365/business) to purchase Microsoft 365 Business licenses.</span></span> 
  
<span data-ttu-id="a9778-111">В разделе [Добавление и изменение, или удаление партнера ядра СУБД подписки](https://support.office.com/article/f86e8177-936e-491e-9024-44dea2b296ff) , чтобы узнать, как можно начать работу с партнером.</span><span class="sxs-lookup"><span data-stu-id="a9778-111">See [Add, change, or delete a subscription advisor partner](https://support.office.com/article/f86e8177-936e-491e-9024-44dea2b296ff) to find out how you can start working with a partner.</span></span> 
  
<span data-ttu-id="a9778-p102">Если пользователь получает ссылку на покупки вашей лицензии, будет Познакомьтесь с помощью мастера приведенной ниже. Выберите **Да, добавить его к учетной записи**. Вы можете также выбрать количество лицензий и способ оплаты.</span><span class="sxs-lookup"><span data-stu-id="a9778-p102">If you are given a link to purchase your licences, you will walk through a wizard like the one below. Choose **Yes, add it to my account**. You can also pick the number of licences and the method of payment.</span></span>
  
![На 365 Microsoft Business прямое приобрести ссылок выберите пункт Добавить учетную запись текущей или Зарегистрируйтесь для новой учетной записи.](media/8bc54fd1-9cab-44d5-af91-c471e89aea46.png)
  
## <a name="assign-microsoft-365-licenses"></a><span data-ttu-id="a9778-116">Назначение лицензий Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a9778-116">Assign Microsoft 365 licenses</span></span>

1. <span data-ttu-id="a9778-117">Как только вы приобрели новых лицензий и в первый раз, как, заголовка программы установки для Microsoft 365 Business будет отображаться вверху центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="a9778-117">Once you have purchased new licenses, and this is the first time you did, the setup banner for Microsoft 365 Business will display on top of the admin center.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a9778-p103">Баннер установки — это возможность добавления новых пользователей, новый домен и перенос электронной почты для новых пользователей. Если вы не планируете выполните какие-либо, по-прежнему следует мастер и выберите параметры по умолчанию, чтобы сделать его исчезают на домашней странице администрирования.</span><span class="sxs-lookup"><span data-stu-id="a9778-p103">The setup banner is an opportunity to add new users, a new domain, and migrate email for new users. If you don't plan to do any, you should still go through the wizard and choose default options to make it disappear from the admin home page.</span></span> 
  
   ![Выберите пункт запустите установку на Microsoft 365 Business готова для настройки заголовка.](media/8d3b0d97-7cca-497f-9364-4b00ad670209.png)
  
    <span data-ttu-id="a9778-121">Выберите **Запустить настройку**.</span><span class="sxs-lookup"><span data-stu-id="a9778-121">Choose **Start setup**.</span></span>
    
2. <span data-ttu-id="a9778-122">На странице **Настройка входе и адрес электронной почты** можно добавить домен, выбрав **Подключить домена, которые вы уже владеете** , если вы хотите использовать эту возможность для добавления другой домен к своей подписке.</span><span class="sxs-lookup"><span data-stu-id="a9778-122">On the **Personalize your sign-in and email** page, you can add a domain by choosing **Connect a domain you already own** if you want to use this opportunity to add another domain to your subscription.</span></span> 
    
    <span data-ttu-id="a9778-p104">Если домен уже настроен, второе поле будет указать, что и будет сказать **продолжить использование** \< _доменное имя_ \> **для электронной почты и выход из системы**. Если вы не установили домен с вы подписки, появится сообщение **с помощью продолжить** \< _вашей компании name.onmicrosoft.com_ \> **для электронной почты и выход из системы**.    </span><span class="sxs-lookup"><span data-stu-id="a9778-p104">If you have already set up a domain, the second field will indicate that and will say **Continue using** \<  _your domain name_\> **for email and signing in**. If you haven't set up a domain with you subscription, it will say **Continue using** \<  _your company name.onmicrosoft.com_\> **for email and signing in**.</span></span>
    
    <span data-ttu-id="a9778-125">Нажмите кнопку **Next** (Далее).</span><span class="sxs-lookup"><span data-stu-id="a9778-125">Choose **Next**.</span></span>
    
    ![На странице Настройка входе и электронной почты нажмите кнопку Добавить домен, или используйте то, что вы используете.](media/c3f5cfb2-1189-4d2f-803b-c9feb008a7a3.png)
  
3. <span data-ttu-id="a9778-127">На странице **Добавить новых пользователей** можно добавить новых пользователей при наличии новых сотрудников, которые необходимо назначить лицензии Майкрософт 365 для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a9778-127">On the **Add new users** page, you can add new users, if you have new employees that you want to assign the Microsoft 365 Business licenses to.</span></span> 
    
    <span data-ttu-id="a9778-128">Если у вас нет новых сотрудников для добавления и требуется назначить число лицензий на по для существующих пользователей, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a9778-128">If you don't have new employees to add and want to assign licences to existing users, choose **Next**.</span></span>
    
4. <span data-ttu-id="a9778-p105">На \*\* сообщений электронной почты Migrate \*\* страницы, вы можете выполнить миграцию электронной почты для каких-либо новых пользователей, добавленные в шаге 3. Также можно пропустить этот шаг. Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a9778-p105">On the \*\* Migrate email messages \*\* page you can choose to migrate email for any of the new users you added in step 3. You can skip this step also. Choose **Next**.</span></span>
    
5. <span data-ttu-id="a9778-132">На последней странице нажмите кнопку **Перейти в центр администрирования**и ли продолжить установку.</span><span class="sxs-lookup"><span data-stu-id="a9778-132">On the last page, choose **go to the admin center**, and continue setup there.</span></span>
    
6. <span data-ttu-id="a9778-133">В центре администрирования перейдите на **пользователей** \> **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="a9778-133">In the admin center, go to **Users** \> **Active users**.</span></span>
    
7. <span data-ttu-id="a9778-134">Выберите пользователя, которому требуется назначить **Microsoft 365 Business** лицензии для и выберите команду **Изменить** рядом с пунктом **Лицензий на продукт**.</span><span class="sxs-lookup"><span data-stu-id="a9778-134">Select the user to whom you want to assign the **Microsoft 365 Business** license to, and then choose **Edit** next to **Product Licenses**.</span></span>
    
    ![В карточке пользователя нажмите кнопку Изменить рядом с пунктом лицензий на продукт.](media/be0fe2d8-7ff8-447c-88f6-d212ed78451c.png)
  
8. <span data-ttu-id="a9778-136">В **лицензий на продукт** слайдов **Microsoft 365 Business** для **на** \> **Сохранить**, а затем **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="a9778-136">In **Product licenses** slide **Microsoft 365 Business** to **On** \> **Save**, and then **Close**.</span></span>
    
<span data-ttu-id="a9778-p106">После покупки исходной лицензии для Microsoft 365 Business можно также добавить дополнительные в **выставления счетов** \> **приобретение служб**. На странице **служб на покупку** можно щелкнуть многоточие на **Microsoft 365 визитной** карточки и нажмите кнопку **изменить количество лицензий** на покупку более.</span><span class="sxs-lookup"><span data-stu-id="a9778-p106">Once you have purchased the initial license for Microsoft 365 Business, you can now also add more in **Billing** \> **Purchase services**. On the **Purchase services** page you can click on the ellipses on the **Microsoft 365 Business** card, and choose **Change license quantity** to purchase more.</span></span> 
  
## <a name="protect-user-devices-and-files"></a><span data-ttu-id="a9778-139">Защитить пользователей устройств и файлов</span><span class="sxs-lookup"><span data-stu-id="a9778-139">Protect user devices and files</span></span>

<span data-ttu-id="a9778-140">После назначения лицензий Microsoft 365 Business вы можете запустить защита устройств и файлы пользователей.</span><span class="sxs-lookup"><span data-stu-id="a9778-140">After you have assigned licenses to Microsoft 365 Business, you can start protecting the users' devices and files.</span></span>
  
1. <span data-ttu-id="a9778-141">В центре администрирования в левая навигационная панель, перейдите к **устройствам** \> **политик**.</span><span class="sxs-lookup"><span data-stu-id="a9778-141">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="a9778-142">На странице **политики устройств** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="a9778-142">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="a9778-143">В области **Добавить политику** имя политики и затем выберите **тип политики** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="a9778-143">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
    <span data-ttu-id="a9778-p107">Можно настроить политики приложений для защиты файлов на Android и iPhone устройств, а также Windows 10, а можно настроить политики конфигурации устройств для компании, владельцем которого устройств Windows 10. Следующие ссылки для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="a9778-p107">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices. See the following links for details:</span></span>
    
  - [<span data-ttu-id="a9778-146">Настройка параметров защиты приложений для устройств с Android и iOS</span><span class="sxs-lookup"><span data-stu-id="a9778-146">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="a9778-147">Настройка параметров защиты приложений для устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="a9778-147">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="a9778-148">Настройка параметров защиты устройств для компьютеров с Windows 10</span><span class="sxs-lookup"><span data-stu-id="a9778-148">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
    
   ![На левой панели добавить политику введите его имя и выберите тип политики в раскрывающемся меню.](media/76ef37e4-1d18-4f34-8a0f-391ab1d0ae2b.png)
  
4. <span data-ttu-id="a9778-150">После настройки политик вас и ваших сотрудников можно настроить устройств:</span><span class="sxs-lookup"><span data-stu-id="a9778-150">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="a9778-151">Если Windows не являются специалистов создателя Windows update, необходимо [Обновить их для специалистов создателей центра обновления Windows](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="a9778-151">If your Windows aren't already on Windows Pro Creator update, you will need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
    
  - <span data-ttu-id="a9778-152">В разделе [Настройка устройства Windows для пользователей Microsoft 365 Business](set-up-windows-devices.md) действия для устройств Windows.</span><span class="sxs-lookup"><span data-stu-id="a9778-152">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="a9778-153">В разделе [Настройка мобильных устройств для пользователей Microsoft 365 Business](set-up-mobile-devices.md) действия для телефонов Android и iPhones.</span><span class="sxs-lookup"><span data-stu-id="a9778-153">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
    
5. <span data-ttu-id="a9778-154">Чтобы автоматически установить клиентские приложения Office, видеть [подготовить для развертывания клиентов Office с Microsoft 365 для бизнеса](prepare-for-office-client-deployment.md) и [автоматически установить или удалить Microsoft Office на устройствах Windows 10](auto-install-or-uninstall-office.md).</span><span class="sxs-lookup"><span data-stu-id="a9778-154">To automatically install Office client apps, see [Prepare for Office client deployment by Microsoft 365 Business](prepare-for-office-client-deployment.md) and [Automatically install or uninstall Office on Windows 10 devices](auto-install-or-uninstall-office.md).</span></span>
    


