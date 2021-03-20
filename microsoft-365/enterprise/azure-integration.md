---
title: Интеграция Azure с Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: Интеграция Microsoft 365 с Azure AD, если требуется синхронизация паролей или один вход с локальной средой.
ms.openlocfilehash: f977969634401d59d7598136f9323cb0e37f9ece
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905336"
---
# <a name="azure-integration-with-microsoft-365"></a>Интеграция Azure с Microsoft 365

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Microsoft 365 использует Azure Active Directory (Azure AD) для управления идентификаторами пользователей за кулисами. Подписка на Microsoft 365 включает бесплатную подписку Azure AD, чтобы можно было интегрировать локальное доменное обслуживание Active Directory для синхронизации учетных записей и паролей пользователей или единой входной записи. Вы также можете приобрести расширенные функции для более эффективного управления учетной записью.
  
Azure AD также предлагает другие функции, например управление интегрированными приложениями, которые можно использовать для расширения и настройки подписки microsoft 365.
  
Консультанты по развертыванию Azure AD можно использовать для управляемой установки и настройки в центре администрирования Microsoft 365 (необходимо войти в Microsoft 365):

 - [Консультант Azure AD Connect](https://aka.ms/aadconnectpwsync)
 - [Консультант по развертыванию AD FS](https://aka.ms/adfsguidance)
 - [Руководство по настройке Azure AD](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Выпуски Azure AD и управление удостоверениями Microsoft 365

Если у вас есть платная подписка на Microsoft 365, у вас также есть бесплатная подписка Azure AD. Вы можете использовать Azure AD для создания и управления учетными записями пользователей и групп. Чтобы активировать эту подписку, необходимо выполнить разовую регистрацию. После этого вы можете получить доступ к Azure AD из центра администрирования Microsoft 365. 

Инструкции по регистрации бесплатной подписки На Azure AD см. в вашей бесплатной подписке [Azure AD.](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) Не перейдите непосредственно к azure.microsoft.com регистрации или получите пробную или платную подписку на Microsoft Azure, которая отделена от бесплатной подписки Azure AD с Microsoft 365. 
  
С помощью бесплатной подписки можно синхронизироваться с локальной каталогами, настроить один вход и синхронизировать со многими программами, такими как приложения-службы, такие как Salesforce, DropBox и многие другие.
  
Если вы хотите повысить функциональность AD DS, двухнаправленную синхронизацию и другие возможности управления, вы можете обновить бесплатную подписку на платную премиум-подписку. Подробные сведения см. в [выпуске Azure Active Directory.](https://azure.microsoft.com/pricing/details/active-directory/)
  
Дополнительные сведения о Microsoft 365 и Azure AD см. в [моделях удостоверений Microsoft 365.](about-microsoft-365-identity.md)
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>Расширение возможностей клиента Microsoft 365

|**Функция**|**Описание**|
|:-----|:-----|
|Интегрированные приложения  <br/> |Вы можете предоставить отдельным приложениям доступ к данным Microsoft 365, таким как почта, календари, контакты, пользователи, группы, файлы и папки. Вы также можете разрешить эти приложения на глобальном уровне администратора и сделать их доступными для всей компании, зарегистрировав приложения в Azure AD. Более подробную информацию см. [в видеоролике Интегрированные приложения и Azure AD для администраторов Microsoft 365.](integrated-apps-and-azure-ads.md)  <br/> Также [см. один вход.](/azure/active-directory/manage-apps/what-is-single-sign-on)  <br/> |
|PowerApps  <br/> | Power apps — это целенаправленные приложения для мобильных устройств, которые могут подключаться к существующим источникам данных, таким как списки SharePoint и другие приложения данных. Дополнительные сведения см. в раздел Создание PowerApp для [списка в SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) и на странице [PowerApps.](https://powerapps.microsoft.com/)  <br/> |
   
## <a name="see-also"></a>См. также

[Обзор Microsoft 365 корпоративный](microsoft-365-overview.md)