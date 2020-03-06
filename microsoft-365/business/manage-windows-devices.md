---
title: Включение управления подключенными к домену устройств с Windows 10 в Microsoft 365 Business
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
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Сведения о том, как включить Microsoft 365 для защиты локальных подключенных к Active Directory устройств с Windows 10 в всего несколько этапов.
ms.openlocfilehash: 8d7caefa1ddcadf684fdb5b712601b1bdd4fb5bd
ms.sourcegitcommit: 26e4d5091583765257b7533b5156daa373cd19fe
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "42550254"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Включение управления подключенными к домену устройств с Windows 10 в Microsoft 365 Business

Если в вашей организации используется локальная версия Windows Server Active Directory, вы можете настроить Microsoft 365 бизнес для защиты устройств с Windows 10, сохранив при этом доступ к локальным ресурсам, для которых требуется локальная проверка подлинности.
Чтобы настроить эту защиту, можно внедрить **гибридные подключенные устройства Azure AD**. Эти устройства присоединяются как к локальной службе Active Directory, так и к Azure Active Directory.

В этом видеоролике описаны действия, которые необходимо выполнить для наиболее распространенного сценария, который также содержит подробные инструкции.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a>1. Подготовка к синхронизации службы каталогов 

Перед синхронизацией пользователей и компьютеров из локального домена Active Directory просмотрите статью подготовка к [синхронизации каталогов в Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization). В частности:

   - Убедитесь, что в каталоге нет дубликатов для следующих атрибутов: **mail**, **proxyAddresses**и **userPrincipalName**. Эти значения должны быть уникальными и все дубликаты должны быть удалены.
   
   - Рекомендуется настроить атрибут **userPrincipalName** (UPN) для каждой учетной записи локального пользователя, чтобы она соответствовала основному адресу электронной почты, соответствующему лицензированному пользователю Microsoft 365. Например: *Mary.Shelley@contoso.com* , а не *Mary@contoso. local*
   
   - Если домен Active Directory завершается в немаршрутизируемый суффиксе, например. *Local* или *. LAN*, вместо суффикса, поддерживающего маршрутизацию в Интернете, например *. com* или *. org*, сначала измените суффикс UPN локальных учетных записей пользователей, как описано в статье [Подготовка домена, не поддерживающего маршрутизацию, для синхронизации службы каталогов](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). 

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Установка и настройка Azure AD Connect

Чтобы синхронизировать пользователей, группы и контакты из локальной службы Active Directory с Azure Active Directory, установите Azure Active Directory Connect и настройте синхронизацию службы каталогов. Чтобы узнать больше, ознакомьтесь со статьей [Настройка синхронизации каталогов для Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) .

> [!NOTE]
> Эти действия одинаковы для Microsoft 365 Business. 

При настройке параметров для Azure AD Connect рекомендуется включить **синхронизацию паролей**, **единый вход**и функцию **обратной записи паролей** , которая также поддерживается в Microsoft 365 Business.

> [!NOTE]
> Существует несколько дополнительных действий для обратной записи пароля за пределами флажка в службе Azure AD Connect. Дополнительные сведения см. [в статье Настройка обратной записи пароля](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). 

## <a name="3-configure-hybrid-azure-ad-join"></a>3. Настройка гибридного подключения Azure AD

Прежде чем включить гибридные устройства с Windows 10 для гибридной службы Azure AD, убедитесь, что выполняются следующие условия:

   - Вы используете последнюю версию Azure AD Connect.

   - Azure AD Connect синхронизирует все объекты компьютеров устройств, которые вы хотите объединить в гибридную службу Azure AD. Если объекты компьютера принадлежат определенным подразделениям (OU), убедитесь, что эти подразделения настроены для синхронизации в Azure AD Connect.

Чтобы зарегистрировать существующие устройства Windows 10, присоединенные к домену, в качестве гибридного подключения к гибридной службе Azure AD, выполните действия, описанные в [руководстве по настройке гибридного подключения Azure Active Directory для управляемых доменов](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join). Эта гибридная среда позволяет использовать существующую локальную службу Active Directory на компьютерах с Windows 10 и обеспечить их готовность к облачному подключению.
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a>4. Включение автоматической регистрации для Windows 10

 Автоматическая регистрация устройств с Windows 10 для управления мобильными устройствами в Intune приведена в статье [Регистрация устройства Windows 10 автоматически с помощью групповой политики](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy). Вы можете настроить групповую политику на локальном уровне компьютера или для массовых операций, чтобы создать этот параметр групповой политики на контроллере домена с помощью шаблонов консоли управления групповой политикой и ADMX.

## <a name="5-configure-seamless-single-sign-on"></a>5. Настройка беспрепятственного единого входа

  Единый единый вход автоматически подписывает пользователей в облачные ресурсы Microsoft 365 при использовании корпоративных компьютеров. Просто разверните один из двух параметров групповой политики, описанных в статье [Azure Active Directory, обеспечивающей единый вход: краткое](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature)руководство. Параметр **групповой политики** не разрешает пользователям изменять свои параметры, а параметр **групповой политики** задает значения, но также оставляет настраиваемые пользователи настраиваемыми.

## <a name="6-set-up-windows-hello-for-business"></a>6. Настройка Windows Hello для бизнеса

 Windows Hello для бизнеса заменяет пароли на строгую двухфакторную проверку подлинности (2FA) для входа на локальный компьютер. Один фактор является асимметричной, а другой — ПИН-кодом или другим локальным жестом, таким как "отпечаток пальца" или "распознавание лица", если устройство поддерживает его. Мы рекомендуем заменять пароли на 2FA и Windows Hello для бизнеса, где это возможно.

Чтобы настроить гибридную Windows Hello для бизнеса, изучите [необходимые условия для развертывания гибридных ключей в Windows Hello для бизнеса](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs). Затем следуйте инструкциям в статье [Настройка параметров доверия для гибридных ключей Windows Hello для бизнеса](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings). 
