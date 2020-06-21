---
title: Управление развертыванием надстроек в центре администрирования
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Узнайте, как развертывать надстройки для пользователей и групп в Организации с помощью централизованного развертывания в центре администрирования.
ms.openlocfilehash: 25a4cd4147f6388cdbd8982eb10624e7b7e8f6cb
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780125"
---
# <a name="manage-deployment-of-add-ins-in-the-microsoft-365-admin-center"></a>Управление развертыванием надстроек в Центре администрирования Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Надстройки Office помогают настраивать документы и оптимизировать способ доступа к данным в Интернете (см. раздел [Начало работы с надстройкой Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Как администратор вы можете развертывать надстройки Office для пользователей в Организации. Это можно сделать с помощью функции централизованного развертывания в центре администрирования Microsoft 365.
  
Централизованное развертывание — это рекомендуемый и наиболее полнофункциональный способ развертывания надстроек для пользователей и групп в Организации с широкими функциональными возможностями. Дополнительные сведения о том, как определить, поддерживает ли Организация централизованное развертывание, можно узнать в статье определение того, [работает ли централизованное развертывание надстроек для вашей организации](centralized-deployment-of-add-ins.md).
  
Централизованное развертывание обеспечивает следующие преимущества:
  
- Глобальный администратор может назначить надстройку непосредственно пользователю, нескольким пользователям через группу или ко всем пользователям в клиенте.
    
- When the relevant Office application starts, the add-in automatically downloads for the user. If the add-in supports add-in commands, the add-in automatically appears in the Ribbon within the Office application.
    
- Надстройки больше не будут отображаться для пользователей, если администратор отключит или удалил надстройку, или если пользователь удален из Azure Active Directory или из группы, которой назначена эта надстройка.
    
> [!NOTE]
>  В Word, Excel и PowerPoint с помощью [каталога приложений SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) можно развертывать надстройки для пользователей в локальной среде без подключения к Microsoft 365 и/или поддержки надстроек SharePoint. > для Outlook используйте панель управления Exchange для развертывания в локальной среде без подключения к Microsoft 365. > 
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Рекомендуемый подход к развертыванию надстроек Office

Consider rolling out add-ins in a phased approach to help ensure your add-in deployment goes smoothly. We recommend the following plan:
  
1. Roll-out the add-in to a small set of business stakeholders and members of the IT department. Evaluate if the deployment was successful, and if so, move on to step 2.
    
2. Roll-out to a larger set of individuals within the business who will be using the add-in. Again, evaluate results and, if all went well, go to the next step of a full deployment.
    
3. Разверните надстройку для всей целевой аудитории пользователей.
    
Этапы развертывания можно добавлять или удалять в зависимости от размера целевой аудитории.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Развертывание надстройки Office с помощью центра администрирования

Прежде чем приступать к работе, ознакомьтесь со статьей определение того, [работает ли централизованное развертывание надстроек для вашей организации](centralized-deployment-of-add-ins.md).

  
1. В центре администрирования откройте страницу "параметры надстроек **Settings** \> **"** .
    
2. В верхней части страницы выберите пункт **развернуть надстройку** . На странице Обзор нажмите кнопку **Далее**.
    
3. Выберите параметр и следуйте инструкциям.
  
4. Если вы выбрали параметр для добавления надстройки из магазина Office, вы можете сделать выбор надстройки. Обратите внимание на возможность просмотра доступных надстроек по категориям **Рекомендуемое**, **Оценка** и **Имя**. Из Магазина Office можно добавить только бесплатные надстройки. В настоящее время возможность добавления платных надстроек не поддерживается. После выбора надстройки необходимо согласиться с некоторыми дополнительными условиями и условиями для продолжения. <br/><br/> Примечание. при использовании параметра магазин Office обновления и расширения для надстройки автоматически становятся доступными для пользователей без вашего вмешательства.

5. На следующей странице выберите **все**, **конкретные пользователи/группы** или **только я** , чтобы указать, в какой надстройке развернута надстройка. Чтобы найти пользователей или группы, для которых необходимо развернуть надстройку, воспользуйтесь полем поиска. <br/>Примечание: сведения о других состояниях, которые применяются к надстройке. Ознакомьтесь со статьей " [состояния надстроек](#add-in-states) " Далее в этом разделе.
  
