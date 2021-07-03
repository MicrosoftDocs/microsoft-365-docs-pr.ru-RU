---
title: Использование самообслуживной регистрации в организации
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: seemg, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_signup
search.appverid: MET150
description: Узнайте о Microsoft 365 и доступных программах самообслуживки, таких как Microsoft Power Apps, Microsoft Flow и Dynamics 365 для финансов.
ms.date: 03/17/2021
ms.openlocfilehash: 7aec03abce468342cfeb23da490b1f950ecd7050
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286589"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>Использование самообслуживной регистрации в организации

Самообслуживка упрощает регистрацию пользователей в организации для онлайн-служб в Корпорации Майкрософт. Мы называем этот процесс регистрации "самообслуживаемой регистрацией", так как пользователи могут зарегистрироваться, чтобы использовать службы, оплачиваемые подпиской, или использовать бесплатные службы, не спрашивая вас принять меры от их имени.

## <a name="how-self-service-sign-up-works"></a>Как работает самообслуживка

В примере ниже описано, как работает самостоятельная регистрация в учебном заведении. Этот же способ подходит для любой организации, для клиента которой включены программы самостоятельной регистрации.

1. У студентов и преподавателей есть адреса электронной почты учебного заведения, которые указывают, что они связаны с ним. Например, адрес электронной почты jakob@uw.edu указать студента Вашингтонского университета.
2. Студенты и преподаватели перейдите на наш веб-сайт [и](https://go.microsoft.com/fwlink/p/?LinkId=536628)используйте свой адрес электронной почты, чтобы зарегистрироваться на службы, которые предлагает ваша организация, такие Приложения Microsoft 365 для предприятий. Они также могут зарегистрироваться для использования бесплатных служб.
3. Мы проверяем их адрес электронной почты, а затем они могут сразу же начать использовать Microsoft 365, Power BI или другие службы.
4. В качестве администратора бизнеса вы можете узнать, кто подписался на  подписку, выбрав подписку на странице Лицензирование в Центр администрирования Microsoft 365. Таким образом вы можете увидеть, когда в клиенте есть новые или непризнаные лицензии на службы. Чтобы определить, могут ли пользователи подписываться на подписки на самообслуживку, используйте комлет [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings) PowerShell с параметром **AllowAdHocSubscriptions.** Дополнительные сведения см. в дополнительных сведениях о том, как управлять настройками [самообслуживки?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="available-self-service-programs"></a>Доступные программы самостоятельной регистрации

Ниже приведены доступные в настоящее время программы самостоятельной регистрации. Этот список будет обновляться по мере добавления новых программ.

| Программа <br/> | Описание <br/> | Дополнительные сведения <br/> | Веб-сайт для самостоятельной регистрации <br/> |
|:-----|:-----|:-----|:-----|
|Office 365 A1**** <br/> |Любой учащийся или преподаватель может использовать школьный адрес электронной почты для регистрации бесплатно Office 365 и получения Office приложений для Интернета, 1 ТБ облачного хранилища OneDrive и SharePoint Online для классов, команд и сайтов проектов.  <br/> |[Office 365 для образования: технические вопросы и ответы](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 для образования](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 A1 Плюс** <br/> |Подходящие студенты и преподаватели могут зарегистрироваться на Office 365 A1 Плюс, который включает все, что упоминалось выше, а также Приложения Microsoft 365 для предприятий. Приложения Microsoft 365 для предприятий это программное обеспечение производительности, в том числе Word, PowerPoint, Excel, Outlook, OneNote, Publisher, Access и Skype для бизнеса, установленное на рабочем столе или ноутбуке.  <br/> |[Office 365 для образования: технические вопросы и ответы](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 для образования](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Power BI позволяет пользователям визуализировать данные, обмениваться открытиями и сотрудничать интуитивно новыми способами. <br/> Если ваша организация уже подписана, вы можете дополнительно увидеть лицензии на "Power BI Pro индивидуальная пробная версия пользователя", которые предоставляют пользователям ограниченный бесплатный доступ к расширенным возможностям.  <br/> |[Power BI в организации](./power-bi-in-your-organization.md) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**Служба управления правами** <br/> |RMS для отдельных пользователей  это бесплатная самостоятельная подписка, которая предлагается пользователям в том случае, если они получили конфиденциальные файлы, защищенные с помощью управления правами Azure (Azure RMS), но их ИТ-отдел не внедрил управление правами Azure (Azure RMS) или службу управления правами Active Directory (AD RMS).  <br/> |[RMS для отдельных пользователей и служба Azure Rights Management](/azure/information-protection/rms-for-individuals) <br/> |[Портал управления правами (Майкрософт)](https://portal.azure.com/), на котором можно проверить, можно ли открыть защищенный документ  <br/> |
|**Microsoft PowerApps** <br/> |Служба PowerApps позволяет использовать приложения, созданные вами или сторонними разработчиками, для управления данными в организации. Приложения можно запускать на мобильных устройствах, например телефонах, или в браузере, открыв Dynamics 365. Вы можете создать любое количество приложений, и вам не придется учить для этого язык программирования, такой как C#.  <br/> |[Самостоятельная регистрация в PowerApps](/powerapps/maker/signup-for-powerapps) <br/> |[Microsoft Power Apps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 for Financials** <br/> |Воспользуйтесь полным решением для управления бизнесом и финансами, предназначенным для малого и среднего бизнеса. Dynamics 365 for Financials упрощает заказы, продажи, выставление счетов и создание отчетов и не требует длительного обучения.  <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 for Operations** <br/> |Работайте еще быстрее. Полный набор ERP-средств, входящий в Dynamics 365 for Operations, обеспечивает глобальную масштабируемость и позволяет использовать аналитику, чтобы поддерживать нужный темп роста.  <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource  это портал SaaS-приложений для бизнеса, основанных на облачной платформе Майкрософт. AppSource содержит сотни приложений, надстройок и пакетов контента, которые расширяют возможности продуктов Майкрософт, таких как Azure, Dynamics 365, Office 365 и Power BI.  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Программы вознаграждения для партнеров Майкрософт** <br/> |Сеть Microsoft Partner Network предполагает три типа членства. Каждый тип имеет свои преимущества, которые способствуют росту компании. Участвуйте в программе того уровня, который соответствует вашим уникальным потребностям, чтобы воспользоваться дополнительными преимуществами и развивать отношения с нами и другими партнерами.  <br/> |[Программы вознаграждения для партнеров Майкрософт](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Программы вознаграждения для партнеров Майкрософт](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft Business Center** <br/> |Бизнес-центр Майкрософт — это портал для клиентов, которые сделали покупки через Соглашение о продуктах и услугах Майкрософт (MPSA). <br/> |[Краткое руководство. Регистрация в Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Центр обслуживания microsoft Volume License** <br/> |Центр обслуживания лицензий Microsoft Volume отображает лицензии, приобретенные по соглашениям Enterprise, Select, Education (Campus или School), Open Value, Open License и ISV Royalty agreements.  <br/> |[Обучение и ресурсы VLSC](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[Центр обслуживания лицензий тома](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft Education Edition** <br/> |Платформа Minecraft помогает преподавателям мотивировать учащихся и увлечь их учебой. Присоединитесь к сообществу преподавателей, чтобы узнать, как они раскрывают потенциал учащихся с помощью Minecraft.  <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |Выкладывайте видео и делитесь ими с другими сотрудниками, чтобы улучшить взаимодействие, совместную работу и обучение.  <br/> |[Sign up &amp; Day 0 experience](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Power Automate** <br/> |Power Automate это продукт, который поможет настроить автоматизированные процессы между вашими любимыми приложениями и службами для синхронизации файлов, получения уведомлений, сбора данных и других.  <br/> |[Зарегистрироваться и войти в Power Automate](/power-automate/sign-up-sign-in) <br/> |[Power Automate](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Power Virtual Agents** <br/> |Power Virtual Agents позволяет группам легко создавать мощные боты с помощью управляемого графического интерфейса без кода без необходимости для ученых и разработчиков данных. Power Virtual Agents решает многие основные проблемы с созданием ботов в отрасли сегодня. Это устраняет разрыв между специалистами по предмету и группами разработки, которые работают с ботами, и длительной задержкой между командами, распознавая проблему и обновляя бот для ее устранения.  <br/> |[Сведения о лицензировании и доступе](/power-virtual-agents/requirements-licensing) <br/> |[Подпишитесь на Power Virtual Agents](https://aka.ms/TryPVA) <br/> |
|**Azure AD B2B** <br/> |Azure Active Directory (Azure AD) совместной работы с бизнесом (B2B) позволяет приглашать внешних пользователей (или "гостевых пользователей") для использования платных служб Azure AD. Некоторые функции являются бесплатными, но для всех платных функций Azure AD можно пригласить до пяти гостевых пользователей для каждой лицензии на выпуск Azure AD, которая принадлежит сотруднику или пользователю, не въехав в клиента. <br/> |[Самообслуживка для регистрации совместной работы Azure AD B2B](/azure/active-directory/b2b/self-service-portal) <br/> |[Azure Active Directory Руководство по лицензированию совместной работы b2B](/azure/active-directory/b2b/licensing-guidance) <br/> |
