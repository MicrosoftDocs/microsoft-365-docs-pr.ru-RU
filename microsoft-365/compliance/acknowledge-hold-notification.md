---
title: Подтверждение уведомления об удержании
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: de542ad950fce061b63aa4b2aaf37821582d7466
ms.sourcegitcommit: e292e9f0181d722a11398fbd012bb84589aef052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2019
ms.locfileid: "39256806"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="6e01b-102">Подтверждение уведомления об удержании</span><span class="sxs-lookup"><span data-stu-id="6e01b-102">Acknowledge a hold notification</span></span> 
<span data-ttu-id="6e01b-103">При ответе на нормативный запрос или исследование вам может потребоваться уведомить custodians о своих обязательствах, чтобы сохранить электронную информацию (РАЗБИРАТЕЛЬСТВАХ) и все материалы, которые могут быть важны для действующего или приближенного юридического лица.</span><span class="sxs-lookup"><span data-stu-id="6e01b-103">When responding to a regulatory request or investigation, you may be required to  inform custodians of their obligation to preserve electronically stored information (ESI) and any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="6e01b-104">После отправки юридические команды должны знать, что каждый хранитель получил, прочитался и понял, а также принял условия, указанные в указанных инструкциях.</span><span class="sxs-lookup"><span data-stu-id="6e01b-104">Once sent, legal teams must know that each custodian has received, read, and understood, and agreed to follow the given instructions.</span></span>

<span data-ttu-id="6e01b-105">Чтобы сократить время, стоимость и усилия по работе с custodians, Расширенное обнаружение электронных данных позволяет отправлять уведомления о юридических удержаниях через электронную почту.</span><span class="sxs-lookup"><span data-stu-id="6e01b-105">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow up on legal hold notifications through email.</span></span> <span data-ttu-id="6e01b-106">Помимо уведомлений по электронной почте, каждый хранитель будет иметь доступ к отдельному порталу соответствия требованиям, позволяя custodians хранить информацию об изменениях своего состояния обязательства.</span><span class="sxs-lookup"><span data-stu-id="6e01b-106">In addition to email notices, each custodian will have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="6e01b-107">Уведомления по электронной почте</span><span class="sxs-lookup"><span data-stu-id="6e01b-107">Email notifications</span></span>
<span data-ttu-id="6e01b-108">После того как уведомление о удержании было принято, каждое хранитель будет получать уникальное и персонализированное сообщение электронной почты, содержащее Ваше заданное уведомление об удержании, и дополнительные инструкции.</span><span class="sxs-lookup"><span data-stu-id="6e01b-108">Once a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!Tip] 
> <span data-ttu-id="6e01b-109">Узнайте, как можно использовать встроенный [Редактор взаимодействия](using-communications-editor.md) , чтобы ваше custodians мог подтвердить свое уведомление или получить доступ к порталу соответствия непосредственно из своей электронной почты.</span><span class="sxs-lookup"><span data-stu-id="6e01b-109">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="6e01b-110">В зависимости от конфигурации вашего уведомления об судебном удержании ваши custodians могут получать следующие уведомления:</span><span class="sxs-lookup"><span data-stu-id="6e01b-110">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="6e01b-111">**Уведомление о выдаче** — первое уведомление, отправленное хранитель.</span><span class="sxs-lookup"><span data-stu-id="6e01b-111">**Issuance notice** - This is the first notice sent to your custodian.</span></span> <span data-ttu-id="6e01b-112">Он будет содержать инструкции по выдаче, а уведомление об удержании добавляется в конец сообщения.</span><span class="sxs-lookup"><span data-stu-id="6e01b-112">This will contain your issuance instructions and the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="6e01b-113">**Уведомление о напоминании** — если этот параметр включен, уведомление о напоминании будет отправлено в custodians в соответствии с заданной частотой и интервалом.</span><span class="sxs-lookup"><span data-stu-id="6e01b-113">**Reminder notice** - If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="6e01b-114">Напоминания продолжат отправку до тех пор, пока в хранитель не будет подтверждено уведомление или пока не будет исчерпано количество напоминаний.</span><span class="sxs-lookup"><span data-stu-id="6e01b-114">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="6e01b-115">**Уведомление о эскалации** — если этот параметр включен, уведомление о эскалации будет отправлено хранитель и руководителю после исчерпания уведомлений.</span><span class="sxs-lookup"><span data-stu-id="6e01b-115">**Escalation notice** - If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="6e01b-116">Система автоматически отправляет уведомления о эскалации до тех пор, пока эти укрупнения не будут завершены или пока хранитель не подтвердит свое уведомление об удержании.</span><span class="sxs-lookup"><span data-stu-id="6e01b-116">The system will automatically send escalation notices until the alloted escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="6e01b-117">**Уведомление о повторной выпуске** — в ходе проведения расследования при обновлении содержимого уведомления об удержании оно автоматически отправляется в хранитель.</span><span class="sxs-lookup"><span data-stu-id="6e01b-117">**Reissue notice** - During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="6e01b-118">**Уведомление о выпуске** — когда хранитель из этого случая, ему будет отправлено уведомление о выпуске.</span><span class="sxs-lookup"><span data-stu-id="6e01b-118">**Release notice** - When a custodian is released from the case, they'll be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="6e01b-119">Портал соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="6e01b-119">Compliance Portal</span></span>
<span data-ttu-id="6e01b-120">Помимо уведомлений по электронной почте, каждый хранитель будет иметь доступ к уникальному порталу соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="6e01b-120">In addition to the email notifications, each custodian will have access to a unique Compliance Portal.</span></span> <span data-ttu-id="6e01b-121">С помощью портала каждый хранитель может просматривать и получать доступ к уведомлениям об активных удержаниях, а также получать к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="6e01b-121">Through the portal, each custodian can view, access, and acknowledge their active hold notifications.</span></span>

![Портал соответствия требованиям для хранитель](media/CustodianPortal.jpg)
