---
title: Трассировка сообщений в Центре безопасности и соответствия требованиям
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут использовать трассировка сообщений в Центре & безопасности, чтобы узнать, что произошло с сообщениями.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 78a7a2bda41f721b9e2084615b9eca1e70cf1f35
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071318"
---
# <a name="message-trace-in-the-security--compliance-center"></a><span data-ttu-id="f58be-103">Трассировка сообщений в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="f58be-103">Message trace in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f58be-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="f58be-104">**Applies to**</span></span>
- [<span data-ttu-id="f58be-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f58be-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f58be-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="f58be-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f58be-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f58be-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

## <a name="message-trace-features"></a><span data-ttu-id="f58be-108">Функции трассировки сообщений</span><span class="sxs-lookup"><span data-stu-id="f58be-108">Message trace features</span></span>

<span data-ttu-id="f58be-109">Трассировка сообщений в Центре & безопасности следует за сообщениями электронной почты во время их перемещения через организацию Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f58be-109">Message trace in the Security & Compliance Center follows email messages as they travel through your Exchange Online organization.</span></span> <span data-ttu-id="f58be-110">Вы можете определить, было ли сообщение получено, отклонено, отложено или доставлено службой.</span><span class="sxs-lookup"><span data-stu-id="f58be-110">You can determine if a message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="f58be-111">В нем также показано, какие действия были приняты в сообщении до его окончательного состояния.</span><span class="sxs-lookup"><span data-stu-id="f58be-111">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="f58be-112">Трассировка сообщений в центре & безопасности улучшает исходный след сообщений, доступный в центре администрирования Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="f58be-112">Message trace in the Security & Compliance Center improves upon the original message trace that was available in the Exchange admin center (EAC).</span></span> <span data-ttu-id="f58be-113">Вы можете использовать сведения из трассировки сообщений, чтобы эффективно отвечать на вопросы пользователей о том, что произошло с сообщениями, устранять проблемы с потоком почты и проверять изменения политики.</span><span class="sxs-lookup"><span data-stu-id="f58be-113">You can use the information from message trace to efficiently answer user questions about what happened to messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="f58be-114">Для выполнения трассировки сообщений необходимо быть членом групп ролей "Управление организацией", "Управление соответствием требованиям" или "Службы поддержки".</span><span class="sxs-lookup"><span data-stu-id="f58be-114">To do a message trace, you need to be a member of the Organization Management, Compliance Management or Help Desk role groups.</span></span> <span data-ttu-id="f58be-115">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f58be-115">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
>
> - <span data-ttu-id="f58be-116">Максимальное количество сообщений, отображаемых в результатах, зависит от выбранного типа отчета (подробнее см. раздел [Выберите](#choose-report-type) тип отчета).</span><span class="sxs-lookup"><span data-stu-id="f58be-116">The maximum number of messages that are displayed in the results depends on the report type you selected (see the [Choose report type](#choose-report-type) section for details).</span></span> <span data-ttu-id="f58be-117">Комлет [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) в Exchange Online PowerShell или автономный EOP PowerShell возвращает все сообщения в результатах.</span><span class="sxs-lookup"><span data-stu-id="f58be-117">The [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) cmdlet in Exchange Online PowerShell or standalone EOP PowerShell returns all messages in the results.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="f58be-118">Трассировка открытого сообщения</span><span class="sxs-lookup"><span data-stu-id="f58be-118">Open message trace</span></span>

1. <span data-ttu-id="f58be-119">Откройте центр & безопасности в <https://protection.office.com> .</span><span class="sxs-lookup"><span data-stu-id="f58be-119">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="f58be-120">**Разорите поток** почты и выберите **трассировку сообщения.**</span><span class="sxs-lookup"><span data-stu-id="f58be-120">Expand **Mail flow**, and then select **Message trace**.</span></span>

## <a name="message-trace-page"></a><span data-ttu-id="f58be-121">Страница трассировки сообщений</span><span class="sxs-lookup"><span data-stu-id="f58be-121">Message trace page</span></span>

<span data-ttu-id="f58be-122">Отсюда можно запустить новый след по умолчанию, нажав кнопку **Начните трассировку.**</span><span class="sxs-lookup"><span data-stu-id="f58be-122">From here you can start a new default trace by clicking on the **Start a trace** button.</span></span> <span data-ttu-id="f58be-123">В течение последних двух дней будут искаться все сообщения для всех отправителей и получателей.</span><span class="sxs-lookup"><span data-stu-id="f58be-123">This will search for all messages for all senders and recipients for the last two days.</span></span> <span data-ttu-id="f58be-124">Или вы можете использовать один из сохраненных запросов из доступных категорий запросов и запускать их как есть, либо использовать их в качестве отправных точек для собственных запросов:</span><span class="sxs-lookup"><span data-stu-id="f58be-124">Or you can use one of the stored queries from the available query categories and either run them as-is or use them as starting points for your own queries:</span></span>

- <span data-ttu-id="f58be-125">**Запросы по** умолчанию: встроенные запросы, предоставляемые Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f58be-125">**Default queries**: Built-in queries provided by Microsoft 365.</span></span>

- <span data-ttu-id="f58be-126">**Настраиваемые запросы.** Запросы, сохраненные администраторами в организации для дальнейшего использования.</span><span class="sxs-lookup"><span data-stu-id="f58be-126">**Custom queries**: Queries saved by admins in your organization for future use.</span></span>

- <span data-ttu-id="f58be-127">**Автоматические запросы.** Последние десять последних запросов, которые запускаются в последнее время.</span><span class="sxs-lookup"><span data-stu-id="f58be-127">**Autosaved queries**: The last ten most recently run queries.</span></span> <span data-ttu-id="f58be-128">Этот список упрощает выбор места, где вы были отключены.</span><span class="sxs-lookup"><span data-stu-id="f58be-128">This list makes it simple to pick up where you left off.</span></span>

<span data-ttu-id="f58be-129">Кроме того, на этой странице находится раздел **Загружаемые** отчеты для отправленных запросов, а также сами отчеты, когда они доступны для скачивания.</span><span class="sxs-lookup"><span data-stu-id="f58be-129">Also on this page is a **Downloadable reports** section for the requests you've submitted, as well as the reports themselves when they're are available for download.</span></span>

## <a name="options-for-a-new-message-trace"></a><span data-ttu-id="f58be-130">Параметры для нового трассировки сообщений</span><span class="sxs-lookup"><span data-stu-id="f58be-130">Options for a new message trace</span></span>

### <a name="filter-by-senders-and-recipients"></a><span data-ttu-id="f58be-131">Фильтрация отправителей и получателей</span><span class="sxs-lookup"><span data-stu-id="f58be-131">Filter by senders and recipients</span></span>

<span data-ttu-id="f58be-132">Значения по умолчанию — **это все** отправители и все получатели, но для фильтрации результатов можно использовать следующие поля: </span><span class="sxs-lookup"><span data-stu-id="f58be-132">The default values are **All senders** and **All recipients**, but you can use the following fields to filter the results:</span></span>

- <span data-ttu-id="f58be-133">**Эти люди:** Щелкните в этом поле, чтобы выбрать одного или несколько отправителей из вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f58be-133">**By these people**: Click in this field to select one or more senders from your organization.</span></span> <span data-ttu-id="f58be-134">Вы также можете начать введите имя, и элементы в списке будут фильтроваться тем, что вы ввели, как и поведение страницы поиска.</span><span class="sxs-lookup"><span data-stu-id="f58be-134">You can also start to type a name and the items in the list will be filtered by what you've typed, much like how a search page behaves.</span></span>

- <span data-ttu-id="f58be-135">**Для этих людей:** Щелкните в этом поле, чтобы выбрать одного или несколько получателей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f58be-135">**To these people**: Click in this field to select one or more recipients in your organization.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="f58be-136">Вы также можете ввести адреса электронной почты внешних отправителей и получателей.</span><span class="sxs-lookup"><span data-stu-id="f58be-136">You can also type the email addresses of external senders and recipients.</span></span> <span data-ttu-id="f58be-137">Поддиальды поддерживаются (например, ), но одновременно нельзя использовать несколько записей под диктовки в одном `*@contoso.com` поле.</span><span class="sxs-lookup"><span data-stu-id="f58be-137">Wildcards are supported (for example, `*@contoso.com`), but you can't use multiple wildcard entries in the same field at the same time.</span></span>
>
> - <span data-ttu-id="f58be-138">Можно вклеить несколько списков отправителей или получателей, разделенных полуколонами ( `;` ).</span><span class="sxs-lookup"><span data-stu-id="f58be-138">You can paste multiple senders or recipients lists separated by semicolons (`;`).</span></span> <span data-ttu-id="f58be-139">пробелы ( `\s` ), возвращается карета `\r` () или следующие строки ( `\n` ).</span><span class="sxs-lookup"><span data-stu-id="f58be-139">spaces (`\s`), carriage returns (`\r`), or next lines (`\n`).</span></span>

### <a name="time-range"></a><span data-ttu-id="f58be-140">Диапазон времени</span><span class="sxs-lookup"><span data-stu-id="f58be-140">Time range</span></span>

<span data-ttu-id="f58be-141">Значение по умолчанию **— 2 дня,** но можно указать диапазоны даты и времени до 90 дней.</span><span class="sxs-lookup"><span data-stu-id="f58be-141">The default value is **2 days**, but you can specify date/time ranges of up to 90 days.</span></span> <span data-ttu-id="f58be-142">При использовании диапазонов дат и времени следует учитывать эти проблемы:</span><span class="sxs-lookup"><span data-stu-id="f58be-142">When you use date/time ranges, consider these issues:</span></span>

- <span data-ttu-id="f58be-143">По умолчанию вы выбираете диапазон времени в представлении **Slider** с помощью строки времени.</span><span class="sxs-lookup"><span data-stu-id="f58be-143">By default, you select the time range in **Slider** view using a time line.</span></span> <span data-ttu-id="f58be-144">Вы можете выбрать только отображаемые параметры дня или времени.</span><span class="sxs-lookup"><span data-stu-id="f58be-144">You can only select the day or time settings that are displayed.</span></span> <span data-ttu-id="f58be-145">При попытке выбрать между значениями щелкнуть пузырек запуска и конца до ближайшего отображаемого параметра.</span><span class="sxs-lookup"><span data-stu-id="f58be-145">Trying to select an in-between value will snap the start/end bubble to the nearest displayed setting.</span></span>

  ![Диапазон времени слайдера в новом следе сообщений в Центре & соответствия требованиям](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  <span data-ttu-id="f58be-147">Кроме того, можно  перейти на настраиваемый  вид,  в котором можно указать значения даты  начала и окончания (включая время), а также выбрать часовой пояс для диапазона даты и времени.</span><span class="sxs-lookup"><span data-stu-id="f58be-147">But, you can also switch to **Custom** view where you can specify the **Start date** and **End date** values (including times), and you can also select the **Time zone** for the date/time range.</span></span> <span data-ttu-id="f58be-148">Обратите внимание, что параметр **Часовой** зоны применяется как к входным данным запроса, так и к результатам запроса.</span><span class="sxs-lookup"><span data-stu-id="f58be-148">Note that the **Time zone** setting applies to both your query inputs and your query results.</span></span>

  ![Настраиваемый диапазон времени в новом следе сообщений в Центре & соответствия требованиям](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  <span data-ttu-id="f58be-150">В течение 10 дней или менее результаты можно получить мгновенно в **сводке.**</span><span class="sxs-lookup"><span data-stu-id="f58be-150">For 10 days or less, the results are available instantly as a **Summary** report.</span></span> <span data-ttu-id="f58be-151">Если указать диапазон времени, который даже немного превышает 10 дней, результаты будут отложены, так как они доступны только  в качестве загружаемого CSV-файла **(расширенные** сводки или расширенные отчеты).</span><span class="sxs-lookup"><span data-stu-id="f58be-151">If you specify a time range that's even slightly greater than 10 days, the results will be delayed as they are only available as a downloadable CSV file ( **Enhanced summary** or **Extended** reports).</span></span>

  <span data-ttu-id="f58be-152">Дополнительные сведения о различных типах отчетов см. в разделе [Выберите](#choose-report-type) тип отчета в этой статье.</span><span class="sxs-lookup"><span data-stu-id="f58be-152">For more information about the different report types, see the [Choose report type](#choose-report-type) section in this article.</span></span>

  > [!NOTE]
  > <span data-ttu-id="f58be-153">Расширенные сводные и расширенные отчеты готовятся с использованием архивных данных трассировки сообщений, и это может занять до нескольких часов, прежде чем ваш отчет будет доступен для скачивания.</span><span class="sxs-lookup"><span data-stu-id="f58be-153">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available for download.</span></span> <span data-ttu-id="f58be-154">В зависимости от того, сколько других администраторов также отправили запросы отчетов примерно в одно и то же время, вы также можете заметить задержку перед началом обработки для вашего запроса в очередь.</span><span class="sxs-lookup"><span data-stu-id="f58be-154">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before processing starts for your queued request.</span></span>

- <span data-ttu-id="f58be-155">Сохранение запроса в **представлении Slider** сохраняет относительный диапазон времени (например, 3 дня с сегодняшнего дня).</span><span class="sxs-lookup"><span data-stu-id="f58be-155">Saving a query in **Slider** view saves the relative time range (for example, 3 days from today).</span></span> <span data-ttu-id="f58be-156">Сохранение запроса в **настраиваемом** представлении сохраняет абсолютный диапазон дат и времени (например, 2018-05-06 с 13:00 до 2018-05-08 18:00).</span><span class="sxs-lookup"><span data-stu-id="f58be-156">Saving a query in **Custom** view saves the absolute date/time range (for example, 2018-05-06 13:00 to 2018-05-08 18:00).</span></span>

### <a name="more-search-options"></a><span data-ttu-id="f58be-157">Дополнительные параметры поиска</span><span class="sxs-lookup"><span data-stu-id="f58be-157">More search options</span></span>

#### <a name="delivery-status"></a><span data-ttu-id="f58be-158">Состояние доставки.</span><span class="sxs-lookup"><span data-stu-id="f58be-158">Delivery status</span></span>

<span data-ttu-id="f58be-159">Вы можете оставить выбранное **значение по** умолчанию или выбрать одно из следующих значений для фильтрации результатов:</span><span class="sxs-lookup"><span data-stu-id="f58be-159">You can leave the default value **All** selected, or you can select one of the following values to filter the results:</span></span>

- <span data-ttu-id="f58be-160">**Доставлено.** Сообщение было успешно доставлено в нужное место.</span><span class="sxs-lookup"><span data-stu-id="f58be-160">**Delivered**: The message was successfully delivered to the intended destination.</span></span>

- <span data-ttu-id="f58be-161">**Ожидание.** Доставка сообщения пытаетсяся или повторно пытаетсяся.</span><span class="sxs-lookup"><span data-stu-id="f58be-161">**Pending**: Delivery of the message is being attempted or re-attempted.</span></span>

- <span data-ttu-id="f58be-162">**Расширенный.** Получатель группы рассылки был расширен до доставки отдельным членам группы.</span><span class="sxs-lookup"><span data-stu-id="f58be-162">**Expanded**: A distribution group recipient was expanded before delivery to the individual members of the group.</span></span>

- <span data-ttu-id="f58be-163">**Не удалось.** Сообщение не было доставлено.</span><span class="sxs-lookup"><span data-stu-id="f58be-163">**Failed**: The message was not delivered.</span></span>

- <span data-ttu-id="f58be-164">**Карантин:** сообщение было карантином (как спам, массовая почта или фишинг).</span><span class="sxs-lookup"><span data-stu-id="f58be-164">**Quarantined**: The message was quarantined (as spam, bulk mail, or phishing).</span></span> <span data-ttu-id="f58be-165">Дополнительные сведения см. в сообщении электронной почты с [карантином в EOP.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="f58be-165">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

- <span data-ttu-id="f58be-166">**Фильтруется как спам.** Сообщение было идентифицировано как нежелательное, и было отклонено или заблокировано (не на карантине).</span><span class="sxs-lookup"><span data-stu-id="f58be-166">**Filtered as spam**: The message was identified spam, and was rejected or blocked (not quarantined).</span></span>

- <span data-ttu-id="f58be-167">**Получение статуса:** Сообщение было недавно получено Корпорацией Майкрософт 365, но других данных о состоянии пока нет.</span><span class="sxs-lookup"><span data-stu-id="f58be-167">**Getting status:** The message was recently received by Microsoft 365, but no other status data is yet available.</span></span> <span data-ttu-id="f58be-168">Возвращайся через несколько минут.</span><span class="sxs-lookup"><span data-stu-id="f58be-168">Check back in a few minutes.</span></span>

> [!NOTE]
> <span data-ttu-id="f58be-169">Значения **"Ожидание",** **"Карантин"** и **"Фильтр** как спам" доступны только для поиска менее чем за 10 дней.</span><span class="sxs-lookup"><span data-stu-id="f58be-169">The values **Pending,** **Quarantined**, and **Filter as spam** are only available for searches less than 10 days.</span></span> <span data-ttu-id="f58be-170">Кроме того, может быть задержка от 5 до 10 минут между фактическим и сообщаемого состояния доставки.</span><span class="sxs-lookup"><span data-stu-id="f58be-170">Also, there might be a 5 to 10 minute delay between the actual and reported delivery status.</span></span>

#### <a name="message-id"></a><span data-ttu-id="f58be-171">ИД сообщения</span><span class="sxs-lookup"><span data-stu-id="f58be-171">Message ID</span></span>

<span data-ttu-id="f58be-172">Это ИД интернет-сообщения (также известный как client ID), найденный в поле **Message-ID:** header в загонщике сообщений.</span><span class="sxs-lookup"><span data-stu-id="f58be-172">This is the internet message ID (also known as the Client ID) that's found in the **Message-ID:** header field in the message header.</span></span> <span data-ttu-id="f58be-173">Пользователи могут предоставить вам это значение для изучения определенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="f58be-173">Users can give you this value to investigate specific messages.</span></span>

<span data-ttu-id="f58be-174">Это значение не изменяется на протяжении всего времени жизни сообщения.</span><span class="sxs-lookup"><span data-stu-id="f58be-174">This value is constant for the lifetime of the message.</span></span> <span data-ttu-id="f58be-175">Для сообщений, созданных в Microsoft 365 или Exchange, значение находится в формате, включая `<GUID@ServerFQDN>` угловые скобки ( \< \> ).</span><span class="sxs-lookup"><span data-stu-id="f58be-175">For messages created in Microsoft 365 or Exchange, the value is in the format `<GUID@ServerFQDN>`, including the angle brackets (\< \>).</span></span> <span data-ttu-id="f58be-176">Например, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span><span class="sxs-lookup"><span data-stu-id="f58be-176">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span> <span data-ttu-id="f58be-177">Другие системы обмена сообщениями могут использовать различные синтаксис или значения.</span><span class="sxs-lookup"><span data-stu-id="f58be-177">Other messaging systems might use different syntax or values.</span></span> <span data-ttu-id="f58be-178">Это значение должно быть уникальным, но не все системы электронной почты строго следуют этому требованию.</span><span class="sxs-lookup"><span data-stu-id="f58be-178">This value is supposed to be unique, but not all email systems strictly follow this requirement.</span></span> <span data-ttu-id="f58be-179">Если поле **message-ID:** поле заголовки не существует или пусто для входящих сообщений из внешних источников, назначено произвольное значение.</span><span class="sxs-lookup"><span data-stu-id="f58be-179">If the **Message-ID:** header field doesn't exist or is blank for incoming messages from external sources, an arbitrary value is assigned.</span></span>

<span data-ttu-id="f58be-180">При **фильтрации результатов** с помощью message ID обязательно включаем полную строку, в том числе любые угловые скобки.</span><span class="sxs-lookup"><span data-stu-id="f58be-180">When you use **Message ID** to filter the results, be sure to include the full string, including any angle brackets.</span></span>

#### <a name="direction"></a><span data-ttu-id="f58be-181">Direction</span><span class="sxs-lookup"><span data-stu-id="f58be-181">Direction</span></span>

<span data-ttu-id="f58be-182">Вы можете оставить  выбранное значение по умолчанию или выбрать входящие **(сообщения,** отосланные получателям в организации) или **Исходящие** (сообщения, отосланные от пользователей в организации) для фильтрации результатов.</span><span class="sxs-lookup"><span data-stu-id="f58be-182">You can leave the default value **All** selected, or you can select **Inbound** (messages sent to recipients in your organization) or **Outbound** (messages sent from users in your organization) to filter the results.</span></span>

#### <a name="original-client-ip-address"></a><span data-ttu-id="f58be-183">Исходный IP-адрес клиента.</span><span class="sxs-lookup"><span data-stu-id="f58be-183">Original client IP address</span></span>

<span data-ttu-id="f58be-184">Вы можете подать результаты по IP-адресу клиента для расследования взлома компьютеров, которые отправляют большое количество нежелательной почты или вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="f58be-184">You can filer the results by client IP address to investigate hacked computers that are sending large amounts of spam or malware.</span></span> <span data-ttu-id="f58be-185">Хотя сообщения могут появиться от нескольких отправителей, вполне вероятно, что один и тот же компьютер создает все сообщения.</span><span class="sxs-lookup"><span data-stu-id="f58be-185">Although the messages might appear to come from multiple senders, it's likely that the same computer is generating all of the messages.</span></span>

> [!NOTE]
> <span data-ttu-id="f58be-186">Сведения об IP-адресе клиента доступны только в течение 10 дней  и доступны только в сводных сводке или расширенных отчетах (загружаемых CSV-файлах). </span><span class="sxs-lookup"><span data-stu-id="f58be-186">The client IP address information is only available for 10 days, and is only available in the **Enhanced summary** or **Extended** reports (downloadable CSV files).</span></span>

### <a name="choose-report-type"></a><span data-ttu-id="f58be-187">Выберите тип отчета</span><span class="sxs-lookup"><span data-stu-id="f58be-187">Choose report type</span></span>

<span data-ttu-id="f58be-188">Доступные типы отчетов:</span><span class="sxs-lookup"><span data-stu-id="f58be-188">The available report types are:</span></span>

- <span data-ttu-id="f58be-189">**Сводка.** Доступно, если диапазон времени не превышает 10 дней и не требует дополнительных вариантов фильтрации.</span><span class="sxs-lookup"><span data-stu-id="f58be-189">**Summary**: Available if the time range is less than 10 days, and requires no additional filtering options.</span></span> <span data-ttu-id="f58be-190">Результаты доступны почти сразу после нажатия **поиска.**</span><span class="sxs-lookup"><span data-stu-id="f58be-190">The results are available almost immediately after you click **Search**.</span></span> <span data-ttu-id="f58be-191">Отчет возвращает до 20000 результатов.</span><span class="sxs-lookup"><span data-stu-id="f58be-191">The report returns up to 20000 results.</span></span>

- <span data-ttu-id="f58be-192">**Расширенные** сводки или расширенные: Эти отчеты доступны только в качестве загружаемых CSV-файлов, и требуются один или несколько из следующих вариантов фильтрации независимо от диапазона **времени:** Эти люди , **Для** этих людей , или сообщение **ID**.</span><span class="sxs-lookup"><span data-stu-id="f58be-192">**Enhanced summary** or **Extended**: These reports are only available as downloadable CSV files, and require one or more of the following filtering options regardless of the time range: **By these people**, **To these people**, or **Message ID**.</span></span> <span data-ttu-id="f58be-193">Вы можете использовать подкарды для отправителей или получателей (например, \* @contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f58be-193">You can use wildcards for the senders or the recipients (for example, \*@contoso.com).</span></span> <span data-ttu-id="f58be-194">Расширенный сводный отчет возвращает до 50000 результатов.</span><span class="sxs-lookup"><span data-stu-id="f58be-194">The Enhanced summary report returns up to 50000 results.</span></span> <span data-ttu-id="f58be-195">Расширенный отчет возвращает до 1000 результатов.</span><span class="sxs-lookup"><span data-stu-id="f58be-195">The Extended report returns up to 1000 results.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="f58be-196">Расширенные сводные и расширенные отчеты готовятся с помощью архивных данных трассировки сообщений, и загрузка отчета может занять до нескольких часов.</span><span class="sxs-lookup"><span data-stu-id="f58be-196">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available to download.</span></span> <span data-ttu-id="f58be-197">В зависимости от того, сколько других администраторов также отправили запросы отчетов примерно в одно и то же время, вы также можете заметить задержку перед началом обработки вашего запроса в очереди.</span><span class="sxs-lookup"><span data-stu-id="f58be-197">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before your queued request starts to be processed.</span></span>
>
> - <span data-ttu-id="f58be-198">Хотя вы можете выбрать расширенный сводный или расширенный отчет для любого диапазона дат и времени, обычно последние четыре часа архивных данных еще не будут доступны для этих двух типов отчетов.</span><span class="sxs-lookup"><span data-stu-id="f58be-198">While you can select an Enhanced summary or Extended report for any date/time range, commonly the last four hours of archived data will not yet be available for these two types of reports.</span></span>
>
> - <span data-ttu-id="f58be-199">Максимальный размер загружаемого отчета — 500 МБ.</span><span class="sxs-lookup"><span data-stu-id="f58be-199">The maximum size for a downloadable report is 500 MB.</span></span> <span data-ttu-id="f58be-200">Если загружаемый отчет превышает 500 МБ, его нельзя открыть в Excel или Блокноте.</span><span class="sxs-lookup"><span data-stu-id="f58be-200">If a downloadable report exceeds 500 MB, you can't open the report in Excel or Notepad.</span></span>

<span data-ttu-id="f58be-201">При нажатии кнопки **Далее** вам будет представлена сводная страница, на которую перечислены выбранные параметры фильтрации, уникальное (редактируемое) название отчета и адрес электронной почты, который получает уведомление по завершению трассировки сообщения (также редактируемой и должен быть в одном из принятых доменов организации).</span><span class="sxs-lookup"><span data-stu-id="f58be-201">When you click **Next**, you're presented with a summary page that lists the filtering options that you selected, a unique (editable) title for the report, and the email address that receives the notification when the message trace completes (also editable, and must be in one of your organization's accepted domains).</span></span> <span data-ttu-id="f58be-202">Нажмите **кнопку Подготовка отчета** для отправки трассировки сообщения.</span><span class="sxs-lookup"><span data-stu-id="f58be-202">Click **Prepare report** to submit the message trace.</span></span> <span data-ttu-id="f58be-203">На главной **странице трассировки** сообщений можно увидеть состояние отчета в разделе **Загружаемые отчеты.**</span><span class="sxs-lookup"><span data-stu-id="f58be-203">On the main **Message trace** page, you can see the status of the report in the **Downloadable reports** section.</span></span>

<span data-ttu-id="f58be-204">Дополнительные сведения о возвращаемой информации в различных типах отчетов см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="f58be-204">For more information about the information that's returned in the different report types, see the next section.</span></span>

## <a name="message-trace-results"></a><span data-ttu-id="f58be-205">Результаты трассировки сообщений</span><span class="sxs-lookup"><span data-stu-id="f58be-205">Message trace results</span></span>

<span data-ttu-id="f58be-206">Различные типы отчетов возвращают различные уровни информации.</span><span class="sxs-lookup"><span data-stu-id="f58be-206">The different report types return different levels of information.</span></span> <span data-ttu-id="f58be-207">Сведения, доступные в различных отчетах, описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="f58be-207">The information that's available in the different reports is described in the following sections.</span></span>

### <a name="summary-report-output"></a><span data-ttu-id="f58be-208">Вывод сводного отчета</span><span class="sxs-lookup"><span data-stu-id="f58be-208">Summary report output</span></span>

<span data-ttu-id="f58be-209">После запуска трассировки сообщения результаты будут перечислены, отсортированы по дате и времени убывания (самый последний первый).</span><span class="sxs-lookup"><span data-stu-id="f58be-209">After running the message trace, the results will be listed, sorted by descending date/time (most recent first).</span></span>

![Результаты сводного отчета для отслеживания сообщений в Центре & соответствия требованиям](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

<span data-ttu-id="f58be-211">Сводный отчет содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="f58be-211">The summary report contains the following information:</span></span>

- <span data-ttu-id="f58be-212">**Дата.** Дата и время, в которые было получено сообщение службой, с помощью настроенного часовой пояс UTC.</span><span class="sxs-lookup"><span data-stu-id="f58be-212">**Date**: The date and time at which the message was received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="f58be-213">**Отправитель.** Адрес электронной почты отправитель *(псевдоним* @ *домена).*</span><span class="sxs-lookup"><span data-stu-id="f58be-213">**Sender**: The email address of the sender (*alias*@*domain*).</span></span>

- <span data-ttu-id="f58be-214">**Получатель.** Адрес электронной почты получателя или получателя.</span><span class="sxs-lookup"><span data-stu-id="f58be-214">**Recipient**: The email address of the recipient or recipients.</span></span> <span data-ttu-id="f58be-215">Для сообщения, отправленного нескольким получателям, существует одна строка на каждого получателя.</span><span class="sxs-lookup"><span data-stu-id="f58be-215">For a message sent to multiple recipients, there's one line per recipient.</span></span> <span data-ttu-id="f58be-216">Если получатель — это группа рассылки, динамическая группа рассылки или группа безопасности с включенной почтой, она будет первым получателем, а затем каждый член группы находится в отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="f58be-216">If the recipient is a distribution group, dynamic distribution group, or mail-enabled security group, the group will be the first recipient, and then each member of the group is on a separate line.</span></span>

- <span data-ttu-id="f58be-217">**Тема.** Первые 256 символов темы **сообщения:** поле.</span><span class="sxs-lookup"><span data-stu-id="f58be-217">**Subject**: The first 256 characters of the message's **Subject:** field.</span></span>

- <span data-ttu-id="f58be-218">**Состояние.** Эти значения описаны в разделе [Состояние доставки.](#delivery-status)</span><span class="sxs-lookup"><span data-stu-id="f58be-218">**Status**: These values are described in the [Delivery status](#delivery-status) section.</span></span>

<span data-ttu-id="f58be-219">По умолчанию загружаются и легко доступны первые 250 результатов.</span><span class="sxs-lookup"><span data-stu-id="f58be-219">By default, the first 250 results are loaded and readily available.</span></span> <span data-ttu-id="f58be-220">При прокрутке вниз происходит небольшая пауза при загрузке следующей партии результатов.</span><span class="sxs-lookup"><span data-stu-id="f58be-220">When you scroll down, there's a slight pause as the next batch of results are loaded.</span></span> <span data-ttu-id="f58be-221">Вместо прокрутки можно нажать кнопку **Загрузить** все, чтобы загрузить все результаты до 10 000.</span><span class="sxs-lookup"><span data-stu-id="f58be-221">Instead of scrolling, you can click **Load all** to load all of the results up to a maximum of 10,000.</span></span>

<span data-ttu-id="f58be-222">Вы можете нажать на столбцы для сортировки результатов по значениям в этом столбце в порядке подъема или убывания.</span><span class="sxs-lookup"><span data-stu-id="f58be-222">You can click on the column headers to sort the results by the values in that column in ascending or descending order.</span></span>

<span data-ttu-id="f58be-223">Вы можете **щелкнуть фильтр результатов,** чтобы отфильтровать результаты одним или несколько столбцов.</span><span class="sxs-lookup"><span data-stu-id="f58be-223">You can click **Filter results** to filter the results by one or more columns.</span></span>

<span data-ttu-id="f58be-224">Вы можете экспортировать результаты после выбора одной или более  строк, щелкнув результаты экспорта, а затем выбрав экспорт всех результатов, экспортировать загруженные результаты **или** **экспортировать выбранные**.</span><span class="sxs-lookup"><span data-stu-id="f58be-224">You can export the results after you've selected one or more rows by clicking **Export results** and then selecting **Export all results**, **Export loaded results**, or **Export selected**.</span></span>

#### <a name="find-related-records-for-this-message"></a><span data-ttu-id="f58be-225">Поиск связанных записей для этого сообщения</span><span class="sxs-lookup"><span data-stu-id="f58be-225">Find related records for this message</span></span>

<span data-ttu-id="f58be-226">Связанные записи сообщений — это записи, которые разделяют один и тот же ID сообщения.</span><span class="sxs-lookup"><span data-stu-id="f58be-226">Related message records are records that shared the same Message ID.</span></span> <span data-ttu-id="f58be-227">Помните, что даже одно сообщение, отправленное между двумя людьми, может создавать несколько записей.</span><span class="sxs-lookup"><span data-stu-id="f58be-227">Remember, even a single message sent between two people can generate multiple records.</span></span> <span data-ttu-id="f58be-228">Количество записей увеличивается, когда на сообщение влияет расширение группы рассылки, пересылание, правила потока почты (также известные как правила транспорта) и т.д.</span><span class="sxs-lookup"><span data-stu-id="f58be-228">The number of records increases when the message is affected by distribution group expansion, forwarding, mail flow rules (also known as transport rules), etc.</span></span>

<span data-ttu-id="f58be-229">После выбора контрольного окна строки можно найти соответствующие записи для сообщения, нажав кнопку  **Find related,** которая появится, или выбрав дополнительные параметры Дополнительные записи поиска для этого ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> сообщения).</span><span class="sxs-lookup"><span data-stu-id="f58be-229">After you select a row's check box, you can find related records for the message by clicking the **Find related** button that appears, or by selecting **More options** ![More](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Find related records for this message**).</span></span>

<span data-ttu-id="f58be-230">Дополнительные сведения о ID сообщения см. в разделе Message ID в этой статье.</span><span class="sxs-lookup"><span data-stu-id="f58be-230">For more information about the Message ID, see the Message ID section earlier in this article.</span></span>

#### <a name="message-trace-details"></a><span data-ttu-id="f58be-231">Сведения о трассировок сообщений</span><span class="sxs-lookup"><span data-stu-id="f58be-231">Message trace details</span></span>

<span data-ttu-id="f58be-232">В сводной сводке отчетов можно просмотреть сведения о сообщении с помощью любого из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="f58be-232">In the summary report output, you can view details about a message by using either of the following methods:</span></span>

- <span data-ttu-id="f58be-233">Выберите строку (щелкните в любом месте строки, кроме контрольного окна).</span><span class="sxs-lookup"><span data-stu-id="f58be-233">Select the row (click anywhere in the row except the check box).</span></span>

- <span data-ttu-id="f58be-234">Выберите контрольный ящик строки и щелкните **Дополнительные параметры** ![ Дополнительные ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **сведения о сообщении просмотра**.</span><span class="sxs-lookup"><span data-stu-id="f58be-234">Select the row's check box and click **More options** ![More](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **View message details**.</span></span>

   ![Сведения после двойного нажатия строки в трассировке сообщений сводного отчета приводит к & Центра & соответствия требованиям.](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

<span data-ttu-id="f58be-236">Сведения о трассировке сообщений содержат следующие дополнительные сведения, которых нет в сводной сводке:</span><span class="sxs-lookup"><span data-stu-id="f58be-236">The message trace details contain the following additional information that's not present in the summary report:</span></span>

- <span data-ttu-id="f58be-237">**События сообщений.** В этом разделе содержатся классификации, которые помогают классифицировать действия, которые служба принимает на сообщения.</span><span class="sxs-lookup"><span data-stu-id="f58be-237">**Message events**: This section contains classifications that help categorize the actions that the service takes on messages.</span></span> <span data-ttu-id="f58be-238">**Некоторые из наиболее интересных событий,** с которыми вы можете столкнуться:</span><span class="sxs-lookup"><span data-stu-id="f58be-238">**Some of the more interesting events** that you might encounter are:</span></span>

  - <span data-ttu-id="f58be-239">**Получение.** Сообщение было получено службой.</span><span class="sxs-lookup"><span data-stu-id="f58be-239">**Receive**: The message was received by the service.</span></span>

  - <span data-ttu-id="f58be-240">**Отправка.** Сообщение было отправлено службой.</span><span class="sxs-lookup"><span data-stu-id="f58be-240">**Send**: The message was sent by the service.</span></span>

  - <span data-ttu-id="f58be-241">**Fail.** Сообщение не было доставлено.</span><span class="sxs-lookup"><span data-stu-id="f58be-241">**Fail**: The message failed to be delivered.</span></span>

  - <span data-ttu-id="f58be-242">**Доставка.** Сообщение было доставлено в почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="f58be-242">**Deliver**: The message was delivered to a mailbox.</span></span>

  - <span data-ttu-id="f58be-243">**Расширение.** Сообщение было отправлено расширенной группе рассылки.</span><span class="sxs-lookup"><span data-stu-id="f58be-243">**Expand**: The message was sent to a distribution group that was expanded.</span></span>

  - <span data-ttu-id="f58be-244">**Передача.** Получатели были перемещены в двухфуркированное сообщение из-за преобразования контента, ограничений получателей сообщений или агентов.</span><span class="sxs-lookup"><span data-stu-id="f58be-244">**Transfer**: Recipients were moved to a bifurcated message because of content conversion, message recipient limits, or agents.</span></span>

  - <span data-ttu-id="f58be-245">**Отсрочка.** Доставка сообщения была отложена и может быть повторно предпринята позже.</span><span class="sxs-lookup"><span data-stu-id="f58be-245">**Defer**: The message delivery was postponed and might be re-attempted later.</span></span>

  - <span data-ttu-id="f58be-246">**Разрешено.** Сообщение было перенаправлено на новый адрес получателя на основе образа Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f58be-246">**Resolved**: The message was redirected to a new recipient address based on an Active Directory look up.</span></span> <span data-ttu-id="f58be-247">В этом случае исходный адрес получателя указывается в отдельной строке трассировки сообщений вместе с итоговым состоянием доставки сообщения.</span><span class="sxs-lookup"><span data-stu-id="f58be-247">When this happens, the original recipient address is listed in a separate row in the message trace along with the final delivery status for the message.</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="f58be-248">Успешно доставленное сообщение с неравномерностью создает несколько **записей события** в следе сообщения.</span><span class="sxs-lookup"><span data-stu-id="f58be-248">An uneventful message that's successfully delivered will generate multiple **Event** entries in the message trace.</span></span>
  > 
  > - <span data-ttu-id="f58be-249">Этот список не является исчерпывающим.</span><span class="sxs-lookup"><span data-stu-id="f58be-249">This list is not meant to be exhaustive.</span></span> <span data-ttu-id="f58be-250">Дополнительные описания событий см. в [журнале отслеживания](/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log)сообщений типами событий.</span><span class="sxs-lookup"><span data-stu-id="f58be-250">For descriptions of more events, see [Event types in the message tracking log](/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log).</span></span> <span data-ttu-id="f58be-251">Обратите внимание, что эта ссылка является Exchange Server (локальной exchange) темой.</span><span class="sxs-lookup"><span data-stu-id="f58be-251">Note that this link is an Exchange Server (on-premises Exchange) topic.</span></span>

- <span data-ttu-id="f58be-252">**Дополнительные сведения.** В этом разделе содержатся следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="f58be-252">**More information**: This section contains the following details:</span></span>

  - <span data-ttu-id="f58be-253">**ID сообщения.** Это значение описано в разделе [Message ID](#message-id) ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="f58be-253">**Message ID**: This value is described in the [Message ID](#message-id) section earlier in this article.</span></span> <span data-ttu-id="f58be-254">Например, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span><span class="sxs-lookup"><span data-stu-id="f58be-254">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

  - <span data-ttu-id="f58be-255">**Размер сообщения**.</span><span class="sxs-lookup"><span data-stu-id="f58be-255">**Message size**</span></span>

  - <span data-ttu-id="f58be-256">**С IP:** IP-адрес компьютера, отправив сообщение.</span><span class="sxs-lookup"><span data-stu-id="f58be-256">**From IP**: The IP address of the computer that sent the message.</span></span> <span data-ttu-id="f58be-257">Для исходящие сообщения, отправленные из Exchange Online, это значение является пустым.</span><span class="sxs-lookup"><span data-stu-id="f58be-257">For outbound messages sent from Exchange Online, this value is blank.</span></span>

  - <span data-ttu-id="f58be-258">**IP:** IP-адрес или адреса, на которых служба попыталась доставить сообщение.</span><span class="sxs-lookup"><span data-stu-id="f58be-258">**To IP**: The IP address or addresses where the service attempted to deliver the message.</span></span> <span data-ttu-id="f58be-259">Если в сообщении несколько получателей, они отображаются.</span><span class="sxs-lookup"><span data-stu-id="f58be-259">If the message has multiple recipients, these are displayed.</span></span> <span data-ttu-id="f58be-260">Для входящие сообщения, отправленные в Exchange Online, это значение является пустым.</span><span class="sxs-lookup"><span data-stu-id="f58be-260">For inbound messages sent to Exchange Online, this value is blank.</span></span>

### <a name="enhanced-summary-reports"></a><span data-ttu-id="f58be-261">Расширенные сводные отчеты</span><span class="sxs-lookup"><span data-stu-id="f58be-261">Enhanced summary reports</span></span>

<span data-ttu-id="f58be-262">Доступные (завершенные) расширенные сводные отчеты доступны в разделе **Загружаемые** отчеты в начале сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="f58be-262">Available (completed) Enhanced summary reports are available in the **Downloadable reports** section at the beginning message trace.</span></span> <span data-ttu-id="f58be-263">В отчете доступны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="f58be-263">The following information is available in the report:</span></span>

- <span data-ttu-id="f58be-264">**origin_timestamp:** дата и время, когда сообщение изначально было получено службой, используя настроенный <sup>\*</sup> часовой пояс UTC.</span><span class="sxs-lookup"><span data-stu-id="f58be-264">**origin_timestamp**<sup>\*</sup>: The date and time when the message was initially received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="f58be-265">**sender_address**: адрес электронной почты отправитель *(псевдоним* @ *домена).*</span><span class="sxs-lookup"><span data-stu-id="f58be-265">**sender_address**: The sender's email address (*alias*@*domain*).</span></span>

- <span data-ttu-id="f58be-266">**Recipient_status:** состояние доставки сообщения получателю.</span><span class="sxs-lookup"><span data-stu-id="f58be-266">**Recipient_status**: The status of the delivery of the message to the recipient.</span></span> <span data-ttu-id="f58be-267">Если сообщение было отправлено нескольким получателям, оно будет показывать всех получателей и соответствующий статус для каждого из них в формате: \<*email address*\> ## \<*status*\> .</span><span class="sxs-lookup"><span data-stu-id="f58be-267">If the message was sent to multiple recipients, it will show all the recipients and the corresponding status for each, in the format: \<*email address*\>##\<*status*\>.</span></span> <span data-ttu-id="f58be-268">Пример.</span><span class="sxs-lookup"><span data-stu-id="f58be-268">For example:</span></span>

  - <span data-ttu-id="f58be-269">**##Receive отправка означает,** что сообщение было получено службой и отправлено в нужное место.</span><span class="sxs-lookup"><span data-stu-id="f58be-269">**##Receive, Send** means the message was received by the service and was sent to the intended destination.</span></span>

  - <span data-ttu-id="f58be-270">**##Receive fail означает,** что сообщение было получено службой, но доставка в нужное место не удалась.</span><span class="sxs-lookup"><span data-stu-id="f58be-270">**##Receive, Fail** means the message was received by the service but delivery to the intended destination failed.</span></span>

  - <span data-ttu-id="f58be-271">**##Receive Deliver означает,** что сообщение было получено службой и доставлено в почтовый ящик получателя.</span><span class="sxs-lookup"><span data-stu-id="f58be-271">**##Receive, Deliver** means the message was received by the service and was delivered to the recipient's mailbox.</span></span>

- <span data-ttu-id="f58be-272">**message_subject**: Первые 256 символов поля Subject **сообщения.**</span><span class="sxs-lookup"><span data-stu-id="f58be-272">**message_subject**: The first 256 characters of the message's **Subject** field.</span></span>

- <span data-ttu-id="f58be-273">**total_bytes:** размер сообщения в bytes, включая вложения.</span><span class="sxs-lookup"><span data-stu-id="f58be-273">**total_bytes**: The size of the message in bytes, including attachments.</span></span>

- <span data-ttu-id="f58be-274">**message_id.** Это значение описано в разделе [Message ID](#message-id) ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="f58be-274">**message_id**: This value is described in the [Message ID](#message-id) section earlier in this article.</span></span> <span data-ttu-id="f58be-275">Например, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span><span class="sxs-lookup"><span data-stu-id="f58be-275">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

- <span data-ttu-id="f58be-276">**network_message_id:** уникальное значение ID сообщения, которое сохраняется во всех копиях сообщения, которое может быть создано из-за расширения группы рассылки или бифуркации.</span><span class="sxs-lookup"><span data-stu-id="f58be-276">**network_message_id**: A unique message ID value that persists across all copies of the message that might be created due to bifurcation or distribution group expansion.</span></span> <span data-ttu-id="f58be-277">Например, значение `1341ac7b13fb42ab4d4408cf7f55890f` .</span><span class="sxs-lookup"><span data-stu-id="f58be-277">An example value is `1341ac7b13fb42ab4d4408cf7f55890f`.</span></span>

- <span data-ttu-id="f58be-278">**original_client_ip:** IP-адрес клиента отправитель.</span><span class="sxs-lookup"><span data-stu-id="f58be-278">**original_client_ip**: The IP address of the sender's client.</span></span>

- <span data-ttu-id="f58be-279">**направленность.** Указывает, было ли сообщение отправлено входящие (1) в вашу организацию, или же оно было отправлено исходящие (2) из организации.</span><span class="sxs-lookup"><span data-stu-id="f58be-279">**directionality**: Indicates whether the message was sent inbound (1) to your organization, or whether it was sent outbound (2) from your organization.</span></span>

- <span data-ttu-id="f58be-280">**connector_id:** имя соединитетеля источника или назначения.</span><span class="sxs-lookup"><span data-stu-id="f58be-280">**connector_id**: The name of the source or destination connector.</span></span> <span data-ttu-id="f58be-281">Дополнительные сведения о соединители в Exchange Online см. в сообщении [Configure mail flow using connectors in Office 365.](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)</span><span class="sxs-lookup"><span data-stu-id="f58be-281">For more information about connectors in Exchange Online, see [Configure mail flow using connectors in Office 365](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

- <span data-ttu-id="f58be-282">**delivery_priority**: Было ли отправлено сообщение с высоким, низким или <sup>\*</sup> **нормальным** приоритетом. </span><span class="sxs-lookup"><span data-stu-id="f58be-282">**delivery_priority**<sup>\*</sup>: Whether the message was sent with **High**, **Low**, or **Normal** priority.</span></span>

<span data-ttu-id="f58be-283"><sup>\*</sup> Эти свойства доступны только в расширенных сводных отчетах.</span><span class="sxs-lookup"><span data-stu-id="f58be-283"><sup>\*</sup> These properties are only available in Enhanced summary reports.</span></span>

### <a name="extended-reports"></a><span data-ttu-id="f58be-284">Расширенные отчеты</span><span class="sxs-lookup"><span data-stu-id="f58be-284">Extended reports</span></span>

<span data-ttu-id="f58be-285">Доступные (завершенные) расширенные отчеты доступны в разделе **Загружаемые** отчеты в начале трассировки сообщений.</span><span class="sxs-lookup"><span data-stu-id="f58be-285">Available (completed) Extended reports are available in the **Downloadable reports** section at the beginning of message trace.</span></span> <span data-ttu-id="f58be-286">Практически все сведения из расширенного сводного отчета доступны в расширенном отчете  (за исключением origin_timestamp **и delivery_priority).**</span><span class="sxs-lookup"><span data-stu-id="f58be-286">Virtually all of the information from an Enhanced summary report is available in an Extended report (with the exception of **origin_timestamp** and **delivery_priority**).</span></span> <span data-ttu-id="f58be-287">Следующие дополнительные сведения доступны только в расширенном отчете:</span><span class="sxs-lookup"><span data-stu-id="f58be-287">The following additional information is only available in an Extended report:</span></span>

- <span data-ttu-id="f58be-288">**client_ip**: IP-адрес сервера электронной почты или клиента обмена сообщениями, которые отправили сообщение.</span><span class="sxs-lookup"><span data-stu-id="f58be-288">**client_ip**: The IP address of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="f58be-289">**client_hostname:** имя хозяина или FQDN сервера электронной почты или клиента обмена сообщениями, которые отправили сообщение.</span><span class="sxs-lookup"><span data-stu-id="f58be-289">**client_hostname**: The host name or FQDN of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="f58be-290">**server_ip:** IP-адрес источника или сервера назначения.</span><span class="sxs-lookup"><span data-stu-id="f58be-290">**server_ip**: The IP address of the source or destination server.</span></span>

- <span data-ttu-id="f58be-291">**server_hostname:** имя или FQDN сервера назначения.</span><span class="sxs-lookup"><span data-stu-id="f58be-291">**server_hostname**: The host name or FQDN of the destination server.</span></span>

- <span data-ttu-id="f58be-292">**source_context**: Дополнительные сведения, связанные с **исходным полем.**</span><span class="sxs-lookup"><span data-stu-id="f58be-292">**source_context**: Extra information associated with the **source** field.</span></span> <span data-ttu-id="f58be-293">Пример.</span><span class="sxs-lookup"><span data-stu-id="f58be-293">For example:</span></span>

  - `Protocol Filter Agent`

  - `3489061114359050000`

- <span data-ttu-id="f58be-294">**источник.** Компонент Exchange Online, ответственный за событие.</span><span class="sxs-lookup"><span data-stu-id="f58be-294">**source**: The Exchange Online component that's responsible for the event.</span></span> <span data-ttu-id="f58be-295">Пример.</span><span class="sxs-lookup"><span data-stu-id="f58be-295">For example:</span></span>

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- <span data-ttu-id="f58be-296">**event_id.** Эти значения соответствуют значениям событий **Message,** которые объясняются в разделе Поиск связанных записей [для этого сообщения.](#find-related-records-for-this-message)</span><span class="sxs-lookup"><span data-stu-id="f58be-296">**event_id**: These correspond to the **Message event** values that are explained in the [Find related records for this message](#find-related-records-for-this-message) section.</span></span>

- <span data-ttu-id="f58be-297">**internal_message_id:** идентификатор сообщения, который назначен сервером Exchange Online, который в настоящее время обрабатывает сообщение.</span><span class="sxs-lookup"><span data-stu-id="f58be-297">**internal_message_id**: A message identifier that's assigned by the Exchange Online server that's currently processing the message.</span></span>

- <span data-ttu-id="f58be-298">**recipient_address:** адреса электронной почты получателей сообщения.</span><span class="sxs-lookup"><span data-stu-id="f58be-298">**recipient_address**: The email addresses of the message's recipients.</span></span> <span data-ttu-id="f58be-299">Если указано несколько адресов, то они отделяются друг от друга точкой с запятой (;).</span><span class="sxs-lookup"><span data-stu-id="f58be-299">Multiple email addresses are separated by the semicolon character (;).</span></span>

- <span data-ttu-id="f58be-300">**recipient_count:** общее число получателей в сообщении.</span><span class="sxs-lookup"><span data-stu-id="f58be-300">**recipient_count**: The total number of recipients in the message.</span></span>

- <span data-ttu-id="f58be-301">**related_recipient_address**: Используется с и событиями для отображения других адресов электронной почты `EXPAND` `REDIRECT` получателей, `RESOLVE` связанных с сообщением.</span><span class="sxs-lookup"><span data-stu-id="f58be-301">**related_recipient_address**: Used with `EXPAND`, `REDIRECT`, and `RESOLVE` events to display other recipient email addresses that are associated with the message.</span></span>

- <span data-ttu-id="f58be-302">**справка.** Это поле содержит дополнительные сведения для определенных типов событий.</span><span class="sxs-lookup"><span data-stu-id="f58be-302">**reference**: This field contains additional information for specific types of events.</span></span> <span data-ttu-id="f58be-303">Пример.</span><span class="sxs-lookup"><span data-stu-id="f58be-303">For example:</span></span>

  - <span data-ttu-id="f58be-304">**DSN**: Содержит ссылку отчета, которая является **message_id** значения связанного уведомления о состоянии доставки (также известного как DSN, отчет о невывозе, NDR или отказов сообщение), если DSN создается после этого события.</span><span class="sxs-lookup"><span data-stu-id="f58be-304">**DSN**: Contains the report link, which is the **message_id** value of the associated delivery status notification (also known as a DSN, non-delivery report, NDR, or bounce message) if a DSN is generated subsequent to this event.</span></span> <span data-ttu-id="f58be-305">Если это сообщение DSN, это **поле** содержит message_id исходного сообщения, для которое был создан DSN.</span><span class="sxs-lookup"><span data-stu-id="f58be-305">If this is a DSN message, this field contains the **message_id** value of the original message that the DSN was generated for.</span></span>

  - <span data-ttu-id="f58be-306">**EXPAND**: **содержит related_recipient_address** значение связанных сообщений.</span><span class="sxs-lookup"><span data-stu-id="f58be-306">**EXPAND**: Contains the **related_recipient_address** value of the related messages.</span></span>

  - <span data-ttu-id="f58be-307">**ПОЛУЧЕНИЕ:** Может содержать **message_id** связанного сообщения, если сообщение было сгенерировано другими процессами (например, правилами почтовых ящиков).</span><span class="sxs-lookup"><span data-stu-id="f58be-307">**RECEIVE**: Might contain the **message_id** value of the related message if the message was generated by other processes (for example, Inbox rules).</span></span>

  - <span data-ttu-id="f58be-308">**SEND:** **содержит internal_message_id** всех сообщений DSN.</span><span class="sxs-lookup"><span data-stu-id="f58be-308">**SEND**: Contains the **internal_message_id** value of any DSN messages.</span></span>

  - <span data-ttu-id="f58be-309">**TRANSFER.** Содержит **internal_message_id** значение разоренного сообщения (например, путем преобразования контента, ограничений получателей сообщений или агентов).</span><span class="sxs-lookup"><span data-stu-id="f58be-309">**TRANSFER**: Contains the **internal_message_id** value of the message that's being forked (for example, by content conversion, message recipient limits, or agents).</span></span>

  - <span data-ttu-id="f58be-310">**MAILBOXRULE.** Содержит **internal_message_id** входящих сообщений, из-за чего правило "Входящие" создает исходящие сообщения.</span><span class="sxs-lookup"><span data-stu-id="f58be-310">**MAILBOXRULE**: Contains the **internal_message_id** value of the inbound message that caused the Inbox rule to generate the outbound message.</span></span>

    <span data-ttu-id="f58be-311">Для других типов событий это поле обычно пусто.</span><span class="sxs-lookup"><span data-stu-id="f58be-311">For other types of events, this field is usually blank.</span></span>

- <span data-ttu-id="f58be-312">**return_path:** адрес электронной почты, указанный командой **MAIL FROM,** отправив сообщение.</span><span class="sxs-lookup"><span data-stu-id="f58be-312">**return_path**: The return email address specified by the **MAIL FROM** command that sent the message.</span></span> <span data-ttu-id="f58be-313">Несмотря на то, что это поле никогда не пусто, оно может иметь значение адреса отправитель null в качестве `<>` .</span><span class="sxs-lookup"><span data-stu-id="f58be-313">Although this field is never empty, it can have the null sender address value represented as `<>`.</span></span>

- <span data-ttu-id="f58be-314">**message_info:** Дополнительные сведения о сообщении.</span><span class="sxs-lookup"><span data-stu-id="f58be-314">**message_info**: Additional information about the message.</span></span> <span data-ttu-id="f58be-315">Пример.</span><span class="sxs-lookup"><span data-stu-id="f58be-315">For example:</span></span>

  - <span data-ttu-id="f58be-316">Дата начала сообщения в UTC и `DELIVER` `SEND` события.</span><span class="sxs-lookup"><span data-stu-id="f58be-316">The message origination date-time in UTC for `DELIVER` and `SEND` events.</span></span> <span data-ttu-id="f58be-317">Дата начала — это время, когда сообщение впервые вступило в организацию Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f58be-317">The origination date-time is the time when the message first entered the Exchange Online organization.</span></span> <span data-ttu-id="f58be-318">Дата UTC представлена в формате дата-времени ISO 8601: , где = год, = месяц, = день, указывает начало компонента `yyyy-mm-ddThh:mm:ss.fffZ` `yyyy` `mm` `dd` `T` времени, = час, = минута, = секунда, = доли `hh` `mm` секунды, `ss` `fff` `Z` и означает `Zulu` , что это еще один способ обозначить UTC.</span><span class="sxs-lookup"><span data-stu-id="f58be-318">The UTC date-time is represented in the ISO 8601 date-time format: `yyyy-mm-ddThh:mm:ss.fffZ`, where `yyyy` = year, `mm` = month, `dd` = day, `T` indicates the beginning of the time component, `hh` = hour, `mm` = minute, `ss` = second, `fff` = fractions of a second, and `Z` signifies `Zulu`, which is another way to denote UTC.</span></span>

  - <span data-ttu-id="f58be-319">Ошибки проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f58be-319">Authentication errors.</span></span> <span data-ttu-id="f58be-320">Например, можно увидеть значение и тип проверки подлинности, которые использовались при `11a` ошибке проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f58be-320">For example, you might see the value `11a` and the type of authentication that was used when the authentication error occurred.</span></span>

- <span data-ttu-id="f58be-321">**tenant_id**: значение GUID, представляю которое представляет организацию Exchange Online (например, `39238e87-b5ab-4ef6-a559-af54c6b07b42` ).</span><span class="sxs-lookup"><span data-stu-id="f58be-321">**tenant_id**: A GUID value that represents the Exchange Online organization (for example, `39238e87-b5ab-4ef6-a559-af54c6b07b42`).</span></span>

- <span data-ttu-id="f58be-322">**original_server_ip**: IP-адрес исходного сервера.</span><span class="sxs-lookup"><span data-stu-id="f58be-322">**original_server_ip**: The IP address of the original server.</span></span>

- <span data-ttu-id="f58be-323">**custom_data**: Содержит данные, связанные с определенными типами событий.</span><span class="sxs-lookup"><span data-stu-id="f58be-323">**custom_data**: Contains data related to specific event types.</span></span> <span data-ttu-id="f58be-324">Дополнительные сведения см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="f58be-324">For more information, see the following sections.</span></span>

#### <a name="custom_data-values"></a><span data-ttu-id="f58be-325">custom_data значения</span><span class="sxs-lookup"><span data-stu-id="f58be-325">custom_data values</span></span>

<span data-ttu-id="f58be-326">Поле **custom_data** для события используется различными агентами Exchange Online для регистрации `AGENTINFO` сведений об обработке сообщений.</span><span class="sxs-lookup"><span data-stu-id="f58be-326">The **custom_data** field for an `AGENTINFO` event is used by a variety of Exchange Online agents to log message processing details.</span></span> <span data-ttu-id="f58be-327">Некоторые из наиболее интересных агентов описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="f58be-327">Some of the more interesting agents are described in the following sections.</span></span>

#### <a name="spam-filter-agent"></a><span data-ttu-id="f58be-328">Агент фильтра нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="f58be-328">Spam filter agent</span></span>

<span data-ttu-id="f58be-329">Значение **custom_data,** которое начинается `S:SFA` с агента фильтра нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="f58be-329">A **custom_data** value that starts with `S:SFA` is from the spam filter agent.</span></span> <span data-ttu-id="f58be-330">Основные сведения описаны в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="f58be-330">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="f58be-331">Значение</span><span class="sxs-lookup"><span data-stu-id="f58be-331">Value</span></span>|<span data-ttu-id="f58be-332">Описание</span><span class="sxs-lookup"><span data-stu-id="f58be-332">Description</span></span>|
|---|---|
|`SFV=NSPM`|<span data-ttu-id="f58be-333">Сообщение помечено как не являющееся нежелательным и отправлено указанным получателям.</span><span class="sxs-lookup"><span data-stu-id="f58be-333">The message was marked as non-spam and was sent to the intended recipients.</span></span>|
|`SFV=SPM`|<span data-ttu-id="f58be-334">Сообщение было отмечено как спам путем фильтрации от нежелательной почты (также известной как фильтрация контента).</span><span class="sxs-lookup"><span data-stu-id="f58be-334">The message was marked as spam by anti-spam filtering (also known as content filtering).</span></span>|
|`SFV=BLK`|<span data-ttu-id="f58be-335">Фильтрация была пропущена, а сообщение было заблокировано, так как оно исходило от заблокированного отправителя.</span><span class="sxs-lookup"><span data-stu-id="f58be-335">Filtering was skipped and the message was blocked because it originated from a blocked sender.</span></span>|
|`SFV=SKS`|<span data-ttu-id="f58be-336">Сообщение было помечено как спам перед обработкой фильтрацией от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="f58be-336">The message was marked as spam prior to being processed by anti-spam filtering.</span></span> <span data-ttu-id="f58be-337">Это применяется к сообщениям, сопоставленным с правилом потока обработки почты (другое название — правило транспорта), требующим автоматически помечать их как нежелательные и обходить любую дополнительную фильтрацию.</span><span class="sxs-lookup"><span data-stu-id="f58be-337">This includes messages where the message matched a mail flow rule (also known as a transport rule) to automatically mark it as spam and bypass all additional filtering.</span></span>|
|`SCL=<number>`|<span data-ttu-id="f58be-338">Дополнительные сведения о различных значениях вероятности нежелательной почты и их значении см. в разделе [Вероятность нежелательной почты](spam-confidence-levels.md).    </span><span class="sxs-lookup"><span data-stu-id="f58be-338">For more information about the different SCL values and what they mean, see [Spam confidence levels](spam-confidence-levels.md).</span></span>|
|`PCL=<number>`|<span data-ttu-id="f58be-p156">Значение вероятности фишинга для сообщения. Эти значения можно интерпретировать так же, как и значения SCL, которые задокументированы в [Вероятность нежелательной почты](spam-confidence-levels.md).  </span><span class="sxs-lookup"><span data-stu-id="f58be-p156">The Phishing Confidence Level (PCL) value of the message. These can be interpreted the same way as the SCL values documented in [Spam confidence levels](spam-confidence-levels.md).</span></span>|
|`DI=SB`|<span data-ttu-id="f58be-341">Отправитель сообщения заблокирован.</span><span class="sxs-lookup"><span data-stu-id="f58be-341">The sender of the message was blocked.</span></span>|
|`DI=SQ`|<span data-ttu-id="f58be-342">Сообщение перемещено в карантин.</span><span class="sxs-lookup"><span data-stu-id="f58be-342">The message was quarantined.</span></span>|
|`DI=SD`|<span data-ttu-id="f58be-343">Сообщение удалено.</span><span class="sxs-lookup"><span data-stu-id="f58be-343">The message was deleted.</span></span>|
|`DI=SJ`|<span data-ttu-id="f58be-344">Сообщение отправлено в папку нежелательной почты получателя.</span><span class="sxs-lookup"><span data-stu-id="f58be-344">The message was sent to the recipient's Junk Email folder.</span></span>|
|`DI=SN`|<span data-ttu-id="f58be-345">Сообщение перенаправлено через пул обычной исходящей доставки.</span><span class="sxs-lookup"><span data-stu-id="f58be-345">The message was routed through the normal outbound delivery pool.</span></span>|
|`DI=SO`|<span data-ttu-id="f58be-346">Сообщение перенаправлено через пул высокого риска доставки.</span><span class="sxs-lookup"><span data-stu-id="f58be-346">The message was routed through the higher risk delivery pool.</span></span> <span data-ttu-id="f58be-347">Дополнительные сведения см. в статье [Пул доставки сообщений с высоким уровнем опасности](high-risk-delivery-pool-for-outbound-messages.md).</span><span class="sxs-lookup"><span data-stu-id="f58be-347">For more information, see [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span>|
|`SFS=[a]|SFS=[b]`|<span data-ttu-id="f58be-348">Это означает выполнение правил нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="f58be-348">This denotes that spam rules were matched.</span></span>|
|`IPV=CAL`|<span data-ttu-id="f58be-349">Сообщение пропущено через фильтр нежелательной почты, поскольку IP-адрес указан в списке разрешенных IP-адресов в фильтре подключений.</span><span class="sxs-lookup"><span data-stu-id="f58be-349">The message was allowed through the spam filters because the IP address was specified in an IP Allow list in the connection filter.</span></span>|
|`H=<EHLOstring>`|<span data-ttu-id="f58be-350">Строка HELO или EHLO подключенного почтового сервера.</span><span class="sxs-lookup"><span data-stu-id="f58be-350">The HELO or EHLO string of the connecting email server.</span></span>|
|`PTR=<ReverseDNS>`|<span data-ttu-id="f58be-351">Запись PTR отправляющего IP-адреса, называемая также обратным DNS-адресом.</span><span class="sxs-lookup"><span data-stu-id="f58be-351">The PTR record of the sending IP address, also known as the reverse DNS address.</span></span>|
|

<span data-ttu-id="f58be-352">Пример **custom_data** для сообщения, фильтруемой для нежелательной почты:</span><span class="sxs-lookup"><span data-stu-id="f58be-352">An example **custom_data** value for a message that's filtered for spam like this:</span></span>

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a><span data-ttu-id="f58be-353">Агент фильтрации вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="f58be-353">Malware filter agent</span></span>

<span data-ttu-id="f58be-354">Значение **custom_data,** которое начинается `S:AMA` с агента фильтра вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="f58be-354">A **custom_data** value that starts with `S:AMA` is from the malware filter agent.</span></span> <span data-ttu-id="f58be-355">Основные сведения описаны в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="f58be-355">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="f58be-356">Значение</span><span class="sxs-lookup"><span data-stu-id="f58be-356">Value</span></span>|<span data-ttu-id="f58be-357">Описание</span><span class="sxs-lookup"><span data-stu-id="f58be-357">Description</span></span>|
|---|---|
|<span data-ttu-id="f58be-358">`AMA=SUM|v=1|` или `AMA=EV|v=1`</span><span class="sxs-lookup"><span data-stu-id="f58be-358">`AMA=SUM|v=1|` or `AMA=EV|v=1`</span></span>|<span data-ttu-id="f58be-359">Сообщение помечено как содержащее вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="f58be-359">The message was determined to contain malware.</span></span> <span data-ttu-id="f58be-360">`SUM` указывает, что вредоносные программы могли быть обнаружены любым числом двигателей.</span><span class="sxs-lookup"><span data-stu-id="f58be-360">`SUM` indicates the malware could've been detected by any number of engines.</span></span> <span data-ttu-id="f58be-361">`EV` указывает, что вредоносная программа была обнаружена определенным двигателем.</span><span class="sxs-lookup"><span data-stu-id="f58be-361">`EV` indicates the malware was detected by a specific engine.</span></span> <span data-ttu-id="f58be-362">Если обработчиком обнаружены вредоносные программы, это вызывает последующие действия.</span><span class="sxs-lookup"><span data-stu-id="f58be-362">When malware is detected by an engine this triggers the subsequent actions.</span></span>|
|`Action=r`|<span data-ttu-id="f58be-363">Сообщение заменено.</span><span class="sxs-lookup"><span data-stu-id="f58be-363">The message was replaced.</span></span>|
|`Action=p`|<span data-ttu-id="f58be-364">Сообщение не проходило фильтрацию.</span><span class="sxs-lookup"><span data-stu-id="f58be-364">The message was bypassed.</span></span>|
|`Action=d`|<span data-ttu-id="f58be-365">Сообщение отложено.</span><span class="sxs-lookup"><span data-stu-id="f58be-365">The message was deferred.</span></span>|
|`Action=s`|<span data-ttu-id="f58be-366">Сообщение удалено.</span><span class="sxs-lookup"><span data-stu-id="f58be-366">The message was deleted.</span></span>|
|`Action=st`|<span data-ttu-id="f58be-367">Сообщение не проходило фильтрацию.</span><span class="sxs-lookup"><span data-stu-id="f58be-367">The message was bypassed.</span></span>|
|`Action=sy`|<span data-ttu-id="f58be-368">Сообщение не проходило фильтрацию.</span><span class="sxs-lookup"><span data-stu-id="f58be-368">The message was bypassed.</span></span>|
|`Action=ni`|<span data-ttu-id="f58be-369">Сообщение отклонено.</span><span class="sxs-lookup"><span data-stu-id="f58be-369">The message was rejected.</span></span>|
|`Action=ne`|<span data-ttu-id="f58be-370">Сообщение отклонено.</span><span class="sxs-lookup"><span data-stu-id="f58be-370">The message was rejected.</span></span>|
|`Action=b`|<span data-ttu-id="f58be-371">Сообщение заблокировано.</span><span class="sxs-lookup"><span data-stu-id="f58be-371">The message was blocked.</span></span>|
|`Name=<malware>`|<span data-ttu-id="f58be-372">Имя обнаруженной вредоносной программы.</span><span class="sxs-lookup"><span data-stu-id="f58be-372">The name of the malware that was detected.</span></span>|
|`File=<filename>`|<span data-ttu-id="f58be-373">Имя файла, содержащего вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="f58be-373">The name of the file that contained the malware.</span></span>|
|

<span data-ttu-id="f58be-374">Пример **custom_data** для сообщения, содержаного вредоносные программы, выглядит так:</span><span class="sxs-lookup"><span data-stu-id="f58be-374">An example **custom_data** value for a message that contains malware looks like this:</span></span>

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a><span data-ttu-id="f58be-375">Агент правил транспорта</span><span class="sxs-lookup"><span data-stu-id="f58be-375">Transport Rule agent</span></span>

<span data-ttu-id="f58be-376">Значение **custom_data,** которое начинается с агента правила транспорта для правил потока почты `S:TRA` (также известного как правила транспорта).</span><span class="sxs-lookup"><span data-stu-id="f58be-376">A **custom_data** value that starts with`S:TRA` is from the Transport Rule agent for mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="f58be-377">Основные сведения описаны в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="f58be-377">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="f58be-378">Значение</span><span class="sxs-lookup"><span data-stu-id="f58be-378">Value</span></span>|<span data-ttu-id="f58be-379">Описание</span><span class="sxs-lookup"><span data-stu-id="f58be-379">Description</span></span>|
|---|---|
|`ETR|ruleId=<guid>`|<span data-ttu-id="f58be-380">Выполнено правило идентификатора.</span><span class="sxs-lookup"><span data-stu-id="f58be-380">The rule ID that was matched.</span></span>|
|`St=<datetime>`|<span data-ttu-id="f58be-381">Дата и время в UTC при совпадении правил.</span><span class="sxs-lookup"><span data-stu-id="f58be-381">The date and time in UTC when the rule match occurred.</span></span>|
|`Action=<ActionDefinition>`|<span data-ttu-id="f58be-382">Примененное действие.</span><span class="sxs-lookup"><span data-stu-id="f58be-382">The action that was applied.</span></span> <span data-ttu-id="f58be-383">Список доступных действий см. в списке действий правил потока [почты в Exchange Online.](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="f58be-383">For a list of available actions, see [Mail flow rule actions in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>|
|`Mode=<Mode>`|<span data-ttu-id="f58be-384">Режим правила.</span><span class="sxs-lookup"><span data-stu-id="f58be-384">The mode of the rule.</span></span> <span data-ttu-id="f58be-385">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="f58be-385">Valid values are:</span></span><ul><li><span data-ttu-id="f58be-386">**Применение.** Все действия по правилу будут применены.</span><span class="sxs-lookup"><span data-stu-id="f58be-386">**Enforce**: All actions on the rule will be enforced.</span></span></li><li><span data-ttu-id="f58be-387">**Тест с помощью советов по политике:** любые действия наконечника политики будут отправлены, но другие действия по принунию не будут действовать.</span><span class="sxs-lookup"><span data-stu-id="f58be-387">**Test with Policy Tips:**: Any Policy Tip actions will be sent, but other enforcement actions will not be acted on.</span></span></li><li><span data-ttu-id="f58be-388">**Test without Policy Tips:** Actions will be listed in a log file, but senders will not be notified in any way, and enforcement actions will not be acted on.</span><span class="sxs-lookup"><span data-stu-id="f58be-388">**Test without Policy Tips**: Actions will be listed in a log file, but senders will not be notified in any way, and enforcement actions will not be acted on.</span></span></li></ul>|
|

<span data-ttu-id="f58be-389">Пример **custom_data** для сообщений, которые совпадают с условиями правила потока почты, выглядит так:</span><span class="sxs-lookup"><span data-stu-id="f58be-389">An example **custom_data** value for a messages that matches the conditions of a mail flow rule looks like this:</span></span>

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`