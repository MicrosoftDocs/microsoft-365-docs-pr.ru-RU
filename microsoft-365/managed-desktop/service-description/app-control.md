---
title: Управление приложениями
description: Использование управления приложениями и доверия с приложениями
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
# <a name="app-control"></a><span data-ttu-id="22ee0-104">Управление приложениями</span><span class="sxs-lookup"><span data-stu-id="22ee0-104">App control</span></span>

<span data-ttu-id="22ee0-105">Управление приложениями — это необязательный метод обеспечения безопасности в компьютере под управлением Майкрософт, ограничивающий выполнение кода на клиентских устройствах.</span><span class="sxs-lookup"><span data-stu-id="22ee0-105">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="22ee0-106">Этот контроль снижает риск вредоносного ПО или вредоносных сценариев, требуя запускать только код, подписанный утвержденным клиентом списком издателей.</span><span class="sxs-lookup"><span data-stu-id="22ee0-106">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="22ee0-107">Этот контроль дает множество преимуществ безопасности, но в первую очередь он предназначен для защиты данных и удостоверений от клиентских эксплойтов.</span><span class="sxs-lookup"><span data-stu-id="22ee0-107">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="22ee0-108">Компьютеры, управляемые Майкрософт, упрощают управление политиками управления приложениями, создавая базовую политику, которая обеспечивает основные сценарии повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="22ee0-108">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="22ee0-109">Вы можете расширить доверие другим подписателям, которые специфичивы для приложений и сценариев в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="22ee0-109">You can extend trust to other signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="22ee0-110">Для любой технологии безопасности требуется баланс между пользовательским интерфейсом, безопасностью и затратами.</span><span class="sxs-lookup"><span data-stu-id="22ee0-110">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="22ee0-111">Управление приложениями снижает угрозу вредоносного ПО в вашей среде, но это может привести к последствиям для пользователя и дальнейших действий для ИТ-администратора.</span><span class="sxs-lookup"><span data-stu-id="22ee0-111">App control reduces the threat of malicious software in your environment, but there are consequences to the user and further actions for your IT administrator.</span></span>

<span data-ttu-id="22ee0-112">**Дополнительная безопасность:**</span><span class="sxs-lookup"><span data-stu-id="22ee0-112">**Additional security:**</span></span>

<span data-ttu-id="22ee0-113">Приложения или сценарии, которые не являются доверенными политикой управления приложениями, не могут работать на устройствах.</span><span class="sxs-lookup"><span data-stu-id="22ee0-113">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="22ee0-114">**Дополнительные обязанности:**</span><span class="sxs-lookup"><span data-stu-id="22ee0-114">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="22ee0-115">Вы несете ответственность за тестирование приложений, чтобы определить, будут ли они блокироваться политикой управления приложениями.</span><span class="sxs-lookup"><span data-stu-id="22ee0-115">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="22ee0-116">Если приложение заблокировано (или будет) заблокировано, вы несете ответственность за определение необходимых сведений о подписываемом документе и запрос на изменение на портале администрирования.</span><span class="sxs-lookup"><span data-stu-id="22ee0-116">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="22ee0-117">**Обязанности компьютеров, управляемых Майкрософт:**</span><span class="sxs-lookup"><span data-stu-id="22ee0-117">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="22ee0-118">Компьютеры, управляемые Майкрософт, поддерживают базовую политику, которая включает основные продукты Майкрософт, такие как приложения M365, Windows, Teams, OneDrive и так далее.</span><span class="sxs-lookup"><span data-stu-id="22ee0-118">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="22ee0-119">Компьютер под управлением Майкрософт вставляет доверенных подписателей и развертывает обновленную политику на устройствах.</span><span class="sxs-lookup"><span data-stu-id="22ee0-119">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="22ee0-120">Управление доверием в приложениях</span><span class="sxs-lookup"><span data-stu-id="22ee0-120">Managing trust in applications</span></span>

<span data-ttu-id="22ee0-121">На компьютере, управляемом Майкрософт, вы можете создать базовую политику, которая доверяет основным компонентам технологий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="22ee0-121">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="22ee0-122">Затем вы *добавляете* доверие для собственных приложений и сценариев, сообщая компьютеру, управляемому Майкрософт, кому из них вы уже доверяете.</span><span class="sxs-lookup"><span data-stu-id="22ee0-122">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="22ee0-123">Базовая политика</span><span class="sxs-lookup"><span data-stu-id="22ee0-123">Base policy</span></span>

