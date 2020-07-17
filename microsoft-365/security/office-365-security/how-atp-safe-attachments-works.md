---
title: Как работают безопасные вложения ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как защитить организацию от вредоносных файлов с помощью безопасных вложений ATP для Office 365.
ms.openlocfilehash: f4f355d4def1f108a72854c3796e0e9373cb5ef1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819404"
---
# <a name="how-atp-safe-attachments-works"></a><span data-ttu-id="7c542-103">Как работают безопасные вложения ATP</span><span class="sxs-lookup"><span data-stu-id="7c542-103">How ATP Safe Attachments works</span></span>

<span data-ttu-id="7c542-104">Функция безопасных вложений в ATP проверяет вложения электронной почты для людей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7c542-104">The ATP Safe Attachments feature checks email attachments for people in your organization.</span></span> <span data-ttu-id="7c542-105">Когда политика безопасных вложений ATP находится на месте и кто-то покрылся этой политикой, просматривает свою электронную почту в Office 365, проверяются вложения электронной почты и выполняются соответствующие действия в соответствии с политиками безопасных вложений ATP.</span><span class="sxs-lookup"><span data-stu-id="7c542-105">When an ATP Safe Attachments policy is in place and someone covered by that policy views their email in Office 365, their email attachments are checked and appropriate actions are taken, based on your ATP Safe Attachments policies.</span></span> <span data-ttu-id="7c542-106">В зависимости от того, как определены политики, люди могут продолжать работу, не зная, что они были отправлены вредоносными файлами.</span><span class="sxs-lookup"><span data-stu-id="7c542-106">Depending on how your policies are defined, people can continue working without ever knowing they were sent malicious files.</span></span>
  
<span data-ttu-id="7c542-107">Ниже приведены два примера безопасных вложений ATP на работе.</span><span class="sxs-lookup"><span data-stu-id="7c542-107">Here are two examples of ATP Safe Attachments at work.</span></span>
  
- <span data-ttu-id="7c542-108">**Пример 1: вложение электронной почты** Предположим, что Иванов получает сообщение электронной почты с вложением.</span><span class="sxs-lookup"><span data-stu-id="7c542-108">**Example 1: Email attachment** Suppose that Lee receives an email message that has an attachment.</span></span> <span data-ttu-id="7c542-109">Неочевидно, что это вложение является безопасным или содержит вредоносную программу, предназначенную для хищения учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="7c542-109">It is not obvious to Lee whether that attachment is safe or actually contains malware designed to steal Lee's user credentials.</span></span> <span data-ttu-id="7c542-110">В Организации Иванов администратор безопасности определил политику безопасных вложений ATP через несколько дней назад.</span><span class="sxs-lookup"><span data-stu-id="7c542-110">In Lee's organization, a security administrator defined an ATP Safe Attachments policy a few days ago.</span></span> <span data-ttu-id="7c542-111">С помощью функции безопасных вложений ATP, вложение электронной почты будет открыто и проверено в виртуальной среде, прежде чем она будет доставлена.</span><span class="sxs-lookup"><span data-stu-id="7c542-111">With the ATP Safe Attachments feature, the email attachment is opened and tested in a virtual environment before Lee receives it.</span></span> <span data-ttu-id="7c542-112">Если вложение определено как вредоносное, оно будет удалено автоматически.</span><span class="sxs-lookup"><span data-stu-id="7c542-112">If the attachment is determined to be malicious, it will be removed automatically.</span></span> <span data-ttu-id="7c542-113">Если вложение является безопасным, оно будет открываться, как ожидалось, при его нажатии.</span><span class="sxs-lookup"><span data-stu-id="7c542-113">If the attachment is safe, it will open as expected when Lee clicks on it.</span></span>

- <span data-ttu-id="7c542-114">**Пример 2: файл в SharePoint Online** Предположим, что Жан получил файл и отправил его в библиотеку в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7c542-114">**Example 2: File in SharePoint Online** Suppose that Jean received a file and uploaded it into a library in SharePoint Online.</span></span> <span data-ttu-id="7c542-115">Жан совместно использует ссылку на файл с остальной частью команды, не зная, что файл на самом деле является вредоносным.</span><span class="sxs-lookup"><span data-stu-id="7c542-115">Jean shares the link to the file with the rest of the team, not knowing that the file is actually malicious.</span></span> <span data-ttu-id="7c542-116">К счастью, [ATP для SharePoint, OneDrive и Microsoft Teams](atp-for-spo-odb-and-teams.md) обнаруживает вредоносный файл и блокирует его.</span><span class="sxs-lookup"><span data-stu-id="7c542-116">Fortunately, [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) detects the malicious file and blocks it.</span></span> <span data-ttu-id="7c542-117">Спустя несколько дней, Крис открывает документ.</span><span class="sxs-lookup"><span data-stu-id="7c542-117">A few days later, Chris goes to open the document.</span></span> <span data-ttu-id="7c542-118">Несмотря на то, что Крис видит файл, Крис не может открыть его или поделиться им, что позволит защитить компьютер и других пользователей от вредоносного файла.</span><span class="sxs-lookup"><span data-stu-id="7c542-118">Although Chris can see the file is there, Chris cannot open or share it, which protects Chris's computer and others from the malicious file.</span></span>

<span data-ttu-id="7c542-119">Политики безопасных вложений ATP могут быть применены к определенным пользователям или группам в организации или ко всему домену.</span><span class="sxs-lookup"><span data-stu-id="7c542-119">ATP Safe Attachments policies can be applied to specific people or groups in your organization, or to your entire domain.</span></span> <span data-ttu-id="7c542-120">Кроме того, политики безопасных вложений ATP можно настроить на использование вложений заполнителя при сканировании реальных вложений.</span><span class="sxs-lookup"><span data-stu-id="7c542-120">In addition, ATP Safe Attachments policies can be configured to use placeholder attachments while actual attachments are being scanned.</span></span> <span data-ttu-id="7c542-121">Чтобы узнать больше, ознакомьтесь со статьей **[Настройка политик безопасных вложений ATP в Office 365](set-up-atp-safe-attachments-policies.md)**.</span><span class="sxs-lookup"><span data-stu-id="7c542-121">To learn more, see **[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)**.</span></span>

> [!NOTE]
> <span data-ttu-id="7c542-122">Проверка безопасных вложений ATP выполняется в том же регионе, в котором размещены ваши данные.</span><span class="sxs-lookup"><span data-stu-id="7c542-122">ATP Safe Attachments scanning takes place in the same region where your data resides.</span></span> <span data-ttu-id="7c542-123">Для получения дополнительных сведений о географическом отношении центра обработки данных Узнайте, [где находятся ваши данные?](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="7c542-123">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 

