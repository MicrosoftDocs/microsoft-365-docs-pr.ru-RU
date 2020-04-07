---
title: Сведения о барьерах информации
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Используйте информационные барьеры, чтобы обеспечить соответствие требованиям, используя Microsoft Teams в вашей организации.
ms.openlocfilehash: f063a18dcadf5de74b43b2efeba3910f65e40102
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153501"
---
# <a name="information-barriers"></a><span data-ttu-id="08e51-103">Информационные барьеры</span><span class="sxs-lookup"><span data-stu-id="08e51-103">Information barriers</span></span>

## <a name="overview"></a><span data-ttu-id="08e51-104">Обзор</span><span class="sxs-lookup"><span data-stu-id="08e51-104">Overview</span></span>

<!--

# Information barriers (click-through test)

## Overview



 [![Click-Through for Information Barriers](./media/information-barriers/clickthrough-information-barriers-thumbnail.png)](./media/information-barriers/clickthrough-information-barriers.pdf)


Click through an overview of Information Barriers: [PDF](./media/information-barriers/clickthrough-information-barriers.pdf) | [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/Click-Through-Test/microsoft-365/compliance/media/information-barriers/Clickthrough-Information-Barriers.pptx)

OLD: Move comment field here

 [![Click-Through for Information Barriers](./media/information-barriers/Clickthrough_InformationBarriers_Thumbnail.png)](./media/information-barriers/Clickthrough_InformationBarriers.pdf)

For the PowerPoint slide of this Click-Through, click [here](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/Click-Through-Test/microsoft-365/compliance/media/information-barriers/InfoBarriersExample.pptx).

>[!Tip]
>Try this new [Click-Through on information barriers](media/information-barriers/Clickthrough_InformationBarriers.pdf) for a quick overview of the essential facts.
>

--> 


<span data-ttu-id="08e51-105">Облачные службы Майкрософт включают мощные возможности общения и совместной работы.</span><span class="sxs-lookup"><span data-stu-id="08e51-105">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="08e51-106">Однако предположим, что вы хотите ограничить связь между двумя группами, чтобы избежать конфликта интересов в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="08e51-106">But suppose that you want to restrict communications between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="08e51-107">Или, возможно, вы хотите ограничить связь между определенными пользователями в Организации, чтобы защитить внутреннюю информацию.</span><span class="sxs-lookup"><span data-stu-id="08e51-107">Or, perhaps you want to restrict communications between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="08e51-108">Microsoft 365 обеспечивает взаимодействие и совместную работу между группами и организациями, поэтому существует ли способ ограничения взаимодействия между определенными группами пользователей, когда это необходимо?</span><span class="sxs-lookup"><span data-stu-id="08e51-108">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communications among specific groups of users when necessary?</span></span> <span data-ttu-id="08e51-109">С помощью информационных барьеров вы можете!</span><span class="sxs-lookup"><span data-stu-id="08e51-109">With information barriers, you can!</span></span> 

