---
title: Тестирование и развертывание Приложения Microsoft 365 партнеров на портале интегрированных приложений
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Поиск, тестирование и развертывание партнерских приложений Microsoft и Microsoft для пользователей и групп в вашей организации на портале интегрированных приложений в Центр администрирования Microsoft 365.
ms.openlocfilehash: dcd4a91d9e43c0a740094615cd3dca0b0e8bc0f6
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007061"
---
# <a name="test-and-deploy-microsoft-365-apps-by-partners-in-the-integrated-apps-portal"></a>Тестирование и развертывание Приложения Microsoft 365 партнеров на портале интегрированных приложений

Эта Центр администрирования Microsoft 365 позволяет развертывать приложения одного магазина, настраиваемую бизнес-линию приложений и Microsoft 365 партнеров из одного расположения. К расположению можно получить доступ в параметрах Центра администрирования Майкрософт, в интегрированных приложениях. Возможность поиска, тестирования и полного развертывания приобретенных и лицензированных приложений партнерами Майкрософт на портале интегрированных приложений обеспечивает удобство и преимущества, необходимые вашей организации для регулярного обновления бизнес-служб и эффективной работы.

Дополнительные сведения о приобретении и лицензировании Microsoft 365 приложений от партнеров для вашей организации см. в Приложения Microsoft 365 и развертывании [Центр администрирования Microsoft 365.](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324)

