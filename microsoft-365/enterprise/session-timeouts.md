---
title: Таймауты сеансов для Microsoft 365
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 6/29/2018
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: 37a5c116-5b07-4f70-8333-5b86fd2c3c40
ms.collection:
- M365-security-compliance
description: Узнайте, как истечения времени ожидания сеанса используется для обеспечения безопасности и простоты доступа в клиентских приложениях Microsoft 365.
ms.openlocfilehash: 8fbbb526fe4b0ac136f79acd564b268489841e0b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693017"
---
# <a name="session-timeouts-for-microsoft-365"></a>Таймауты сеансов для Microsoft 365

Время жизни сеансов является важной частью проверки подлинности для Microsoft 365 и является важным компонентом в балансировке безопасности и числом запросов на ввод учетных данных для пользователей.
  
## <a name="session-times-for-microsoft-365-services"></a>Времена сеансов для служб Microsoft 365

Когда пользователи проходят проверку подлинности в любом из веб-приложений Microsoft 365 или мобильных приложений, устанавливается сеанс. В течение сеанса пользователи не должны повторно пройти проверку подлинности. Сеансы могут истечь, если пользователи не активны, когда они закрывают браузер или вкладку, или когда истечет срок действия маркера проверки подлинности по другим причинам, например, при сбросе пароля. В службах Microsoft 365 существует разный таймаут сеансов, который соответствует типичному использованию каждой службы.
  
В следующей таблице перечислены времена жизни сеансов для служб Microsoft 365:
  
|**Служба Microsoft 365**|**Время ожидания сеанса**|
|:-----|:-----|
|Центр администрирования Microsoft 365  <br/> |Вам будет предложено предоставить учетные данные для центра администрирования каждые 8 часов.  <br/> |
|SharePoint Online  <br/> |5 дней бездействия до тех пор, пока пользователь выберет " **оставаться в**систему". Если пользователь получает доступ к SharePoint Online через 24 или более часов из предыдущего входа, значение времени ожидания сбрасывается до 5 дней.  <br/> |
|Outlook Web App  <br/> |6 часов.  <br/> Это значение можно изменить с помощью параметра  _активитибаседаусентикатионтимеаутинтервал_ в командлете [Set – OrganizationConfig](https://go.microsoft.com/fwlink/p/?LinkId=615378) .  <br/> |
|Azure Active Directory  <br/> (Используется в Office 2013 клиенты Windows с включенной современной проверкой подлинности)  <br/> | Современная проверка подлинности использует маркеры доступа и обновляет маркеры, чтобы предоставить пользователям доступ к ресурсам Microsoft 365 с помощью Azure Active Directory. Маркер доступа — это веб-маркер JSON, предоставленный после успешной проверки подлинности и действительный в течение 1 часа. Кроме того, предоставляется маркер обновления с более длинным временем жизни. После истечения срока действия маркеров доступа клиенты Office используют действительный маркер обновления для получения нового маркера доступа. Такой обмен проходит успешно, если начальная проверка подлинности пользователя еще действительна.  <br/>  Маркеры обновления действительны в течение 90 дней, и при непрерывном использовании они могут быть действительными до отмены.  <br/>  Маркеры обновления могут быть аннулированы несколькими событиями, такими как:  <br/>  Пароль пользователя изменился с момента выдачи маркера обновления.  <br/>  Администратор может применять политики условного доступа, которые ограничивают доступ к ресурсу, к которому пользователь пытается получить доступ.  <br/> |
|Мобильные приложения SharePoint и OneDrive для Android, iOS и Windows 10  <br/> |Срок действия маркера доступа по умолчанию составляет 1 час. По умолчанию максимальное время неактивности маркера обновления составляет 90 дней.  <br/> [Дополнительные сведения о маркерах и настройке времени жизни маркеров](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> Чтобы отозвать маркер обновления, можно сбросить пароль пользователя Microsoft 365.  <br/> |
|Yammer с помощью входа в Microsoft 365  <br/> |Время существования браузера. Если пользователи закрывают браузер и получают доступ к Yammer в новом браузере, Yammer повторно проверяет их с помощью Microsoft 365. Если пользователи используют сторонние браузеры, которые кэшируют файлы cookie, им не потребуется повторно пройти проверку подлинности при повторном открытии браузера.  <br/> > [!NOTE]> это допустимо только для сетей, использующих вход в систему Microsoft 365 для Yammer.           |
   
