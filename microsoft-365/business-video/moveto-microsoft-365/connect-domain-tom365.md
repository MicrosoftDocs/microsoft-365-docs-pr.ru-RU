---
title: Подключение домена к Microsoft 365
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Узнайте, как подключить домен к Microsoft 365.
ms.openlocfilehash: c7827b93b56560579b31bd2abb5a852467565103
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794706"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a><span data-ttu-id="df212-103">Подключение домена к Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="df212-103">Connect your domain to Microsoft 365 for business</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

<span data-ttu-id="df212-104">После того как вы настроите Microsoft 365 и переместите данные электронной почты из Google Workspace, вы можете подключить свой домен к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="df212-104">Once you’ve set up Microsoft 365 and moved your email data from Google Workspace, you can connect your domain to Microsoft 365.</span></span> 

<span data-ttu-id="df212-105">Сначала вам потребуется удалить существующие записи DNS из Google, а затем мы можем добавить новые записи DNS из Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="df212-105">First you will need to delete existing DNS records from Google, then we can add new DNS records from Microsoft 365.</span></span>

## <a name="try-it"></a><span data-ttu-id="df212-106">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="df212-106">Try it!</span></span>

1. <span data-ttu-id="df212-107">Во sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="df212-107">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>
1. <span data-ttu-id="df212-108">Выберите **"Домены",** **"Управление доменами",** **"Просмотр сведений",** **"Управление доменом",** **"DNS"** в левой области.</span><span class="sxs-lookup"><span data-stu-id="df212-108">Select **Domains**, **Manage domains**, **View details**, **Manage domain**, then **DNS** in the left nav.</span></span>
1. <span data-ttu-id="df212-109">Прокрутите вниз до **искусственных записей,** откройте **Google Workspace,** выберите **"Удалить"** и **"Удалить** еще раз".</span><span class="sxs-lookup"><span data-stu-id="df212-109">Scroll down to **Synthetic records**, open **Google Workspace**, select **Delete**, then **Delete** again.</span></span>
1. <span data-ttu-id="df212-110">**Прокрутите** вниз до пользовательских записей ресурсов и удалите все существующие записи DNS, которые отображаются, включая те, которые вы могли создать ранее для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="df212-110">Scroll down to **Custom resource records** and delete any existing DNS records that appear, including any you may have created previously for Microsoft 365.</span></span>
1. <span data-ttu-id="df212-111">Перейдите в [Центр администрирования Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="df212-111">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="df212-112">In the left nav, choose, **Show all**, **Settings**, **Domains**.</span><span class="sxs-lookup"><span data-stu-id="df212-112">In the left nav, choose, **Show all**, **Settings**, **Domains**.</span></span>
1. <span data-ttu-id="df212-113">Затем выберите домен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="df212-113">Then choose your default domain.</span></span>
1. <span data-ttu-id="df212-114">Выберите **"Продолжить** установку", а затем, чтобы подключить домен, выберите **"Продолжить".**</span><span class="sxs-lookup"><span data-stu-id="df212-114">Select **Continue setup**, then, to connect your domain, choose  **Continue**.</span></span>
1. <span data-ttu-id="df212-115">Прокрутите вниз, чтобы просмотреть записи DNS, которые необходимо скопировать в Google.</span><span class="sxs-lookup"><span data-stu-id="df212-115">Scroll down to view the DNS records that need to be copied to Google.</span></span>
1. <span data-ttu-id="df212-116">Откройте **записи MX** и в области **"Указывает на адрес" или "Значение"** скопируйте запись.</span><span class="sxs-lookup"><span data-stu-id="df212-116">Open **MX Records**, and under **Points to address or value**, copy the record.</span></span>
1. <span data-ttu-id="df212-117">Вернись в Google и в **разделе** "Пользовательские записи ресурсов" откройте в dropdown тип записи и выберите **MX.**</span><span class="sxs-lookup"><span data-stu-id="df212-117">Return to Google, and in the **Custom resource records** section, open the record type dropdown and select **MX**.</span></span>
1. <span data-ttu-id="df212-118">В поле **"Данные"** в paste the record you copied.</span><span class="sxs-lookup"><span data-stu-id="df212-118">In the **Data** field, paste the record you copied.</span></span>
1. <span data-ttu-id="df212-119">Затем нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="df212-119">Then select **Add**.</span></span>
1. <span data-ttu-id="df212-120">Повторите процесс для записей CNAME и TXT и добавьте значения на странице управления DNS Google.</span><span class="sxs-lookup"><span data-stu-id="df212-120">Repeat the process for CNAME and TXT records and add the values in the Google DNS management page.</span></span>
1. <span data-ttu-id="df212-121">Вернись в Центр администрирования Microsoft 365 и выберите **"Продолжить".**</span><span class="sxs-lookup"><span data-stu-id="df212-121">Return to the Microsoft 365 Admin center and select **Continue**.</span></span>

    <span data-ttu-id="df212-122">Настройка домена завершена.</span><span class="sxs-lookup"><span data-stu-id="df212-122">Your domain setup is complete.</span></span>