Дополнительные сведения о создании этих приложений партнерами см. в дополнительных сведениях о планировании [предложения SaaS для коммерческого рынка.](https://go.microsoft.com/fwlink/?linkid=2158277)

Портал интегрированных приложений доступен только глобальным администраторам и доступен только для клиентов во всем мире. Эта функция недоступна в суверенных и государственных облаках.

Портал интегрированных приложений отображает список приложений, включаний в себя отдельные приложения и Microsoft 365 от партнеров, развернутых в вашей организации. Перечислены только веб SPFx приложения, Office надстройки и Teams приложения. В веб-приложениях можно увидеть два типа приложений.

- Приложения SaaS, доступные в appsource.microsoft.com, и могут быть развернуты администраторами, дая согласие от имени организации.
- Приложения галереи SAML, связанные с надстройки office.

## <a name="manage-apps-in-the-integrated-apps-portal"></a>Управление приложениями на портале интегрированных приложений

Вы можете управлять тестированием и развертыванием приобретенных и лицензированных Приложения Microsoft 365 партнеров.

1. В центре администрирования выберите **Параметры,** а затем выберите **интегрированные приложения.**

2. Выберите приложение со **статусом** **дополнительных приложений, доступных** для открытия области **Управление.** Состояние **дополнительных доступных приложений** позволяет узнать, что еще не развернуты дополнительные интеграции из isvs.

3. На **вкладке Обзор** выберите **Развертывание**. Некоторые приложения требуют добавления пользователей, прежде чем выбрать Развертывание.

4. Выберите  **Пользователи**, **выберите Это тестовая развертывание,** а затем выберите **всю** организацию, **конкретные пользователи / группы** или **Просто меня**. Вы также можете выбрать **развертывание Test,** если вы хотите подождать, чтобы развернуть приложение во всей организации. Конкретные пользователи или группы могут быть Microsoft 365, группой безопасности или группой рассылки.

5. Выберите **обновление,** а затем **готово.** Теперь можно выбрать Развертывание на вкладке Обзор.

6. Просмотрите сведения о приложении и выберите **Развертывание.**

7. Выберите **Готовое** на странице Завершено развертывание и просмотрите сведения о тесте или полном развертывании на вкладке **Обзор.**

8. Если приложение имеет состояние Обновления в ожидании, вы можете нажать на приложение, чтобы открыть области Управления и обновить приложение.

## <a name="find-published-apps-for-testing-and-full-deployment"></a>Поиск опубликованных приложений для тестирования и полного развертывания

Вы можете найти, протестировать и полностью развернуть опубликованные приложения, которые еще не отображаются в списке на странице Интегрированные приложения. Приобретая и лицензируя приложения из центра администрирования, вы можете добавить в список партнерские приложения Microsoft и Microsoft из одного расположения.

1. В центре администрирования в левом nav выберите **Параметры,** а затем выберите **интегрированные приложения.**

2. Выберите **Получить приложения,** чтобы получить представление приложений.

3. На странице **Приложения Microsoft 365** опубликованных приложений выберите приложение, которое необходимо развернуть, выбрав **Get it now**. В основном отображаются приложения Word, PowerPoint, Excel, Outlook надстройки, Teams приложения и SharePoint приложения (построенные на SharePoint Framework технологии). Примите разрешения и выберите **Продолжить**.

5. Выберите **Развертывание** в верхней части страницы рядом с сообщением, которое ссылается на ожидание развертывания.

    Если выбранное приложение связано с предложением SaaS от isV, все другие приложения, которые являются частью этого связанного предложения, будут отображаться на странице Конфигурация. Если вы решите развернуть все приложения, выберите **Далее**. В противном случае **выберите изменить** и выбрать, какие приложения необходимо развернуть. Некоторые приложения требуют добавления пользователей, прежде чем выбрать **Развертывание.**

6. Выберите **Добавить пользователей,** выберите **Это тестового развертывания,** а затем выбрать **всю** организацию или **конкретные пользователи / группы** или Просто **меня**.

    Конкретные пользователи/группы могут быть Microsoft 365, группой безопасности или распределенной группой. Вы также можете выбрать **развертывание Test,** если вы хотите подождать, чтобы развернуть приложение во всей организации.

7. Выберите **Далее,** чтобы добраться до страницы **запроса на разрешение Accept.** Перечислены возможности и разрешения приложения для каждого из приложений. Если приложению требуется согласие, выберите **разрешения Accept**. Только глобальный администратор может дать согласие.

8. Выберите **Далее,** чтобы просмотреть развертывание и выбрать **готовое развертывание.** Развертывание можно просмотреть со вкладки **Обзор,** выбрав **просмотр этого развертывания.** В Центр администрирования Microsoft 365 вы можете увидеть состояние каждого развернутого приложения и дату развертывания приложения.

> [!NOTE]
> Если приложение ранее было развернуто из-за портала Интегрированные приложения, тип **развертывания** **настраивается.**

## <a name="unsupported-scenarios"></a>Неподдерживаемые сценарии

Вы не сможете развернуть одно приложение магазина или Приложения Microsoft 365 партнером из портала интегрированных приложений для следующих сценариев.

- Одна и та же надстройка связана с более чем одним предложением SaaS.
- Предложение SaaS связано с надстройки, но оно не интегрируется с Microsoft Graph и не предоставляется AAD-ID приложения.
- Предложение SaaS связано с надстройкими, но AAD App ID, предоставленный для Microsoft Graph, является общим для нескольких предложений SaaS.

## <a name="upload-custom-line-of-business-apps-for-testing-and-full-deployment"></a>Upload настраиваемые приложения для тестирования и полного развертывания

1. В центре администрирования в левом nav выберите **Параметры,** а затем **интегрированные приложения.**

2. Выберите **Upload настраиваемые приложения.** Поддерживается только настраиваемая строка приложений для Word, PowerPoint, Excel и Outlook.

3. Upload файл манифеста с устройства или добавьте ссылку URL-адреса. Некоторые приложения требуют добавления пользователей, прежде чем выбрать Развертывание.

4. Выберите **Добавить пользователей,** выберите **Это тест развертывания**, и выбрать всю организацию **или** **конкретные пользователи / группы** или Просто **мне**.

    Конкретные пользователи/группы могут быть Microsoft 365, группой безопасности или распределенной группой. Вы также можете выбрать **развертывание Test,** если вы хотите подождать, чтобы развернуть приложение во всей организации.

5. Выберите **Далее,** чтобы добраться до страницы **запроса на разрешение Accept.** Перечислены возможности и разрешения приложений. Если приложению требуется согласие, выберите **разрешения Accept**. Только глобальный администратор может дать согласие.

6. Выберите **Далее,** чтобы просмотреть развертывание и выбрать **готовое развертывание.** Развертывание можно просмотреть со вкладки **Обзор,** выбрав **просмотр этого развертывания.**

## <a name="prepare-to-deploy-add-ins-in-integrated-apps"></a>Подготовка к развертыванию надстройок в интегрированных приложениях

Office надстройки помогут вам персонализировать документы и упростить доступ к информации в Интернете (см. в Office надстройку). 

Надстройки предоставляют следующие преимущества: 

- Когда соответствующее приложение Office, надстройка автоматически загружается. Если надстройка поддерживает команды надстройки, надстройка автоматически появляется в ленте в Office приложении. 

- Надстройки больше не отображаются для пользователей, если администратор отключит или удаляет надстройки, или если пользователь удален из Azure Active Directory или из группы, которую надстройка назначена. 

Надстройки поддерживаются в трех настольных платформах Windows, Mac и Online Office приложениях. Он также поддерживается в iOS и Android (Outlook только для мобильных надстроек). 

Для показа надстройки для клиента для всех пользователей может занять до 24 часов. 

Сегодня как Exchange, так и глобальные администраторы могут развертывать надстройки из интегрированных приложений.   

### <a name="before-you-begin"></a>Прежде чем начать

Развертывание надстройок требует, чтобы пользователи использовали Microsoft 365 корпоративный лицензии (E3/E5/F3) или Microsoft 365 бизнес-лицензии (Business Basic, Business Standard, Business Premium). Пользователи также должны быть подписаны в Office с помощью их организационного ID) и имеют Exchange Online и Exchange Online почтовых ящиков. Каталог подписки должен быть либо в каталоге, либо в федерате, чтобы Azure Active Directory. 

