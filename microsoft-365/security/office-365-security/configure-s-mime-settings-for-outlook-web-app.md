---
title: Настройка параметров S/MIME в Exchange Online для Outlook в Интернете
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Краткое описание администраторов Exchange Online, необходимых для просмотра и настройки параметров S/MIME в Outlook в Интернете в Exchange Online.
ms.openlocfilehash: 759e48544e9c9dedca15500edb56e9111987bf93
ms.sourcegitcommit: ba223b4fd069fc6fd09c2a2e34c770a18bc7b2a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "39866341"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="1b52b-103">Настройка параметров S/MIME в Exchange Online для Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="1b52b-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

<span data-ttu-id="1b52b-104">В качестве администратора Exchange Online можно настроить Outlook в Интернете (прежнее название — Outlook Web App), чтобы разрешить отправку и получение сообщений, защищенных с помощью S/MIME.</span><span class="sxs-lookup"><span data-stu-id="1b52b-104">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="1b52b-105">Используйте командлеты **Get-SmimeConfig** и **Set-SmimeConfig** для просмотра и управления этой функцией в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b52b-105">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="1b52b-106">Сведения о подключении к Exchange Online PowerShell см. в статье [Подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="1b52b-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

<span data-ttu-id="1b52b-107">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-smimeconfig) и [Set/SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).</span><span class="sxs-lookup"><span data-stu-id="1b52b-107">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="1b52b-108">Рекомендации для Chrome</span><span class="sxs-lookup"><span data-stu-id="1b52b-108">Considerations for Chrome</span></span>

<span data-ttu-id="1b52b-109">Чтобы использовать S/MIME в Outlook в Интернете в веб-браузере Google Chrome, вы (или другой администратор) должны настроить и настроить политику Чромиум с именем **екстенсионинсталлфорцелист** , чтобы установить расширение Microsoft S/MIME в Chrome.</span><span class="sxs-lookup"><span data-stu-id="1b52b-109">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="1b52b-110">Значение политики — `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span><span class="sxs-lookup"><span data-stu-id="1b52b-110">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="1b52b-111">Обратите внимание, что для применения этой политики требуются компьютеры, присоединенные к домену, поэтому для эффективного использования S/MIME в Chrome необходимы компьютеры, присоединенные к домену.</span><span class="sxs-lookup"><span data-stu-id="1b52b-111">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="1b52b-112">Подробные сведения о политике **екстенсионинсталлфорцелист** можно найти в статье [екстенсионинсталлфорцелист](https://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist).</span><span class="sxs-lookup"><span data-stu-id="1b52b-112">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist).</span></span>

<span data-ttu-id="1b52b-113">Этот шаг является необходимым условием для использования Chrome; Он не заменяет элемент управления S/MIME, установленный пользователями.</span><span class="sxs-lookup"><span data-stu-id="1b52b-113">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="1b52b-114">При первом использовании S/MIME пользователям предлагается скачать и установить элемент управления S/MIME в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="1b52b-114">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="1b52b-115">Кроме того, пользователи могут активно перейти к параметру **S/MIME** в Outlook в Интернете, чтобы получить ссылку для скачивания этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1b52b-115">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="1b52b-116">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="1b52b-116">For more information</span></span>

[<span data-ttu-id="1b52b-117">S/MIME для подписи и шифрования сообщений</span><span class="sxs-lookup"><span data-stu-id="1b52b-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
