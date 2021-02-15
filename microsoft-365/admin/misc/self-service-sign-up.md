---
title: Использование самостоятельной регистрации в организации
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_SMB
search.appverid:
- MET150
ms.assetid: 4f8712ff-9346-4c6c-bb63-a21ad7a62cbd
description: Узнайте о программах самостоятельной регистрации в Microsoft 365 и доступных программах самостоятельного обслуживания, таких как Microsoft Power Apps, Microsoft Flow и Dynamics 365 for Finance.
ms.openlocfilehash: 21e41661141a817a1751c80608035d839d2e3952
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906577"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>Использование самостоятельной регистрации в организации

Самообслуживка упрощает регистрацию пользователей в организации для работы с веб-службами майкрософт. Мы называем этот процесс регистрации самостоятельной регистрацией, так как ваши пользователи могут зарегистрироваться для использования услуг, оплаченных вашей подпиской, или использовать бесплатные службы, не просите вас принять меры от их имени.
  
## <a name="how-self-service-sign-up-works"></a>Как работает самообслуживка

В примере ниже описано, как работает самостоятельная регистрация в учебном заведении. Этот же способ подходит для любой организации, для клиента которой включены программы самостоятельной регистрации.
  
1. У студентов и преподавателей есть адреса электронной почты учебного заведения, которые указывают, что они связаны с ним. Например, адрес электронной почты jakob@uw.edu указать учащегося в университете Вашингтона.
2. Студенты и преподаватели [](https://go.microsoft.com/fwlink/p/?LinkId=536628)перейдите на наш веб-сайт и используйте свой адрес электронной почты для регистрации в службах, которые предлагает ваша организация, таких как приложения Microsoft 365 для предприятий. Они также могут зарегистрироваться для использования бесплатных служб.
3. Мы проверяем их адрес электронной почты, а затем они могут сразу приступить к использованию Microsoft 365, Power BI или других служб.
4. Администратор предприятия может видеть, кто подписывался на подписку, выбрав  ее на странице "Лицензирование" в Центре администрирования Microsoft 365. Таким образом вы сможете увидеть, когда в клиенте есть новые или неузнаные лицензии на службы. Чтобы определить, могут ли пользователи подписываться на самообслуживающие подписки, используйте с параметром **AllowAdHocSubscriptions** с помощью powerShell [set-MsolCompanySettings.](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) Дополнительные сведения см. в сведениях о том, [как управлять настройками самообслуживки?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="available-self-service-programs"></a>Доступные программы самостоятельной регистрации

Ниже приведены доступные в настоящее время программы самостоятельной регистрации. Этот список будет обновляться по мере добавления новых программ.
  
| Программа <br/> | Description <br/> | Дополнительные сведения <br/> | Веб-сайт для самостоятельной регистрации <br/> |
|:-----|:-----|:-----|:-----|
|Office 365 A1**** <br/> |Любой учащийся или преподаватель может использовать адрес электронной почты учебного заведения для бесплатной регистрации в Office 365 и получения приложений Office в Интернете, 1 ТБ облачного хранилища OneDrive и SharePoint Online для сайтов классов, команд и проектов.  <br/> |[Office 365 для образования: технические вопросы и ответы](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 для образования](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 A1 Plus** <br/> |Соответствующие требованиям учащиеся и преподаватели могут зарегистрироваться в Office 365 A1 Plus, который включает все вышеперечисленные решения, а также приложения Microsoft 365 для предприятий. Приложения Microsoft 365 для предприятий — это производительное программное обеспечение, в том числе Word, PowerPoint, Excel, Outlook, OneNote, Publisher, Access и Skype для бизнеса, установленное на настольном компьютере или ноутбуке.  <br/> |[Office 365 для образования: технические вопросы и ответы](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 для образования](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Power BI позволяет пользователям визуализировать данные, обмениваться данными и совместно работать интуитивно новыми способами. <br/> Если ваша организация уже подписана, вы можете дополнительно увидеть лицензии на пробную подписку power BI Pro для отдельных пользователей, которые предоставляют пользователям ограниченный бесплатный доступ к расширенным возможностям.  <br/> |[Power BI в организации](https://go.microsoft.com/fwlink/p/?LinkId=536626) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**Служба управления правами** <br/> |RMS для отдельных пользователей  это бесплатная самостоятельная подписка, которая предлагается пользователям в том случае, если они получили конфиденциальные файлы, защищенные с помощью управления правами Azure (Azure RMS), но их ИТ-отдел не внедрил управление правами Azure (Azure RMS) или службу управления правами Active Directory (AD RMS).  <br/> |[RMS для отдельных пользователей и служба Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=536627) <br/> |[Портал управления правами (Майкрософт)](https://portal.azure.com/), на котором можно проверить, можно ли открыть защищенный документ  <br/> |
|**Microsoft PowerApps** <br/> |Служба PowerApps позволяет использовать приложения, созданные вами или сторонними разработчиками, для управления данными в организации. Приложения можно запускать на мобильных устройствах, например телефонах, или в браузере, открыв Dynamics 365. Вы можете создать любое количество приложений, и вам не придется учить для этого язык программирования, такой как C#.  <br/> |[Самостоятельная регистрация в PowerApps](https://go.microsoft.com/fwlink/p/?linkid=841461) <br/> |[Microsoft Power Apps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 for Financials** <br/> |Воспользуйтесь полным решением для управления бизнесом и финансами, предназначенным для малого и среднего бизнеса. Dynamics 365 for Financials упрощает заказы, продажи, выставление счетов и создание отчетов и не требует длительного обучения.  <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 for Operations** <br/> |Работайте еще быстрее. Полный набор ERP-средств, входящий в Dynamics 365 for Operations, обеспечивает глобальную масштабируемость и позволяет использовать аналитику, чтобы поддерживать нужный темп роста.  <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource  это портал SaaS-приложений для бизнеса, основанных на облачной платформе Майкрософт. AppSource включает сотни приложений, надстройки и пакеты содержимого, которые расширяют функциональные возможности продуктов Майкрософт, таких как Azure, Dynamics 365, Office 365 и Power BI.  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Программы вознаграждения для партнеров Майкрософт** <br/> |Сеть Microsoft Partner Network предполагает три типа членства. Каждый тип имеет свои преимущества, которые способствуют росту компании. Участвуйте в программе того уровня, который соответствует вашим уникальным потребностям, чтобы воспользоваться дополнительными преимуществами и развивать отношения с нами и другими партнерами.  <br/> |[Программы вознаграждения для партнеров Майкрософт](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Программы вознаграждения для партнеров Майкрософт](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft Business Center** <br/> |Microsoft Business Center — это портал для клиентов, которые сделали покупки в рамках соглашения о продуктах и услугах Майкрософт (MPSA). <br/> |[Краткое руководство. Регистрация в Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Microsoft Volume License Service Center** <br/> |В Центре обслуживания корпоративных лицензий Майкрософт отображаются лицензии, приобретенные в рамках соглашений Enterprise, Select, Education (Campus или School), Open Value, Open License и ISV Royalty.  <br/> |[Обучение и ресурсы по VLSC](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[Центр обслуживания volume License](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft Education Edition** <br/> |Платформа Minecraft помогает преподавателям мотивировать учащихся и увлечь их учебой. Присоединитесь к сообществу преподавателей, чтобы узнать, как они раскрывают потенциал учащихся с помощью Minecraft.  <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |Выкладывайте видео и делитесь ими с другими сотрудниками, чтобы улучшить взаимодействие, совместную работу и обучение.  <br/> |[Sign up &amp; Day 0 experience](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Power Automate** <br/> |Power Automate — это продукт, который помогает настроить автоматизированные процессы между вашими избранными приложениями и службами для синхронизации файлов, получения уведомлений, сбора данных и других данных.  <br/> |[Sign up and sign in for Power Automate](https://docs.microsoft.com/power-automate/sign-up-sign-in) <br/> |[Power Automate](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Виртуальные агенты Power** <br/> |Виртуальные агенты Power Позволяет группам легко создавать мощные боты с помощью управляемого графического интерфейса без кода без необходимости в компьютерах с данными или разработчиками. Виртуальные агенты Power Virtual в настоящее время решает многие основные проблемы с созданием ботов в отрасли. Это устраняет разрыв между экспертами по предмету и группами разработки, которые работают с ботами, и длительной задержкой между тем, как команды распознают проблему и обновляют бота для ее решения.  <br/> |[Сведения о лицензировании и доступе](https://go.microsoft.com/fwlink/?linkid=2113708) <br/> |[Sign up for Power Virtual Agents](https://aka.ms/TryPVA) <br/> |
|**Azure AD B2B** <br/> |Совместная работа azure Active Directory (Azure AD) с бизнес-бизнесом (B2B) позволяет приглашать внешних пользователей (или гостевых пользователей) использовать платные службы Azure AD. Некоторые функции бесплатны, но для любых платных функций Azure AD вы можете пригласить до пяти гостевых пользователей для каждой лицензии на выпуск Azure AD, которую вы владеете для сотрудника или не гостевого пользователя в клиенте. <br/> |[Самообслужба для регистрации для совместной работы Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/self-service-portal) <br/> |[Руководство по лицензированию совместной работы Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) <br/> |
