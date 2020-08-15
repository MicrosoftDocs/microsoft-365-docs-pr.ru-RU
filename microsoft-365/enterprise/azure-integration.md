---
title: Интеграция с Microsoft Azure с помощью Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/09/2019
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
ms.openlocfilehash: 045760f000abdbf053e09d89b296fbafa4c24786
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693508"
---
# <a name="azure-integration-with-microsoft-365"></a>Интеграция с Microsoft Azure с помощью Microsoft 365

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Microsoft 365 использует Azure Active Directory (Azure AD) для управления удостоверениями пользователей в фоновом режиме. Подписка на Microsoft 365 включает бесплатную подписку на Azure AD, чтобы вы могли интегрировать Microsoft 365 с Azure AD, если вы хотите синхронизировать пароли или настроить единый вход в локальной среде. Кроме того, вы можете приобрести дополнительные функции, чтобы лучше управлять учетными записями.
  
Azure также предоставляет другие функциональные возможности, такие как Управление интегрированными приложениями, которые можно использовать для расширения и настройки подписок Microsoft 365.
  
Вы можете использовать рекомендации по развертыванию Azure AD для пошаговой установки и настройки (необходимо войти в Microsoft 365):

 - [Советник по подключению Azure AD](https://aka.ms/aadconnectpwsync)
 - [Помощник по развертыванию AD FS](https://aka.ms/adfsguidance)
 - [Руководство по установке Azure AD](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Выпуски Azure AD и Microsoft 365 Identity Management

Если у вас есть платная подписка на Microsoft 365, у вас также есть бесплатная подписка на Azure AD. Вы можете использовать Azure AD для создания учетных записей пользователей и групп и управления ими. Чтобы активировать эту подписку, необходимо выполнить одноразовую регистрацию. После этого вы сможете получить доступ к Azure AD из центра администрирования Microsoft 365. 

Инструкции см. [в разделе Использование бесплатной подписки на Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=617127). Следуйте инструкциям по регистрации бесплатной подписки на Azure AD, которая входит в состав подписки на Microsoft 365. Не переходите непосредственно к azure.microsoft.com, чтобы зарегистрироваться или получить пробную или платную подписку на Microsoft Azure, отделенную от бесплатной версии для Microsoft 365. 
  
С помощью бесплатной подписки вы можете синхронизироваться с локальными каталогами, настроить единый вход и синхронизировать с множеством программ в качестве приложений служб, таких как Salesforce, DropBox и многие другие.
  
Если вам нужны расширенные функции доменных служб Active Directory (AD DS), двунаправленной синхронизации и другие возможности управления, вы можете обновить бесплатную подписку до платной подписки. Дополнительные сведения см. в статье [Azure Active Directory Editions](https://azure.microsoft.com/pricing/details/active-directory/).
  
Для получения дополнительных сведений о Microsoft 365 и Azure AD, ознакомьтесь со статьей [сведения об удостоверении microsoft 365 и Azure Active Directory](about-microsoft-365-identity.md).
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>Расширьте возможности клиента Microsoft 365

|**Функция**|**Описание**|
|:-----|:-----|
|Интегрированные приложения  <br/> |Вы можете предоставить отдельным приложениям доступ к данным Microsoft 365, например к почте, календарям, контактам, пользователям, группам, файлам и папкам. Вы также можете авторизовать эти приложения на глобальном уровне администратора и сделать их доступными для всей компании, зарегистрировав приложения в Azure AD. Дополнительные сведения см. [интегрированные приложения и Azure AD для администраторов Microsoft 365](https://support.office.com/article/cb2250e3-451e-416f-bf4e-363549652c2a).  <br/> Кроме того, вы можете просматривать [единый вход в приложения](https://go.microsoft.com/fwlink/p/?LinkId=698604).  <br/> |
|PowerApps  <br/> | Приложения Power Apps ориентированы на приложения для мобильных устройств, которые могут подключаться к существующим источникам данных, таким как списки SharePoint и другие приложения для передачи данных. [В статье Создание поверапп для списка на странице SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) и [PowerApps](https://powerapps.microsoft.com/) для получения дополнительных сведений.  <br/> |
   
Узнайте больше об [интегрированных приложениях и Azure AD для администраторов Microsoft 365](integrated-apps-and-azure-ads.md) , а [коллекции приложений Azure AD и единого входа](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).

## <a name="see-also"></a>См. также

[Обзор Microsoft 365 корпоративный](microsoft-365-overview.md)