Развертывание не поддерживает следующее: 

- надстройки, ориентированные на Word, Excel или PowerPoint в Office 2013; 
- локальную службу каталогов; 
- Развертывание надстройки в Exchange почтового ящика on-prem 
- Развертывание компонентной объектной модели (COM) или набор средств Visual Studio для Office (VSTO) надстройки. 
- Развертывание Microsoft 365, которые не включают Exchange Online, например Приложения Microsoft 365 для бизнеса и Приложения Microsoft 365 для Enterprise.  

### <a name="office-requirements"></a>Office Требования 

Для word, Excel и PowerPoint надстройки пользователи должны использовать одно из следующих: 
- На устройстве Windows версии 1704 или более поздней версии Microsoft 365 корпоративный лицензий (E3/E5/F3) или Microsoft 365 бизнес-лицензий (Business Basic, Business Standard, Business Premium). 
- На Mac версии 15.34 или более поздней версии. 

Для Outlook пользователи должны использовать один из следующих ниже. 
- Версия 1701 или более поздней версии Microsoft 365 корпоративный лицензий (E3/E5/F3) или Microsoft 365 бизнес-лицензий (Business Basic, Business Standard, Business Premium). 
- Версия 1808 или более поздней версии Office профессиональный плюс 2019 или Office Standard 2019. 
- Версия 16.0.4494.1000 или более поздней версии Office профессиональный плюс 2016 (MSI) или Office Standard 2016 (MSI).
    > [!NOTE]
    > MSI-версии Outlook показывают надстройки, установленные администратором, в соответствующей ленте Outlook, а не в разделе "Мои надстройки".  