6. Нажмите **Развернуть**.
  
7. Когда надстройка будет развернута, появится зеленый импульс. Чтобы убедиться, что надстройка успешно развернута, можно воспользоваться инструкциями на странице.

> [!NOTE]
> Пользователям может потребоваться перезапустить Office, чтобы увидеть значок надстройки на ленте приложения. Для отображения на лентах пользователей надстройки Outlook могут занимать до 24 часов.
    
8. По завершении нажмите кнопку **Далее**. Если вы развернули только себя, вы можете выбрать команду **изменить, кто имеет доступ к надстройке** , чтобы развернуть ее для большего числа пользователей.



Если вы развернули надстройку для членов вашей организации, отличных от самого себя, следуйте инструкциям, отображаемым для эффективного объявления развертывания надстройки. <br/>Теперь надстройка будет отображаться вместе с другими приложениями в Microsoft 365.
  
Рекомендуется сообщить пользователям и группам о том, что для них была развернута надстройка. Можно отправить им сообщение электронной почты, в котором будет описано, когда и как использовать надстройку, а также будут указаны ее преимущества для работы. Включение или ссылка на соответствующее содержимое справки или часто задаваемые вопросы, которые могут помочь при возникновении проблем с надстройкой.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Рекомендации при назначении надстройки пользователям и группам

Admins can assign an add-in to everyone or to specific users and groups. Each option has implications:
  
- **Everyone**: As the name implies, this option assigns the add-in to every user in the tenant. Use this option sparingly and only for add-ins that are truly universal to your organization. 
    
- **Users**: If you assign an add-in to an individual user, then to deploy the add-in to a new user, you will need to first add that user. The same goes for removing users. 
    
- **Groups**: If you assign an add-in to a group, users who are added to the group will automatically be assigned the add-in. And, when a user is removed from a group, the user loses access to the add-in. In either case, no additional action is required from you as the admin. 

- **Только я**: Если вы назначите надстройку только для себя, эта надстройка будет назначена только вашей учетной записи. Это идеальный вариант, если вы хотите сначала протестировать надстройку.
    
Параметр, который подходит для вашей организации, зависит от конфигурации. Тем не менее мы рекомендуем выполнять назначение с помощью групп. Администратору может быть проще управлять надстройками с помощью групп и вносить изменения в состав их участников, а не пользователей, которым назначена настройка. С другой стороны, в некоторых случаях может потребоваться предоставить доступ только очень небольшой группе пользователей, и тогда назначение надстройки отдельным пользователям вполне оправдано. Как следствие, такими пользователями необходимо будет управлять вручную.
  
### <a name="add-in-states"></a>Состояния надстроек

Надстройка может находиться в состоянии " **включено** " или " **отключено** ".
  
|**Состояние**|**Механизм перехода**|**Влияние**|
|:-----|:-----|:-----|
|**Active**  <br/> |Администратор отправил надстройку и назначил ее пользователям или группам.  <br/> |Пользователи и группы, которым назначена эта надстройка, видят ее в соответствующих клиентах.  <br/> |
|**Отключена**  <br/> |Администратор отключил надстройку.  <br/> |Пользователи и группы, которым назначена эта надстройка, больше не имеют к ней доступа.  <br/> Если изменить состояние надстройки на "Активна", пользователи и группы снова получат к ней доступ.  <br/> |
|**Deleted**  <br/> |Администратор удалил надстройку.  <br/> |Пользователи и группы, которым назначена эта надстройка, больше не имеют к ней доступа.  <br/> |
   
Рекомендуется удалить надстройку, если она больше не используется. Отключение надстройки целесообразно в том случае, если она используется только в определенные периоды в течение года.
  
### <a name="security-of-office-add-ins"></a>Безопасность надстроек Office

Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:
  
- Выводить данные.
    
- Читать документ пользователя для предоставления контекстных услуг.
    
- Считывать данные из документа пользователя и записывать их в него для предоставления значений.
    
