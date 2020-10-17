---
title: Управление Skype для бизнеса Online с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: 054c16e6-9fd1-4e85-a0e6-81788b8410ea
description: Управляйте политиками, индивидуальными политиками и настройками собраний Skype для бизнеса Online, используя PowerShell для Microsoft 365.
ms.openlocfilehash: ff35463dc0c2e16106432c393b10e31e6bf0a5d2
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477105"
---
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="2271f-103">Управление Skype для бизнеса Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="2271f-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="2271f-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="2271f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2271f-105">Одной из основных задач администратора Skype для бизнеса Online является управление политиками.</span><span class="sxs-lookup"><span data-stu-id="2271f-105">Skype for Business Online administrators are responsible for managing policies.</span></span> <span data-ttu-id="2271f-106">Хотя вы можете выполнить некоторые из указанных ниже задач в Центре администрирования Microsoft 365, другие задачи гораздо легче выполнить с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2271f-106">Although you can do some of these tasks in the Microsoft 365 admin center, others are easier to do in PowerShell.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="2271f-107">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="2271f-107">Before you start</span></span>

  > [!Note]
   > <span data-ttu-id="2271f-108">Соединитель Skype для бизнеса Online в настоящее время является частью последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2271f-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="2271f-109">Если вы используете последний общедоступный выпуск Teams PowerShell, вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="2271f-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
   
<span data-ttu-id="2271f-110">Установите модуль [Teams PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="2271f-110">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>


## <a name="connect-using-admin-credentials"></a><span data-ttu-id="2271f-111">Подключение с учетными данными администратора</span><span class="sxs-lookup"><span data-stu-id="2271f-111">Connect using admin credentials</span></span>

1. <span data-ttu-id="2271f-112">Откройте командную строку Windows PowerShell и выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="2271f-112">Open a Windows PowerShell command prompt window and run the following commands:</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="2271f-113">В диалоговом окне **Запрос учетных данных Windows PowerShell** введите имя и пароль учетной записи администратора, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2271f-113">In the **Windows PowerShell Credential Request** dialog box, type your administrator account name and password, and then select **OK**.</span></span>


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a><span data-ttu-id="2271f-114">Подключение с помощью учетной записи администратора Skype для бизнеса Online с многофакторной идентификацией</span><span class="sxs-lookup"><span data-stu-id="2271f-114">Connect using an admin account with multi-factor authentication</span></span>

1. <span data-ttu-id="2271f-115">Откройте командную строку Windows PowerShell и выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="2271f-115">Open a Windows PowerShell command prompt window, and run the following commands:</span></span>

   ```powershell
   Import-Module MicrosoftTeams
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="2271f-116">По запросу команды **New-CsOnlineSession** введите имя учетной записи администратора Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="2271f-116">When prompted by the **New-CsOnlineSession** command, enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="2271f-117">В диалоговом окне **Вход в учетную запись** введите пароль администратора Skype для бизнеса Online, а затем нажмите кнопку **Войти**.</span><span class="sxs-lookup"><span data-stu-id="2271f-117">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password and select **Sign in**.</span></span>

4. <span data-ttu-id="2271f-118">Следуя инструкциям в диалоговом окне **Вход в учетную запись**, предоставьте дополнительные сведения для идентификации, например код проверки, а затем нажмите кнопку **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="2271f-118">In the **Sign in to your account** dialog box, follow the instructions to add authentication information, such as a verification code, and then select **Verify**.</span></span>

<span data-ttu-id="2271f-119">Дополнительную информацию см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="2271f-119">For more information, see:</span></span>
  
- [<span data-ttu-id="2271f-120">Управление политиками Skype для бизнеса Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="2271f-120">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="2271f-121">Назначение индивидуальных политик для Skype для бизнеса Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="2271f-121">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a><span data-ttu-id="2271f-122">См. также</span><span class="sxs-lookup"><span data-stu-id="2271f-122">See also</span></span>

[<span data-ttu-id="2271f-123">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="2271f-123">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="2271f-124">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2271f-124">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="2271f-125">Справка по командлетам PowerShell в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2271f-125">Skype for Business PowerShell cmdlet references</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
