---
title: Элемент управления App
description: ''
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: e9d33df0ae11d01c8c214fbe0f001a16e8f4908d
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170725"
---
# <a name="app-control"></a><span data-ttu-id="1695b-103">Элемент управления App</span><span class="sxs-lookup"><span data-stu-id="1695b-103">App control</span></span>

<span data-ttu-id="1695b-104">Управление приложениями — это необязательная практика безопасности на настольном компьютере, управляемом Майкрософт, которая запрещает выполнение кода на клиентских устройствах.</span><span class="sxs-lookup"><span data-stu-id="1695b-104">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="1695b-105">Этот элемент управления позволяет снизить риск заражения вредоносными и вредоносными сценариями, требуя запуска только кода, подписанного списком издателей, утвержденным клиентом.</span><span class="sxs-lookup"><span data-stu-id="1695b-105">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="1695b-106">Этот элемент управления обладает многими преимуществами безопасности, но в основном предназначен для защиты данных и идентификации от клиентских эксплойтов.</span><span class="sxs-lookup"><span data-stu-id="1695b-106">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="1695b-107">Рабочий стол, управляемый корпорацией Майкрософт, упрощает управление политиками управления приложениями, создавая базовую политику, которая позволяет выполнять основные сценарии продуктивности.</span><span class="sxs-lookup"><span data-stu-id="1695b-107">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="1695b-108">Вы можете расширить возможности доверия для дополнительных подписывающих, относящихся к приложениям и сценариям в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="1695b-108">You can extend trust to additional signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="1695b-109">Любая технология безопасности требует баланса между опытом взаимодействия с пользователем, безопасностью и стоимостью.</span><span class="sxs-lookup"><span data-stu-id="1695b-109">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="1695b-110">Управление приложениями уменьшает угрозу вредоносного программного обеспечения в вашей среде, но у конечного пользователя и дополнительных действий для ИТ ИТ.</span><span class="sxs-lookup"><span data-stu-id="1695b-110">App control reduces the threat of malicious software in your environment, but there are consequences to the end user and additional actions for your IT administrator.</span></span>

<span data-ttu-id="1695b-111">**Дополнительная безопасность:**</span><span class="sxs-lookup"><span data-stu-id="1695b-111">**Additional security:**</span></span>

<span data-ttu-id="1695b-112">Приложения или скрипты, которые не являются доверенными для политики управления приложениями, блокируются на устройствах.</span><span class="sxs-lookup"><span data-stu-id="1695b-112">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="1695b-113">**Ваши дополнительные обязанности:**</span><span class="sxs-lookup"><span data-stu-id="1695b-113">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="1695b-114">Вы несете ответственность за тестирование приложений, чтобы определить, будут ли они блокироваться политикой управления приложениями.</span><span class="sxs-lookup"><span data-stu-id="1695b-114">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="1695b-115">Если приложение заблокировано, вы несете ответственность за идентификацию необходимых сведений о подписавшем и запрос на изменение через портал администрирования.</span><span class="sxs-lookup"><span data-stu-id="1695b-115">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="1695b-116">**Функциональные обязанности по управлению рабочими столами Майкрософт:**</span><span class="sxs-lookup"><span data-stu-id="1695b-116">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="1695b-117">На рабочем столе Майкрософт поддерживается Базовая политика, которая включает основные продукты Майкрософт, такие как приложения M365, Windows, Teams, OneDrive и т. д.</span><span class="sxs-lookup"><span data-stu-id="1695b-117">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="1695b-118">Рабочий стол, управляемый Майкрософт, вставляет доверенных подписывающих и развертывает обновленную политику на устройствах.</span><span class="sxs-lookup"><span data-stu-id="1695b-118">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="1695b-119">Управление доверием в приложениях</span><span class="sxs-lookup"><span data-stu-id="1695b-119">Managing trust in applications</span></span>

<span data-ttu-id="1695b-120">На рабочем столе Майкрософт разрабатываются базовые политики, которые являются доверенными для основных компонентов технологий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1695b-120">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="1695b-121">После этого вы *добавляете* доверительные отношения для собственных приложений и сценариев, предменяя управляемый корпорацией Майкрософт компьютер, к которому вы уже доверяете.</span><span class="sxs-lookup"><span data-stu-id="1695b-121">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="1695b-122">Базовая политика</span><span class="sxs-lookup"><span data-stu-id="1695b-122">Base policy</span></span>

