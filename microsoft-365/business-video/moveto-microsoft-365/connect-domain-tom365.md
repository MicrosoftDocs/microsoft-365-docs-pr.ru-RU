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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Узнайте, как подключить домен к Microsoft 365.
ms.openlocfilehash: 1bec66a43026321ddf1979c73902a533bee3a07b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925114"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a><span data-ttu-id="b8f79-103">Подключение домена к Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b8f79-103">Connect your domain to Microsoft 365 for business</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

<span data-ttu-id="b8f79-104">После того как вы настроите Microsoft 365 и переместите данные электронной почты из Google Workspace, вы можете подключить свой домен к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b8f79-104">Once you’ve set up Microsoft 365 and moved your email data from Google Workspace, you can connect your domain to Microsoft 365.</span></span> 

<span data-ttu-id="b8f79-105">Сначала вам потребуется удалить существующие записи DNS из Google, а затем мы можем добавить новые записи DNS из Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b8f79-105">First you will need to delete existing DNS records from Google, then we can add new DNS records from Microsoft 365.</span></span>

## <a name="try-it"></a><span data-ttu-id="b8f79-106">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="b8f79-106">Try it!</span></span>

1. <span data-ttu-id="b8f79-107">Во sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="b8f79-107">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>
1. <span data-ttu-id="b8f79-108">Select **Domains**, **Manage domains**, **View details**, Manage **domain**, then **DNS** in the left nav.</span><span class="sxs-lookup"><span data-stu-id="b8f79-108">Select **Domains**, **Manage domains**, **View details**, **Manage domain**, then **DNS** in the left nav.</span></span>
1. <span data-ttu-id="b8f79-109">Прокрутите вниз до **искусственных записей,** откройте **Google Workspace,** выберите **"Удалить"** и **"Удалить** еще раз".</span><span class="sxs-lookup"><span data-stu-id="b8f79-109">Scroll down to **Synthetic records**, open **Google Workspace**, select **Delete**, then **Delete** again.</span></span>
1. <span data-ttu-id="b8f79-110">**Прокрутите** вниз до пользовательских записей ресурсов и удалите все существующие записи DNS, которые отображаются, включая те, которые вы могли создать ранее для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b8f79-110">Scroll down to **Custom resource records** and delete any existing DNS records that appear, including any you may have created previously for Microsoft 365.</span></span>
1. <span data-ttu-id="b8f79-111">Перейдите в [Центр администрирования Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="b8f79-111">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="b8f79-112">In the left nav, choose, **Show all**, **Settings**, **Domains**.</span><span class="sxs-lookup"><span data-stu-id="b8f79-112">In the left nav, choose, **Show all**, **Settings**, **Domains**.</span></span>
1. <span data-ttu-id="b8f79-113">Затем выберите домен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b8f79-113">Then choose your default domain.</span></span>
1. <span data-ttu-id="b8f79-114">Выберите **"Продолжить** установку", а затем, чтобы подключить домен, выберите **"Продолжить".**</span><span class="sxs-lookup"><span data-stu-id="b8f79-114">Select **Continue setup**, then, to connect your domain, choose  **Continue**.</span></span>
1. <span data-ttu-id="b8f79-115">Прокрутите вниз, чтобы просмотреть записи DNS, которые необходимо скопировать в Google.</span><span class="sxs-lookup"><span data-stu-id="b8f79-115">Scroll down to view the DNS records that need to be copied to Google.</span></span>
1. <span data-ttu-id="b8f79-116">Откройте **записи MX** и в области **"Указывает на адрес" или "Значение"** скопируйте запись.</span><span class="sxs-lookup"><span data-stu-id="b8f79-116">Open **MX Records**, and under **Points to address or value**, copy the record.</span></span>
1. <span data-ttu-id="b8f79-117">Вернись в Google и в **разделе** "Пользовательские записи ресурсов" откройте в dropdown тип записи и выберите **MX.**</span><span class="sxs-lookup"><span data-stu-id="b8f79-117">Return to Google, and in the **Custom resource records** section, open the record type dropdown and select **MX**.</span></span>
1. <span data-ttu-id="b8f79-118">В поле **"Данные"** в paste the record you copied.</span><span class="sxs-lookup"><span data-stu-id="b8f79-118">In the **Data** field, paste the record you copied.</span></span>
1. <span data-ttu-id="b8f79-119">Затем нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b8f79-119">Then select **Add**.</span></span>
1. <span data-ttu-id="b8f79-120">Повторите процесс для записей CNAME и TXT и добавьте значения на странице управления DNS Google.</span><span class="sxs-lookup"><span data-stu-id="b8f79-120">Repeat the process for CNAME and TXT records and add the values in the Google DNS management page.</span></span>
1. <span data-ttu-id="b8f79-121">Вернись в Центр администрирования Microsoft 365 и выберите **"Продолжить".**</span><span class="sxs-lookup"><span data-stu-id="b8f79-121">Return to the Microsoft 365 Admin center and select **Continue**.</span></span>

    <span data-ttu-id="b8f79-122">Настройка домена завершена.</span><span class="sxs-lookup"><span data-stu-id="b8f79-122">Your domain setup is complete.</span></span>