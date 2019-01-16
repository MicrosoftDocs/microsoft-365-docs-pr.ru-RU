---
title: Рекомендуемые политики для защиты документов — Microsoft 365 Enterprise | Документы Майкрософт
description: Описание рекомендаций Майкрософт по защите доступа к файлам SharePoint.
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.date: 06/07/2018
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: 72dd50649dba9e290d50c2831557c06db3cb7586
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870724"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Политика рекомендации по обеспечению безопасности сайтов SharePoint и файлов
В этой статье описывается, как реализовать рекомендуемые удостоверений и доступа к устройствам политик для защиты SharePoint Online и OneDrive для бизнеса. Данное руководство построена на странице [Общие удостоверения и откройте политики устройств](identity-access-policies.md). 

Эти рекомендации основаны на три разных уровня безопасности и защиты для файлов SharePoint, которые могут быть применены на основании детализации вашим требованиям: **Базовое** **конфиденциальных**и **сильно регулируемого**. Дополнительные сведения об этих уровней безопасности и рекомендуемые клиентские операционные системы, ссылается этим рекомендациям в статье [обзора](microsoft-365-policies-configurations.md).

В дополнение к реализации данное руководство, убедитесь, что для настройки сайтов SharePoint с правом объем защиты, включая установку соответствующие разрешения для конфиденциальных и сильно регулируемого содержимого. Дополнительные сведения о создании сайтов для защиты конфиденциальных и сильно регулируемого базового, видеть [безопасного SharePoint Online сайтами и файлами](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files). 

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Обновление общих политик для включения SharePoint и OneDrive для бизнеса
На следующем рисунке показано набора рекомендуемые политик для защиты файлов в SharePoint Online и OneDrive для бизнеса. Указывает, какие политики следует обновить или вновь созданный для добавления защиты для SharePoint Online и OneDrive для бизнеса.

![Сводка по политики для SharePoint Online и OneDrive](../images/identity-access-ruleset-sharepoint.png)

Если вы включили SharePoint Online, во время создания распространенных политик, только необходимые создания новой политики. При настройке правила условного доступа к SharePoint Online включает в себя OneDrive для бизнеса.

Новые политики реализовать устройства защита конфиденциальных и сильно регулируемого содержимого с применением требования к определенным доступа к сайтам SharePoint, которые можно указать. 

В следующей таблице приведены политик, которые необходимо либо просмотрите и обновите или создать новый по SharePoint Online. Общие политики ссылка на инструкции по настройке связанного в статье [распространенных политик доступа удостоверения и устройства](identity-access-policies.md) .


