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
ms.openlocfilehash: d50f35d7d5e81622eb8dfc3bbf8328a8c43e9676
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430038"
---
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="0ec86-103">Управление Skype для бизнеса Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ec86-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="0ec86-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="0ec86-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0ec86-105">Одной из основных задач администратора Skype для бизнеса Online является управление политиками.</span><span class="sxs-lookup"><span data-stu-id="0ec86-105">Skype for Business Online administrators are responsible for managing policies.</span></span> <span data-ttu-id="0ec86-106">Хотя вы можете выполнить некоторые из указанных ниже задач в Центре администрирования Microsoft 365, другие задачи гораздо легче выполнить с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0ec86-106">Although you can do some of these tasks in the Microsoft 365 admin center, others are easier to do in PowerShell.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="0ec86-107">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="0ec86-107">Before you start</span></span>

<span data-ttu-id="0ec86-108">Скачайте и установите [модуль PowerShell для Skype для бизнеса Online](https://www.microsoft.com/download/details.aspx?id=39366), а затем перезапустите компьютер.</span><span class="sxs-lookup"><span data-stu-id="0ec86-108">Download and install the [Skype for Business Online Windows PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer.</span></span>


## <a name="connect-using-skype-for-business-online-admin-credentials"></a><span data-ttu-id="0ec86-109">Подключение с помощью учетной записи администратора Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="0ec86-109">Connect using Skype for Business Online admin credentials</span></span>

1. <span data-ttu-id="0ec86-110">Откройте командную строку Windows PowerShell и выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="0ec86-110">Open a Windows PowerShell command prompt window and run the following commands:</span></span>
    
   ```powershell
   Import-Module SkypeOnlineConnector
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="0ec86-111">В диалоговом окне **Запрос учетных данных Windows PowerShell** введите имя и пароль учетной записи администратора Skype для бизнеса Online, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0ec86-111">In the **Windows PowerShell Credential Request** dialog box, type your Skype for Business Online administrator account name and password, and then select **OK**.</span></span>


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a><span data-ttu-id="0ec86-112">Подключение с помощью учетной записи администратора Skype для бизнеса Online с многофакторной идентификацией</span><span class="sxs-lookup"><span data-stu-id="0ec86-112">Connect using an admin account with multi-factor authentication</span></span>

1. <span data-ttu-id="0ec86-113">Откройте командную строку Windows PowerShell и выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="0ec86-113">Open a Windows PowerShell command prompt window, and run the following commands:</span></span>

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="0ec86-114">По запросу команды **New-CsOnlineSession** введите имя учетной записи администратора Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="0ec86-114">When prompted by the **New-CsOnlineSession** command, enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="0ec86-115">В диалоговом окне **Вход в учетную запись** введите пароль администратора Skype для бизнеса Online, а затем нажмите кнопку **Войти**.</span><span class="sxs-lookup"><span data-stu-id="0ec86-115">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password and select **Sign in**.</span></span>

4. <span data-ttu-id="0ec86-116">Следуя инструкциям в диалоговом окне **Вход в учетную запись**, предоставьте дополнительные сведения для идентификации, например код проверки, а затем нажмите кнопку **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="0ec86-116">In the **Sign in to your account** dialog box, follow the instructions to add authentication information, such as a verification code, and then select **Verify**.</span></span>

<span data-ttu-id="0ec86-117">Дополнительную информацию см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="0ec86-117">For more information, see:</span></span>
  
- [<span data-ttu-id="0ec86-118">Управление политиками Skype для бизнеса Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ec86-118">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="0ec86-119">Назначение индивидуальных политик для Skype для бизнеса Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ec86-119">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a><span data-ttu-id="0ec86-120">См. также</span><span class="sxs-lookup"><span data-stu-id="0ec86-120">See also</span></span>

[<span data-ttu-id="0ec86-121">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ec86-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="0ec86-122">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0ec86-122">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="0ec86-123">Справка по командлетам PowerShell в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0ec86-123">Skype for Business PowerShell cmdlet references</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
