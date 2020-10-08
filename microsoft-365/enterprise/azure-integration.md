---
title: Интеграция с Microsoft Azure с помощью Microsoft 365
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
description: Интегрируйте Microsoft 365 с Azure AD, если вы хотите выполнить синхронизацию паролей или единый вход с локальной средой.
ms.openlocfilehash: b1f20ebc692421ed6df0d6f7c31a4d80347133e3
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384748"
---
# <a name="azure-integration-with-microsoft-365"></a>Интеграция с Microsoft Azure с помощью Microsoft 365

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Microsoft 365 использует Azure Active Directory (Azure AD) для управления удостоверениями пользователей в фоновом режиме. Подписка на Microsoft 365 включает бесплатную подписку на Azure AD, позволяющую интегрировать локальные доменные службы Active Directory (AD DS), чтобы синхронизировать учетные записи пользователей и пароли или настроить единый вход. Вы также можете приобрести дополнительные функции, чтобы лучше управлять своими учетными записями.
  
Azure AD также предоставляет другие функциональные возможности, такие как Управление интегрированными приложениями, которые можно использовать для расширения и настройки подписок Microsoft 365.
  
Помощник по развертыванию Azure AD можно использовать для настройки интерактивной установки и настройки в центре администрирования Microsoft 365 (необходимо войти в Microsoft 365):

 - [Советник по подключению Azure AD](https://aka.ms/aadconnectpwsync)
 - [Помощник по развертыванию AD FS](https://aka.ms/adfsguidance)
 - [Руководство по установке Azure AD](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Выпуски Azure AD и Microsoft 365 Identity Management

Если у вас есть платная подписка на Microsoft 365, у вас также есть бесплатная подписка на Azure AD. Вы можете использовать Azure AD для создания учетных записей пользователей и групп и управления ими. Чтобы активировать эту подписку, необходимо выполнить одноразовую регистрацию. После этого вы сможете получить доступ к Azure AD из центра администрирования Microsoft 365. 

Чтобы получить инструкции по регистрации бесплатной подписки на Azure AD, ознакомьтесь со статьей [использование бесплатной подписки на Azure AD](../compliance/use-your-free-azure-ad-subscription-in-office-365.md). Не переходите непосредственно к azure.microsoft.com, чтобы зарегистрироваться или получить пробную или платную подписку на Microsoft Azure, отделенную от вашей бесплатной подписки на Azure AD с помощью Microsoft 365. 
  
С помощью бесплатной подписки вы можете синхронизироваться с локальными каталогами, настроить единый вход и синхронизировать с множеством программ в качестве приложений служб, таких как Salesforce, DropBox и многие другие.
  
Если вы хотите улучшить функции AD DS, двунаправленную синхронизацию и другие возможности управления, вы можете обновить бесплатную подписку на платную подписку. Дополнительные сведения см. в статье [Azure Active Directory Editions](https://azure.microsoft.com/pricing/details/active-directory/).
  
Дополнительные сведения о Microsoft 365 и Azure AD можно найти в [статье microsoft 365 Identity Models](about-microsoft-365-identity.md).
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>Расширьте возможности клиента Microsoft 365

|**Функция**|**Описание**|
|:-----|:-----|
|Интегрированные приложения  <br/> |Можно предоставить отдельным приложениям доступ к данным Microsoft 365, таким как почта, календари, контакты, пользователи, группы, файлы и папки. Вы также можете авторизовать эти приложения на глобальном уровне администратора и сделать их доступными для всей компании, зарегистрировав приложения в Azure AD. Сведения о форморе: [интегрированные приложения и Azure AD для администраторов Microsoft 365](integrated-apps-and-azure-ads.md).  <br/> Кроме того, вы можете увидеть [единый вход](https://go.microsoft.com/fwlink/p/?LinkId=698604).  <br/> |
|PowerApps  <br/> | Приложения Power Apps ориентированы на приложения для мобильных устройств, которые могут подключаться к существующим источникам данных, таким как списки SharePoint и другие приложения для передачи данных. Ознакомьтесь со статьей [Создание поверапп для списка в SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) и на [странице PowerApps](https://powerapps.microsoft.com/) для получения подробных сведений.  <br/> |
   
## <a name="see-also"></a>См. также

[Обзор Microsoft 365 корпоративный](microsoft-365-overview.md)
