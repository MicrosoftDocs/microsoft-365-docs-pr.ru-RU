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
description: Сводка. Управляйте политиками, индивидуальными политиками и настройками собраний Skype для бизнеса Online, используя PowerShell для Microsoft 365.
ms.openlocfilehash: aea78d135a5d7ffbb5d8480c549d0fdee88f7d51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693411"
---
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="0eaa2-103">Управление Skype для бизнеса Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="0eaa2-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="0eaa2-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="0eaa2-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0eaa2-105">Одной из основных задач администратора Skype для бизнеса Online является управление политиками.</span><span class="sxs-lookup"><span data-stu-id="0eaa2-105">One of the primary tasks of any Skype for Business Online administrator is managing policies.</span></span> <span data-ttu-id="0eaa2-106">Хотя вы можете выполнить некоторые из указанных ниже задач в Центре администрирования Microsoft 365, другие задачи гораздо быстрее и проще выполнить с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0eaa2-106">Although you can accomplish some of these tasks in the Microsoft 365 admin center, other tasks are much quicker and easier in PowerShell.</span></span> 

## <a name="before-you-start"></a><span data-ttu-id="0eaa2-107">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="0eaa2-107">Before you start</span></span>

<span data-ttu-id="0eaa2-108">Скачайте и установите [модуль соединителя Skype для бизнеса Online](https://www.microsoft.com/download/details.aspx?id=39366), а затем перезапустите компьютер.</span><span class="sxs-lookup"><span data-stu-id="0eaa2-108">Download and install the [Skype for Business Online Connector module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer.</span></span>


## <a name="connect-using-a-skype-for-business-online-administrator-account-name-and-password"></a><span data-ttu-id="0eaa2-109">Подключение с помощью имени и пароля учетной записи администратора Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="0eaa2-109">Connect using a Skype for Business Online administrator account name and password</span></span>

1. <span data-ttu-id="0eaa2-110">Откройте командную строку Windows PowerShell и выполните указанные команды:</span><span class="sxs-lookup"><span data-stu-id="0eaa2-110">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
    
   ```powershell
   Import-Module SkypeOnlineConnector
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="0eaa2-111">В диалоговом окне **Запрос учетных данных Windows PowerShell** введите имя и пароль учетной записи администратора Skype для бизнеса Online, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0eaa2-111">In the **Windows PowerShell Credential Request** dialog box, type your Skype for Business Online administrator account name and password, and then click **OK**.</span></span>


## <a name="connect-using-a-skype-for-business-online-administrator-account-with-multi-factor-authentication"></a><span data-ttu-id="0eaa2-112">Подключение с помощью учетной записи администратора Skype для бизнеса Online с многофакторной проверкой подлинности</span><span class="sxs-lookup"><span data-stu-id="0eaa2-112">Connect using a Skype for Business Online administrator account with multi-factor authentication</span></span>

1. <span data-ttu-id="0eaa2-113">Откройте командную строку Windows PowerShell и выполните указанные команды:</span><span class="sxs-lookup"><span data-stu-id="0eaa2-113">Open a Windows PowerShell command prompt and run the following commands:</span></span>

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="0eaa2-114">По запросу команды **New-CsOnlineSession** введите имя учетной записи администратора Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="0eaa2-114">When prompted by the **New-CsOnlineSession** command, enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="0eaa2-115">В диалоговом окне **Вход в учетную запись** введите пароль администратора Skype для бизнеса Online, а затем нажмите кнопку **Войти**.</span><span class="sxs-lookup"><span data-stu-id="0eaa2-115">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password, and then click **Sign in**.</span></span>

4. <span data-ttu-id="0eaa2-116">Следуя инструкциям в диалоговом окне **Вход в учетную запись**, предоставьте дополнительные сведения для проверки подлинности, например код проверки, а затем нажмите кнопку **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="0eaa2-116">Follow the instructions in the **Sign in to your account** dialog box to provide additional authentication information, such as a verification code, and then click **Verify**.</span></span>

<span data-ttu-id="0eaa2-117">Дополнительную информацию см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="0eaa2-117">For more information, see the following topics:</span></span>
  
- [<span data-ttu-id="0eaa2-118">Управление политиками Skype для бизнеса Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="0eaa2-118">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="0eaa2-119">Назначение индивидуальных политик для Skype для бизнеса Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="0eaa2-119">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a><span data-ttu-id="0eaa2-120">См. также</span><span class="sxs-lookup"><span data-stu-id="0eaa2-120">See also</span></span>

[<span data-ttu-id="0eaa2-121">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="0eaa2-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="0eaa2-122">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0eaa2-122">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="0eaa2-123">Справка по командлетам PowerShell в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0eaa2-123">Skype for Business PowerShell cmdlet references</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)