- Версия 15.0.4937.1000 или более поздней версии Office профессиональный плюс 2013 (MSI) или Office Standard 2013 (MSI).
- Версия 16.0.9318.1000 или более поздней версии Office 2016 для Mac. 
- Версия 2.75.0 или более поздней версии Outlook mobile для iOS. 
- Версия 2.2.145 или более поздней версии Outlook для Android. 



### <a name="exchange-online-requirements"></a>Требования Exchange Online 
Microsoft Exchange хранит манифесты надстройки в клиенте организации. Администратор, развертывающий надстройки, и пользователи, получающие эти надстройки, должны быть в версии Exchange Online, которая поддерживает проверку подлинности OAuth. 

Чтобы узнать, какая конфигурация используется, обратитесь к администратору Exchange своей организации. Подключение OAuth для каждого пользователя можно проверить с помощью комлета [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity)   PowerShell. 

### <a name="user-and-group-assignments"></a>Назначения для пользователей и групп
В настоящее время развертывание надстройки поддерживается для большинства групп, поддерживаемых Azure Active Directory, включая группы Microsoft 365, списки рассылки и группы безопасности. Развертывание поддерживает пользователей в группах верхнего уровня или группах без родительских групп, но не пользователей в вложенных группах или группах с родительскими группами. 

> [!NOTE]
> Сейчас группы безопасности без электронной почты не поддерживаются. 

В следующем примере Сандра, Шейла и группа отдела продаж назначены надстройке. Так как группа West Coast Sales является вложенной, надстройка не назначается Николаю и Максиму. 