<span data-ttu-id="08e51-110">На этом этапе можно выполнить развертывание, начиная с Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="08e51-110">Information barriers are rolling out now, beginning with Microsoft Teams.</span></span> <span data-ttu-id="08e51-111">Предполагая, что ваша [Подписка](#required-licenses-and-permissions) включает в себя барьеры информации, администратор соответствия требованиям или администратор по управлению данными может определять политики для разрешения или запрета связи между группами пользователей в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="08e51-111">Assuming your [subscription](#required-licenses-and-permissions) includes information barriers, a compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="08e51-112">Политики барьера информации могут использоваться в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="08e51-112">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="08e51-113">Пользователь в дне Trader Group не должен общаться с группой маркетинга</span><span class="sxs-lookup"><span data-stu-id="08e51-113">User in the day trader group should not communicate with the marketing team</span></span>
- <span data-ttu-id="08e51-114">Сотрудники отдела финансов, работающие с конфиденциальной информацией о компании, не должны общаться с определенными группами в Организации</span><span class="sxs-lookup"><span data-stu-id="08e51-114">Finance personnel working on confidential company information should not communicate with certain groups within their organization</span></span>
- <span data-ttu-id="08e51-115">Внутренняя группа с коммерческими секретными материалами не должна звонить или общаться с людьми в определенных группах в Организации</span><span class="sxs-lookup"><span data-stu-id="08e51-115">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="08e51-116">Справочная группа должна обращаться к сети или общаться только с другими участниками группы разработчиков продуктов</span><span class="sxs-lookup"><span data-stu-id="08e51-116">A research team should only call or chat online with a product development team</span></span>

> [!IMPORTANT]
> <span data-ttu-id="08e51-117">Информационные барьеры ***поддерживают только*** два способа ограничения.</span><span class="sxs-lookup"><span data-stu-id="08e51-117">Information barriers ***only supports*** two way restrictions.</span></span> <span data-ttu-id="08e51-118">Один из таких ограничений, например маркетинг, может общаться с днями недели, но день не ***может поддерживать обмен данными с маркетингом***.</span><span class="sxs-lookup"><span data-stu-id="08e51-118">One way restrictions, such as marketing can communicate with day traders, but day traders cannot communicate with marketing ***is not supported***.</span></span>

<span data-ttu-id="08e51-119">Для всех приведенных ниже примеров сценариев (и более) можно определить политики информационных барьеров, чтобы запретить или разрешить взаимодействие в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="08e51-119">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications in Microsoft Teams.</span></span> <span data-ttu-id="08e51-120">Такие политики могут препятствовать абонентам звонить или общаться, которые им не нужны, или разрешить пользователям общаться только с определенными группами в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="08e51-120">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="08e51-121">С действующими политиками для работы с информационными барьерами, когда пользователи, покрытые этими политиками, пытаются связаться с другими пользователями в Microsoft Teams, выполняются проверки, чтобы запретить (или разрешить) связь (как определено политиками барьера информации).</span><span class="sxs-lookup"><span data-stu-id="08e51-121">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate with others in Microsoft Teams, checks are done to prevent (or allow) communication (as defined by information barrier policies).</span></span> <span data-ttu-id="08e51-122">Чтобы узнать больше о пользовательском интерфейсе с помощью барьеров информации, ознакомьтесь с разделом [Information барьеры в Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span><span class="sxs-lookup"><span data-stu-id="08e51-122">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="08e51-123">В настоящее время барьеры информации не применяются к сообщениям электронной почты или к общему доступу к файлам через SharePoint Online или OneDrive.</span><span class="sxs-lookup"><span data-stu-id="08e51-123">Currently, information barriers do not apply to email communications or to file sharing through SharePoint Online or OneDrive.</span></span> <span data-ttu-id="08e51-124">Кроме того, барьеры информации не зависят от [ограничений на соответствие требованиям](set-up-compliance-boundaries.md).</span><span class="sxs-lookup"><span data-stu-id="08e51-124">In addition, information barriers are independent from [compliance boundaries](set-up-compliance-boundaries.md).</span></span><p><span data-ttu-id="08e51-125">Перед определением и применением политик барьера данных убедитесь, что в Организации не действуют [политики адресной книги Exchange](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) .</span><span class="sxs-lookup"><span data-stu-id="08e51-125">Before you define and apply information barrier policies, make sure your organization does not have [Exchange address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) in effect.</span></span> <span data-ttu-id="08e51-126">(Барьеры на основе информации основаны на политиках адресных книг.)</span><span class="sxs-lookup"><span data-stu-id="08e51-126">(Information barriers are based on address book policies.)</span></span> 

## <a name="what-happens-with-information-barriers"></a><span data-ttu-id="08e51-127">Что происходит с барьерами информации</span><span class="sxs-lookup"><span data-stu-id="08e51-127">What happens with information barriers</span></span>

<span data-ttu-id="08e51-128">При наличии политик барьера информации пользователи, которые не должны общаться с другими пользователями, не смогут найти, выбрать, чат или позвонить этим пользователям.</span><span class="sxs-lookup"><span data-stu-id="08e51-128">When information barrier policies are in place, people who should not communicate with other specific users won't be able to find, select, chat, or call those users.</span></span> <span data-ttu-id="08e51-129">С помощью таких барьеров вы можете предотвратить несанкционированный обмен данными.</span><span class="sxs-lookup"><span data-stu-id="08e51-129">With information barriers, checks are in place to prevent unauthorized communication.</span></span>

<span data-ttu-id="08e51-130">Изначально информационные барьеры применяются только к разговорам и каналам Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="08e51-130">Initially, information barriers apply to Microsoft Teams chats and channels only.</span></span> <span data-ttu-id="08e51-131">В Microsoft Teams политики информационных барьеров определяют и предотвращают следующие виды неавторизованных коммуникаций.</span><span class="sxs-lookup"><span data-stu-id="08e51-131">In Microsoft Teams, information barrier policies determine and prevent the following kinds of unauthorized communications:</span></span>
- <span data-ttu-id="08e51-132">Поиск пользователя</span><span class="sxs-lookup"><span data-stu-id="08e51-132">Searching for a user</span></span>
- <span data-ttu-id="08e51-133">Добавление участника в группу</span><span class="sxs-lookup"><span data-stu-id="08e51-133">Adding a member to a team</span></span>
- <span data-ttu-id="08e51-134">Начало сеанса беседы с пользователем</span><span class="sxs-lookup"><span data-stu-id="08e51-134">Starting a chat session with someone</span></span>
- <span data-ttu-id="08e51-135">Начало сеанса групповой беседы</span><span class="sxs-lookup"><span data-stu-id="08e51-135">Starting a group chat</span></span>
- <span data-ttu-id="08e51-136">Приглашение пользователя присоединиться к собранию</span><span class="sxs-lookup"><span data-stu-id="08e51-136">Inviting someone to join a meeting</span></span>
- <span data-ttu-id="08e51-137">Совместное использование экрана</span><span class="sxs-lookup"><span data-stu-id="08e51-137">Sharing a screen</span></span>
- <span data-ttu-id="08e51-138">Размещение звонка</span><span class="sxs-lookup"><span data-stu-id="08e51-138">Placing a call</span></span> 

<span data-ttu-id="08e51-139">Если вовлеченные люди включены в политику барьера информации для предотвращения действий, они не смогут продолжить работу.</span><span class="sxs-lookup"><span data-stu-id="08e51-139">If the people involved are included in an information barrier policy to prevent the activity, they will not be able to proceed.</span></span> <span data-ttu-id="08e51-140">Кроме того, в Microsoft Teams можно блокировать связь всех пользователей, включенных в политику барьера информации.</span><span class="sxs-lookup"><span data-stu-id="08e51-140">In addition, potentially, everyone included in an information barrier policy can be blocked from communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="08e51-141">Если пользователи, затронутые политиками барьера информации, входят в одну и ту же команду или группу, они могут быть удалены из этих сеансов чата, а дальнейшие связи с группой могут быть не разрешены.</span><span class="sxs-lookup"><span data-stu-id="08e51-141">When people affected by information barrier policies are part of the same team or group chat, they might be removed from those chat sessions and further communication with the group might not be allowed.</span></span>

<span data-ttu-id="08e51-142">Чтобы узнать больше о пользовательском интерфейсе с помощью барьеров информации, ознакомьтесь с разделом [Information барьеры в Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span><span class="sxs-lookup"><span data-stu-id="08e51-142">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="08e51-143">Обязательные лицензии и разрешения</span><span class="sxs-lookup"><span data-stu-id="08e51-143">Required licenses and permissions</span></span>

<span data-ttu-id="08e51-144">На этом этапе можно выполнить развертывание, а также включить в подписки следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="08e51-144">Information barriers are rolling out now, and are included in subscriptions, such as:</span></span>

- <span data-ttu-id="08e51-145">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="08e51-145">Microsoft 365 E5</span></span>
- <span data-ttu-id="08e51-146">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="08e51-146">Office 365 E5</span></span>
- <span data-ttu-id="08e51-147">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="08e51-147">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="08e51-148">Microsoft 365, защита информации и соответствие требованиям</span><span class="sxs-lookup"><span data-stu-id="08e51-148">Microsoft 365 E5 Information Protection and Compliance</span></span>

<span data-ttu-id="08e51-149">Дополнительные сведения [см.](https://products.office.com/business/security-and-compliance/compliance-solutions)</span><span class="sxs-lookup"><span data-stu-id="08e51-149">For more details, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span></span>

<span data-ttu-id="08e51-150">Чтобы [определить или изменить политики барьера данных](information-barriers-policies.md), необходимо назначить одну из следующих ролей:</span><span class="sxs-lookup"><span data-stu-id="08e51-150">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="08e51-151">Глобальный администратор Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="08e51-151">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="08e51-152">Глобальный администратор Office 365</span><span class="sxs-lookup"><span data-stu-id="08e51-152">Office 365 global administrator</span></span>
- <span data-ttu-id="08e51-153">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="08e51-153">Compliance administrator</span></span>
- <span data-ttu-id="08e51-154">Управление соответствием требованиям (это новая роль)</span><span class="sxs-lookup"><span data-stu-id="08e51-154">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="08e51-155">(Дополнительные сведения о ролях и разрешениях см. [в разделе разрешения в центре безопасности Office 365 & соответствия требованиям](../security/office-365-security/protect-against-threats.md).)</span><span class="sxs-lookup"><span data-stu-id="08e51-155">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](../security/office-365-security/protect-against-threats.md).)</span></span>

<span data-ttu-id="08e51-156">Вы должны быть знакомы с командлетами PowerShell, чтобы определить, проверить или изменить политики барьера данных.</span><span class="sxs-lookup"><span data-stu-id="08e51-156">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="08e51-157">Хотя в [этой статье рассказывается о](information-barriers-policies.md)нескольких примерах командлетов PowerShell, необходимо знать дополнительные сведения, например параметры, для Организации.</span><span class="sxs-lookup"><span data-stu-id="08e51-157">Although we provide several examples of PowerShell cmdlets in the [how-to article](information-barriers-policies.md), you'll need to know additional details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="08e51-158">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="08e51-158">Next steps</span></span>

- [<span data-ttu-id="08e51-159">Дополнительные сведения об барьерах информации в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="08e51-159">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

- [<span data-ttu-id="08e51-160">Просмотр атрибутов, которые можно использовать для политик барьера информации</span><span class="sxs-lookup"><span data-stu-id="08e51-160">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)

- [<span data-ttu-id="08e51-161">Определение политик для барьеров информации</span><span class="sxs-lookup"><span data-stu-id="08e51-161">Define policies for information barriers</span></span>](information-barriers-policies.md)

- [<span data-ttu-id="08e51-162">Изменение (или удаление) политик барьера информации</span><span class="sxs-lookup"><span data-stu-id="08e51-162">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md) 
