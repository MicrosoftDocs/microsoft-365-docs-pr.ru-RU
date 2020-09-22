---
title: Безопасные ссылки ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: В этой статье рассказывается, как использовать безопасные ссылки для защиты Организации от фишинга и других атак.
ms.openlocfilehash: 486c19fa0ba47baadf7b3418608a644407e6e1d0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200437"
---
# <a name="atp-safe-links"></a>Безопасные ссылки ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="overview-of-office-365-atp-safe-links"></a>Обзор безопасных ссылок на Office 365 ATP

> [!IMPORTANT]
> Эта статья предназначена для бизнес-клиентов, у которых есть [Office 365 Advanced Threat Protection](office-365-atp.md). Если вы используете Outlook.com, семейство Microsoft 365 или Microsoft 365 персональный, а вы ищете сведения о безопасных ссылках в Outlook, ознакомьтесь со статьей [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Office 365 ATP Safe Links (часть [office 365 Advanced Threat protection](office-365-atp.md)) поможет защитить организацию, предоставив время на проверку веб-адресов (URL-адресов) в [сообщениях электронной почты](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-email) и [документах Office](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-office-documents). Защита определяется с помощью [политик безопасных ссылок ATP](set-up-atp-safe-links-policies.md) , которые задаются группой безопасности Microsoft 365.

После выполнения политик безопасных ссылок ATP, глобальные администраторы, администраторы безопасности и средства чтения безопасности могут [просматривать отчеты для Advanced Threat protection](view-reports-for-atp.md). Сведения, содержащиеся в этих отчетах, помогут вашей группе по обеспечению безопасности выполнить дальнейшие действия по защите Организации или исследованию инцидентов безопасности.

По мере [добавления новых функций в ATP](office-365-atp.md#new-features-in-office-365-atp)группа Microsoft 365 Security может добавить или изменить [политики безопасных ссылок ATP](set-up-atp-safe-links-policies.md)в Организации. Кроме того, вы можете заметить изменения и улучшения, такие как новые пересмотренные [страницы предупреждений](atp-safe-links-warning-pages.md) и визуализация собственных ссылок в Outlook (впервые появилась в приложениях Microsoft 365 для enterprise версии 1809).

## <a name="how-to-get-atp-safe-links-protection"></a>Как получить защиту от безопасных ссылок ATP

**Сначала убедитесь, что подписка включает [Office 365 Advanced Threat protection](office-365-atp.md) ** План 1 или план 2. Office 365 ATP входит в подписку, например, [microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 бизнес, Microsoft бизнес](https://www.microsoft.com/microsoft-365/business), Office 365 корпоративный, Office 365 для образования A5 и т. д. Если у вашей организации есть подписка на Microsoft 365, не включающая в себя Office 365 ATP, вы можете приобрести ATP как надстройку. Дополнительные сведения см. на следующих ресурсах: 

- [Планы и цены Advanced Threat Protection в Office 365](https://products.office.com/exchange/advance-threat-protection)

- [Описание службы Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

**Далее Убедитесь, что политики безопасных ссылок ATP определены**. (См. раздел [Настройка политик безопасных ссылок Office 365 ATP](set-up-atp-safe-links-policies.md)). Функции безопасных ссылок ATP активны в следующих случаях:

- Политики безопасных ссылок ATP настраиваются для электронной почты и документов Office. (См. раздел [Настройка политик безопасных ссылок ATP](set-up-atp-safe-links-policies.md)).

- Клиентские приложения Microsoft 365 настроены для использования современной проверки подлинности (это относится к защите ссылок ATP в документах Office). (См. [современная проверка подлинности для Office 2016](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)).

- Пользователи выполнили вход с помощью рабочей или учебной учетной записи. (См. раздел [Вход в Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)).

- Электронная почта Организации проходит через Exchange Online Protection.

**Кроме того, убедитесь, что у вас есть необходимые разрешения**. Для определения (или изменения) политик ATP необходимо назначить соответствующую роль. Некоторые примеры описаны в таблице ниже.

****

|Роль|Где/как назначено|
|---|---|
|Глобальный администратор|Сотрудник, который подписывается на приобретение Microsoft 365, по умолчанию является глобальным администратором. (Чтобы узнать больше, ознакомьтесь со статьей [о ролях администратора майкрософт 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .)|
|Администратор безопасности|Центр администрирования Azure Active Directory ( <https://aad.portal.azure.com> )|
|Управление организациями в Exchange Online|Центр администрирования Exchange ( <https://outlook.office365.com/ecp> ) <br>или <br>  Командлеты PowerShell (см. [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|
|

## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a>Как убедиться в том, что функция защиты безопасных ссылок ATP находится на месте

В качестве глобального администратора или администратора безопасности обязательно проверяйте [политики безопасных ссылок ATP](set-up-atp-safe-links-policies.md) . Политики безопасных ссылок ATP определяют, применяется ли защита к гиперссылкам только в сообщениях электронной почты, а также к URL-адресам в документах Office.

По завершении политики безопасных ссылок ATP группа безопасности Организации видит сведения о том, как работает защита от "безопасных" ссылок ATP для вашей организации: [Просмотр отчетов для Advanced Threat protection](view-reports-for-atp.md).

## <a name="example-scenarios"></a>Примеры сценариев

В следующей таблице приводятся примеры сценариев, в которых защита ATP может быть недоступна. (Во всех этих случаях предполагается, что у Организации есть Office 365 корпоративный, а).

****

|Пример сценария|Применяется ли защита ATP с безопасными связями в этом случае?|
|---|---|
|Жан является участником группы, имеющей политики безопасных ссылок ATP, охватывающие URL-адреса в электронной почте и документах Office. Жан открывает презентацию PowerPoint, которую отправили кто-то другой, а затем щелкает URL-адрес в презентации.|Да. Политики безопасных ссылок ATP применяются к группе Жан, электронной почте Жан и документам Word, Excel, PowerPoint или Visio, которые Жан открыть, до тех пор, пока Жан вошли и используете приложения Microsoft 365 для предприятий на устройствах с Windows, iOS и Android.|
|В Организации Крис ни один администратор глобального или по безопасности не определил политики безопасных ссылок ATP. Крис получает сообщение электронной почты, содержащее URL-адрес вредоносного веб-сайта. Крис не знает, что URL-адрес является вредоносным и щелкает ссылку.|Нет. Политика по умолчанию, которая охватывает URL-адреса для всех в Организации, должна быть определена для обеспечения защиты.|
|В Организации Pat нет глобальных или измененных политик безопасных ссылок ATP. Pat открывает документ Word и щелкает URL-адрес в файле.|Нет. Политика, включающая документы Office, должна быть определена для обеспечения защиты. Ознакомьтесь со статьей [Настройка политик безопасных ссылок ATP в Office 365](set-up-atp-safe-links-policies.md).|
|У Организации Иванов есть политика безопасных ссылок ATP, `https://tailspintoys.com` указанная в качестве заблокированного веб-сайта. Иванов получает сообщение электронной почты, содержащее URL-адрес `https://tailspintoys.com/aboutus/trythispage` . "Иванов" выбирает URL-адрес.|Это зависит от того, включены ли весь сайт и все его дочерние страницы в список заблокированных URL-адресов. [В разделе Настройка настраиваемого списка заблокированных URL-адресов с помощью ссылок ATP Safe](set-up-a-custom-blocked-urls-list-atp.md).|
|Ресурс Жан, коллега отправляет электронную почту в Жан, не зная, что сообщение содержит вредоносный URL-адрес.|Это зависит от того, определены ли политики безопасных ссылок ATP для электронной почты, отправляемой в пределах организации. Ознакомьтесь со статьей [Настройка политик безопасных ссылок ATP в Office 365](set-up-atp-safe-links-policies.md).|
|
