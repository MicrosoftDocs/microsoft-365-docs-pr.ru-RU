---
title: Перемещение сайта OneDrive в другой геообъект
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Сведения о перемещении сайта OneDrive в другое географическое расположение, в том числе планирование перемещения сайта и связи ожидания с пользователями.
ms.openlocfilehash: 59b3fb47fd195967e7af056c7a71fb4e736471d1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692933"
---
# <a name="move-a-onedrive-site-to-a-different-geo-location"></a><span data-ttu-id="961a6-103">Перемещение сайта OneDrive в другой геообъект</span><span class="sxs-lookup"><span data-stu-id="961a6-103">Move a OneDrive site to a different geo location</span></span> 

<span data-ttu-id="961a6-p101">С помощью географического перемещения OneDrive вы можете переместить OneDrive пользователя в другое географическое расположение. Географическое перемещение OneDrive выполняется администратором SharePoint Online или глобальным администратором Microsoft 365. Перед началом перемещения OneDrive необходимо уведомить пользователя о том, что OneDrive перемещается, и порекомендует закрыть все файлы на время перемещения. (Если пользователь открыл документ с помощью клиента Office во время перемещения, то после перемещения документ потребуется сохранить в новом расположении.) При необходимости перемещение можно запланировать на будущее время.</span><span class="sxs-lookup"><span data-stu-id="961a6-p101">With OneDrive geo move, you can move a user's OneDrive to a different geo location. OneDrive geo move is performed by the SharePoint Online administrator or the Microsoft 365 global administrator. Before you start a OneDrive geo move, be sure to notify the user whose OneDrive is being moved and recommend they close all files for the duration of the move. (If the user has a document open using the Office client during the move, then upon move completion the document will need to be saved to the new location.) The move can be scheduled for a future time, if desired.</span></span>

<span data-ttu-id="961a6-p102">Служба OneDrive использует хранилище больших двоичных объектов Azure для хранения контента. Большой двоичный объект хранилища, связанный с хранилищем OneDrive пользователя, будет перемещен из источника в конечное географическое расположение в течение 40 дней с момента назначения OneDrive, доступных пользователю. Доступ к OneDrive пользователя восстанавливается, как только конечный OneDrive будет доступен.</span><span class="sxs-lookup"><span data-stu-id="961a6-p102">The OneDrive service uses Azure Blob Storage to store content. The Storage blob associated with the user's OneDrive will be moved from the source to destination geo location within 40 days of destination OneDrive being available to the user. The access to the user's OneDrive will be restored as soon as the destination OneDrive is available.</span></span>

<span data-ttu-id="961a6-p103">Пока открыто окно перемещения OneDrive в отношении геообъекта (около 2–6 часов), служба OneDrive пользователя доступна только для чтения. Пользователь по-прежнему сможет получить доступ к своим файлам с помощью клиента синхронизации OneDrive или на сайте OneDrive в SharePoint Online. После перемещения OneDrive в отношении геообъекта пользователь будет автоматически подключен к OneDrive в целевом географическом расположении, когда попробует перейти к OneDrive в средстве запуска приложений Microsoft 365. Клиент синхронизации в новом расположении автоматически начнет синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="961a6-p103">During OneDrive geo move window (about 2-6 hours) the user's OneDrive is set to read-only. The user can still access their files via the OneDrive sync client or their OneDrive site in SharePoint Online. After OneDrive geo move is complete, the user will be automatically connected to their OneDrive at the destination geo location when they navigate to OneDrive in the Microsoft 365 app launcher. The sync client will automatically begin syncing from the new location.</span></span>

