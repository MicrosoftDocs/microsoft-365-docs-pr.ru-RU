---
title: Управление приложениями
description: Использование управления приложениями и доверия к ним с приложениями
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6f5cc923b5a18b1f45dd186e88228db8c3a891cc
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841307"
---
# <a name="app-control"></a><span data-ttu-id="a29dc-104">Управление приложениями</span><span class="sxs-lookup"><span data-stu-id="a29dc-104">App control</span></span>

<span data-ttu-id="a29dc-105">Управление приложениями — это необязательная практика безопасности в компьютеры, управляемые Майкрософт, которая ограничивает выполнение кода на клиентских устройствах.</span><span class="sxs-lookup"><span data-stu-id="a29dc-105">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="a29dc-106">Этот контроль снижает риск вредоносных программ или вредоносных скриптов, требуя, чтобы запускался только код, подписанный утвержденным клиентом списком издателей.</span><span class="sxs-lookup"><span data-stu-id="a29dc-106">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="a29dc-107">Этот контроль дает множество преимуществ безопасности, но в первую очередь он направлен на защиту данных и удостоверений от клиентских эксплойтов.</span><span class="sxs-lookup"><span data-stu-id="a29dc-107">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="a29dc-108">компьютеры, управляемые Майкрософт упрощает управление политиками управления приложениями, создав базовую политику, которая включает основные сценарии производительности.</span><span class="sxs-lookup"><span data-stu-id="a29dc-108">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="a29dc-109">Вы можете распространить доверие на других подписателей, которые являются специфическими для приложений и сценариев в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="a29dc-109">You can extend trust to other signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="a29dc-110">Любая технология безопасности требует баланса между пользовательским опытом, безопасностью и затратами.</span><span class="sxs-lookup"><span data-stu-id="a29dc-110">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="a29dc-111">Управление приложениями снижает угрозу вредоносного программного обеспечения в среде, но это может привести к последствиям для пользователя и дальнейших действий для ИТ-администратора.</span><span class="sxs-lookup"><span data-stu-id="a29dc-111">App control reduces the threat of malicious software in your environment, but there are consequences to the user and further actions for your IT administrator.</span></span>

<span data-ttu-id="a29dc-112">**Дополнительная безопасность:**</span><span class="sxs-lookup"><span data-stu-id="a29dc-112">**Additional security:**</span></span>

<span data-ttu-id="a29dc-113">Приложения или скрипты, которые не доверяют политике управления приложениями, блокируют работу на устройствах.</span><span class="sxs-lookup"><span data-stu-id="a29dc-113">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="a29dc-114">**Дополнительные обязанности:**</span><span class="sxs-lookup"><span data-stu-id="a29dc-114">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="a29dc-115">Вы несете ответственность за тестирование приложений, чтобы определить, будут ли они заблокированы политикой управления приложениями.</span><span class="sxs-lookup"><span data-stu-id="a29dc-115">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="a29dc-116">Если приложение заблокировано (или будет заблокировано), вы несете ответственность за определение необходимых сведений о подписывщике и запрос изменения через портал Admin.</span><span class="sxs-lookup"><span data-stu-id="a29dc-116">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="a29dc-117">**компьютеры, управляемые Майкрософт обязанностей:**</span><span class="sxs-lookup"><span data-stu-id="a29dc-117">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="a29dc-118">компьютеры, управляемые Майкрософт поддерживает базовую политику, которая включает основные продукты Майкрософт, такие как M365 Apps, Windows, Teams, OneDrive и так далее.</span><span class="sxs-lookup"><span data-stu-id="a29dc-118">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="a29dc-119">компьютеры, управляемые Майкрософт вставляет доверенных подписателей и развертывает обновленную политику на устройствах.</span><span class="sxs-lookup"><span data-stu-id="a29dc-119">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="a29dc-120">Управление доверием к приложениям</span><span class="sxs-lookup"><span data-stu-id="a29dc-120">Managing trust in applications</span></span>

<span data-ttu-id="a29dc-121">компьютеры, управляемые Майкрософт является куратором базовой политики, которая доверяет основным компонентам технологий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a29dc-121">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="a29dc-122">Затем вы *добавляете* доверие к собственным приложениям и сценариям, информируя компьютеры, управляемые Майкрософт, кому из них вы уже доверяете.</span><span class="sxs-lookup"><span data-stu-id="a29dc-122">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="a29dc-123">Базовая политика</span><span class="sxs-lookup"><span data-stu-id="a29dc-123">Base policy</span></span>