Дополнительные сведения о типах и возможностях надстроек Office см. в статье [Общие сведения о платформе надстроек Office](https://go.microsoft.com/fwlink/p/?linkid=846362) (на английском языке). Особое внимание обратите на раздел "Структура надстройки Office".
  
To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://go.microsoft.com/fwlink/p/?linkid=848863).
  
When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.
  
Надстройки обновляются следующим образом:
  
- **Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time. 

    > [!NOTE]
    > Администратору не нужно удалять бизнес-надстройку для обновления.   В разделе надстройки администратор может просто щелкнуть надстройку LOB и нажать **кнопку Обновить** в правом нижнем углу. Обновление будет работать только в том случае, если версия новой надстройки больше, чем у существующей надстройки.   
    
- **Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time. 

### <a name="edit-add-in-access"></a>Изменение доступа к надстройке

После развертывания администраторы также могут изменять доступ пользователей к надстройкам.

1. В центре администрирования откройте страницу " **Параметры**  >  **служб &** надстроек".

2. Выберите развернутую надстройку.

3. Щелкните элемент **изменить** в разделе **у кого есть доступ**.
4. Сохраните изменения.
    
### <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Запрет загрузки надстроек путем отключения магазина Office между всеми клиентами (кроме Outlook)

> [!NOTE]
> Установка надстройки Outlook осуществляется с помощью [другого процесса](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).

В качестве организации вы можете запретить загрузку новых надстроек Office из магазина Office. Это можно использовать совместно с централизованным развертыванием, чтобы обеспечить развертывание только утвержденных в Организации надстроек для пользователей в вашей организации.
  
Чтобы отключить получение надстройки, выполните указанные ниже действия.
  
1. В центре администрирования перейдите в раздел **Параметры ** \> [Услуги&amp;](https://go.microsoft.com/fwlink/p/?linkid=2053743) надстроек.
    
3. Выберите **приложения и службы, принадлежащие пользователю**.
    
4. Снимите флажок, чтобы предоставить пользователям доступ к магазину Office.

Это предотвратит получение всеми пользователями следующих надстроек из хранилища.
  
- Надстройки для Word, Excel и PowerPoint 2016 из:
    
  - Windows
    
  - Mac
    
  - Office
    
    
- Ввод в эксплуатацию, начиная с **AppSource**
    
- Надстройки в Microsoft 365
    
Пользователь, пытающийся получить доступ к хранилищу, увидит следующее сообщение: **к сожалению, Microsoft 365 настроен для предотвращения индивидуального приобретения надстроек магазина Office.**
  
Поддержка отключения магазина Office доступна в следующих версиях:
  
- Windows: 16.0.9001, в настоящее время доступен.
    
- Mac: 16.10.18011401 — в настоящее время доступен.
    
- iOS: 2.9.18010804, доступные в настоящее время.
    
- Веб-в настоящее время доступен.
    
Это не запрещает администратору использовать централизованное развертывание для назначения надстройки из магазина Office.
  
Чтобы запретить пользователю выполнять вход с помощью учетной записи Майкрософт, можно ограничить вход в систему, чтобы использовать только учетную запись организации. Для получения дополнительных сведений обратитесь к [этой статье](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).
 
  
## <a name="minors-and-acquiring-add-ins-from-the-store"></a>Вспомогательные и приобретение надстроек из магазина

Общая норма защиты данных (GDPR) — это регламентирование Европейского союза, которое вступает в силу до 25 мая 2018 г. Он предоставляет пользователям права и защиту своих данных. Одним из аспектов GDPR является то, что небольшие данные не могут быть отправлены сторонам, которые не были утверждены их родительским или опекуном. Определенный возраст, определенный как второстепенный, зависит от региона, где находится пользователь.
  
Регионы, имеющие нормативные требования о доходе разрешения родителей, включают в себя США, Южная Корея, Великобритания и Европейского союза. Для этих регионов дополнительный набор будет заблокирован (через Azure Active Directory) от получения новых надстроек Office из Store и запущенных ранее надстроек. Для стран без нормативных нормативных ограничений отсутствуют ограничения на загрузку.
  
Определено, что пользователь является незначительным в зависимости от данных, указанных в Azure Active Directory. Администратор клиента несет ответственность за объявление допустимой возрастной группы и согласие пользователя на его родительский доступ.
  
Если родительский/опекун отправляется во вспомогательную надстройку с помощью определенной надстройки, администратор клиента может использовать централизованное развертывание для развертывания этой надстройки во всех незначительных разрешениях.
  
Чтобы обеспечить GDPR требованиям к дополнительным значениям, необходимо убедиться в том, что в вашем учебном заведении или организации развернута одна из следующих сборок Office.
  
 **Для Word, Excel, PowerPoint и Project**: 
  
|||
|:-----|:-----|
|**Платформа** <br/> |**Номер сборки** <br/> |
|Приложения Microsoft 365 для предприятий (текущий канал)  <br/> |9001,2138   <br/> |
|Приложения Microsoft 365 для предприятий (полугодовой канал предприятия)  <br/> |8431,2159  <br/> |
|Office 2016 для Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 для Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 для Mac  <br/> |16.11.18020200  <br/> |
|Office в Интернете  <br/> |Недоступно  <br/> |
   
 **Для Outlook**: 
  
|||
|:-----|:-----|
|**Платформа** <br/> |**Номер сборки** <br/> |
|Outlook 2016 для Windows (MSI)  <br/> |Сборка не подлежит определению  <br/> |
|Outlook 2016 для Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 для Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook Mobile для iOS  <br/> |2.75.0  <br/> |
|Outlook Mobile для Android  <br/> |2.2.145  <br/> |
|Outlook.com.  <br/> |Недоступно  <br/> |
   
 **Требования к Office 2013**
  
Word, Excel и PowerPoint 2013 для Windows будут поддерживать одни и те же небольшие проверки, если включена библиотека проверки подлинности Active Directory (ADAL). Существует два варианта соответствия требованиям, как описано далее.
  
- **Включите ADAL**. В этой статье объясняется, как включить ADAL для Office 2013: [использование современной проверки подлинности Microsoft 365 с клиентами Office](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).<br/>Кроме того, необходимо настроить разделы реестра для включения ADAL, как описано в разделе [Включение современной проверки подлинности для Office 2013 на устройствах с Windows](../security-and-compliance/enable-modern-authentication.md).<br/>Кроме того, необходимо установить следующие обновления за Апрель для Office 2013:
    
  - [Описание обновления для системы безопасности для Office 2013:10 апреля 2018 г.](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [3 апреля 2018 г., обновление для Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **Не ВКЛЮЧАЙТЕ ADAL**. Если вы не можете включить ADAL в Office 2013, мы рекомендуем использовать групповую политику, чтобы отключить магазин для клиентов Office. Сведения о том, как отключить параметры приложения для Office, находятся [здесь](https://technet.microsoft.com/library/cc178992.aspx).
    
## <a name="end-user-experience-with-add-ins"></a>Работа пользователей с надстройками

Now that you've deployed the add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). The add-in will appear on all platforms that the add-in supports.
  
If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in. 

![Лента Office с ссылками поиска](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Если развернутая надстройка не поддерживает команды надстроек или вы хотите просмотреть все развернутые надстройки, вы можете просматривать их **с помощью надстроек**. 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>В Word 2016, Excel 2016 или PowerPoint 2016

1. Выберите **Вставить \> Мои надстройки**. 
    
2. Откройте вкладку **Управляются администратором** в окне "Надстройки Office". 
    
3. Дважды щелкните надстройку, которую вы развернули ранее (в данном примере  **Цитаты** ). <br/>![Вкладка "управляемая администратором" на странице "надстройки Office"](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>В Outlook

1. На ленте **Главная** щелкните **получить**надстройки.<br/>![Кнопка "Хранилище" в Outlook](../../media/getaddinsicon.png)
  
2. Выберите **Управление, управляемое администратором** , в левой панели навигации.

## <a name="delete-the-add-in"></a>Удаление надстройки

Вы также можете удалить развернутую надстройку.

1. В центре администрирования откройте страницу " **Параметры**  >  **служб &** надстроек".

2. Выберите развернутую надстройку.

3. Нажмите кнопку **удалить надстройку**. Удалите кнопку надстройки в правом нижнем углу.
4. Проверяйте выбранные параметры и нажмите кнопку **удалить надстройку**.
  
## <a name="learn-more"></a>Подробнее

Получите дополнительные сведения о создании [надстроек Office](https://go.microsoft.com/fwlink/p/?linkid=846362).
  
[Используйте командлеты PowerShell централизованного развертывания для управления](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)надстройками.
  
[Устранение неполадок: пользователь не видит надстройки](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
