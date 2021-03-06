---
title: Добавление настраиваемых плиток в средство запуска приложений
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
manager: scotv
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: Создайте быстрые ссылки на электронную почту, документы, приложения, SharePoint сайты, внешние сайты и другие ресурсы, добавив настраиваемые плитки в пусковую площадку приложения.
ms.openlocfilehash: 0f4141d08811847e8e27cf35975cfa6c6b1b1192
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393683"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>Добавление настраиваемых плиток в средство запуска приложений

В Microsoft 365 вы можете быстро и легко добраться до электронной почты, календарей, документов и приложений с помощью запуска приложения[(подробнее](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)). Это приложения, которые вы получаете с Microsoft 365, а также настраиваемые приложения, которые вы добавляете из [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) или [Azure AD.](/previous-versions/office/office-365-api/)
  
Кроме того, вы можете добавить в средство запуска приложений собственные плитки, указывающие на сайты SharePoint, внешние сайты, устаревшие приложения и т. д. В средстве запуска приложений настраиваемые плитки по умолчанию отображаются на вкладке **Все**, но вы также можете закрепить их на вкладке **Главная** и рассказать пользователям, как сделать то же самое. Таким образом они смогут быстро получать доступ к нужным сайтам, приложениям и ресурсам для работы. В примере ниже показано, как с помощью настраиваемой плитки "Портал Contoso" можно быстро переходить на основной сайт интрасети SharePoint, используемый в организации. 
  
![Средство запуска приложений](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>Добавление настраиваемой плитки в средство запуска приложений

1. Войдите в центр администрирования в качестве глобального администратора, перейдите в Параметры org Параметры и выберите вкладку  >   **профилей** Организации.
    
2. На **вкладке профилей Организации** выберите **настраиваемые плитки запуска приложений.**
  
3. Выберите **Добавить настраиваемую плитку.** 
  
4. Введите **имя** новой плитки, которое будет на ней отображаться. 
    
5. Введите **URL-адрес веб-сайта** для плитки. Это расположение, куда необходимо, чтобы пользователи могли перейти при выборе плитки в пусковом Используйте HTTPS в URL-адресе.

    > [!TIP]
    > Чтобы создать плитку для сайта SharePoint, перейдите на этот сайт, скопируйте URL-адрес и вставьте его здесь. URL-адрес сайта группы по умолчанию выглядит так: `https://<company_name>.sharepoint.com` 
  
6. Введите **URL-адрес изображения** для плитки. Изображение будет отображаться на странице "Мои приложения" и в средстве запуска приложений.

    > [!TIP]
    > Изображение должно быть 60x60 пикселей и быть доступным для всех в вашей организации без необходимости проверки подлинности.

7. Введите **описание** плитки. Это видно при выборе плитки на странице Мои приложения и выборе **сведений о приложении.** 
  
8. Выберите **Сохранить изменения** для создания настраиваемой плитки. 
    
    Ваша настраиваемая плитка теперь доступна вам и вашим пользователям в средстве запуска приложений на вкладке **Все**. 

    > [!NOTE]
    > Если настраиваемая плитка, созданная в предыдущих шагах, отсутствует, убедитесь, что вам назначен почтовый ящик Exchange Online и что вы входили в него по крайней мере один раз. Эти действия необходимы для настраиваемой плитки в Microsoft 365. 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. В центре администрирования перейдите на **вкладку Параметры**  >  **Org Параметры**  >  **организации.**
    
2. На странице **профилей Организации,** рядом с   **добавлением настраиваемой плитки для организации,** выберите **Изменить**.

3. Измените для настраиваемой плитки параметры **Имя плитки**, **URL-адрес**, **Описание** или **URL-адрес изображения** (см. [Добавление настраиваемой плитки в средство запуска приложений](#add-a-custom-tile-to-the-app-launcher)).
    
4. Выберите **Обновление** \> **Закрыть**. 
    
Чтобы удалить настраиваемую плитку из окна **Настраиваемые** плитки, выберите плитку, выберите **Удалить плитку**  >  **Удалить**. 
  
## <a name="next-steps"></a>Дальнейшие действия

В дополнение к добавлению плитки в пусковую систему приложения можно добавить плитки для запуска приложений в панели навигации[(дополнительные).](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985) Чтобы настроить внешний вид Microsoft 365 в соответствие с брендом организации, см. в Microsoft 365 [темы](../setup/customize-your-organization-theme.md).

## <a name="related-content"></a>См. также:

[Pin apps to your users' app launcher](pin-apps-to-app-launcher.md) (article)\
[Обновление Microsoft 365 для](../setup/upgrade-users-to-latest-office-client.md) бизнес-пользователей до Office клиента (статья)\
[Управление надстройки в центре администрирования](../manage/manage-addins-in-the-admin-center.md) (статья)
