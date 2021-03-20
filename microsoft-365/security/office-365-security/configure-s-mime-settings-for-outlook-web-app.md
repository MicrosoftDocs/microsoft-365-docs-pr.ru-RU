---
title: Настройка параметров S/MIME - Exchange Online для Outlook в Интернете
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
ms.openlocfilehash: 6ab1aaabf0e7651a5a84642c178c28961430eea0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906484"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="74aa6-103">Настройка параметров S/MIME в Exchange Online для Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="74aa6-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="74aa6-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="74aa6-104">**Applies to**</span></span>
- [<span data-ttu-id="74aa6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="74aa6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="74aa6-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="74aa6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="74aa6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74aa6-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="74aa6-108">В качестве администратора Exchange Online можно настроить Outlook в Интернете (ранее известный как Outlook Web App), чтобы разрешить отправку и получение сообщений, защищенных S/MIME.</span><span class="sxs-lookup"><span data-stu-id="74aa6-108">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="74aa6-109">Для просмотра и управления этой функцией в Exchange Online PowerShell используйте комлеты **Get-SmimeConfig** и **Set-SmimeConfig.**</span><span class="sxs-lookup"><span data-stu-id="74aa6-109">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="74aa6-110">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="74aa6-110">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="74aa6-111">Подробные сведения о синтаксисах и параметрах см. в [сведениях Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig) и [Set-SmimeConfig.](/powershell/module/exchange/set-smimeconfig)</span><span class="sxs-lookup"><span data-stu-id="74aa6-111">For detailed syntax and parameter information, see [Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="74aa6-112">Соображения для нового Microsoft Edge (на основе хрома)</span><span class="sxs-lookup"><span data-stu-id="74aa6-112">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="74aa6-113">Чтобы использовать S/MIME в Outlook в Интернете в новом веб-браузере [Microsoft Edge,](https://www.microsoft.com/windows/microsoft-edge) вам (или другому администратору) необходимо установить и настроить политику браузера Microsoft Edge с именем **ExtensionInstallForcelist** для установки расширения Microsoft S/MIME в новом Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="74aa6-113">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="74aa6-114">Значение политики `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="74aa6-114">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="74aa6-115">Обратите внимание, что для применения этой политики требуются устройства, присоединившись к домену или к Azure AD, поэтому для использования S/MIME в новом браузере Microsoft Edge эффективно требуются устройства, присоединившись к домену или к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="74aa6-115">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="74aa6-116">Сведения о политике **ExtensionInstallForcelist** см. в [материале ExtensionInstallForcelist.](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)</span><span class="sxs-lookup"><span data-stu-id="74aa6-116">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="74aa6-117">Этот шаг является обязательным условием для использования нового Microsoft Edge; он не заменяет установленный пользователями контроль S/MIME.</span><span class="sxs-lookup"><span data-stu-id="74aa6-117">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="74aa6-118">Пользователям предложено скачать и установить управление S/MIME в Outlook в Интернете во время первого использования S/MIME.</span><span class="sxs-lookup"><span data-stu-id="74aa6-118">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="74aa6-119">Или пользователи могут упреждающим образом перейти в **S/MIME** в Outlook на веб-параметры, чтобы получить ссылку на скачивание для управления.</span><span class="sxs-lookup"><span data-stu-id="74aa6-119">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="74aa6-120">Соображения для Chrome</span><span class="sxs-lookup"><span data-stu-id="74aa6-120">Considerations for Chrome</span></span>

<span data-ttu-id="74aa6-121">Чтобы использовать S/MIME в Outlook в веб-браузере Google Chrome, вам (или другому администратору) необходимо установить и настроить политику Chromium с именем **ExtensionInstallForcelist** для установки расширения Microsoft S/MIME в Chrome.</span><span class="sxs-lookup"><span data-stu-id="74aa6-121">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="74aa6-122">Значение политики `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="74aa6-122">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="74aa6-123">И обратите внимание, что для применения этой политики требуются компьютеры, присоединившись к домену, поэтому для использования S/MIME в Chrome эффективно требуются компьютеры, присоединившись к домену.</span><span class="sxs-lookup"><span data-stu-id="74aa6-123">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="74aa6-124">Сведения о политике **ExtensionInstallForcelist** см. в [материале ExtensionInstallForcelist.](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)</span><span class="sxs-lookup"><span data-stu-id="74aa6-124">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="74aa6-125">Этот шаг является обязательным условием для использования Chrome; он не заменяет установленный пользователями контроль S/MIME.</span><span class="sxs-lookup"><span data-stu-id="74aa6-125">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="74aa6-126">Пользователям предложено скачать и установить управление S/MIME в Outlook в Интернете во время первого использования S/MIME.</span><span class="sxs-lookup"><span data-stu-id="74aa6-126">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="74aa6-127">Или пользователи могут упреждающим образом перейти в **S/MIME** в Outlook на веб-параметры, чтобы получить ссылку на скачивание для управления.</span><span class="sxs-lookup"><span data-stu-id="74aa6-127">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="74aa6-128">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="74aa6-128">For more information</span></span>

[<span data-ttu-id="74aa6-129">S/MIME для подписи и шифрования сообщений</span><span class="sxs-lookup"><span data-stu-id="74aa6-129">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)