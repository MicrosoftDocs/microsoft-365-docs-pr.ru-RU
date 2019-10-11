---
title: 'Создание отчета о группе ролей администраторов в EOP '
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
description: Администраторы могут узнать, как запустить отчет о группе ролей администратора в Exchange Online Protection (EOP). Этот отчет заносится в журнал, когда администратор добавляет или удаляет участников из групп ролей администраторов, Microsoft Exchange Online Protection (EOP) записывает каждый экземпляр.
ms.openlocfilehash: 59557f6fab2281cd36569b40afcf3e0225bd9347
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441406"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a><span data-ttu-id="52b42-104">Создание отчета о группе ролей администраторов в EOP</span><span class="sxs-lookup"><span data-stu-id="52b42-104">Run an administrator role group report in EOP</span></span>

 <span data-ttu-id="52b42-105">Когда администратор добавляет или удаляет участников из групп ролей администраторов, в Exchange Online Protection (EOP) записываются все экземпляры.</span><span class="sxs-lookup"><span data-stu-id="52b42-105">When an admin adds members to or removes members from administrator role groups, Exchange Online Protection (EOP) logs each occurrence.</span></span> <span data-ttu-id="52b42-106">При запуске отчета о группе ролей администраторов в центре администрирования Exchange записи отображаются в виде результатов поиска и включают затронутые группы ролей, которые изменяют членство в группе ролей, а также сведения о том, когда и как были сделаны обновления членства.</span><span class="sxs-lookup"><span data-stu-id="52b42-106">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="52b42-107">Этот отчет можно использовать для отслеживания изменений в административных разрешениях, назначенных пользователям в организации.</span><span class="sxs-lookup"><span data-stu-id="52b42-107">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="52b42-108">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="52b42-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="52b42-109">Предполагаемое время выполнения: 2 минуты.</span><span class="sxs-lookup"><span data-stu-id="52b42-109">Estimated time to complete: 2 minutes</span></span>

- <span data-ttu-id="52b42-110">Чтобы открыть центр администрирования Exchange, ознакомьтесь со статьей [центр администрирования Exchange в Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="52b42-110">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="52b42-p103">Для выполнения этих процедур необходимы соответствующие разрешения. Сведения о необходимых разрешениях см. в статье Статья "Отчеты" раздела [Разрешения на функции в службе EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="52b42-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Reports" section of the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="52b42-113">Дополнительные сведения о сочетаниях клавиш, которые могут применяться к процедурам, описанным в этой статье, приведены в статье [сочетания клавиш для центра администрирования Exchange в Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="52b42-113">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="52b42-114">Возникли проблемы?</span><span class="sxs-lookup"><span data-stu-id="52b42-114">Having problems?</span></span> <span data-ttu-id="52b42-115">Обратитесь за помощью к форуму [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="52b42-115">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="52b42-116">Запуск отчета о группе ролей администраторов с помощью Центра администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="52b42-116">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="52b42-117">Запустите отчет о группе ролей администраторов, чтобы найти изменения в группах ролей управления в Организации в течение определенного промежутка времени.</span><span class="sxs-lookup"><span data-stu-id="52b42-117">Run the administrator role group report to find the changes to management role groups in your organization within a particular time frame.</span></span>

1. <span data-ttu-id="52b42-118">В Центре администрирования Exchange выберите пункты **Управление соответствием требованиям** \> **Аудит**, а затем выберите команду **Запустить отчет о группе ролей администраторов**.</span><span class="sxs-lookup"><span data-stu-id="52b42-118">In the EAC, navigate to **Compliance management** \> **Auditing**, and choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="52b42-p105">Задайте параметры **Дата начала** и **Дата окончания**. По умолчанию отчет выполняет поиск изменений в группе ролей администраторов за последние две недели.</span><span class="sxs-lookup"><span data-stu-id="52b42-p105">Choose the **Start date** and **End date**. By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

3. <span data-ttu-id="52b42-p106">Чтобы просмотреть изменения в определенной группе ролей, нажмите кнопку **Выбрать группы ролей**. В появившемся диалоговом окне выберите группу или группы ролей, затем нажмите кнопку **ОК**. Чтобы найти все изменения групп ролей, оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="52b42-p106">To view the changes for a specific role group, click **Select role groups**. Select the role group (or groups) in the subsequent dialog box, and click **OK**. You can also leave the field blank to find all changed role groups.</span></span>

4. <span data-ttu-id="52b42-124">Нажмите кнопку **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="52b42-124">Click **Search**.</span></span>

<span data-ttu-id="52b42-p107">Если будут найдены любые изменения, соответствующие заданным критериям, они появятся в области результатов. Чтобы в области сведений увидеть изменения, выберите группу ролей в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="52b42-p107">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="52b42-127">Как проверить, все ли получилось?</span><span class="sxs-lookup"><span data-stu-id="52b42-127">How do you know this worked?</span></span>

<span data-ttu-id="52b42-p108">Если отчет о группе ролей администрирования запущен успешно, группы ролей, измененные в рамках диапазона дат, отображаются в области результатов поиска. Если результатов нет  в указанный диапазон дат группы ролей изменены не были. Если вы считаете, что результаты должны быть, измените диапазон дат и повторно запустите отчет.</span><span class="sxs-lookup"><span data-stu-id="52b42-p108">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="52b42-131">Отслеживание изменений состава группы ролей</span><span class="sxs-lookup"><span data-stu-id="52b42-131">Monitor changes to role group membership</span></span>

<span data-ttu-id="52b42-p109">При добавлении или удалении участников группы ролей результаты поиска в области сведений указывают на изменение состава группы ролей с указанием ее текущих участников. В результатах не говорится явно, кто был добавлен или удален.</span><span class="sxs-lookup"><span data-stu-id="52b42-p109">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="52b42-p110">Чтобы определить, был ли добавлен или удален пользователь, следует сравнить две записи в отчете. Например, рассмотрим следующие записи журнала для группы ролей **HelpDesk**.</span><span class="sxs-lookup"><span data-stu-id="52b42-p110">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="52b42-136">1/27/2018 4:43 PM</span><span class="sxs-lookup"><span data-stu-id="52b42-136">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="52b42-137">Администратор</span><span class="sxs-lookup"><span data-stu-id="52b42-137">Administrator</span></span> <br> <span data-ttu-id="52b42-138">Обновленные участники: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="52b42-138">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="52b42-139">2/06/2018 10:09 AM</span><span class="sxs-lookup"><span data-stu-id="52b42-139">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="52b42-140">Администратор</span><span class="sxs-lookup"><span data-stu-id="52b42-140">Administrator</span></span> <br> <span data-ttu-id="52b42-141">Обновленные участники: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="52b42-141">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="52b42-142">2/19/2018 2:12 PM</span><span class="sxs-lookup"><span data-stu-id="52b42-142">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="52b42-143">Администратор</span><span class="sxs-lookup"><span data-stu-id="52b42-143">Administrator</span></span> <br> <span data-ttu-id="52b42-144">Обновленные участники: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="52b42-144">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="52b42-145">В этом примере администратор внес следующие изменения:</span><span class="sxs-lookup"><span data-stu-id="52b42-145">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="52b42-146">В 2/06/2018 они добавили пользователя tonip.</span><span class="sxs-lookup"><span data-stu-id="52b42-146">On 2/06/2018, they added the user tonip.</span></span>

- <span data-ttu-id="52b42-147">В 2/19/2018 он удалил пользователя pilarp.</span><span class="sxs-lookup"><span data-stu-id="52b42-147">On 2/19/2018, they removed the user pilarp.</span></span>
