---
title: Microsoft 365 Отчеты в центре администрирования — отчет Yammer групп
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- MST160
- MET150
- MOE150
description: Получите отчет Yammer групп, чтобы узнать о количестве созданных и используемых Yammer в организации, а также об их активности.
ms.openlocfilehash: 470fd7dc70069688f6d0ec0bbf3ba92b40a82ae1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244060"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-groups-activity-report"></a>Microsoft 365 Отчеты в центре администрирования — отчет Yammer групп

Панель Microsoft 365 **отчетов** показывает обзор действий в продуктах организации. Вы можете просмотреть отчеты по отдельным продуктам, чтобы получить более подробные сведения о действиях с каждым приложением. Ознакомьтесь с [общими сведениями о панели отчетов](activity-reports.md). В отчете о действиях в группах Yammer можно просмотреть сведения об активности, связанной с группами Yammer в вашей организации, и узнать, сколько групп создано и используется.
  
> [!NOTE]
> Чтобы увидеть отчеты, вы должны быть глобальным администратором, глобальным читателем или читателем отчетов в Microsoft 365 или Exchange, SharePoint, Teams Service, Teams Communications или Skype для бизнеса администратором.  
 
## <a name="how-do-i-get-to-the-yammer-groups-activity-report"></a>Как добраться до отчета Yammer групп?

1. В центре администрирования перейдите в раздел **отчеты о** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">использование</a> страницы. 
2. На домашней странице панели мониторинга нажмите кнопку **Просмотр** дополнительных на Yammer карте.

  
## <a name="interpret-the-yammer-groups-activity-report"></a>Анализ отчета о действиях в группах Yammer

Вы можете просмотреть действия групп в отчете Yammer, выбрав вкладку **"Действия групп".**<br/>![Microsoft 365 отчеты — отчет о Yammer групп Майкрософт.](../../media/3afdafe5-9269-402e-8264-c7695ceb227d.png)

Выберите **выберите столбцы для** добавления или удаления столбцов из отчета.  <br/> ![Yammer группы — выберите столбцы](../../media/54744932-34fe-48c3-9779-1d10c3f05be1.png)

Вы также можете экспортировать данные отчета в Excel .csv, выбрав ссылку **Экспорт.** При этом данные всех пользователей будут экспортированы в формат, позволяющий сортировать и фильтровать их для дальнейшего анализа. Если у вас менее 2000 пользователей, вы можете сортировать и фильтровать значения в самой таблице отчета. Если пользователей больше 2000, для фильтрации и сортировки потребуется экспортировать данные. 
  
|Item|Описание|
|:-----|:-----|
|**Метрика**|**Определение**|
|Имя группы  <br/> |Имя группы. <br/> |
|Администратор группы  <br/> |Имя администратора группы или владельца.  <br/> |
|Удалена  <br/> |Количество удаленных Yammer групп. Если группа удалена, но в ней выполнялись действия в пределах отчетного периода, она будет показана в таблице, но этот флаг будет иметь значение ИСТИНА.  <br/> |
|Тип  <br/> |Тип группы, общедоступный или частный. <br/> |
|Подключение к Office 365  <br/> |Указывает, является ли Yammer также Microsoft 365 группой. <br/> |
|Последняя дата действия (UTC)  <br/> | Последняя дата чтения, публикации или понравилась группе.  <br/> |
|"Участники"  <br/> | Количество участников в группе.  <br/> |
|"Posted" (Опубликовано);  <br/> |Количество сообщений, размещенных в группе Yammer за отчетный период. <br/>|
|Чтение  <br/> |Количество бесед, читаемых в группе Yammer за отчетный период.  <br/> |
|"Liked" (Понравилось);  <br/> |Количество сообщений, которые понравились в группе Yammer за отчетный период. <br/>|
|Сетевое имя  <br/> |Полное имя сети, к которой принадлежит группа. |
|||