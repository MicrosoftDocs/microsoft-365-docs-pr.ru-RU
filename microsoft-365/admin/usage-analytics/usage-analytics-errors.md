---
title: Устранение неполадок аналитики использования Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Узнайте, как устранять проблемы с шаблоном приложения Microsoft 365 Usage Analytics.
ms.openlocfilehash: bf8e4ece7b1e310d91f418f5388cae9aa27f2aa7
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841439"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Устранение неполадок аналитики использования Microsoft 365

Изучите следующий список сообщений об ошибках, чтобы получить помощь по наиболее распространенным вопросам аналитики использования Microsoft 365.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>We are unable to process your request. Сначала необходимо подписаться на эти данные из Центра администрирования Microsoft 365

 **Код ошибки:** 422 
  
 **Где вы увидите это сообщение:** В Power BI при подключении к приложению "Аналитика использования Microsoft 365" или при непосредственном вызове API отчетов Microsoft 365. 
  
 **Причина:** Перед подключением к приложению необходимо подписаться на данные из Центра администрирования Microsoft 365. Если это не сделать сначала, вы не сможете подключиться к приложению шаблона, даже если укажете свой ИД клиента Microsoft 365. 
  
 **Чтобы устранить эту ошибку:** Чтобы подписаться на данные, перейдите в Центр администрирования "Использование отчетов" и найдите плитку аналитики использования \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 на главной странице панели мониторинга. Выберите **кнопку "Начало** работы", а затем в открывскойся области "Отчеты" включите параметр "Сделать данные доступными для аналитики использования **Microsoft 365"** и "Сохранить" **в** Power BI. 
  
## <a name="we-are-processing-your-data"></a>We are processing your data

 **Где вы увидите это сообщение:** На **плитке аналитики использования Microsoft 365** на информационной панели "Использование" в Центре администрирования Microsoft 365.  
  
 **Причина:** Если вы [решите](enable-usage-analytics.md) увидеть данные в приложении шаблона из Центра администрирования Microsoft 365, система Microsoft 365 начнет создавать исторические данные об использовании для вашей организации. В зависимости от размера клиента это действие может занять от 2 до 48 часов. 
  
 **Чтобы устранить эту проблему:** Просто помялись, но если сообщение не изменится на Ваши данные, готово **через** 3 дня, обратитесь в службу поддержки [Microsoft 365 для бизнеса.](../contact-support-for-business-products.md)
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>We are unable to process your request at this time. We are still preparing the data for your organization

 **Код ошибки**: 423 
  
 **Где вы увидите это сообщение:** В Power BI при подключении к шаблону "Аналитика использования Microsoft 365" или при непосредственном вызове API отчетов Microsoft 365. 
  
 **Причина:** Если вы [решите увидеть](enable-usage-analytics.md) данные в приложении шаблона из Центра администрирования, система Microsoft 365 начнет создавать исторические данные об использовании для вашей организации. В зависимости от размера клиента этот шаг может занять от двух до 48 часов. 
  
 **Чтобы устранить эту проблему:** Просто помялись, но если  сообщение не изменится на Ваши данные, оно будет готово даже через 3 дня с момента инициации, обратитесь в службу поддержки [Microsoft 365 для бизнеса.](../contact-support-for-business-products.md)
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>The tenant ID you provided is not in the correct format

 **Код ошибки**: 400 
  
 **Где вы увидите это сообщение:** В Power BI при подключении к шаблону "Аналитика использования Microsoft 365" или при непосредственном вызове API отчетов Microsoft 365. 
  
 **Причина:** ИД клиента — это guid, который должен иметь формат xxxxxxxxx-xxxx-xxxx-xxxx-xxxxxx. Если ввести любую другую строку в поле ввода клиента, вы получите эту ошибку. 
  
 **Чтобы устранить эту ошибку:** Перейдите в центр администрирования "Отчеты об использовании" и найдите плитку аналитики использования \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 на главной странице панели мониторинга. На плитке указан ИД клиента. Вы можете скопировать его здесь и вкопировать в диалоговое окно для подключения к приложению шаблона. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>The tenant ID you provided is not recognized by our system

 **Код ошибки**: 404 
  
 **Где вы увидите это сообщение:** В Power BI при подключении к приложению "Аналитика использования Microsoft 365" или при непосредственном вызове API отчетов Microsoft 365. 
  
 **Причина:** Предоставленный вами ИД клиента не является допустимым или не существует. 
  
 **Чтобы устранить эту ошибку:** Перейдите в центр администрирования "Отчеты об использовании" и найдите плитку аналитики использования \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 на главной странице панели мониторинга. На плитке указан ИД клиента. Вы можете скопировать его здесь и вкопировать в диалоговое окно для подключения к приложению шаблона. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Please re-enter your credentials to sign in to Power BI again

Код ошибки: 302
  
 **Где вы увидите это сообщение:** В Power BI при подключении к приложению "Аналитика использования Microsoft 365" или при непосредственном вызове API отчетов Microsoft 365. 
  
 **Причина:** код авторизации не сработал; возможно, вам потребуется повторно ввести учетные данные. 
  
 **Как исправить ошибку**: выйдите из Power BI, а затем войдите еще раз. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>You do not have the right authorization to access to this data. To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins

 **Код ошибки**: 403 
  
 **Где вы увидите это сообщение:** В Power BI при подключении к приложению "Аналитика использования Microsoft 365" или при непосредственном вызове API отчетов Microsoft 365. 
  
 **Причина:** Сбой кода авторизации, так как пользователь, пытающийся подключиться к приложению шаблона, не имеет нужного уровня авторизации для доступа к этим данным. 
  
 **Чтобы устранить эту ошибку:** Укажете учетные  данные глобального администратора, **администратора Exchange,** **администратора Skype** для  бизнеса,  **администратора SharePoint,** глобального читателя или читателя отчетов, чтобы подключиться к приложению шаблона. Дополнительные [сведения см. в](../add-users/about-admin-roles.md) сведениях о ролях администраторов. 
  
## <a name="refresh-failed"></a>Refresh failed

 **Где выводится это сообщение:** в сообщениях электронной почты от Power BI или в сообщениях о сбоях в журнале обновления. 
  
 **Причина:** Иногда учетные данные пользователя, подключенного к приложению шаблона, сбрасываются и не обновляются в параметрах подключения приложения шаблона, что приводит к ошибкам обновления. 
  
 **Чтобы устранить эту ошибку:** В Power BI найдите набор данных, соответствующий шаблону приложения "Аналитика использования Microsoft 365", выберите обновление расписания и укажийте учетные данные администратора.  
  
Если это не работает, очищайте кэш и повторно создайте приложение шаблона.
  
  