<span data-ttu-id="a29dc-124">компьютеры, управляемые Майкрософт совместно с экспертами По кибербезопасности Майкрософт создает и поддерживает стандартную политику, которая позволяет большинству приложений, развернутых через Microsoft Intune, блокировать опасные действия, такие как компиляция кода или выполнение ненадежных файлов.</span><span class="sxs-lookup"><span data-stu-id="a29dc-124">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates, and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="a29dc-125">Базовая политика принимает следующий подход к ограничению выполнения программного обеспечения:</span><span class="sxs-lookup"><span data-stu-id="a29dc-125">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="a29dc-126">Файлы, которые управляются администраторами, будут разрешены для запуска.</span><span class="sxs-lookup"><span data-stu-id="a29dc-126">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="a29dc-127">Файлы в расположениях, *не* вписаемых в пользовательские каталоги, будут разрешены для запуска.</span><span class="sxs-lookup"><span data-stu-id="a29dc-127">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="a29dc-128">Файлы подписываются доверенным [подписавщиком.](#signer-requests)</span><span class="sxs-lookup"><span data-stu-id="a29dc-128">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="a29dc-129">Большинство файлов, подписанных Корпорацией Майкрософт, будут работать, однако некоторые из них заблокированы, чтобы предотвратить действия с высоким уровнем риска, такие как компиляция кода.</span><span class="sxs-lookup"><span data-stu-id="a29dc-129">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="a29dc-130">Если пользователь, помимо администратора, мог добавить приложение или сценарий на устройство (то есть в каталоге, который можно использовать для пользователя), мы не разрешим его выполнять, если это уже было специально разрешено администратором.</span><span class="sxs-lookup"><span data-stu-id="a29dc-130">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="a29dc-131">Если пользователя обманом пытаются установить вредоносные программы, если уязвимость в приложении выполняется попытка установки вредоносных программ, или если пользователь намеренно пытается запустить несанкционированное приложение или сценарий, наша политика остановит выполнение.</span><span class="sxs-lookup"><span data-stu-id="a29dc-131">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="a29dc-132">Запросы подписав</span><span class="sxs-lookup"><span data-stu-id="a29dc-132">Signer requests</span></span>

<span data-ttu-id="a29dc-133">Вы сообщаете нам о том, какие приложения предоставляют издатели программного обеспечения, которым вы доверяете, подав запрос *подписав.*</span><span class="sxs-lookup"><span data-stu-id="a29dc-133">You inform us of which apps are provided by software publishers you trust by filing a *signer request*.</span></span> <span data-ttu-id="a29dc-134">Таким образом мы добавляем эти доверятельные сведения в базовую политику управления приложениями и разрешаем любому программному обеспечению, подписанное сертификатом издателя, работать на ваших устройствах.</span><span class="sxs-lookup"><span data-stu-id="a29dc-134">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="a29dc-135">Политики аудита и принудительного</span><span class="sxs-lookup"><span data-stu-id="a29dc-135">Audit and Enforced policies</span></span>

<span data-ttu-id="a29dc-136">компьютеры, управляемые Майкрософт для управления приложениями Microsoft Intune двух политик:</span><span class="sxs-lookup"><span data-stu-id="a29dc-136">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="a29dc-137">Политика аудита</span><span class="sxs-lookup"><span data-stu-id="a29dc-137">Audit policy</span></span>
<span data-ttu-id="a29dc-138">Эта политика создает журналы для записи того, будет ли приложение или сценарий заблокировано политикой Enforced.</span><span class="sxs-lookup"><span data-stu-id="a29dc-138">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="a29dc-139">Политики аудита не исполняют правила управления приложениями и предназначены для тестирования, чтобы определить, потребуется ли приложению освобождение от издателя.</span><span class="sxs-lookup"><span data-stu-id="a29dc-139">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="a29dc-140">Он регистрировал предупреждения (8003 или 8006 событий) в viewer событий, а не блокировал выполнение или установку указанных приложений или скриптов.</span><span class="sxs-lookup"><span data-stu-id="a29dc-140">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="a29dc-141">Принудительное применение политики</span><span class="sxs-lookup"><span data-stu-id="a29dc-141">Enforced policy</span></span>
<span data-ttu-id="a29dc-142">Эта политика блокирует запуск ненарушимые приложения и сценарии и создает журналы всякий раз, когда приложение или сценарий заблокированы.</span><span class="sxs-lookup"><span data-stu-id="a29dc-142">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="a29dc-143">Принудительным политикам не позволяет стандартным пользователям выполнять приложения или скрипты, хранимые в каталогах, которые можно использовать для выполнения.</span><span class="sxs-lookup"><span data-stu-id="a29dc-143">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="a29dc-144">На устройствах группы Test применяется политика аудита, с помощью которых можно проверить, будут ли какие-либо приложения вызывать проблемы.</span><span class="sxs-lookup"><span data-stu-id="a29dc-144">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="a29dc-145">Все другие группы (First, Fast и Broad) используют политику Enforced, поэтому пользователи в этих группах не смогут запускать ненавязаные приложения или сценарии.</span><span class="sxs-lookup"><span data-stu-id="a29dc-145">All other groups (First, Fast, and Broad) use an Enforced policy, so users in those groups won't be able to run untrusted apps or scripts.</span></span>







