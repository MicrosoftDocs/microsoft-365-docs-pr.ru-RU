---
title: Безопасные ссылки Office 365 ATP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: Функция "безопасные ссылки" обеспечивает проверку гиперссылок в документах Office и в сообщениях электронной почты. Используйте безопасные ссылки, чтобы защитить организацию от фишинга и других атак.
ms.openlocfilehash: fadec60dc25aad418480d7c26a06e92f5a2065dd
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970915"
---
# <a name="office-365-atp-safe-links"></a>Безопасные ссылки Office 365 ATP

## <a name="overview-of-office-365-atp-safe-links"></a>Обзор безопасных ссылок на Office 365 ATP

> [!IMPORTANT]
> Эта статья предназначена для бизнес-клиентов, у которых есть [Office 365 Advanced Threat Protection](office-365-atp.md). Если вы используете Outlook.com, Office 365 для дома или Office 365 персональный и ищете сведения о функции "Безопасные ссылки" в Outlook, см. статью [Улучшенная безопасность Outlook.com](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).

Office 365 ATP Safe Links (часть [Advanced Threat protection](office-365-atp.md)) помогает защитить организацию, предоставляя время на проверку веб-адресов (URL-адресов) в [сообщениях электронной почты](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-email) и [документах Office](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-office-documents). Защита определяется с помощью [политик безопасных ссылок ATP](set-up-atp-safe-links-policies.md) , которые задаются группой безопасности Office 365.
  
После включения политик безопасных ссылок на ATP в Office 365 глобальные администраторы, администраторы безопасности и средства чтения безопасности могут [просматривать отчеты для Advanced Threat protection](view-reports-for-atp.md). Сведения, содержащиеся в этих отчетах, помогут вашей группе по обеспечению безопасности выполнить дальнейшие действия по защите Организации или исследованию инцидентов безопасности.

