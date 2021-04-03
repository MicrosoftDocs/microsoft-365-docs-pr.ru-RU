---
title: Устранение неполадок аналитики использования Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Узнайте, как устранить проблемы с помощью приложения шаблона Microsoft 365 Use Analytics.
ms.openlocfilehash: bc7f1f7188a209188f1a67a20bf79477c6e1d4a0
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580742"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Устранение неполадок аналитики использования Microsoft 365

Ознакомьтесь со следующим списком сообщений об ошибках, чтобы получить помощь в наиболее распространенных проблемах с помощью аналитики использования Microsoft 365.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>We are unable to process your request. Сначала необходимо подписаться на эти данные из центра администрирования Microsoft 365

 **Код ошибки:** 422 
  
 **Где вы увидите это сообщение:** В Power BI при подключении к приложению Microsoft 365 Use Analytics или при непосредственном вызове API отчетов Microsoft 365. 
  
 **Причина:** Прежде чем подключиться к приложению, необходимо подписаться на данные центра администрирования Microsoft 365. Если этот шаг не будет сделан первым, вы не сможете подключиться к приложению шаблона, даже если вы предоставите свой ID клиента Microsoft 365. 
  
 **Чтобы устранить эту ошибку:** Чтобы подписаться на данные, перейдите в центр администрирования Отчеты Использования и найти \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> плитку аналитики использования Microsoft 365 на главной странице панели мониторинга. Выберите кнопку **Начало** работы, а затем в открываемой области **Отчеты** включите параметр Make **data available to Microsoft 365 use analytics for Power BI** setting on and **Save**.
  
## <a name="we-are-processing-your-data"></a>We are processing your data

 **Где вы увидите это сообщение:** В **плитке аналитики использования Microsoft 365** на **панели** мониторинга использования в центре администрирования Microsoft 365. 
  
 **Причина:** Когда вы [решите](enable-usage-analytics.md) увидеть данные в приложении шаблона из центра администрирования Microsoft 365, система Microsoft 365 начинает создавать исторические данные об использовании для вашей организации. В зависимости от размера клиента это действие может занять от 2 до 48 часов. 
  
 **Чтобы исправить это:** Просто будьте терпеливы, но если сообщение  не изменится, чтобы ваши данные были готовы через 3 дня, обратитесь в [Корпорацию Майкрософт 365 для поддержки бизнеса.](../contact-support-for-business-products.md)
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>We are unable to process your request at this time. We are still preparing the data for your organization

 **Код ошибки**: 423 
  
 **Где вы увидите это сообщение:** В Power BI при подключении к приложению Microsoft 365 Use Analytics или при непосредственном вызове API отчетов Microsoft 365. 
  
 **Причина:** Когда вы [решите увидеть](enable-usage-analytics.md) данные в приложении шаблона из центра администрирования, система Microsoft 365 начинает создавать исторические данные об использовании для вашей организации. В зависимости от размера клиента этот шаг может занять от двух часов до 48 часов. 
  
 **Чтобы исправить это:** Просто будьте терпеливы, но если сообщение  не меняется на ваши данные готовы даже через 3 дня с момента инициации, свяжитесь с [Microsoft 365 для поддержки бизнеса](../contact-support-for-business-products.md).
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>The tenant ID you provided is not in the correct format

 **Код ошибки**: 400 
  
 **Где вы увидите это сообщение:** В Power BI при подключении к приложению Microsoft 365 Use Analytics или при непосредственном вызове API отчетов Microsoft 365. 
  
 **Причина:** ID клиента — это guid и должен быть в формате xxxxx-xxxx-xxxx-xxxx-xxxx. Если вы введите любую другую строку в поле ввода клиента, вы получите эту ошибку. 
  
 **Чтобы устранить эту ошибку:** Перейдите к центру администрирования Отчеты Использования и найдите плитку аналитики использования \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 на главной странице панели мониторинга. ID клиента указан на плитке. Вы можете скопировать его здесь и вклеить в диалоговое окно для подключения к приложению шаблона. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>The tenant ID you provided is not recognized by our system

 **Код ошибки**: 404 
  
 **Где вы увидите это сообщение:** В Power BI при подключении к приложению Microsoft 365 Use Analytics или при непосредственном вызове API отчетов Microsoft 365. 
  
 **Причина:** Предоставленный вами удостоверение клиента не является действительным или не существует. 
  
 **Чтобы устранить эту ошибку:** Перейдите к центру администрирования Отчеты Использования и найдите плитку аналитики использования \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 на главной странице панели мониторинга. ID клиента указан на плитке. Вы можете скопировать его здесь и вклеить в диалоговое окно для подключения к приложению шаблона. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Please re-enter your credentials to sign in to Power BI again

Код ошибки: 302
  
 **Где вы увидите это сообщение:** В Power BI при подключении к приложению Microsoft 365 Use Analytics или при непосредственном вызове API отчетов Microsoft 365. 
  
 **Причина:** код авторизации не сработал; возможно, вам потребуется повторно ввести учетные данные. 
  
 **Как исправить ошибку**: выйдите из Power BI, а затем войдите еще раз. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>You do not have the right authorization to access to this data. To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins

 **Код ошибки**: 403 
  
 **Где вы увидите это сообщение:** В Power BI при подключении к приложению Microsoft 365 Use Analytics или при непосредственном вызове API отчетов Microsoft 365. 
  
 **Причина:** Код авторизации не удалось, так как пользователь, который пытался подключиться к приложению шаблона, не имеет нужного уровня авторизации для доступа к этим данным. 
  
 **Чтобы устранить эту ошибку:** Предоставление учетных данных пользователя, который является глобальным администратором, администратором   **Exchange,** **администратором Skype для** бизнеса, администратором  **SharePoint,** глобальным читателем или читателем отчетов для подключения к приложению шаблона. Дополнительные [сведения см. в](../add-users/about-admin-roles.md) дополнительных сведениях о ролях администратора. 
  
## <a name="refresh-failed"></a>Refresh failed

 **Где выводится это сообщение:** в сообщениях электронной почты от Power BI или в сообщениях о сбоях в журнале обновления. 
  
 **Причина:** Иногда учетные данные пользователя, подключенного к приложению шаблона, сбрасываются и не обновляются в параметрах подключения приложения-шаблона, из-за чего пользователь может видеть ошибки сбоя обновления. 
  
 **Чтобы устранить эту ошибку:** В Power BI найдите набор данных, соответствующий шаблону Microsoft 365 Use Analytics, выберите обновление расписания и укажи учетные данные администратора.  
  
Если это не работает, очистить кэш и повторно создать приложение шаблона.
  
  
