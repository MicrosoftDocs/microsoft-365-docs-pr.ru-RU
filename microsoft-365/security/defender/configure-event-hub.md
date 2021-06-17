---
title: Настройка центра событий
description: Узнайте, как настроить центр событий
keywords: концентратор событий, настройка, сведения
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.openlocfilehash: d28ad22721e22dfd0dc5962bd46bab2b45469781
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985664"
---
# <a name="configure-your-event-hub"></a><span data-ttu-id="25968-104">Настройка центра событий</span><span class="sxs-lookup"><span data-stu-id="25968-104">Configure your Event Hub</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="25968-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="25968-105">**Applies to:**</span></span>
- [<span data-ttu-id="25968-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="25968-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="25968-107">Узнайте, как настроить центр событий, чтобы он может гнать события из Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="25968-107">Learn how to configure your Event Hub so that it can ingest events from Microsoft 365 Defender.</span></span>


## <a name="setup-the-required-resource-provider-in-the-event-hub-subscription"></a><span data-ttu-id="25968-108">Настройка необходимого поставщика ресурсов в подписке Event Hub</span><span class="sxs-lookup"><span data-stu-id="25968-108">Setup the required Resource Provider in the Event Hub subscription</span></span>


1. <span data-ttu-id="25968-109">Войдите на [портал Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="25968-109">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
1. <span data-ttu-id="25968-110">Выберите **подписки \> { Выберите ***подписку,*** \>** в центре событий будет развернут } Поставщик ресурсов .</span><span class="sxs-lookup"><span data-stu-id="25968-110">Select **Subscriptions \> {***Select the subscription the event hub will be deployed to***} \> Resource providers**.</span></span>
1. <span data-ttu-id="25968-111">Убедитесь, что **поставщик microsoft.Аналитика** зарегистрирован.</span><span class="sxs-lookup"><span data-stu-id="25968-111">Verify that the **Microsoft.Insights** Provider is registered.</span></span> <span data-ttu-id="25968-112">В противном случае зарегистрируйте его.</span><span class="sxs-lookup"><span data-stu-id="25968-112">Otherwise, register it.</span></span>

![Изображение поставщиков ресурсов в Microsoft Azure](../../media/f893db7a7b1f7aa520e8b9257cc72562.png)

## <a name="setup-azure-active-directory-app-registration"></a><span data-ttu-id="25968-114">Настройка Azure Active Directory регистрации приложений</span><span class="sxs-lookup"><span data-stu-id="25968-114">Setup Azure Active Directory App Registration</span></span>


><span data-ttu-id="25968-115">! [ПРИМЕЧАНИЕ] Необходимо установить роль администратора или Azure Active Directory (AAD), чтобы разрешить не администраторам регистрировать приложения.</span><span class="sxs-lookup"><span data-stu-id="25968-115">![NOTE] You must have Administrator role or Azure Active Directory (AAD) must be set to allow non-Administrators to register apps.</span></span> <span data-ttu-id="25968-116">Кроме того, для назначения главной роли службы должна быть роль администратора доступа к пользователю или владельца.</span><span class="sxs-lookup"><span data-stu-id="25968-116">You must also have an Owner or User Access Administrator role to assign the service principal a role.</span></span>  
><span data-ttu-id="25968-117">Дополнительные сведения см. в статью Создание приложения Azure AD & на портале — платформа удостоверений Майкрософт [ \| Microsoft Docs.](/azure/active-directory/develop/howto-create-service-principal-portal)</span><span class="sxs-lookup"><span data-stu-id="25968-117">For more information, see [Create an Azure AD app & service principal in the portal - Microsoft identity platform \| Microsoft Docs](/azure/active-directory/develop/howto-create-service-principal-portal).</span></span>

1. <span data-ttu-id="25968-118">Создайте новую регистрацию (которая по своей сути создает главную службу) в Azure Active Directory **\> регистрации Приложения \> Новая регистрация.**</span><span class="sxs-lookup"><span data-stu-id="25968-118">Create a new registration (which inherently creates a service principal) in **Azure Active Directory \> App registrations \> New registration.**</span></span>

1. <span data-ttu-id="25968-119">Заполните форму только именем (URI перенаправления не требуется).</span><span class="sxs-lookup"><span data-stu-id="25968-119">Fill out the form with just the Name (no Redirect URI is required).</span></span>

    ![Изображение регистрации приложения](../../media/336bc84e6be23900c43232b4ef0c253c.png)

    ![Изображение сведений об обзоре](../../media/06ac04c4ff713c2065cec2ef2f99a294.png)

1. <span data-ttu-id="25968-122">Создайте секрет, щелкнув по **сертификатам & \> секреты Новый секрет клиента:**</span><span class="sxs-lookup"><span data-stu-id="25968-122">Create a secret by clicking on **Certificates & secrets \> New client secret**:</span></span>

    ![Изображение сертификатов и секретов](../../media/d2ef88d3d2310d2c60c294b569cdf02e.png)

>[!WARNING]
><span data-ttu-id="25968-124">Вы не сможете получить доступ к секрету **клиента снова, поэтому убедитесь, что сохранить его**.</span><span class="sxs-lookup"><span data-stu-id="25968-124">**You won't be able to access the client secret again so make sure to save it**.</span></span>

## <a name="setup-event-hub-namespace"></a><span data-ttu-id="25968-125">Пространство имен центра событий установки</span><span class="sxs-lookup"><span data-stu-id="25968-125">Setup Event Hub namespace</span></span>


1. <span data-ttu-id="25968-126">Создание пространства имен концентратора событий:</span><span class="sxs-lookup"><span data-stu-id="25968-126">Create an Event Hub Namespace:</span></span>

    <span data-ttu-id="25968-127">Перейдите к концентраторам событий **\> Добавить** и выбрать уровень цен, единиц пропускной способности и Авто-Надув (требует стандартного ценообразования и под функции), соответствующие нагрузке, которая ожидается.</span><span class="sxs-lookup"><span data-stu-id="25968-127">Go **to Event Hubs \> Add** and select the pricing tier, throughput units and Auto-Inflate (requires standard pricing and under features) appropriate for the load you are expecting.</span></span>  
    <span data-ttu-id="25968-128">Дополнительные сведения см. в [руберсе Pricing - Event Hubs \| Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="25968-128">For more information, see [Pricing - Event Hubs \| Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)</span></span>

    >[!NOTE]
    > <span data-ttu-id="25968-129">Можно использовать существующий концентратор событий, но пропускная способность и масштабирование задаваются на уровне пространства имен, поэтому рекомендуется разместить узел событий в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="25968-129">You can use an existing event hub, but the throughput and scaling are set at the namespace level so it is recommended to place an event hub in itsown namespace.</span></span>

   ![Изображение пространства имен event Hub](../../media/ebc4ca37c342ad1da75c4aee4018e51a.png)

1. <span data-ttu-id="25968-131">Вам также потребуется ИД ресурса этого пространства имен центра событий.</span><span class="sxs-lookup"><span data-stu-id="25968-131">You will also need the Resource ID of this Event Hub Namespace.</span></span> <span data-ttu-id="25968-132">Перейдите на страницу Свойства пространства имен Azure Event \> Hubs.</span><span class="sxs-lookup"><span data-stu-id="25968-132">Go to your Azure Event Hubs namespace page \> Properties.</span></span> <span data-ttu-id="25968-133">Скопируйте текст в разделе Resource ID и зафиксируйте его для использования в разделе Конфигурация M365 ниже.</span><span class="sxs-lookup"><span data-stu-id="25968-133">Copy the text under Resource ID and record it for use during the M365 Configuration section below.</span></span> 

    ![Изображение свойств](../../media/759498162a4e93cbf17c4130d704d164.png)

1. <span data-ttu-id="25968-135">После создания пространства имен центра событий необходимо добавить главу службы регистрации приложений в качестве ридера, приемник данных Azure Event Hubs и пользователя, который будет войти в Microsoft 365 Defender в качестве участника (это также можно сделать на уровне Resource Group или Подписка).</span><span class="sxs-lookup"><span data-stu-id="25968-135">Once the Event Hub Namespace is created you will need to add the App Registration Service Principal as Reader, Azure Event Hubs Data Receiver, and the user who will be logging into Microsoft 365 Defender as Contributor (this can also be done at Resource Group or Subscription level).</span></span>

    <span data-ttu-id="25968-136">Это делается в центре событий **Namespace \> Access Control (IAM) \> Add** and verify under **Role assignments:**</span><span class="sxs-lookup"><span data-stu-id="25968-136">This is done in **Event Hubs Namespace \> Access Control (IAM) \> Add** and verify under **Role assignments**:</span></span>

    ![Изображение управления доступом](../../media/9c9c29137b90d5858920202d87680d16.png)

## <a name="setup-event-hub"></a><span data-ttu-id="25968-138">Центр событий установки</span><span class="sxs-lookup"><span data-stu-id="25968-138">Setup Event Hub</span></span>


<span data-ttu-id="25968-139">**Вариант 1:**</span><span class="sxs-lookup"><span data-stu-id="25968-139">**Option 1:**</span></span>

<span data-ttu-id="25968-140">Вы можете создать центр событий в  пространстве имен, и все типы событий (таблицы), выбранные для экспорта, будут записаны в этом **центре** событий.</span><span class="sxs-lookup"><span data-stu-id="25968-140">You can create an Event Hub within your Namespace and **all** the Event Types (Tables) you select to export will be written into this **one** Event Hub.</span></span>

<span data-ttu-id="25968-141">**Вариант 2:**</span><span class="sxs-lookup"><span data-stu-id="25968-141">**Option 2:**</span></span>

<span data-ttu-id="25968-142">Вместо того чтобы экспортировать все типы событий (таблицы) в один центр событий, вы можете экспортировать каждую таблицу в другой центр событий в пространстве имен центра событий (по одному концентратору событий на тип событий).</span><span class="sxs-lookup"><span data-stu-id="25968-142">Instead of exporting all the Event Types (Tables) into one Event Hub, you can export each table into a different Event Hub inside your Event Hub Namespace (one Event Hub per Event Type).</span></span>  

<span data-ttu-id="25968-143">В этом варианте Microsoft 365 Defender для вас будут создаваться концентраторы событий.</span><span class="sxs-lookup"><span data-stu-id="25968-143">In this option, Microsoft 365 Defender will create Event Hubs for you.</span></span>  
>[!NOTE]
> <span data-ttu-id="25968-144">Если вы используете пространство имен центра  событий, которое не входит в кластер event Hub, вы сможете экспортировать до 10 типов событий (Таблицы) для экспорта в каждом экспортируемом Параметры, которое вы определяете, из-за ограничения Azure в 10 концентраторов событий в пространстве имен узлов событий.</span><span class="sxs-lookup"><span data-stu-id="25968-144">If you are using an Event Hub Namespace that is **not** part of an Event Hub Cluster, you will only be able to choose up to 10 Event Types (Tables) to export in each Export Settings you define, due to an Azure limitation of 10 Event Hubs per Event Hub Namespace.</span></span>

<span data-ttu-id="25968-145">Например:</span><span class="sxs-lookup"><span data-stu-id="25968-145">For example:</span></span>

![Image of example Event Hub](../../media/005c1f6c10c34420d387f594987f9ffe.png)

<span data-ttu-id="25968-147">Если вы выберете этот параметр, вы можете перейти к разделу [Configure Microsoft 365 Defender для отправки таблиц электронной](#configure-microsoft-365-defender-to-send-email-tables) почты.</span><span class="sxs-lookup"><span data-stu-id="25968-147">If you choose this option, you can skip to the [Configure Microsoft 365 Defender to send email tables](#configure-microsoft-365-defender-to-send-email-tables) section.</span></span>

<span data-ttu-id="25968-148">Создайте центр событий в пространстве имен, выбрав **концентраторы \> событий и концентратор событий.**</span><span class="sxs-lookup"><span data-stu-id="25968-148">Create an Event Hub within your Namespace by selecting **Event Hubs \> + Event Hub**.</span></span>

<span data-ttu-id="25968-149">Количество разделов позволяет увеличить пропускную способность с помощью параллелизма, поэтому рекомендуется увеличить это число в зависимости от ожидаемой нагрузки.</span><span class="sxs-lookup"><span data-stu-id="25968-149">The Partition Count allows for additional throughput via parallelism, so it is recommended to increase this number based on the load you are expecting.</span></span>  
<span data-ttu-id="25968-150">Рекомендуется использовать значения хранения и захвата сообщений по умолчанию 1 и off.</span><span class="sxs-lookup"><span data-stu-id="25968-150">Default Message Retention and Capture values of 1 and Off are recommended.</span></span>

![Изображение создания центра событий](../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png)

<span data-ttu-id="25968-152">Для этого центра событий (а не пространства имен) необходимо настроить политику общего доступа с помощью отправки, прослушивания утверждений.</span><span class="sxs-lookup"><span data-stu-id="25968-152">For this Event Hub (not namespace) you will need to configure a Shared Access Policy with Send, Listen Claims.</span></span> <span data-ttu-id="25968-153">Щелкните политики общего доступа к центру событий **\> + \> Добавить,** а затем дать ему имя политики (не используется в других местах) и проверить **Отправка** и **прослушивание**.</span><span class="sxs-lookup"><span data-stu-id="25968-153">Click on your **Event Hub \> Shared access policies \> + Add** and then give it a Policy name (not used elsewhere) and check **Send** and **Listen**.</span></span>

![Изображение политик общего доступа](../../media/1867d13f46dc6a0f4cdae6cf00df24db.png)

## <a name="configure-microsoft-365-defender-to-send-email-tables"></a><span data-ttu-id="25968-155">Настройка Microsoft 365 Defender для отправки таблиц электронной почты</span><span class="sxs-lookup"><span data-stu-id="25968-155">Configure Microsoft 365 Defender to send email tables</span></span>


### <a name="setup-microsoft-365-defender-send-email-tables-to-splunk-via-event-hub"></a><span data-ttu-id="25968-156">Настройка Microsoft 365 Defender таблицы электронной почты в Splunk через центр событий</span><span class="sxs-lookup"><span data-stu-id="25968-156">Setup Microsoft 365 Defender send Email tables to Splunk via Event Hub</span></span>


1. <span data-ttu-id="25968-157">Войти в Microsoft 365 Defender с <https://security.microsoft.com> учетной записью, которая соответствует всем следующим требованиям роли:</span><span class="sxs-lookup"><span data-stu-id="25968-157">Login to Microsoft 365 Defender at <https://security.microsoft.com> with an account that meets all the following role requirements:</span></span>

    - <span data-ttu-id="25968-158">Роль участника на уровне ресурсов пространства *имен центра* событий или выше для центра событий, в который будет экспортироваться.</span><span class="sxs-lookup"><span data-stu-id="25968-158">Contributor role at the Event Hub *Namespace* Resource level or higher for the Event Hub that you will be exporting to.</span></span> <span data-ttu-id="25968-159">Без этого вы получите ошибку экспорта при попытке сохранить параметры.</span><span class="sxs-lookup"><span data-stu-id="25968-159">Without this you will get an export error when you try to save the settings.</span></span>

    - <span data-ttu-id="25968-160">Роль глобального администратора или администратора безопасности в клиенте, связанной с Microsoft 365 Defender и Azure.</span><span class="sxs-lookup"><span data-stu-id="25968-160">Global Admin or Security Admin Role on the tenant tied to Microsoft 365 Defender and Azure.</span></span>

    ![Изображение портала безопасности](../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png)

1. <span data-ttu-id="25968-162">Нажмите **кнопку Экспорт необработанных \> данных +Add**.</span><span class="sxs-lookup"><span data-stu-id="25968-162">Click on **Raw Data Export \> +Add**.</span></span>

    <span data-ttu-id="25968-163">Теперь вы будете использовать данные, записанные выше.</span><span class="sxs-lookup"><span data-stu-id="25968-163">You will now use the data that your recorded above.</span></span>

    <span data-ttu-id="25968-164">**Имя.** Это локальное и должно быть все, что работает в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="25968-164">**Name**: This is local and should be whatever works in your environment.</span></span>

    <span data-ttu-id="25968-165">**Переадранить события в центр событий.** Выберите этот почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="25968-165">**Forward events to event hub**: Select this checkbox.</span></span>

    <span data-ttu-id="25968-166">**ИД ресурса Event-Hub.** Это ИД ресурса пространства имен event Hub, который был записан выше при настройке центра событий.</span><span class="sxs-lookup"><span data-stu-id="25968-166">**Event-Hub Resource ID**: This is the Event Hub Namespace Resource ID you  recorded above when you setup the Event Hub.</span></span>

    <span data-ttu-id="25968-167">**Имя Event-Hub.** Если вы создали центр событий в пространстве имен центра событий, вклейте имя Центра событий, записанное выше.</span><span class="sxs-lookup"><span data-stu-id="25968-167">**Event-Hub name**:  If you created an Event Hub inside your Event Hub Namespace, paste the Event Hub  name you recorded above.</span></span>

    <span data-ttu-id="25968-168">Если вы хотите Microsoft 365 Defender создать концентраторы событий для типов событий (Таблицы), оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="25968-168">If you choose to let Microsoft 365 Defender to create Event Hubs per Event Types  (Tables) for you, leave this field empty.</span></span>

    <span data-ttu-id="25968-169">**Типы событий.** Выберите таблицы advanced Hunting, которые необходимо переадружить в центр событий, а затем в настраиваемые приложения.</span><span class="sxs-lookup"><span data-stu-id="25968-169">**Event Types**: Select the Advanced Hunting tables that you want to forward to the Event Hub and then on to your custom app.</span></span> <span data-ttu-id="25968-170">Таблицы оповещений из Microsoft 365 Defender, таблицы Устройств — из Microsoft Defender для конечной точки (EDR), а таблицы электронной почты — из Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="25968-170">Alert tables are from Microsoft 365 Defender, Devices tables are from Microsoft Defender for Endpoint (EDR), and Email tables are from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="25968-171">События электронной почты записывают все транзакции электронной почты.</span><span class="sxs-lookup"><span data-stu-id="25968-171">Email Events records all Email Transactions.</span></span> <span data-ttu-id="25968-172">Url-адрес (SafeLinks), Вложения (Сейф вложения) и события после доставки (ZAP) также записываются и могут быть соединены с событиями электронной почты в поле NetworkMessageId.</span><span class="sxs-lookup"><span data-stu-id="25968-172">The URL (SafeLinks), Attachment (Safe Attachments) and Post Delivery Events (ZAP) are also recorded and can be joined to the Email Events on the NetworkMessageId field.</span></span>

    ![Изображение параметров API потоковой передачи](../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png)

1. <span data-ttu-id="25968-174">Убедитесь, что нажмите **кнопку Отправить**.</span><span class="sxs-lookup"><span data-stu-id="25968-174">Make sure to click **Submit**.</span></span>

### <a name="verify-that-the-events-are-being-exported-to-the-event-hub"></a><span data-ttu-id="25968-175">Убедитесь, что события экспортируются в центр событий</span><span class="sxs-lookup"><span data-stu-id="25968-175">Verify that the events are being exported to the Event Hub</span></span>


<span data-ttu-id="25968-176">Вы можете убедиться в том, что события отправляются в центр событий с помощью базового запроса advanced Hunting.</span><span class="sxs-lookup"><span data-stu-id="25968-176">You can verify that events are being sent to the Event Hub by running a basic Advanced Hunting query.</span></span> <span data-ttu-id="25968-177">Выберите **запрос \> "Охота расширенный \> запрос на охоту"** и введите следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="25968-177">Select **Hunting \> Advanced Hunting \> Query** and enter the following query:</span></span>

```
EmailEvents
|joinkind=fullouterEmailAttachmentInfoonNetworkMessageId
|joinkind=fullouterEmailUrlInfoonNetworkMessageId
|joinkind=fullouterEmailPostDeliveryEventsonNetworkMessageId
|whereTimestamp\>ago(1h)
|count
```

<span data-ttu-id="25968-178">Это покажет, сколько электронных писем было получено за последний час, соединив их во всех остальных таблицах.</span><span class="sxs-lookup"><span data-stu-id="25968-178">This will show you how many emails were received in the last hour joined across all the other tables.</span></span> <span data-ttu-id="25968-179">Он также покажет, видят ли вы события, которые можно экспортировать в центр событий.</span><span class="sxs-lookup"><span data-stu-id="25968-179">It will also show you if you are seeing events that could be exported to the event hub.</span></span> <span data-ttu-id="25968-180">Если в этом подсчете показано 0, то вы не увидите никаких данных, выехав в центр событий.</span><span class="sxs-lookup"><span data-stu-id="25968-180">If this count shows 0 then you won't see any data going out to the Event Hub.</span></span>

![Изображение продвинутой охоты](../../media/c305e57dc6f72fa9eb035943f244738e.png)

<span data-ttu-id="25968-182">После проверки экспорта данных можно просмотреть центр событий, чтобы убедиться, что сообщения входящие.</span><span class="sxs-lookup"><span data-stu-id="25968-182">Once you have verified there is data to export, you can view the Event Hub to verify that messages are incoming.</span></span> <span data-ttu-id="25968-183">Это может занять до одного часа.</span><span class="sxs-lookup"><span data-stu-id="25968-183">This can take up to one hour.</span></span> 
 
1. <span data-ttu-id="25968-184">В Azure перейдите в **концентраторы событий Нажмите кнопку Концентраторы событий пространства имен \> \> \> Щелкните центр событий.**</span><span class="sxs-lookup"><span data-stu-id="25968-184">In Azure, go to **Event Hubs \> Click on the Namespace \> Event Hubs \> Click on the Event Hub**.</span></span>  
1. <span data-ttu-id="25968-185">В **обзоре** прокрутите вниз и в графе Сообщения вы увидите входящие сообщения.</span><span class="sxs-lookup"><span data-stu-id="25968-185">Under **Overview**, scroll down and in the Messages graph you should see Incoming Messages.</span></span> <span data-ttu-id="25968-186">Если вы не видите никаких результатов, не будет сообщений для пользовательского приложения, чтобы гнать.</span><span class="sxs-lookup"><span data-stu-id="25968-186">If you don't see any results, then there will be no messages for your custom app to ingest.</span></span>

    ![Изображение вкладки обзор с сообщениями](../../media/e88060e315d76e74269a3fc866df047f.png)