По мере [добавления новых функций в ATP](office-365-atp.md#new-features-in-office-365-atp)группа безопасности Office 365 может добавить или изменить [политики безопасных ссылок ATP](set-up-atp-safe-links-policies.md)в Организации. Кроме того, вы можете заметить изменения и улучшения, такие как новые пересмотренные [страницы предупреждений](atp-safe-links-warning-pages.md) и визуализация собственных ссылок в Outlook (впервые появилась в Office 365 proplus версии 1809).
         
## <a name="how-to-get-atp-safe-links-protection"></a>Как получить защиту от безопасных ссылок ATP

Для **начала убедитесь, что в подписке включена [Расширенная защита от угроз](office-365-atp.md)**. ATP включается в подписки, такие как [microsoft 365 корпоративный](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 бизнес](https://www.microsoft.com/microsoft-365/business), Office 365 enterprise, в Office 365 образование A5 и т. д. Если в вашей организации есть подписка на Office 365, не включающая в себя Office 365 ATP, вы можете приобрести ATP как надстройку. Дополнительные сведения см. в следующих источниках: 

- [Планы и цены Advanced Threat Protection в Office 365](https://products.office.com/exchange/advance-threat-protection)

- [Описание службы Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 
  
**Далее Убедитесь, что политики безопасных ссылок ATP определены**. (См. раздел [Настройка политик безопасных ссылок Office 365 ATP](set-up-atp-safe-links-policies.md)). Функции безопасных ссылок ATP активны в следующих случаях:
  
- Политики безопасных ссылок ATP настраиваются для электронной почты и документов Office. (См. раздел [Настройка политик безопасных ссылок ATP в Office 365](set-up-atp-safe-links-policies.md)).

- Клиентские приложения Office 365 настроены для использования современной проверки подлинности (это для защиты безопасных ссылок ATP в документах Office). (См. [современная проверка подлинности для Office 2016](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)). 
    
- Пользователи вошли в Office 365 с помощью рабочей или учебной учетной записи. (См. раздел [Вход в Office или office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)
    
- Электронная почта Организации проходит через Exchange Online Protection.  

**Кроме того, убедитесь, что у вас есть необходимые разрешения**. Для определения (или изменения) политик ATP необходимо назначить соответствующую роль. Некоторые примеры описаны в таблице ниже.

|Role  |Где/как назначено  |
|---------|---------|
|Глобальный администратор Office 365 |Пользователь, который подписывается на приобретение Office 365, по умолчанию является глобальным администратором. (Чтобы узнать больше, ознакомьтесь со статьей [о ролях администратора Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .)         |
|Администратор безопасности |Центр администрирования Azure Active Directory ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Управление организациями в Exchange Online |Центр администрирования Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>или <br>  Командлеты PowerShell (см. [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) |
    
## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a>Как убедиться в том, что функция защиты безопасных ссылок ATP находится на месте

В качестве глобального администратора или администратора безопасности обязательно проверяйте [политики безопасных ссылок ATP](set-up-atp-safe-links-policies.md) . Политики безопасных ссылок ATP определяют, применяется ли защита к гиперссылкам только в сообщениях электронной почты, а также к URL-адресам в документах Office.

По завершении политики безопасных ссылок ATP группа безопасности Организации видит сведения о том, как работает защита от "безопасных" ссылок ATP для вашей организации: [Просмотр отчетов для Advanced Threat protection](view-reports-for-atp.md). 

## <a name="example-scenarios"></a>Примеры сценариев
  
В следующей таблице приводятся примеры сценариев, в которых защита ATP может быть недоступна. (Во всех этих случаях предполагается, что у Организации есть Office 365 корпоративный, а).
  
|**Пример сценария**|**Применяется ли защита ATP с безопасными связями в этом случае?**|
|:-----|:-----|
|Жан является участником группы, имеющей политики безопасных ссылок ATP, охватывающие URL-адреса в электронной почте и документах Office. Жан открывает презентацию PowerPoint, которую отправили кто-то другой, а затем щелкает URL-адрес в презентации.  <br/> |Да. Политики безопасных ссылок ATP применяются к группе Жан, электронной почте Жан и документам Word, Excel, PowerPoint или Visio, которые Жан открыть, до тех пор, пока Жан вошли и используете Office 365 профессиональный плюс на устройствах с Windows, iOS и Android.  <br/> |
|В Организации Крис ни один администратор глобального или по безопасности не определил политики безопасных ссылок ATP. Крис получает сообщение электронной почты, содержащее URL-адрес вредоносного веб-сайта. Крис не знает, что URL-адрес является вредоносным и щелкает ссылку.  <br/> |Нет. Политика по умолчанию, которая охватывает URL-адреса для всех в Организации, должна быть определена для обеспечения защиты.  <br/> |
|В Организации Pat нет глобальных или измененных политик безопасных ссылок ATP. Pat открывает документ Word и щелкает URL-адрес в файле.  <br/> |Нет. Политика, включающая документы Office, должна быть определена для обеспечения защиты. Ознакомьтесь со статьей [Настройка политик безопасных ссылок ATP в Office 365](set-up-atp-safe-links-policies.md).  <br/> |
|У Организации Иванов есть политика безопасных ссылок ATP, `https://tailspintoys.com` указанная в качестве заблокированного веб-сайта. Иванов получает сообщение электронной почты, содержащее URL-адрес `https://tailspintoys.com/aboutus/trythispage`. "Иванов" выбирает URL-адрес.  <br/> |Это зависит от того, включены ли весь сайт и все его дочерние страницы в список заблокированных URL-адресов. [В разделе Настройка настраиваемого списка заблокированных URL-адресов с помощью ссылок ATP Safe](set-up-a-custom-blocked-urls-list-wtih-atp.md).  <br/> |
|Ресурс Жан, коллега отправляет электронную почту в Жан, не зная, что сообщение содержит вредоносный URL-адрес.  <br/> |Это зависит от того, определены ли политики безопасных ссылок ATP для электронной почты, отправляемой в пределах организации. Ознакомьтесь со статьей [Настройка политик безопасных ссылок ATP в Office 365](set-up-atp-safe-links-policies.md).  <br/> |


  

