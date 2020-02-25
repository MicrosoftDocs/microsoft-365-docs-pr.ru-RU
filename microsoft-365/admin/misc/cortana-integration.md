---
title: Интеграция Кортаны с Office 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7257cb50-0d5c-4f7a-ac2e-9fe5d13bb5cb
description: 'Узнайте, как использовать Кортану, интегрированные с Office 365. Вы можете отключить Кортану в центре администрирования, чтобы ограничить доступ к данным вашей организации. '
ms.openlocfilehash: 21de80d127498dd40db932923a8d650b87b8a24c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42257422"
---
# <a name="cortana-in-office-365"></a><span data-ttu-id="40c5b-104">Кортана в Office 365</span><span class="sxs-lookup"><span data-stu-id="40c5b-104">Cortana in Office 365</span></span>

<span data-ttu-id="40c5b-105">Кортана — это облачный цифровой помощник и Microsoft 365 и служба Office 365, которые работают на ваших устройствах и службах Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="40c5b-105">Cortana is a cloud-based digital assistant and Microsoft 365 and Office 365 service that works across your devices and Microsoft services.</span></span> <span data-ttu-id="40c5b-106">Кортана может использовать сведения, хранящиеся в Microsoft 365 и Office 365, чтобы помочь людям в Организации поддерживать актуальность и получение ценных сведений, предлагаемые задачи и помощь по собраниям, документам и контактам.</span><span class="sxs-lookup"><span data-stu-id="40c5b-106">Cortana can use information stored in Microsoft 365 and Office 365 to help people in your organization stay up to date and get insights, suggested tasks, and help with their meetings, documents, and contacts.</span></span>
  
## <a name="info-for-admins"></a><span data-ttu-id="40c5b-107">Сведения для администраторов</span><span class="sxs-lookup"><span data-stu-id="40c5b-107">Info for admins</span></span>

<span data-ttu-id="40c5b-108">Соответствие требованиям является обязательством, которое корпорация Майкрософт делает для корпоративных клиентов.</span><span class="sxs-lookup"><span data-stu-id="40c5b-108">Compliance is a commitment that Microsoft makes to enterprise customers.</span></span> [<span data-ttu-id="40c5b-109">Узнайте больше о платформе Microsoft для обеспечения соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="40c5b-109">Learn more about the Microsoft compliance framework.</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=2109173)