<span data-ttu-id="1695b-123">Компьютер, управляемый корпорацией Майкрософт, при совместной работе с экспертами Майкрософт циберсекурити создает и поддерживает стандартную политику, которая обеспечивает большинство приложений, развернутых с помощью Microsoft Intune, блокируя опасные действия, такие как компиляция кода или выполнение ненадежных файлов.</span><span class="sxs-lookup"><span data-stu-id="1695b-123">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="1695b-124">Для ограничения выполнения программ Базовая политика использует следующий подход:</span><span class="sxs-lookup"><span data-stu-id="1695b-124">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="1695b-125">Запуск файлов, выполняемых администраторами, разрешен.</span><span class="sxs-lookup"><span data-stu-id="1695b-125">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="1695b-126">Разрешен запуск файлов в расположениях, которые *не* входят в каталоги, доступные для записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="1695b-126">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="1695b-127">Файлы подписываются [доверенным подписывающий](#signer-requests).</span><span class="sxs-lookup"><span data-stu-id="1695b-127">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="1695b-128">Большинство файлов, подписанных корпорацией Майкрософт, будут работать, но некоторые из них блокируются для предотвращения таких действий, как компиляция кода.</span><span class="sxs-lookup"><span data-stu-id="1695b-128">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="1695b-129">Если пользователь, не являющийся администратором, может добавить приложение или сценарий на устройство (то есть он находится в каталоге, доступном пользователю), мы не допускайте его выполнение, если он не был специально разрешен администратором.</span><span class="sxs-lookup"><span data-stu-id="1695b-129">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="1695b-130">Если пользователь подключается к установке вредоносного программного обеспечения, то при наличии уязвимости в приложении, которая пытается установить вредоносную программу, или если пользователь намеренно пытается запустить неавторизованное приложение или сценарий, наша политика перестанет выполнение.</span><span class="sxs-lookup"><span data-stu-id="1695b-130">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="1695b-131">Запросы подписавшего</span><span class="sxs-lookup"><span data-stu-id="1695b-131">Signer requests</span></span>

<span data-ttu-id="1695b-132">Вы сообщите нам о том, какие приложения предоставляются поставщиками программного обеспечения, которым вы доверяете, заменив *запрос подписавшего*.</span><span class="sxs-lookup"><span data-stu-id="1695b-132">You inform us of which apps are provided by software vendors you trust by filing a *signer request*.</span></span> <span data-ttu-id="1695b-133">Для этого мы добавим эти сведения о доверии в базовую политику управления приложениями и разрешите любому программному обеспечению, подписанному с помощью сертификата этого издателя, на устройствах.</span><span class="sxs-lookup"><span data-stu-id="1695b-133">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="1695b-134">Аудит и применение политик</span><span class="sxs-lookup"><span data-stu-id="1695b-134">Audit and Enforced policies</span></span>

<span data-ttu-id="1695b-135">Для предоставления управления приложениями на рабочем столе Майкрософт используются две политики Microsoft Intune:</span><span class="sxs-lookup"><span data-stu-id="1695b-135">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="1695b-136">Политика аудита</span><span class="sxs-lookup"><span data-stu-id="1695b-136">Audit policy</span></span>
<span data-ttu-id="1695b-137">Эта политика создает журналы для записи того, блокируется ли принудительно примененная политика приложением или сценарием.</span><span class="sxs-lookup"><span data-stu-id="1695b-137">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="1695b-138">Политики аудита не применяют правила управления приложениями и предназначены для целей тестирования, чтобы определить, требуется ли для приложения исключение издателя.</span><span class="sxs-lookup"><span data-stu-id="1695b-138">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="1695b-139">Он регистрирует предупреждения (8003 или 8006) в средстве просмотра событий, а не блокирует выполнение или установку указанных приложений или скриптов.</span><span class="sxs-lookup"><span data-stu-id="1695b-139">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="1695b-140">Принудительная политика</span><span class="sxs-lookup"><span data-stu-id="1695b-140">Enforced policy</span></span>
<span data-ttu-id="1695b-141">Эта политика блокирует запуск недоверенных приложений и сценариев и создает журналы всякий раз, когда приложение или сценарий блокируется.</span><span class="sxs-lookup"><span data-stu-id="1695b-141">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="1695b-142">Принудительные политики запрещают обычным пользователям запускать приложения или скрипты, хранящиеся в каталогах, доступных для записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="1695b-142">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="1695b-143">К устройствам в тестовой группе применена политика аудита, поэтому их можно использовать для проверки того, могут ли какие-либо приложения вызывать проблемы.</span><span class="sxs-lookup"><span data-stu-id="1695b-143">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="1695b-144">Все остальные группы (первая, быстрая и общая) используют принудительно примененную политику, поэтому конечные пользователи в этих группах не смогут запускать недоверенные приложения и скрипты.</span><span class="sxs-lookup"><span data-stu-id="1695b-144">All other groups (First, Fast, and Broad) use an Enforced policy, so end users in those groups won't be able to run untrusted apps or scripts.</span></span>







