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
description: Интегрируйте Microsoft 365 с Azure AD, если вы хотите синхронизировать пароль или единый вход с локальной средой.
ms.openlocfilehash: b1f20ebc692421ed6df0d6f7c31a4d80347133e3
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384748"
---
# <a name="azure-integration-with-microsoft-365"></a>Интеграция Azure с Microsoft 365

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Microsoft 365 использует Azure Active Directory (Azure AD) для управления удостоверениями пользователей. Ваша подписка на Microsoft 365 включает бесплатную подписку На Azure AD, чтобы вы могли интегрировать свои локальное доменное службы Active Directory (AD DS) для синхронизации учетных записей пользователей и паролей или настроить единый вход. Вы также можете приобрести дополнительные функции для более эффективного управления учетной записью.
  
Azure AD также предоставляет другие функции, например управление интегрированными приложениями, которые можно использовать для расширения и настройки подписок Microsoft 365.
  
Вы можете использовать помощники по развертыванию Azure AD для настройки и настройки в Центре администрирования Microsoft 365 (вам необходимо войти в Microsoft 365):

 - [Помощник по Azure AD Connect](https://aka.ms/aadconnectpwsync)
 - [Помощник по развертыванию AD FS](https://aka.ms/adfsguidance)
 - [Руководство по настройке Azure AD](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Выпуски Azure AD и управление удостоверениями Microsoft 365

Если у вас есть платная подписка на Microsoft 365, у вас также есть бесплатная подписка на Azure AD. Azure AD можно использовать для создания учетных записей пользователей и групп и управления ими. Чтобы активировать эту подписку, необходимо выполнить разовую регистрацию. После этого вы сможете получить доступ к Azure AD из Центра администрирования Microsoft 365. 

Инструкции по регистрации бесплатной подписки На Azure AD см. в этой [бесплатной подписке.](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) Не перейдите непосредственно в azure.microsoft.com регистрации или получите пробную или платную подписку на Microsoft Azure, которая отделена от бесплатной подписки Azure AD с Microsoft 365. 
  
С помощью бесплатной подписки вы можете синхронизироваться с локальной службой каталогов, настроить единый вход и синхронизироваться со многими приложениями-службами, такими как Salesforce, DropBox и многие другие.
  
Если вам нужны расширенные функции AD DS, двунаправленная синхронизация и другие возможности управления, вы можете обновить бесплатную подписку до платной расширенной подписки. Подробные сведения [см. в выпусках Azure Active Directory.](https://azure.microsoft.com/pricing/details/active-directory/)
  
Дополнительные сведения о Microsoft 365 и Azure AD см. в моделях [удостоверений Microsoft 365.](about-microsoft-365-identity.md)
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>Расширение возможностей клиента Microsoft 365

|**Функция**|**Описание**|
|:-----|:-----|
|Интегрированные приложения  <br/> |Вы можете предоставить отдельным приложениям доступ к данным Microsoft 365, таким как почта, календари, контакты, пользователи, группы, файлы и папки. Вы также можете авторизировать эти приложения на уровне глобального администратора и сделать их доступными для всей компании, зарегистрировав их в Azure AD. Более подробную информацию см. в [интегрированных приложениях и Azure AD для администраторов Microsoft 365.](integrated-apps-and-azure-ads.md)  <br/> См. [также единый вход.](https://go.microsoft.com/fwlink/p/?LinkId=698604)  <br/> |
|PowerApps  <br/> | Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps. Дополнительные сведения см. в подсети "Создание PowerApp для списка [в SharePoint Online"](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) и на странице [PowerApps.](https://powerapps.microsoft.com/)  <br/> |
   
## <a name="see-also"></a>См. также

[Обзор Microsoft 365 корпоративный](microsoft-365-overview.md)
