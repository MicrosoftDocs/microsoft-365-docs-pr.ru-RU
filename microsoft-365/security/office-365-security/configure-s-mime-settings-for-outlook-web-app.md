---
title: Настройка параметров S/MIME — Exchange Online для Outlook в Интернете
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Краткое описание того, что необходимо сделать администраторам Exchange Online для просмотра и настройки параметров S/MIME в Outlook в Интернете в Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a81db5ec933f1d0d6e2944103be53c0169dde62f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165683"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="c5406-103">Настройка параметров S/MIME в Exchange Online для Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="c5406-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c5406-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="c5406-104">**Applies to**</span></span>
- [<span data-ttu-id="c5406-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c5406-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="c5406-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="c5406-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="c5406-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c5406-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="c5406-108">Администратор Exchange Online может настроить Outlook в Интернете (прежнее название — Outlook Web App), чтобы разрешить отправку и получение сообщений с защитой S/MIME.</span><span class="sxs-lookup"><span data-stu-id="c5406-108">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="c5406-109">Используйте **get-SmimeConfig** и **set-SmimeConfig** для просмотра и управления этой функцией в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5406-109">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="c5406-110">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c5406-110">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="c5406-111">Подробные сведения о синтаксисах и параметрах см. в описании [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) и [Set-SmimeConfig.](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)</span><span class="sxs-lookup"><span data-stu-id="c5406-111">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="c5406-112">Вопросы, которые следует учитывать при новых решениях Microsoft Edge (на основе Chromium)</span><span class="sxs-lookup"><span data-stu-id="c5406-112">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="c5406-113">Чтобы использовать S/MIME в Outlook в Интернете в новом веб-браузере [Microsoft Edge,](https://www.microsoft.com/windows/microsoft-edge) необходимо установить и настроить политику браузера Microsoft Edge с именем **ExtensionInstallForcelist,** чтобы установить расширение Microsoft S/MIME в новом Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="c5406-113">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="c5406-114">Значение политики: `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="c5406-114">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="c5406-115">Обратите внимание, что для применения этой политики требуются устройства, присоединимые к домену или Azure AD, поэтому для использования S/MIME в новом браузере Microsoft Edge фактически требуются устройства, которые присоединяются к домену или к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c5406-115">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="c5406-116">Подробные сведения о **политике ExtensionInstallForcelist** см. в [списке ExtensionInstallForcelist.](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)</span><span class="sxs-lookup"><span data-stu-id="c5406-116">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="c5406-117">Это необходимое условие для использования нового Microsoft Edge; Он не заменяет установленный пользователями контроль S/MIME.</span><span class="sxs-lookup"><span data-stu-id="c5406-117">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="c5406-118">При первом использовании S/MIME пользователям будет предложено скачать и установить в Outlook в Интернете контроль S/MIME.</span><span class="sxs-lookup"><span data-stu-id="c5406-118">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="c5406-119">Кроме того, пользователи могут заблаговременно перейти к **S/MIME** в своих параметрах Outlook в Интернете, чтобы получить ссылку для скачивания для этого управления.</span><span class="sxs-lookup"><span data-stu-id="c5406-119">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="c5406-120">Вопросы, которые следует учитывать при chrome</span><span class="sxs-lookup"><span data-stu-id="c5406-120">Considerations for Chrome</span></span>

<span data-ttu-id="c5406-121">Чтобы использовать S/MIME в Outlook в Интернете в веб-браузере Google Chrome, вам (или другому администратору) необходимо установить расширение Microsoft S/MIME в Chrome и настроить политику Chromium с именем **ExtensionInstallForcelist.**</span><span class="sxs-lookup"><span data-stu-id="c5406-121">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="c5406-122">Значение политики: `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="c5406-122">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="c5406-123">Обратите внимание, что для применения этой политики требуются компьютеры, присоединимые к домену, поэтому для использования S/MIME в Chrome фактически требуются компьютеры, присоединимые к домену.</span><span class="sxs-lookup"><span data-stu-id="c5406-123">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="c5406-124">Подробные сведения о **политике ExtensionInstallForcelist** см. в [списке ExtensionInstallForcelist.](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)</span><span class="sxs-lookup"><span data-stu-id="c5406-124">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="c5406-125">Это необходимое условие для использования Chrome; Он не заменяет установленный пользователями контроль S/MIME.</span><span class="sxs-lookup"><span data-stu-id="c5406-125">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="c5406-126">При первом использовании S/MIME пользователям будет предложено скачать и установить в Outlook в Интернете контроль S/MIME.</span><span class="sxs-lookup"><span data-stu-id="c5406-126">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="c5406-127">Кроме того, пользователи могут заблаговременно перейти к **S/MIME** в своих параметрах Outlook в Интернете, чтобы получить ссылку для скачивания для этого управления.</span><span class="sxs-lookup"><span data-stu-id="c5406-127">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="c5406-128">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c5406-128">For more information</span></span>

[<span data-ttu-id="c5406-129">S/MIME для подписи и шифрования сообщений</span><span class="sxs-lookup"><span data-stu-id="c5406-129">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