![Схема отдела продаж](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

### <a name="find-out-if-a-group-contains-nested-groups"></a>Проверка наличия вложенных групп в группе

Самый простой способ проверить, содержит ли группа вложенные группы,  посмотреть ее карточку контакта в Outlook. Если вы введите имя группы в поле **To** электронной почты, а затем выберите имя группы, когда оно разрешится, оно покажет, содержит ли оно пользователей или вложенные   группы. В приведенной ниже примере вкладка **Участники** контактной карты Outlook для тестовой группы не показывает пользователей   и только две подгруппы. 

![Вкладка участников контактной карты Outlook](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)

Подключив группу, вы также можете выполнить обратную проверку и узнать, входит ли она в состав другой. В приведенной ниже примере на вкладке <b>Членство</b>в контактной карте Outlook можно увидеть, что подгруппа 1 входит   в группу тестирования. 

![Вкладка членство контактной карты Outlook](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)

Обратите внимание, что для поиска списка групп в группе можно использовать API Azure Active Directory Graph для запуска запросов. Дополнительные сведения см. в [группе Operations on groups | Ссылка на API graph](/previous-versions/azure/ad/graph/api/groups-operations). 

## <a name="recommended-approach-for-deploying-office-add-ins"></a>Рекомендуемый подход к развертыванию надстроек Office 
Чтобы выкатать надстройки с помощью поэтапного подхода, рекомендуется следующее: 
1. Разверните надстройку для небольшой группы заинтересованных лиц в организации и сотрудников ИТ-отдела. Вы можете включить флаг **Это тестовая развертывание.** Если развертывание успешно, переходить на шаг 2. 

2. Развяйте надстройку для большего числе пользователей в бизнесе. Снова оцените результаты и в случае успешного развертывания продолжайте развертывание в полном объеме. 

3. Выполните полный выкат для всех пользователей. Выключите флаг **из Развертывания Тест.** 

В зависимости от размера целевой аудитории можно добавлять или удалять этапы выкатки.  

## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Развертывание надстройки Office с помощью Центра администрирования 

1. В центре администрирования выберите **Параметры,** а затем выберите **интегрированные приложения.** 

2. Выберите **Получить приложения** в верхней части страницы. AppSource загружается в встроенном формате. Либо поиск надстройки, либо поиск ее путем нажатия на Продукт в левом nav.  Если надстройка была подключена isV к приложению SaaS или другим приложениям и надстройки и если приложение SaaS является платным приложением, вам будет показано диалоговое окно для покупки лицензии или развертывания. Независимо от того, приобрели вы лицензию или нет, вы можете перейти к развертыванию. Нажмите **Развернуть**.  

3. Вы увидите страницу **Конфигурация,** на которой указаны все приложения. Если у вас нет разрешений или правильного доступа к развертыванию приложения, будут выделены соответствующие сведения. Вы можете выбрать приложения, которые необходимо развернуть. Выбрав **Далее,** вы будете просматривать страницу **Пользователи.** Если надстройка не была подключена isV, вы будете перенастрояться на страницу Пользователи. 

4. Выберите **"Все", "Конкретные пользователи/группы"** или "Просто **я",** чтобы указать, кому ****   развернута надстройка. Используйте поле Поиска для поиска определенных пользователей или групп. Если вы тестируете надстройки, выберите **Это тестовая развертывание.** 

5. Нажмите кнопку **Далее**. Все возможности и разрешения приложения отображаются в одной области вместе с сведениями о сертификации, если приложение имеет сертификат Microsoft 365. Выбор логотипа сертификации позволяет пользователю получить дополнительные сведения о сертификации.  

6. Просмотрите, а затем выберите **развертывание Finish.**  

7. При развертывании надстройки появляется зеленый значок "тик". Выполните инструкции по проверке надстройки на странице. 

> [!NOTE]
> Пользователям может потребоваться перезапустить Office, чтобы просмотреть значок надстройки на ленте приложения. Добавление Outlook может занять до 24 часов, чтобы отображаться на лентах приложений. 

Это хорошая практика для информирования пользователей и групп о том, что развернутая надстройка доступна. Рассмотрите возможность отправки электронной почты с описанием того, когда и как использовать надстройки. Включайте или ссылки, чтобы помочь содержимому или вопросы, которые могут помочь пользователям, если у них возникли проблемы с надстройки. 

## <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Рекомендации при назначении надстройки пользователям и группам 

Глобальные администраторы и администраторы Exchange могут назначать надстройки всем пользователям и группам. Каждый вариант имеет ряд особенностей. 

- **Все**   Этот параметр назначает надстройки каждому пользователю организации. Используйте этот вариант осторожно и только для тех надстроек, которые действительно применяются во всей организации. 

- **Пользователи**   Если вы назначите надстройки отдельному пользователю, а затем развернете надстройки новому пользователю, сначала необходимо добавить нового пользователя. 

- **Группы**   Если надстройка назначается группе, пользователям, добавляемой в группу, автоматически назначается надстройка. При удалении пользователя из группы пользователь теряет доступ к надстройки. В любом случае от администратора не требуется никаких дополнительных действий. 

- **Только я**   Если надстройка назначается только себе, надстройка назначается только вашей учетной записи, которая идеально подходит для тестирования надстройки. 

Правильный вариант для организации зависит от конфигурации. Однако мы рекомендуем выполнять назначения с помощью групп. В качестве администратора может быть проще управлять надстройки с помощью групп и управления членством этих групп, а не назначать отдельных пользователей каждый раз. В некоторых ситуациях может потребоваться ограничить доступ к небольшому набору пользователей, назначив пользователям назначения вручную. 

### <a name="more-about-office-add-ins-security"></a>Подробнее о безопасности надстройок Office 
Надстройки Office включают XML-файл манифеста, содержащий метаданные и, что главное, указывающий на веб-приложение, которое содержит весь код и алгоритмы. У разных настроек разные возможности. Например, надстройки могут:
- Выводить данные. 
- Читать документ пользователя для предоставления контекстных услуг. 
- Считывать данные из документа пользователя и записывать их в него для предоставления значений.  

Дополнительные сведения о типах и возможностях надстройок Office см. в обзоре платформы надстройки [Office,](/office/dev/add-ins/overview/office-add-ins)особенно в разделе "Анатомия надстройки Office". 

Чтобы взаимодействовать с документом пользователя, надстройка должна объявить, какие разрешения ему нужны в манифесте. Пятиуровневая модель разрешений доступа к API JavaScript обеспечивает основу для конфиденциальности и безопасности пользователей надстройок области задач. Большинство надстройок в Магазине Office — это level ReadWriteDocument, почти все надстройки поддерживают по крайней мере уровень ReadDocument. Дополнительные сведения об уровнях разрешений см. в материалах [Requesting permissions for API use in content and task pane add-ins.](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins) 

При обновлении манифеста обычно изменения связаны со значком и текстом надстройки. Иногда изменяются сами ее команды. Однако разрешения надстройки не изменяются. Веб-приложение, где выполняется весь код и алгоритм надстроек, может измениться в любое время. 

Надстройки обновляются следующим образом: 
- **Надстройка line-of-business.** В этом случае, когда администратор явно загрузил манифест, надстройка требует, чтобы администратор загрузил новый файл манифеста для поддержки изменений метаданных. При следующем запуске соответствующего приложения Office надстройка будут обновлена. Веб-приложение может изменяться в любое время. 

- Надстройка Office **Store.** Если администратор выбрал надстройку из Магазина Office, если надстройка обновляется в Магазине Office, при следующем запуске соответствующих приложений Office надстройка будет обновляться. Веб-приложение может изменяться в любое время. 

> [!NOTE]
> Для Word Excel и PowerPoint используют каталог [приложений SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)для развертывания надстройок для пользователей в локальной среде без подключения к Microsoft 365 и/или поддержки надстройок   SharePoint. Для Outlook используйте панель управления Exchange для развертывания в локальной среде без подключения к Microsoft 365.  

## <a name="add-in-states"></a>Состояния надстроек
Надстройка может быть в состоянии **On**   или **Off.**   

| Состояние | Причины | Влияние |
|:-----|:-----|:-----|
|**Активна**  <br/> |Администратор загрузил надстройки и назначен пользователям или группам.  <br/> |Пользователи и группы, которым назначена эта надстройка, видят ее в соответствующих клиентах.  <br/> |
|**Отключена**  <br/> |Администратор отключил надстройку.  <br/> |Пользователи и группы, которым назначена эта надстройка, больше не имеют к ней доступа.  <br/> Если изменить состояние надстройки на "Активна", пользователи и группы снова получат к ней доступ.  <br/> |
|**Deleted**  <br/> |Администратор удалил надстройку.  <br/> |Пользователи и группы, которым назначена эта надстройка, больше не имеют к ней доступа.  <br/> |
 
Если надстройка больше не используется, рассмотрите возможность удаления надстройки. Например, отключение надстройки может иметь смысл, если надстройка используется только в определенное время года. 

## <a name="manage-an-office-add-in-using-the-admin-center"></a>Управление надстройки Office с помощью центра администрирования

После развертывания администраторы также могут управлять доступом пользователей к надстройки. 

1. В центре администрирования выберите **Параметры,** а затем выберите **интегрированные приложения.** 
2. На странице Интегрированные приложения будет отображаться список приложений, которые будут либо одними надстройки, либо надстройки, связанные с другими приложениями. 
3. Выберите приложение со **статусом**    **дополнительных приложений, доступных** для открытия области    **Управление.**   Состояние **дополнительных доступных приложений** позволяет узнать, что еще не развернуты дополнительные интеграции из   isvs. 
4. На **вкладке Обзор**   выберите **Развертывание**. Некоторые приложения требуют добавления пользователей, прежде чем выбрать Развертывание. 
5. Выберите **Пользователи**, **выберите Это тестовая развертывание,** а затем выберите либо **всю** организацию, **конкретные** пользователи / группы   или Просто **меня**. Вы также можете выбрать **развертывание Test,** если вы хотите подождать,   чтобы развернуть приложение во всей организации. Конкретные пользователи или группы могут быть Microsoft 365, группой безопасности или группой рассылки. 
6. Выберите  **Обновление,**   а затем выберите **Готово**. Теперь можно выбрать **Развертывание на** вкладке **Обзор.** 
7. Просмотрите сведения о приложении и выберите **Развертывание.**
8. Выберите **Готовое** на странице Завершено развертывание и просмотрите сведения о тесте или полном   развертывании на вкладке   **Обзор.**   
9. Если приложение имеет состояние  **** Обновления в ожидании, вы можете нажать на приложение, чтобы открыть области **Управления** и обновить приложение. 
10. Чтобы просто обновить пользователей, выберите вкладку **Пользователи** и внести соответствующие изменения. Выберите **Обновление** после внесения изменений.  

## <a name="delete-an-add-in"></a>Удаление надстройки

Можно также удалить развернутую надстройка.

1. В центре администрирования выберите **Параметры,** а затем выберите **интегрированные приложения.**
2. Выберите любую строку для отображения области управления. 
3. Выберите **вкладку Configuration.** 
4. Выберите надстройки, которые необходимо удалить, а затем выберите **Remove**.  

> [!NOTE]
>  Если надстройка развернута другим администратором, кнопка Удалить будет отключена. Только администратор, развернувший приложение или глобальный администратор, может удалить надстройки.

## <a name="scenarios-where-exchange-admin-cannot-deploy-an-add-in"></a>Сценарии, Exchange администратор не может развернуть надстройки 

Существует два случая, когда администратор Exchange не сможет развернуть надстройки:
- Если надстройка нуждается в разрешении на Graph API и требуется согласие глобального администратора.
- Если надстройка связана с двумя или более надстройкими и веб-приложениями, и по крайней мере одна из этих надстройок развернута другим администратором (exchange/global), и назначение пользователя не является однородным. Мы разрешаем развертывание надстройок только в том случае, если назначение пользователя одинаково для всех уже развернутых приложений.  


## <a name="frequently-asked-questions"></a>Вопросы и ответы

### <a name="which-administrator-role-do-i-need-to-access-integrated-apps"></a>Какая роль администратора требуется для доступа к интегрированным приложениям?

Доступ к интегрированным приложениям могут получать только глобальные администраторы. Интегрированные приложения не будут показываться в левом nav для других администраторов.

### <a name="why-do-i-see-add-in-in-the-left-nav-under-setting-but-not-integrated-apps"></a>Почему я вижу надстройки в левом nav под Параметры, но не интегрированные приложения?

Причин может быть несколько:

- Вошел администратор является администратором Exchange администратора.
- Клиент находится в суверенном облаке, а интегрированные приложения доступны для суверенных клиентов облака.

### <a name="what-apps-can-i-deploy-from-integrated-apps"></a>Какие приложения можно развернуть из интегрированных приложений?

Интегрированные приложения позволяют развертывать веб-приложения, Teams, Excel, PowerPoint, Word, Outlook надстройки и SPFx приложения. Для надстройок интегрированные приложения поддерживают развертывание Exchange почтовых ящиков, а не Exchange почтовых ящиков.

### <a name="can-administrators-delete-or-remove-apps"></a>Могут ли администраторы удалять или удалять приложения?

Да. Глобальные администраторы могут удалять или удалять приложения.

- Выберите приложение из представления списка. На **вкладке Конфигурация** выберите, какие приложения удалить.  

### <a name="is-integrated-apps-available-in-sovereign-cloud"></a>Доступны ли интегрированные приложения в суверенном облаке?

Нет. Интегрированные приложения недоступны для клиентов из суверенных облаков.

### <a name="is-integrated-apps-available-in-government-clouds"></a>Доступны ли интегрированные приложения в облаках правительства?

Нет. Интегрированные приложения недоступны для государственных облачных клиентов.
