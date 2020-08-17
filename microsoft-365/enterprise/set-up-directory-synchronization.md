---
title: Настройка синхронизации каталогов для Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/15/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED15
- MBS150
- BCS160
ms.assetid: 1b3b5318-6977-42ed-b5c7-96fa74b08846
description: Узнайте, как настроить синхронизацию каталогов между Microsoft 365 и локальной службой Active Directory.
ms.openlocfilehash: 3a846a6c558f221c1869dce6da27e3d34680f75d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693015"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a>Настройка синхронизации каталогов для Microsoft 365

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Microsoft 365 использует клиент Azure Active Directory (Azure AD) для хранения и управления удостоверениями для проверки подлинности и разрешений на доступ к облачным ресурсам. 

Если у вас есть локальные доменные службы Active Directory (AD DS), вы можете синхронизировать учетные записи пользователей доменных служб Active Directory, группы и контакты с клиентом Azure AD вашей подписки на Microsoft 365. Это гибридный идентификатор для Microsoft 365. Ниже перечислены его компоненты.

![Компоненты синхронизации каталогов для Microsoft 365](../media/about-microsoft-365-identity/hybrid-identity.png)

Azure AD Connect запускается на локальном сервере и синхронизирует ваши доменные службы Active Directory с клиентом Azure AD. Одновременно с синхронизацией каталогов вы можете также задать приведенные ниже параметры проверки подлинности.

- Синхронизация хэша паролей (PHS)

  Проверка подлинности выполняется с помощью Azure AD.

- Сквозная проверка подлинности (PTA)

  Проверка подлинности выполняется с помощью доменных служб Aсtive Directory в Azure AD.

- Федеративная проверка подлинности

  Azure AD перенаправляет клиентский компьютер, запрашивающий проверку подлинности, установить контакт с другим поставщиком удостоверений.

Дополнительные сведения см. в статье [Гибридные удостоверения](plan-for-directory-synchronization.md).
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a>1. Необходимые условия для Azure AD Connect

Вы получаете бесплатную подписку на Azure AD с подпиской на Microsoft 365. При настройке синхронизации каталогов вы устанавливаете Azure AD Connect на одном из локальных серверов.
  
Для Microsoft 365 вам потребуется:
  
- Проверка локального домена. Мастер Azure AD Connect направляет этот процесс.
- Получите имена пользователей и пароли для учетных записей администраторов клиента Microsoft 365 и доменных служб Active Directory.

Для локального сервера, на котором выполняется установка Azure AD Connect, вам потребуется
  
|**Серверная ОС**|**Другое ПО**|
|:-----|:-----|
|Windows Server 2012 R2 и более поздних версий | - PowerShell устанавливается по умолчанию; никаких действий не требуется.  <br> - Net 4.5.1 и более поздние выпуски можно получить через Центр обновления Windows. На панели управления убедитесь в том, что установлены последние обновления для Windows Server. |
|Windows Server 2008 R2 с пакетом обновления 1 (SP1)** или Windows Server 2012 | - Последняя версия PowerShell доступна в составе платформы Windows Management Framework 4.0. Найти ее можно в [Центре загрузки Майкрософт](https://go.microsoft.com/fwlink/p/?LinkId=717996).  <br> - .Net 4.5.1 и более поздние выпуски доступны в [Центре загрузки Майкрософт](https://go.microsoft.com/fwlink/p/?LinkId=717996). |
|Windows Server 2008 | Последняя поддерживаемая версия PowerShell доступна в составе платформы Windows Management Framework 3.0, которую можно найти в [Центре загрузки Майкрософт](https://go.microsoft.com/fwlink/p/?LinkId=717996).  <br> - .Net 4.5.1 и более поздние выпуски доступны в [Центре загрузки Майкрософт](https://go.microsoft.com/fwlink/p/?LinkId=717996). |

Более подробно ознакомиться с требованиями к оборудованию, программному обеспечению, учетным записям, разрешениям и SSL-сертификатам, а также с ограничениями на объекты для Azure AD Connect можно в статье [Необходимые условия для Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).
  
Вы также можете ознакомиться с [журналом выпуска версий](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history) Azure AD Connect, чтобы выяснить, что добавилось или было исправлено в каждой версии.

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a>2. Установка Azure AD Connect и настройка синхронизации каталогов.

Перед началом вам необходимо иметь

- Имя пользователя и пароль глобального администратора Microsoft 365
- Имя пользователя и пароль администратора доменных служб Active Directory
- Метод проверки подлинности (синхронизация хэша паролей, сквозная или федеративная)
- Либо [Простой единый вход Azure AD](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso) по вашему желанию.

Выполните приведенные ниже действия.

1. Войдите в [Центр администрирования Microsoft 365](https://admin.microsoft.com) https://admin.microsoft.com)и в области навигации слева выберите пункты **Пользователи** \> ** > Активные пользователи**.
2. На странице **Активные пользователи** выберите пункт **больше** (три точки) \> **синхронизации каталогов**.
  
3. На странице " **Подготовка Azure Active Directory** " щелкните ссылку **Перейти в центр загрузки, чтобы получить ссылку на средство Azure AD Connect** , чтобы приступить к работе. 
4. Выполните действия в статье [План установки Azure AD Connect и Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-roadmap).

## <a name="3-finish-setting-up-domains"></a>3. Завершение настройки доменов

Выполните действия, описанные в статье [CREATE DNS Records for Microsoft 365, когда вы управляете записями DNS](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) для завершения настройки доменов.

## <a name="next-step"></a>Следующий шаг

[Назначение лицензий учетным записям пользователей](assign-licenses-to-user-accounts.md)