<span data-ttu-id="961a6-115">Процедуры, описываемые в этой статье, требуют наличия [модуля Microsoft SharePoint Online для PowerShell](https://www.microsoft.com/download/details.aspx?id=35588).</span><span class="sxs-lookup"><span data-stu-id="961a6-115">The procedures in this article require the [Microsoft SharePoint Online PowerShell Module](https://www.microsoft.com/download/details.aspx?id=35588).</span></span>

## <a name="communicating-to-your-users"></a><span data-ttu-id="961a6-116">Общение с пользователями</span><span class="sxs-lookup"><span data-stu-id="961a6-116">Communicating to your users</span></span>

<span data-ttu-id="961a6-p104">При перемещении сайтов OneDrive из одного географического расположения в другое важно объяснить пользователям, чего ожидать. Это поможет избежать недоразумений и снизит количество обращений в службу поддержки. Перед тем как начать перемещение, отправьте пользователям по электронной почте следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="961a6-p104">When moving OneDrive sites between geo locations, it's important to communicate to your users what to expect. This can help reduce user confusion and calls to your help desk. Email your users before the move and let them know the following information:</span></span>

- <span data-ttu-id="961a6-120">время начала перемещения и его длительность;</span><span class="sxs-lookup"><span data-stu-id="961a6-120">When the move is expected to start and how long it is expected to take</span></span>
- <span data-ttu-id="961a6-121">географическое расположение, в которое переносится OneDrive, и новый URL-адрес для доступа к нему;</span><span class="sxs-lookup"><span data-stu-id="961a6-121">What geo location their OneDrive is moving to, and the URL to access the new location</span></span>
- <span data-ttu-id="961a6-122">напомните, что необходимо закрыть файлы и не редактировать их во время перемещения;</span><span class="sxs-lookup"><span data-stu-id="961a6-122">They should close their files and not make edits during the move.</span></span>
- <span data-ttu-id="961a6-123">после перемещения разрешения для файлов и параметры общего доступа к файлам остаются без изменений;</span><span class="sxs-lookup"><span data-stu-id="961a6-123">File permissions and sharing will not change as a result of the move.</span></span>
- <span data-ttu-id="961a6-124">чего ожидать от [пользовательского интерфейса в среде с поддержкой нескольких регионов](multi-geo-user-experience.md).</span><span class="sxs-lookup"><span data-stu-id="961a6-124">What to expect from the [user experience in a multi-geo environment](multi-geo-user-experience.md)</span></span>

<span data-ttu-id="961a6-125">Обязательно известите пользователей об успешном окончании перемещения и сообщите, что они могут возобновить работу в OneDrive.</span><span class="sxs-lookup"><span data-stu-id="961a6-125">Be sure to send your users an email when the move has successfully completed informing them that they can resume working in OneDrive.</span></span>

## <a name="scheduling-onedrive-site-moves"></a><span data-ttu-id="961a6-126">Планирование перемещений сайтов OneDrive</span><span class="sxs-lookup"><span data-stu-id="961a6-126">Scheduling OneDrive site moves</span></span>

<span data-ttu-id="961a6-p105">Вы можете заранее спланировать перемещения сайтов OneDrive (описано далее в этой статье). Рекомендуется начать с небольшого количества пользователей для проверки рабочих процессов и стратегий коммуникации. После ознакомления с процессом можно планировать перемещения следующим образом:</span><span class="sxs-lookup"><span data-stu-id="961a6-p105">You can schedule OneDrive site moves in advance (described later in this article). We recommend that you start with a small number of users to validate your workflows and communication strategies. Once you are comfortable with the process, you can schedule moves as follows:</span></span>

- <span data-ttu-id="961a6-130">Можно запланировать до 4000 перемещений за один раз.</span><span class="sxs-lookup"><span data-stu-id="961a6-130">You can schedule up to 4,000 moves at a time.</span></span>
- <span data-ttu-id="961a6-131">После начала перемещения можно продолжить планирование, не превышая 4000 ожидаемых перемещений в очереди в любой момент времени.</span><span class="sxs-lookup"><span data-stu-id="961a6-131">As the moves begin, you can schedule more, with a maximum of 4,000 pending moves in the queue and any given time.</span></span>
- <span data-ttu-id="961a6-132">Максимальный размер OneDrive, который можно переместить, составляет 1 терабайт (1 ТБ).</span><span class="sxs-lookup"><span data-stu-id="961a6-132">The maximum size of a OneDrive that can be moved is 1 terabyte (1 TB).</span></span>

## <a name="moving-a-onedrive-site"></a><span data-ttu-id="961a6-133">Перемещение сайта OneDrive</span><span class="sxs-lookup"><span data-stu-id="961a6-133">Moving a OneDrive site</span></span>

<span data-ttu-id="961a6-p106">Чтобы выполнить перемещение OneDrive в географическом формате, администратор клиента должен сначала задать предпочтительное расположение данных (PDL) пользователя в соответствующем географическом расположении. После настройки PDL подождите не менее 24 часов, чтобы обновление PDL было синхронизировано между географическими расположениями до того, как будет начато перемещение OneDrive.</span><span class="sxs-lookup"><span data-stu-id="961a6-p106">To perform a OneDrive geo move, the tenant administrator must first set the user's Preferred Data Location (PDL) to the appropriate geo location. Once the PDL is set, wait for at least 24 hours for the PDL update to sync across the geo locations before starting the OneDrive geo move.</span></span>

<span data-ttu-id="961a6-136">При использовании командлетов Geo Move подключитесь к службе SPO в текущем географическом расположении OneDrive пользователя с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="961a6-136">When using the geo move cmdlets, connect to SPO Service at the user's current OneDrive geo location, using the following syntax:</span></span>

`Connect-SPOService -url https://<tenantName>-admin.sharepoint.com`

<span data-ttu-id="961a6-137">Например: чтобы переместить OneDrive для пользователя "Matt@contosoenergy.onmicrosoft.com", подключитесь к центру администрирования SharePoint в евро, так как OneDrive пользователя находится в географическом расположении EUR:</span><span class="sxs-lookup"><span data-stu-id="961a6-137">For example: To move OneDrive of user 'Matt@contosoenergy.onmicrosoft.com', connect to EUR SharePoint Admin center as the user's OneDrive is in EUR geo location:</span></span>

`Connect-SPOSservice -url https://contosoenergyeur-admin.sharepoint.com`

![Снимок экрана: окно PowerShell с командлетом connect-sposervice](../media/move-onedrive-between-geo-locations-image1.png)

## <a name="validating-the-environment"></a><span data-ttu-id="961a6-139">Проверка среды</span><span class="sxs-lookup"><span data-stu-id="961a6-139">Validating the environment</span></span>

<span data-ttu-id="961a6-140">Прежде чем начинать перемещение OneDrive в отношении геообъекта, рекомендуем проверить среду.</span><span class="sxs-lookup"><span data-stu-id="961a6-140">Before you start a OneDrive geo move, we recommend that you validate the environment.</span></span>

<span data-ttu-id="961a6-141">Чтобы проверить, все ли геообъекты совместимы, выполните такую команду:</span><span class="sxs-lookup"><span data-stu-id="961a6-141">To ensure that all geo locations are compatible, run:</span></span>

`Get-SPOGeoMoveCrossCompatibilityStatus`

<span data-ttu-id="961a6-142">Вы увидите список ваших геообъектов, а контент, который можно перемещать между ними будет обозначен как Compatible (Совместимый).</span><span class="sxs-lookup"><span data-stu-id="961a6-142">You will see a list of your geo locations and whether content can be moved between will be denoted as "Compatible".</span></span> <span data-ttu-id="961a6-143">Если команда возвращает значение Incompatible (Несовместимый), попробуйте проверить состояние позднее.</span><span class="sxs-lookup"><span data-stu-id="961a6-143">If the command returns "Incompatible" please retry validating the status at a later date.</span></span>

<span data-ttu-id="961a6-144">Переместить службу OneDrive невозможно, если она, к примеру, содержит дочерний сайт.</span><span class="sxs-lookup"><span data-stu-id="961a6-144">If a OneDrive contains a subsite, for example, it cannot be moved.</span></span> <span data-ttu-id="961a6-145">Чтобы проверить возможность перемещения OneDrive, выполните командлет Start-SPOUserAndContentMove с параметром -ValidationOnly.</span><span class="sxs-lookup"><span data-stu-id="961a6-145">You can use the Start-SPOUserAndContentMove cmdlet with the -ValidationOnly parameter to validate if the OneDrive is able to be moved:</span></span>

`Start-SPOUserAndContentMove -UserPrincipalName <UPN> -DestinationDataLocation <DestinationDataLocation> -ValidationOnly`

<span data-ttu-id="961a6-p109">Если служба OneDrive готова к перемещению, вернется отклик, указывающий на успешное выполнение. Если же есть состояние удержания по юридическим причинам или дочерний сайт, что будет препятствовать перемещению, вернется отклик, указывающий на ошибку. Убедившись в том, что служба OneDrive готова к перемещению, начинайте эту процедуру.</span><span class="sxs-lookup"><span data-stu-id="961a6-p109">This will return Success if the OneDrive is ready to be moved or Fail if there is a legal hold or subsite that would prevent the move. Once you have validated that the OneDrive is ready to move, you can start the move.</span></span>

## <a name="start-a-onedrive-geo-move"></a><span data-ttu-id="961a6-148">Перемещение OneDrive в отношении геообъекта</span><span class="sxs-lookup"><span data-stu-id="961a6-148">Start a OneDrive geo move</span></span>

<span data-ttu-id="961a6-149">Чтобы начать перемещение, выполните такую команду:</span><span class="sxs-lookup"><span data-stu-id="961a6-149">To start the move, run:</span></span>  

`Start-SPOUserAndContentMove -UserPrincipalName <UserPrincipalName> -DestinationDataLocation <DestinationDataLocation>`

<span data-ttu-id="961a6-150">Используйте эти параметры:</span><span class="sxs-lookup"><span data-stu-id="961a6-150">Using these parameters:</span></span>

-   <span data-ttu-id="961a6-151">_UserPrincipalName_ — имя участника-пользователя, OneDrive которого перемещается.</span><span class="sxs-lookup"><span data-stu-id="961a6-151">_UserPrincipalName_ – UPN of the user whose OneDrive is being moved.</span></span>

-   <span data-ttu-id="961a6-p110">_Дестинатиондаталокатион_ — географическое расположение, в котором необходимо переместить OneDrive. Это значение должно совпадать с расположением данных, предпочитаемым пользователем.</span><span class="sxs-lookup"><span data-stu-id="961a6-p110">_DestinationDataLocation_ – Geo-Location where the OneDrive needs to be moved. This should be same as the user's preferred data location.</span></span>

<span data-ttu-id="961a6-154">Например, чтобы переместить OneDrive matt@contosoenergy.onmicrosoft.com из Европы в Австралию, выполните такую команду:</span><span class="sxs-lookup"><span data-stu-id="961a6-154">For example, to move the OneDrive of matt@contosoenergy.onmicrosoft.com from EUR to AUS, run:</span></span>

`Start-SPOUserAndContentMove -UserPrincipalName matt@contosoenergy.onmicrosoft.com -DestinationDataLocation AUS`

![Снимок экрана: окно PowerShell с командлетом Start-SPOUserAndContentMove](../media/move-onedrive-between-geo-locations-image2.png)

<span data-ttu-id="961a6-156">Чтобы запланировать перемещение в отношении геообъекта на более позднее время, используйте один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="961a6-156">To schedule a geo move for a later time, use one of the following parameters:</span></span>

-   <span data-ttu-id="961a6-p111">_PreferredMoveBeginDate_ — предполагаемое время начала перемещения. Должно быть задано в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="961a6-p111">_PreferredMoveBeginDate_ – The move will likely begin at this specified time. Time must be specified in Coordinated Universal Time (UTC).</span></span>

-   <span data-ttu-id="961a6-p112">_PreferredMoveEndDate_ — предполагаемое время завершения перемещения (самый короткий период). Должно быть задано в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="961a6-p112">_PreferredMoveEndDate_ – The move will likely be completed by this specified time, on a best effort basis. Time must be specified in Coordinated Universal Time (UTC).</span></span> 

## <a name="cancel-a-onedrive-geo-move"></a><span data-ttu-id="961a6-161">Отмена перемещения OneDrive в отношении геообъекта</span><span class="sxs-lookup"><span data-stu-id="961a6-161">Cancel a OneDrive geo move</span></span> 

<span data-ttu-id="961a6-162">Вы можете остановить географическое перемещение OneDrive пользователя, если перемещение не выполняется или не завершено с помощью командлета:</span><span class="sxs-lookup"><span data-stu-id="961a6-162">You can stop the geo move of a user's OneDrive, provided the move is not in progress or completed by using the cmdlet:</span></span>

`Stop-SPOUserAndContentMove – UserPrincipalName <UserPrincipalName>`

<span data-ttu-id="961a6-163">Здесь _UserPrincipalName_ — имя участника-пользователя, перемещение OneDrive которого нужно остановить.</span><span class="sxs-lookup"><span data-stu-id="961a6-163">Where _UserPrincipalName_ is the UPN of the user whose OneDrive move you want to stop.</span></span>

## <a name="determining-current-status"></a><span data-ttu-id="961a6-164">Определение текущего состояния</span><span class="sxs-lookup"><span data-stu-id="961a6-164">Determining current status</span></span>

<span data-ttu-id="961a6-165">С помощью командлета Get – Спаусерандконтентмовестате можно проверить состояние географического перемещения OneDrive, который вы подключились, с помощью командлета Get –.</span><span class="sxs-lookup"><span data-stu-id="961a6-165">You can check the status of a OneDrive geo move in or out of the geo that you're connected to by using the Get-SPOUserAndContentMoveState cmdlet.</span></span>

<span data-ttu-id="961a6-166">Состояния перемещения описаны в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="961a6-166">The move statuses are described in the following table.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="961a6-167"><strong>Состояние</strong></span><span class="sxs-lookup"><span data-stu-id="961a6-167"><strong>Status</strong></span></span></th>
<th align="left"><span data-ttu-id="961a6-168"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="961a6-168"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="961a6-169">NotStarted</span><span class="sxs-lookup"><span data-stu-id="961a6-169">NotStarted</span></span></td>
<td align="left"><span data-ttu-id="961a6-170">Перемещение не начато.</span><span class="sxs-lookup"><span data-stu-id="961a6-170">The move has not started.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="961a6-171">InProgress (<em>n</em>/4)</span><span class="sxs-lookup"><span data-stu-id="961a6-171">InProgress (<em>n</em>/4)</span></span></td>
<td align="left"><span data-ttu-id="961a6-172">Перемещение в процессе и находится в одном из следующих состояний: "проверка" (1/4), "резервное копирование" (2/4), "восстановление" (3/4), "очистка" (4/4).</span><span class="sxs-lookup"><span data-stu-id="961a6-172">The move is in progress in one of the following states: Validation (1/4), Backup (2/4), Restore (3/4), Cleanup (4/4).</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="961a6-173">Success</span><span class="sxs-lookup"><span data-stu-id="961a6-173">Success</span></span></td>
<td align="left"><span data-ttu-id="961a6-174">Перемещение успешно завершено.</span><span class="sxs-lookup"><span data-stu-id="961a6-174">The move has completed successfully.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="961a6-175">Failed</span><span class="sxs-lookup"><span data-stu-id="961a6-175">Failed</span></span></td>
<td align="left"><span data-ttu-id="961a6-176">Перемещение не удалось выполнить.</span><span class="sxs-lookup"><span data-stu-id="961a6-176">The move failed.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="961a6-177">Чтобы узнать состояние перемещения определенного пользователя, используйте параметр UserPrincipalName:</span><span class="sxs-lookup"><span data-stu-id="961a6-177">To find the status of a specific user's move, use the UserPrincipalName parameter:</span></span>

`Get-SPOUserAndContentMoveState -UserPrincipalName <UPN>`

<span data-ttu-id="961a6-178">Чтобы найти состояние всех перемещений в географическом расположении или из него, к которому вы подключены, используйте параметр Мовестате с одним из следующих значений: NotStarted, Progress, Success, Failed.</span><span class="sxs-lookup"><span data-stu-id="961a6-178">To find the status of all of the moves in or out of the geo location that you're connected to, use the MoveState parameter with one of the following values: NotStarted, InProgress, Success, Failed, All.</span></span>

`Get-SPOUserAndContentMoveState -MoveState <value>`

<span data-ttu-id="961a6-179">Для более подробного описания состояния перемещения вы можете добавить параметр `-Verbose`.</span><span class="sxs-lookup"><span data-stu-id="961a6-179">You can also add the `-Verbose` parameter for more verbose descriptions of the move state.</span></span>

## <a name="user-experience"></a><span data-ttu-id="961a6-180">Взаимодействие с пользователем</span><span class="sxs-lookup"><span data-stu-id="961a6-180">User Experience</span></span>

<span data-ttu-id="961a6-p113">Перемещение OneDrive пользователей в другой геообъект должно проходить максимально незаметно для них. Если не считать кратковременного состояния доступа только для чтения при перемещении, после завершения этого процесса существующие ссылки и разрешения будут доступны в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="961a6-p113">Users of OneDrive should notice minimal disruption if their OneDrive is moved to a different geo location. Aside from a brief read-only state during the move, existing links and permissions will continue to work as expected once the move is completed.</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="961a6-183">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="961a6-183">OneDrive for Business</span></span>

<span data-ttu-id="961a6-p114">Пока выполняется перемещение, в OneDrive пользователя задается значение только для чтения. Когда перемещение будет завершено, пользователь направляется в OneDrive в новом географическом расположении при переходе на OneDrive — средство запуска приложений Microsoft 365 или веб-браузер.</span><span class="sxs-lookup"><span data-stu-id="961a6-p114">While the move is in progress the user's OneDrive is set to read-only. Once the move is completed, the user is directed to their OneDrive in the new geo location when they navigate to OneDrive the Microsoft 365 app launcher or a web browser.</span></span>

### <a name="permissions-on-onedrive-content"></a><span data-ttu-id="961a6-186">Разрешения для содержимого OneDrive</span><span class="sxs-lookup"><span data-stu-id="961a6-186">Permissions on OneDrive content</span></span>

<span data-ttu-id="961a6-187">Пользователи с разрешениями на доступ к контенту OneDrive продолжат доступ к контенту во время перемещения и после его завершения.</span><span class="sxs-lookup"><span data-stu-id="961a6-187">Users with permissions to OneDrive content will continue to have access to the content during the move and after it's complete.</span></span>

### <a name="onedrive-sync-client"></a><span data-ttu-id="961a6-188">Клиент синхронизации OneDrive</span><span class="sxs-lookup"><span data-stu-id="961a6-188">OneDrive Sync Client</span></span> 

<span data-ttu-id="961a6-p115">Когда будет выполнено перемещение OneDrive в отношении геообъекта, клиент синхронизации OneDrive автоматически обнаружит и легко перенесет синхронизацию в новое расположение OneDrive. Пользователю не нужно выполнять повторный вход или любые другие действия. (Требуется клиент синхронизации версии 17.3.6943.0625 или более поздней.)</span><span class="sxs-lookup"><span data-stu-id="961a6-p115">The OneDrive sync client will automatically detect and seamlessly transfer syncing to the new OneDrive location once the OneDrive geo move is complete. The user does not need to sign-in again or take any other action.  (Version 17.3.6943.0625 or later of the sync client required.)</span></span>

<span data-ttu-id="961a6-192">Если пользователь попробует обновить файл во время перемещения OneDrive в отношении геообъекта, клиент синхронизации уведомит его о том, что отправка файла при выполнении перемещения приостанавливается.</span><span class="sxs-lookup"><span data-stu-id="961a6-192">If a user updates a file while the OneDrive geo move is in progress, the sync client will notify them that file uploads are pending while the move is underway.</span></span>

### <a name="sharing-links"></a><span data-ttu-id="961a6-193">Предоставление ссылок</span><span class="sxs-lookup"><span data-stu-id="961a6-193">Sharing links</span></span> 

<span data-ttu-id="961a6-194">Когда перемещение OneDrive в отношении геообъекта будет завершено, для существующих предоставленных ссылок на перемещенные файлы будет автоматически выполняться перенаправление на новый геообъект.</span><span class="sxs-lookup"><span data-stu-id="961a6-194">Upon OneDrive geo move completion, the existing shared links for the files that were moved will automatically redirect to the new geo location.</span></span>

### <a name="onenote-experience"></a><span data-ttu-id="961a6-195">Интерфейс OneNote</span><span class="sxs-lookup"><span data-stu-id="961a6-195">OneNote Experience</span></span> 

<span data-ttu-id="961a6-p116">Когда перемещение OneDrive в отношении геообъекта будет завершено, приложение UWP (универсальное) и клиент OneNote win32 автоматически обнаружат и легко синхронизируют записные книжки с новым расположением OneDrive. Пользователю не нужно будет выполнять повторный вход или любые другие действия. Во время выполнения перемещения OneDrive в отношении геообъекта единственным отображаемым индикатором для пользователя является уведомление об ошибке синхронизации записной книжки. Эта возможность доступна для следующих клиентских версий OneNote:</span><span class="sxs-lookup"><span data-stu-id="961a6-p116">OneNote win32 client and UWP (Universal) App will automatically detect and seamlessly sync notebooks to the new OneDrive location once OneDrive geo move is complete. The user does not need to sign-in again or take any other action. The only visible indicator to the user is notebook sync would fail when OneDrive geo move is in progress. This experience is available on the following OneNote client versions:</span></span>

-   <span data-ttu-id="961a6-200">OneNote win32 версии 16.0.8326.2096 (или более поздней);</span><span class="sxs-lookup"><span data-stu-id="961a6-200">OneNote win32 – Version 16.0.8326.2096 (and later)</span></span>

-   <span data-ttu-id="961a6-201">OneNote UWP версии 16.0.8431.1006 (или более поздней);</span><span class="sxs-lookup"><span data-stu-id="961a6-201">OneNote UWP – Version 16.0.8431.1006 (and later)</span></span>

-   <span data-ttu-id="961a6-202">приложение OneNote Mobile версии 16.0.8431.1011 (или более поздней).</span><span class="sxs-lookup"><span data-stu-id="961a6-202">OneNote Mobile App – Version 16.0.8431.1011 (and later)</span></span>

### <a name="teams-app"></a><span data-ttu-id="961a6-203">Приложение Teams</span><span class="sxs-lookup"><span data-stu-id="961a6-203">Teams app</span></span>

<span data-ttu-id="961a6-p117">Когда перемещение OneDrive в отношении геообъекта будет завершено, пользователи получат доступ к своим файлам OneDrive в приложении Teams. Кроме того, файлы, отправленные из OneDrive через чат Teams до такого перемещения, будут продолжать работать и после него.</span><span class="sxs-lookup"><span data-stu-id="961a6-p117">Upon OneDrive geo move completion, users will have access to their OneDrive files on the Teams app. Additionally, files shared via Teams chat from their OneDrive prior to geo move will continue to work after move is complete.</span></span>

### <a name="onedrive-for-business-mobile-app-ios"></a><span data-ttu-id="961a6-206">Мобильное приложение OneDrive для бизнеса (iOS)</span><span class="sxs-lookup"><span data-stu-id="961a6-206">OneDrive for Business Mobile App (iOS)</span></span> 

<span data-ttu-id="961a6-207">Когда перемещение OneDrive в отношении геообъекта будет завершено, пользователю понадобится выйти из мобильного приложения для iOS и снова войти в него. Благодаря этому будет выполнена синхронизация с новым расположением OneDrive.</span><span class="sxs-lookup"><span data-stu-id="961a6-207">Upon OneDrive geo move completion, the user would need to sign out and sign in again on the iOS Mobile App to sync to the new OneDrive location.</span></span>

### <a name="existing-followed-groups-and-sites"></a><span data-ttu-id="961a6-208">Существующие отслеживаемые группы и сайты</span><span class="sxs-lookup"><span data-stu-id="961a6-208">Existing followed groups and sites</span></span>

<span data-ttu-id="961a6-p118">Отслеживаемые сайты и группы будут отображаться в OneDrive пользователя независимо от их географических расположений. Сайты и группы, размещенные в другом географическом расположении, открываются на отдельной вкладке.</span><span class="sxs-lookup"><span data-stu-id="961a6-p118">Followed sites and groups will show up in the user's OneDrive regardless of their geo location. Sites and groups hosted in another geo location will open in a separate tab.</span></span>

### <a name="delve-geo-url-updates"></a><span data-ttu-id="961a6-211">Обновления для географических URL-адресов delve</span><span class="sxs-lookup"><span data-stu-id="961a6-211">Delve Geo URL updates</span></span>

<span data-ttu-id="961a6-212">Пользователи будут отправлены в элемент GEO, соответствующий их PDL, только после того, как они были перемещены в новый географическое хранилище.</span><span class="sxs-lookup"><span data-stu-id="961a6-212">Users will be sent to the Delve geo corresponding to their PDL only after their OneDrive has been moved to the new geo.</span></span>