|Уровень защиты|Политики.|Дополнительные сведения|
|:---------------|:-------|:----------------|
|**Базовый уровень**|[После входа в риска *Средний* или *высокий* требуют многофакторной проверкой Подлинности](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Включить SharePoint Online в назначении облачных приложений|
|        |[Блокировать клиенты, не поддерживающие современных проверки подлинности](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Включить SharePoint Online в назначении облачных приложений|
|        |[Определение политик защиты от приложения](identity-access-policies.md#define-app-protection-policies)|Убедитесь, что все рекомендуемые приложения включены в списке приложений. Не забудьте изменить политику для каждой платформы (операций ввода-вывода, Android, Windows)|
|        |[Требовать спецификации ПК](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Включить SharePoint Online в список облачных приложений|
|        |[Использование приложения применяются ограничения в SharePoint Online](#use-app-enforced-restrictions-in-sharepoint-online)|Добавление этой новой политики. Это указывает Azure AD для использования параметров, указанных в SharePoint Online. Это правило применяется ко всем пользователям, но влияет только на доступ к сайтам, включенные в SharePoint Online политик доступа|
|**Конфиденциальный**|[После входа в риска *низкий*, *Средний* или *высокий* требуют многофакторной проверкой Подлинности](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Включить SharePoint Online в назначениях облачных приложений|
|         |[Требовать спецификации ПК *и* мобильных устройств.](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Включить SharePoint Online в списке облачных приложений|
||[SharePoint Online политики управления доступом](#sharepoint-online-access-control-policies): разрешить доступ только для браузера для конкретных сайтов SharePoint с помощью неуправляемые устройств|Это не позволяет изменить и загрузки файлов. Чтобы указать сайты с помощью PowerShell|
|**Строго регулируемый уровень**|[*Всегда* требовать многофакторной проверкой Подлинности](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Включить SharePoint Online в назначении облачных приложений|
||[SharePoint Online политики управления доступом](#use-app-enforced-restrictions-in-sharepoint-online): заблокируйте доступ к определенным сайтам SharePoint с помощью неуправляемые устройств|Чтобы указать сайты с помощью PowerShell|

## <a name="use-app-enforced-restrictions-in-sharepoint-online"></a>Используйте ограничения применяются приложения в SharePoint Online
При реализации управления доступом в SharePoint Online, необходимо создать эту политику условного доступа в Azure AD, чтобы сообщить Azure AD для применения политик, настроенных в SharePoint Online. Это правило применяется ко всем пользователям, но влияет только на доступ к сайтам, указанному с помощью PowerShell при создании элементов управления доступа в SharePoint Online.

Для настройки этой политики см «блокировать или ограничение доступа определенных семейств веб-сайтов SharePoint или OneDrive учетные записи» в этой статье: [Управление доступом с неуправляемых устройств](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).


## <a name="sharepoint-online-access-control-policies"></a>SharePoint Online политик управления доступом
Корпорация Майкрософт рекомендует защиты контента на сайтах SharePoint конфиденциальных и сильно регулируемого содержимое с элементами управления доступа устройства. Для этого необходимо создать политику, которая определяет уровень защиты и сайты, чтобы применить защиту для. 
- Важные сайты: разрешить доступ только для браузера. Это не позволяет пользователям редактирования и загрузку файлов.
- Очень регулируемого сайтов: заблокируйте доступ с неуправляемых устройств.

См. «блокировать или ограничение доступ к учетным записям OneDrive или определенных семейств веб-сайтов SharePoint» в этой статье: [Управление доступом с неуправляемых устройств](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622) . 

## <a name="how-these-policies-work-together"></a>Как работают эти политики
Важно понимать, что разрешения для сайта SharePoint обычно на основе принципа необходимого для доступа к сайтам. Эти разрешения управляют владельцы сайтов и может быть очень динамических. С помощью SharePoint политики доступа устройств гарантирует защиту таких сайтов, независимо от того, ли пользователей, назначенных группе Azure AD связанных с базовой конфиденциальные, или очень регулируемого защиты. 

Ниже приведен пример как политики доступа SharePoint устройств защиты доступа к сайтам.

![Как политики доступа SharePoint устройств защиты сайтов](../images/SharePoint-rules-scenario.png)

На этом рисунке:
- Джеймс назначается условного доступа политики, связанные с защитой базового, но он может предоставляться доступ к сайтам SharePoint, связанного с защитой засекреченные или очень регулируемого. 
- Если Джеймс обращается к засекреченные или очень регулируемого сайта, он является членом свой ПК, его доступа, пока свой компьютер соответствует требованиям.
- Если Джеймс обращается к конфиденциальных сайта, он является членом с помощью свой неуправляемые телефон, разрешенные для базового пользователей, он будет получать доступ только для браузера конфиденциальных сайта из-за политики доступа устройств, настроенных для этого сайта. 
- Если Джеймс обращается к сильно регулируемого сайта, он является членом с помощью свой неуправляемые телефон, он будет заблокировано из-за политики доступа, настроенных для этого сайта. Он только доступ к узлу, используя свой ПК управляемых и ее соответствие требованиям.


<!---
##Block access to content from unmanaged devices (SharePoint admin center)
In the case of SharePoint Online, when a conditional access policy is applied to enforce Intune app protection policies, this might not apply to all applications that access SharePoint Online. Some applications, such as Exchange, have access to some SharePoint resources. For example, Exchange allows attaching SharePoint files by default. Conditional access policies applied to SharePoint Online will not restrict this access. 

To ensure baseline protection is applied uniformly, regardless of which service is accessing SharePoint Online and OneDrive for Business, configure access controls directly in SharePoint admin center. We recommend you configure the following:
- Block access from unmanaged devices. This includes devices that aren't compliant or joined to a domain. 
- Block access from app that don't use modern authentication.

See [Control access from unmanaged devices](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).
-->



## <a name="next-steps"></a>Дальнейшие действия
[Безопасность сайтов и файлов SharePoint Online](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)