<span data-ttu-id="40c5b-110">Согласованность с другими службами Microsoft 365 и Office 365 соответствующие функции Кортаны защищены и защищены в соответствии с условиями интерактивной службы, включающей в себя набор обещаний, включающий защиту пользовательских данных от случайных потерь, изменения, несанкционированный доступ или несанкционированный доступ или уничтожение незаконному.</span><span class="sxs-lookup"><span data-stu-id="40c5b-110">Consistent with other Microsoft 365 and Office 365 services, compliant Cortana features are protected and secured subject to the Online Service Terms that includes a set of promises involving protection of user data against accidental loss, alteration, unauthorized disclosure or access, or unlawful destruction.</span></span> <span data-ttu-id="40c5b-111">Все остальные функции Кортаны (например, необязательные подключенные службы Кортаны) подчиняются [соглашению об услугах Майкрософт](https://go.microsoft.com/fwlink/p/?LinkId=2109174) и [заявлению о конфиденциальности Майкрософт.](https://go.microsoft.com/fwlink/p/?LinkId=2109175)</span><span class="sxs-lookup"><span data-stu-id="40c5b-111">All other Cortana features (i.e., Cortana optional connected services) are subject to the [Microsoft Services Agreement](https://go.microsoft.com/fwlink/p/?LinkId=2109174) and  [Microsoft Privacy Statement.](https://go.microsoft.com/fwlink/p/?LinkId=2109175)</span></span>

<span data-ttu-id="40c5b-112">Службы кортаны разбиваются на две категории данных, **соответствующие** и **необязательные подключенные службы**, которые можно контролировать.</span><span class="sxs-lookup"><span data-stu-id="40c5b-112">Cortana services are broken into two data categories, **compliant** and **optional connected services**, which you can control.</span></span>

## <a name="turn-off-cortana-optional-connected-services"></a><span data-ttu-id="40c5b-113">Отключить необязательные подключенные службы Кортаны</span><span class="sxs-lookup"><span data-stu-id="40c5b-113">Turn off Cortana optional connected services</span></span>

<span data-ttu-id="40c5b-114">Необязательные службы кортаны могут быть отключены для сотрудников Организации.</span><span class="sxs-lookup"><span data-stu-id="40c5b-114">Cortana optional connected services can be turned off for employees at your organization.</span></span> <span data-ttu-id="40c5b-115">Это приведет к отключению необязательных служб Кортаны в Кортаны в Windows и мобильном приложении Кортаны.</span><span class="sxs-lookup"><span data-stu-id="40c5b-115">This will disable Cortana optional connected services in Cortana on Windows and the Cortana mobile app.</span></span> <span data-ttu-id="40c5b-116">Сюда входят напоминания Кортаны, списки, задачи и другие функции.</span><span class="sxs-lookup"><span data-stu-id="40c5b-116">This includes Cortana reminders, lists, tasks, and other features.</span></span> <span data-ttu-id="40c5b-117">Службы в категории "совместимый" (например, "Кортана OST"), такие как информационный бюллетень кортаны и воспроизводимые сообщения электронной почты в Outlook Mobile, останутся активными.</span><span class="sxs-lookup"><span data-stu-id="40c5b-117">Services in the compliant category (i.e., Cortana OST experiences), such as Cortana’s Briefing email, and Play My Emails in Outlook mobile, will remain active.</span></span>

1. <span data-ttu-id="40c5b-118">В центре администрирования Microsoft 365 выберите**Параметры** **параметров** > и нажмите **кортаны**.</span><span class="sxs-lookup"><span data-stu-id="40c5b-118">In the Microsoft 365 admin center, select **Settings** > **Settings** and select **Cortana**.</span></span>

4. <span data-ttu-id="40c5b-119">Установите флажок **Разрешить Кортане необязательные подключения, чтобы использовать размещенные в организации данные Майкрософт** для включения или отключения взаимодействия с пользователем кортаны.</span><span class="sxs-lookup"><span data-stu-id="40c5b-119">Select the checkbox for **Allow Cortana optional connected experiences to use your organizations's Microsoft hosted data** to enable or disable Cortana connected experiences.</span></span>

5. <span data-ttu-id="40c5b-120">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="40c5b-120">Select **Save changes**.</span></span>

## <a name="turn-off-cortana-ost-experiences"></a><span data-ttu-id="40c5b-121">Отключение АВТОНОМных функций Кортаны</span><span class="sxs-lookup"><span data-stu-id="40c5b-121">Turn off Cortana OST experiences</span></span>

<span data-ttu-id="40c5b-122">Сотрудники Организации могут отказаться от использования OST-файлов по отдельности, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="40c5b-122">Your organization's employees can opt out of Cortana OST experiences individually by following the steps below.</span></span>

1. <span data-ttu-id="40c5b-123">Откройте Outlook Mobile.</span><span class="sxs-lookup"><span data-stu-id="40c5b-123">Open Outlook mobile.</span></span>

2. <span data-ttu-id="40c5b-124">Перейдите в раздел **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="40c5b-124">Go to **Settings**.</span></span>
  
3. <span data-ttu-id="40c5b-125">Выберите пункт **проигрывать мои сообщения**.</span><span class="sxs-lookup"><span data-stu-id="40c5b-125">Select **Play My Emails**.</span></span>

4. <span data-ttu-id="40c5b-126">Установите переключатель в положение отключено для учетных записей, которые требуется отключить.</span><span class="sxs-lookup"><span data-stu-id="40c5b-126">Move the toggle to off on the accounts you want to disable.</span></span>

### <a name="briefing-email"></a><span data-ttu-id="40c5b-127">Информационные сообщения</span><span class="sxs-lookup"><span data-stu-id="40c5b-127">Briefing email</span></span>

<span data-ttu-id="40c5b-128">Отключение Кортаны на панели задач не приводит к отключению информационного сообщения Кортаны.</span><span class="sxs-lookup"><span data-stu-id="40c5b-128">Disabling Cortana on the taskbar won't disable Cortana’s Briefing email.</span></span> <span data-ttu-id="40c5b-129">Сотрудники должны отписываться индивидуально.</span><span class="sxs-lookup"><span data-stu-id="40c5b-129">Employees must unsubscribe individually.</span></span> <span data-ttu-id="40c5b-130">Пользователи организации могут отказаться от использования информационного сообщения Кортаны, выбрав пункт **Отменить подписку** в нижнем колонтитуле сообщения.</span><span class="sxs-lookup"><span data-stu-id="40c5b-130">Individuals from your organization can opt out of Cortana’s Briefing email by selecting **Unsubscribe** in the footer of the message.</span></span>