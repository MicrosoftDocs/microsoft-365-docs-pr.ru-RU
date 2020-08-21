---
title: Вопросы и ответы о доменах
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Узнайте больше о доменах, накоторых наследовать ответы на часто задаваемые вопросы.
ms.openlocfilehash: fe602c45059be1b273b7ebe3a11cd91adf89a479
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845848"
---
# <a name="domains-faq"></a>Вопросы и ответы о доменах

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

В этой статье содержатся ответы на часто задаваемые вопросы о доменах в Microsoft 365.

Если вы не нашли ответ на свой вопрос, оставьте комментарий и мы добавим его в список.

В этой статье

- [Что такое приоритет записей MX?](#what-is-mx-priority)
- [Как проверить записи SPF для домена?](#how-can-i-validate-spf-records-for-my-domain)
- [Что такое доменное имя?](#what-is-a-domain-name)
- [Что произойдет, если поставщик DNS не поддерживает некоторые типы записей?](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [Как установить или изменить домен по умолчанию в Microsoft 365?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [Могу ли я добавлять пользовательские поддомены или несколько доменов в Microsoft 365?](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [Как перенести домен из Microsoft 365 в другой узел?](#how-do-i-transfer-a-domain-from-microsoft-365-to-another-host)
- [Почему у меня есть домен onmicrosoft.com?](#why-do-i-have-an-onmicrosoftcom-domain)
- [Почему у меня есть onmicrosoft.de?](#why-do-i-have-an-onmicrosoftde-domain)
- [Как проверить состояние некоммерческого использования или образования?](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a>Что такое приоритет записей MX?

Почта доставляется на сервер почтового обменника, который имеет наименьший номер предпочтения (наивысший приоритет), поэтому у записи MX, которая используется для маршрутизации, должен быть наименьший номер предпочтения (обычно 0) или  *высокий*  приоритет. 
  
- При создании записи MX большинство поставщиков услуг размещения DNS требуют указать номер предпочтения.
    
- В некоторых службах соответствующий параметр называется  *предпочтением*  , а в некоторых   *приоритетом*  . 
    
- В некоторых требуется указать число, а в некоторых  выбрать значение  *Низкий*  ,  *Средний*  или  *Высокий*  . 
    
- Если у вас только одна запись MX, подойдет любое значение.
    
- Если у вас есть несколько таких записей, убедитесь, что запись MX, используемая для маршрутизации почты, имеет более высокий приоритет, чем та, которая применяется для подтверждения владения доменом.
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>Как проверить записи SPF для домена?

Важно использовать только одну запись **TXT для spF.** Если у вас уже есть запись SPF, нужно добавить в нее новые значения Microsoft 365, а не создавать новую. После добавления или обновления записи SPF для электронной почты Майкрософт проверьте правильности синтаксиса с помощью одного из следующих средств: 
  
- [Инструменты для тестирования записей SPF](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- [Веб-интерфейс Dig](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a>Что такое доменное имя?

Домен  это уникальное имя, которое указано после символа **@** в адресах электронной почты и после **www.** в веб-адресах. Как правило, за основу берется название вашей организации, к которому добавляется стандартный суффикс, например  *vasha_kompaniya.com*  или  *universitet.edu*  . 
  
Использование личного домена, например** \@ "надежного contoso.com" с**Microsoft 365, помогает сформировать доверие и повысить свою торговую марку. 
  
В [Microsoft 365 можно купить](../get-help-with-domains/buy-a-domain-name.md)домен в Microsoft 365 и настроить его автоматически, или вы можете купить или воспользоваться им ее у регистратора доменных имен.
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>Что произойдет, если поставщик DNS не поддерживает некоторые типы записей?

Если вы управляете своими записями DNS сами, но ваш узел DNS поддерживает не все записи, необходимые для Microsoft 365, некоторые функции Microsoft 365 не будут работать. Мы рекомендуем передать домен регистратору, который поддерживает все необходимые записи DNS.
  
Поставщики, поддерживающие все необходимые записи DNS:
  
- Dynadot
    
- eNomCentral
    
- Europe Registry
    
- GoDaddy
    
- Hover
    
- MyHosting.com
    
- Name.com
    
- Nearly Free Speech
    
- Nettica
    
- Network Information Center (NIC)
    
- Network Solutions
    
- Register.com
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a>Как установить или изменить домен по умолчанию в Microsoft 365?

Чтобы можно было выбрать домен по умолчанию, необходимо добавить хотя бы один настроенный домен, добавленный в Microsoft 365.

::: moniker range="o365-worldwide"

1. В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).

::: moniker-end

::: moniker range="o365-germany"

1. В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> (Домены).

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> (Домены).

::: moniker-end
    
2. На странице **"Домены"** выберите домен, который необходимо использовать по умолчанию для новых адресов электронной почты. 
    
3. Нажмите кнопку **По умолчанию**.
    
::: moniker range="o365-worldwide"

Изменить имя первоначального домена  *.onmicrosoft.com*  невозможно. 

::: moniker-end

::: moniker range="o365-germany"

Невозможно изменить имя исходного *домена .onmicrosoft.de.* 

::: moniker-end

::: moniker range="o365-21vianet"

Невозможно изменить имя исходного *домена partner.onmschina.cn нельзя.* 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a>Могу ли я добавлять пользовательские поддомены или несколько доменов в Microsoft 365?

::: moniker range="o365-worldwide"

Да. Чтобы добавить поддомены, необходимо управлять собственными настройками DNS на веб-сайте регистратора. Если вы позволяете Майкрософт управлять параметрами DNS с записями nS или если вы его купили на сайте Майкрософт, вы не сможете добавить поддомены.

::: moniker-end

::: moniker range="o365-germany"

Да! Чтобы добавить поддомены, необходимо управлять собственными настройками DNS на веб-сайте регистратора. Если вы позволяете Майкрософт управлять параметрами DNS с записями nS или если вы его купили на сайте Майкрософт, вы не сможете добавить поддомены.

::: moniker-end

::: moniker range="o365-21vianet"

Да! Чтобы добавить поддомены, необходимо управлять собственными настройками DNS на веб-сайте регистратора. Если вы дали возможности управлять параметрами DNS с записями NS в 21Vianet, вы не сможете добавить поддомены.

::: moniker-end

Обычно в подписку Microsoft 365 можно добавить до 900 доменов.
  
Например, вы можете добавить домены contoso.com и contosomarketing.com, а затем  поддомены www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com и т. д.
  
При добавлении поддомена он автоматически проверяется на основе проверяемого родительского домена.
  
При добавлении в Microsoft 365 нескольких доменов в любом из добавленных вами доменов можно разместить любую службу (например, почтовую).  *Когда вы меняете электронную почту в Microsoft 365, обновывая запись MX домена, все сообщения, отправляемые в этот домен, будут поступать в Microsoft 365.* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> Если вы добавили contoso.com в подписку на Microsoft 365, вы также можете добавить дочернего домена xyz.contoso.com к другой организации Microsoft 365. При добавлении поддомена вам будет предложено добавить запись TXT в поставщик услуг размещения DNS.

## <a name="how-do-i-transfer-a-domain-from-microsoft-365-to-another-host"></a>Как перенести домен из Microsoft 365 в другой узел?

Процедура передачи домена см. в разделе ["Передача домена из Майкрософт на другой узел".](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host)

## <a name="pilot-microsoft-365-from-my-custom-domain"></a>Тестирование Microsoft 365 с личного домена

Процедуру пилотной работы с электронной почтой Microsoft 365 с личного домена в почтовый ящик Microsoft 365 см. в [пилотном проекте Microsoft 365 из своего личного домена.](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain)

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>Почему у меня есть домен onmicrosoft.com?

После регистрации в службе Microsoft 365 *создает contoso.onmicrosoft.com.* Он будет исползован при регистрации *(например, alan@contoso.onmicrosoft.com).* 
  
 **Если вы хотите, чтобы ваша электронная почта * \@ выглядела как contoso.com-адрес, или*** выполните действия, описанные в разделе Добавление пользователей и домена в Microsoft [365,](add-domain.md) если вы уже принадлежите ему. [buy the domain](../get-help-with-domains/buy-a-domain-name.md) 
  
- **Домен onmicrosoft невозможно переименовать после регистрации.** Например, если первоначально вы выбрали домен fourthcoffee.onmicrosoft.com, его не удастся переименовать в fabrikam.onmicrosoft.com. Чтобы использовать другой onmicrosoft.com, необходимо создать новую подписку в Microsoft 365. 
    
- **URL-адрес сайта группы переименовать нельзя.** URL-адрес сайта группы основан на onmicrosoft.com вашего имени. К сожалению, из-за такого способа архитектуры SharePoint Online невозможно переименовать сайт группы. 
    
- **Домен onmicrosoft невозможно удалить.** Microsoft 365 необходимо держать это решение, так как она используется в нем в своей подписке в работе. Несмотря на это, вы можете им не пользоваться, если добавите личный домен. 
    
При желании можно продолжить использование исходного домена onmicrosoft.com даже после добавления личного домена. Он будет поддерживаться в электронной почте и других службах.
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>Почему у меня есть onmicrosoft.de?

При регистрации в службе Microsoft 365 создает *для вас домен, например contoso.onmicrosoft.de.* Он будет исползован при регистрации *(например, alan@contoso.onmicrosoft.de.* 
  
 **Если вы хотите, чтобы *ваше сообщение электронной почты выглядело как alan@contoso.de:* купите** [домен или](../get-help-with-domains/buy-a-domain-name.md) просто выполните действия, описанные в разделе Добавление пользователей и домена в [Microsoft 365,](add-domain.md) если вы уже владеете им. 
  
- **Домен onmicrosoft невозможно переименовать после регистрации.** Например, если первоначально вы выбрали fourthcoffee.onmicrosoft.de, не можете использовать fabrikam.onmicrosoft.de. Чтобы использовать другой onmicrosoft.de, необходимо создать новую подписку в Microsoft 365. 
    
- **URL-адрес сайта группы переименовать нельзя.** URL-адрес сайта группы основан на onmicrosoft.de имя вашего домена. К сожалению, из-за такого способа архитектуры SharePoint Online невозможно переименовать сайт группы. 
    
- **Домен onmicrosoft невозможно удалить.** Microsoft 365 необходимо держать это решение, так как она используется в нем в своей подписке в работе. Несмотря на это, вы можете им не пользоваться, если добавите личный домен. 
    
Можно продолжить использование исходного домена onmicrosoft.de даже после добавления домена. Он будет поддерживаться в электронной почте и других службах.
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>Как проверить состояние некоммерческого использования или образования?

1. Выберите **"Настройка"** в [Центре администрирования,](https://docs.microsoft.com/microsoft-365/admin/admin-home) чтобы запустить мастер. (Сначала войдите в Microsoft 365.) 
    
2. Чтобы стать администратором в учебном заведении, выберите  **параметр "Стать администратором"** в Microsoft 365. 
    
3. Вам будет предложено добавить запись DNS TXT на сайте узла DNS для вашего домена. Почему? Поскольку при входе на узел DNS добавлена запись для вашего домена, вы послушаете Microsoft 365 подтвердить, что вы владеете доменным именем.
    
4. После добавления записи вернитесь на портал Microsoft 365 и подтвердите, что вы добавили запись, чтобы Microsoft 365 мог проверить.
    
У вас есть некоммерческая организация и вам требуется получить Microsoft 365? [Убедитесь, что ваша организация квалифицицируется,](https://www.microsoft.com/en-us/nonprofits/eligibility) и затем зарегистрируйтесь для получения этой услуги. 
  
Хотите узнать больше о получении прав администратора в учебном заведении? [Узнайте о нем целиком.](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)