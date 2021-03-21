---
title: Устранение проблем с синхронизацией службы каталогов для Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MBS150
ms.assetid: 79c43023-5a47-45ae-8068-d8a26eee6bc2
description: В этой статье описаны распространенные причины проблем с синхронизацией службы каталогов в Office 365, а также несколько способов их решения.
ms.openlocfilehash: c6d810bd2f98df2c8df1c0e7fc942502c32d07f8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922440"
---
# <a name="fixing-problems-with-directory-synchronization-for-microsoft-365"></a>Устранение проблем с синхронизацией службы каталогов для Microsoft 365

С помощью синхронизации службы каталогов можно продолжать локально управлять пользователями и группами и синхронизировать добавления, удаления и изменения с облаком. Тем не менее ее настройка немного сложна и иногда бывает трудно определить причину проблемы. Мы предлагаем ресурсы, которые помогут вам выявить потенциальные проблемы и устранить их.
  
## <a name="how-do-i-know-if-something-is-wrong"></a>Как узнать, что что-то пошло не так?

Первым сигналом о наличии проблемы служит сообщение, появляющееся на плитке "Состояние DirSync" в Центре администрирования Microsoft 365.
  
Вы также получите от Microsoft 365 почтовое сообщение (на адрес электронной почты администратора и запасной адрес) о том, что в вашем клиенте обнаружены ошибки синхронизации службы каталогов. Подробные сведения см. в статье [Определение ошибок синхронизации службы каталогов в Microsoft 365](identify-directory-synchronization-errors.md).
  
## <a name="how-do-i-get-azure-active-directory-connect-tool"></a>Как получить средство Azure Active Directory Connect?

В [Центре администрирования Microsoft 365](https://admin.microsoft.com) перейдите к разделу **Пользователи** \> **Активные пользователи**. В меню **Другие действия** (три точки) выберите **Синхронизация службы каталогов**. 
  
Следуйте [инструкциям в мастере](set-up-directory-synchronization.md), чтобы скачать Azure AD Connect. 
  
Если вы все еще используете средство синхронизации (DirSync) Azure Active Directory (Azure AD), ознакомьтесь со статьей [Устранение ошибок установки инструмента для синхронизации Azure Active Directory и мастера настройки в Microsoft 365](/troubleshoot/azure/active-directory/installation-configuration-wizard-errors), чтобы узнать о требованиях к системе для установки средства, необходимых разрешениях и устранении распространенных ошибок. 
  
Чтобы перейти от службы синхронизации Azure AD к Azure AD Connect, см. [инструкции по обновлению](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started).
  
## <a name="resolving-common-causes-of-problems-with-directory-synchronization-in-microsoft-365"></a>Устранение распространенных причин проблем с синхронизаций службы каталогов в Microsoft 365

### <a name="synchronized-objects-arent-appearing-or-updating-online-or-im-getting-synchronization-error-reports-from-the-service"></a>Синхронизированные объекты не отображаются или не обновляются в режиме онлайн. Или служба возвращает отчеты об ошибках синхронизации.

- [Синхронизация удостоверений и устойчивость повторяющихся атрибутов](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)

### <a name="i-have-an-alert-in-the-admin-center-or-am-receiving-automated-emails-that-there-hasnt-been-a-recent-synchronization-event"></a>Я получаю оповещение в Центре администрирования. Или на мой электронный адрес приходят автоматические сообщения о том, что в последнее время синхронизация не выполнялась
- [Устранение неполадок подключения с помощью Azure AD Connect](/azure/active-directory/hybrid/tshoot-connect-connectivity)
- [Azure AD Connect: учетные записи и разрешения](/azure/active-directory/hybrid/reference-connect-accounts-permissions)
- [Синхронизация Azure AD Connect: управление учетной записью службы Azure AD](/azure/active-directory/hybrid/how-to-connect-azureadaccount)
- [Синхронизация каталогов с Azure Active Directory остановлена или более суток не зарегистрировано попыток синхронизации](https://support.microsoft.com/help/2882421/directory-synchronization-to-azure-active-directory-stops-or-you-re-warned-that-sync-hasn-t-registered-in-more-than-a-day)

### <a name="password-hashes-arent-synchronizing-or-im-seeing-an-alert-in-the-admin-center-that-there-hasnt-been-a-recent-password-hash-synchronization"></a>Не синхронизируются пароли. Или в Центре администрирования появляется оповещение о том, что в последнее время синхронизация паролей не выполнялась
- [Реализация синхронизации хэша паролей в службе синхронизации Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)

### <a name="im-seeing-an-alert-that-object-quota-exceeded"></a>Появляется оповещение о том, что превышена квота на объекты
- Для защиты службы используется встроенная квота на объекты. Если в каталоге слишком много объектов, которые нужно синхронизировать с Microsoft 365, [обратитесь в службу поддержки продуктов для бизнеса](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) с просьбой увеличить квоту.

### <a name="i-need-to-know-which-attributes-are-synchronized"></a>Необходимо определить, какие атрибуты синхронизируются
- Список всех атрибутов, которые синхронизируются между локальной средой и облаком, можно найти [здесь](https://go.microsoft.com/fwlink/p/?LinkId=396719).

### <a name="i-cant-manage-or-remove-objects-that-were-synchronized-to-the-cloud"></a>Не удается управлять объектами, синхронизированными с облаком, и удалять их
- Вы готовы управлять объектами только в облаке? Или вы удалили объект локально, но он все еще существует в облаке? Ознакомьтесь с этой статьей [Устранение ошибок синхронизации во время синхронизации](/azure/active-directory/hybrid/tshoot-connect-sync-errors) и [справочной статьей](/troubleshoot/azure/active-directory/cannot-manage-objects), чтобы получить инструкции по устранению этих проблем.

### <a name="i-got-an-error-message-that-my-company-has-exceeded-the-number-of-objects-that-can-be-synchronized"></a>Появляется сообщение о том, что в компании превышено максимальное количество объектов, которые можно синхронизировать
- Подробнее об этой проблеме вы можете узнать [здесь](/troubleshoot/azure/active-directory/exceed-number-objects-synced).
   
## <a name="other-resources"></a>Другие ресурсы

- [Сценарий для устранения повторяющихся имен участников-пользователей](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Сведения о подготовке немаршрутизируемого домена (например, .local) для синхронизации службы каталогов](prepare-a-non-routable-domain-for-directory-synchronization.md)
    
- [Сценарий для подсчета общего числа синхронизированных объектов](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Устранение неполадок AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=396727)
    
- [Использование PowerShell для исправления пустых атрибутов DisplayName для групп, поддерживающих почту](https://go.microsoft.com/fwlink/p/?LinkId=396728)
    
- [Использование PowerShell для устранения повторяющихся имен участников-пользователей](https://go.microsoft.com/fwlink/p/?LinkId=396730)
    
- [Использование PowerShell для устранения повторяющихся адресов электронной почты](https://go.microsoft.com/fwlink/p/?LinkId=396731)