<span data-ttu-id="22ee0-124">Компьютер под управлением Майкрософт в сотрудничестве со специалистами майкрософт по кибербезопасности создает и поддерживает стандартную политику, которая позволяет большинству приложений развертываться с помощью Microsoft Intune, блокируя опасные действия, такие как компиляция кода или выполнение ненадежных файлов.</span><span class="sxs-lookup"><span data-stu-id="22ee0-124">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates, and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="22ee0-125">Базовая политика принимает следующий подход к ограничению выполнения программного обеспечения:</span><span class="sxs-lookup"><span data-stu-id="22ee0-125">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="22ee0-126">Запускать файлы, которые будут запускать администраторы, будет разрешено.</span><span class="sxs-lookup"><span data-stu-id="22ee0-126">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="22ee0-127">Файлы в расположениях, *которые не* находятся в пользовательских каталогах, будут запускаться.</span><span class="sxs-lookup"><span data-stu-id="22ee0-127">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="22ee0-128">Файлы подписываются [доверенным подписав лицом.](#signer-requests)</span><span class="sxs-lookup"><span data-stu-id="22ee0-128">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="22ee0-129">Большинство файлов, подписанных корпорацией Майкрософт, будут работать, но некоторые из них блокируются, чтобы предотвратить рискованные действия, например компиляцию кода.</span><span class="sxs-lookup"><span data-stu-id="22ee0-129">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="22ee0-130">Если пользователь, кроме администратора, мог добавить приложение или сценарий на устройство (т. е. находится в доступном для записи каталоге), мы не разрешим его выполнение, если это не разрешено специально администратором.</span><span class="sxs-lookup"><span data-stu-id="22ee0-130">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="22ee0-131">Если пользователь пытается установить вредоносное ПО, если уязвимость в приложении запускается, пользователь пытается установить вредоносное ПО или если пользователь намеренно пытается запустить неавторизованные приложения или сценарии, наша политика остановит выполнение.</span><span class="sxs-lookup"><span data-stu-id="22ee0-131">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="22ee0-132">Запросы подписав</span><span class="sxs-lookup"><span data-stu-id="22ee0-132">Signer requests</span></span>

<span data-ttu-id="22ee0-133">Вы сообщаете нам о том, какие приложения предоставляются издателями программного обеспечения, которым вы доверяете, подав запрос *подписав.*</span><span class="sxs-lookup"><span data-stu-id="22ee0-133">You inform us of which apps are provided by software publishers you trust by filing a *signer request*.</span></span> <span data-ttu-id="22ee0-134">Таким образом мы добавляем эти сведения о доверии в базовую политику управления приложениями и разрешаем запуск любого программного обеспечения, подписанного сертификатом этого издателя, на ваших устройствах.</span><span class="sxs-lookup"><span data-stu-id="22ee0-134">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="22ee0-135">Политики аудита и принудительного соблюдения</span><span class="sxs-lookup"><span data-stu-id="22ee0-135">Audit and Enforced policies</span></span>

<span data-ttu-id="22ee0-136">Компьютеры, управляемые Майкрософт, используют две политики Microsoft Intune для управления приложениями:</span><span class="sxs-lookup"><span data-stu-id="22ee0-136">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="22ee0-137">Политика аудита</span><span class="sxs-lookup"><span data-stu-id="22ee0-137">Audit policy</span></span>
<span data-ttu-id="22ee0-138">Эта политика создает журналы, в которые записывают, будут ли приложение или сценарий заблокированы политикой "Принудительно".</span><span class="sxs-lookup"><span data-stu-id="22ee0-138">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="22ee0-139">Политики аудита не принудительно применяют правила управления приложениями и предназначены для тестирования, чтобы определить, требуется ли приложению исключение издателя.</span><span class="sxs-lookup"><span data-stu-id="22ee0-139">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="22ee0-140">Он регистрировал предупреждения (события 8003 или 8006) в окне просмотра событий, а не блокировал выполнение или установку указанных приложений или сценариев.</span><span class="sxs-lookup"><span data-stu-id="22ee0-140">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="22ee0-141">Принуивная политика</span><span class="sxs-lookup"><span data-stu-id="22ee0-141">Enforced policy</span></span>
<span data-ttu-id="22ee0-142">Эта политика блокирует запуск недоверных приложений и сценариев и создает журналы при блокировке приложения или сценария.</span><span class="sxs-lookup"><span data-stu-id="22ee0-142">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="22ee0-143">Принудительным политикам не позволяет стандартным пользователям выполнять приложения или сценарии, хранимые в доступных для записи каталогах.</span><span class="sxs-lookup"><span data-stu-id="22ee0-143">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="22ee0-144">К устройствам в группе тестирования применяется политика аудита, с помощью которых можно проверить, будут ли какие-либо приложения вызывать проблемы.</span><span class="sxs-lookup"><span data-stu-id="22ee0-144">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="22ee0-145">Все остальные группы (First, Fast, and Broad) используют политику принудительного применения, поэтому пользователи в этих группах не смогут запускать неподтверщенные приложения или сценарии.</span><span class="sxs-lookup"><span data-stu-id="22ee0-145">All other groups (First, Fast, and Broad) use an Enforced policy, so users in those groups won't be able to run untrusted apps or scripts.</span></span>







