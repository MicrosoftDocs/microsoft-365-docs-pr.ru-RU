---
title: Настройка настраиваемого списка заблокированных URL-адресов с помощью безопасных ссылок ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как настроить список заблокированных URL-адресов для Организации с помощью Office 365 Advanced Threat protection.
ms.openlocfilehash: 9e0c6e75358c97a21ab0765edf5a15bafe53d75e
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046320"
---
# <a name="set-up-a-custom-blocked-urls-list-using-atp-safe-links"></a>Настройка настраиваемого списка заблокированных URL-адресов с помощью безопасных ссылок ATP

> [!IMPORTANT]
> Эта статья предназначена для бизнес-клиентов, у которых есть [Office 365 Advanced Threat Protection](office-365-atp.md). Если вы являетесь домашним пользователем, который ищет сведения о безопасных ссылках в Outlook, ознакомьтесь со статьей [Advanced Outlook.com Security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).

В [Office 365 Advanced Threat protection](office-365-atp.md) (ATP) в Организации может быть настроен список блокируемых адресов веб-сайтов (URL-адресов). Если URL-адрес заблокирован, пользователи, которые щелкают ссылки на заблокированный URL-адрес, отправляются на [страницу предупреждения](atp-safe-links-warning-pages.md) , напоминающую следующему изображению: 
  
![Этот сайт заблокирован](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
Список заблокированных URL-адресов определяется группой безопасности Microsoft 365 для бизнеса, и этот список применяется ко всем пользователям в Организации, на которые распространяется политика безопасных ссылок Office 365 ATP. 
  
В этой статье рассказывается, как настроить настраиваемый список заблокированных URL-адресов вашей организации для [безопасных ссылок ATP в Office 365](atp-safe-links.md).
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a>Просмотр или изменение настраиваемого списка заблокированных URL-адресов

[Для безопасных ссылок ATP в Office 365](atp-safe-links.md) используется несколько списков, в том числе настраиваемый список заблокированных URL-адресов вашей организации. Если у вас есть необходимые разрешения, вы можете настроить настраиваемый список в Организации. Для этого необходимо изменить политику безопасных ссылок по умолчанию в Организации.

Чтобы изменить (или определить) политики ATP, необходимо назначить одну из ролей, описанных в следующей таблице. 

|Role  |Где/как назначено  |
|---------|---------|
|Глобальный администратор |Сотрудник, который подписывается на приобретение Microsoft 365, по умолчанию является глобальным администратором. (Чтобы узнать больше, ознакомьтесь со статьей [о ролях администратора майкрософт 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .)         |
|Администратор безопасности |Центр администрирования Azure Active Directory ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Управление организациями в Exchange Online |Центр администрирования Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>или <br>  Командлеты PowerShell (см. [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) |

> [!TIP]
> Дополнительные сведения о ролях и разрешениях приведены [в разделе разрешения в &amp; центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a>Просмотр или изменение настраиваемого списка заблокированных URL-адресов
  
1. Перейдите к [https://protection.office.com](https://protection.office.com) рабочей или учебной учетной записи и войдите в нее. 
    
2. В панели навигации слева в разделе **Управление угрозами**выберите **пункт** \> **безопасные ссылки**.
    
3. В разделе **политики, которые применяются ко всей Организации** , выберите **значение по умолчанию**, а затем нажмите кнопку **изменить** (кнопка Изменить напоминает карандаш).<br/>![Нажмите кнопку изменить, чтобы изменить политику по умолчанию для защиты безопасных ссылок](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)<br/>Это позволяет просматривать список заблокированных URL-адресов. В первую очередь могут не быть указаны URL-адреса.<br/>![Список заблокированных URL-адресов в политике безопасных ссылок по умолчанию](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)
  
4. Выберите поле **Введите допустимый URL** -адрес, введите URL-адрес, а затем выберите знак плюса (**+**). 

5. Завершив добавление URL-адресов, в правом нижнем углу экрана нажмите кнопку **сохранить**.
    
## <a name="a-few-things-to-keep-in-mind"></a>Следует учитывать несколько моментов.

При добавлении URL-адресов в список учитывайте следующие моменты. 

- Не включайте косую черту ( **/**) в конце URL-адреса. Например, вместо ввода `https://www.contoso.com/`введите. `https://www.contoso.com`
    
- Можно указать URL-адрес только для домена (например `contoso.com` , `tailspintoys.com`или). При этом будут заблокированы нажатия на любой URL-адрес, содержащий домен.

- Можно указать поддомен (например `toys.contoso.com*`,), не блокируя полный домен (например `contoso.com`,). При этом будет выполняться переход по любому URL-адресу, который содержит поддомен, но не будет блокировать переходы по URL-адресу, содержащему полный домен.  
    
- В URL-адрес можно добавить до трех подстановочных\*знаков (). В следующей таблице приведено несколько примеров того, что можно ввести и какие действия имеют эти записи.
    
|**Пример записи**|**Что он делает**|
|:-----|:-----|
|`contoso.com` или `*contoso.com*`  <br/> |Блокирует домен, дочерние домены и пути, например `https://www.contoso.com`, и `https://sub.contoso.com``https://contoso.com/abc`  <br/> |
|`https://contoso.com/a`  <br/> |Блокирует сайт `https://contoso.com/a` , но не дополнительные подпути, такие как`https://contoso.com/a/b`  <br/> |
|`https://contoso.com/a*`  <br/> |Блокирует сайт `https://contoso.com/a` и дополнительные подпути, такие как`https://contoso.com/a/b`  <br/> |
|`https://toys.contoso.com*`  <br/> |Блокирует поддомен (в данном случае — "Toys"), но разрешить переход на другие URL-адреса доменов `https://contoso.com` ( `https://home.contoso.com`например, или).  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a>Определение исключений для определенных пользователей в Организации

Если требуется, чтобы определенные группы могли просматривать URL-адреса, которые могут быть заблокированы для других, можно указать политику безопасных ссылок ATP, которая применяется к определенным получателям. Узнайте [, как настроить настраиваемый список URL-адресов "не переопределять" с помощью ссылок ATP Safe](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).
  
