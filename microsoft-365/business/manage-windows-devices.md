---
title: Включение управления подключенными к домену устройств с Windows 10 в Microsoft 365 Business
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Сведения о том, как включить Microsoft 365 для защиты локальных подключенных устройств AD к Windows 10.
ms.openlocfilehash: 452e884f952a4b2c2e87148bb7203ed48a48d944
ms.sourcegitcommit: 3a632d8ec009abf1aac57363eaf78aeeda5db136
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "37376102"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Включение управления подключенными к домену устройств с Windows 10 в Microsoft 365 Business

Если ваша организация использует локальную службу Windows Server Active Directory, вы можете настроить Microsoft 365 бизнес для защиты устройств с Windows 10, сохраняя доступ к локальным ресурсам, требующим локальной проверки подлинности.
Чтобы настроить это, вы можете реализовать **гибридные подключенные устройства Azure AD**. Это устройства, которые присоединяются к локальному каталогу Active Directory и вашей службе Azure Active Directory.

В приведенных ниже сведениях о видео описываются действия, которые необходимо выполнить для наиболее распространенного сценария, который также описывается в следующих шагах.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a>1. Подготовка к синхронизации службы каталогов 

Перед синхронизацией пользователей и компьютеров из локального домена Active Directory просмотрите статью подготовка к [синхронизации каталогов в Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization). В частности:

   - Убедитесь, что в каталоге нет дубликатов для следующих атрибутов: **mail**, **proxyAddresses**и **userPrincipalName**. Эти значения должны быть уникальными и удаляться все дубликаты.
   
   - Рекомендуется, чтобы атрибут **userPrincipalName** (UPN) для каждой локальной учетной записи пользователя настроился так, чтобы соответствовать основному адресу электронной почты, соответствующему лицензированному пользователю Microsoft 365. Например, *Mary.Shelley@contoso.com* вместо *Мэри @ contoso. local*
   
   - Если домен Active Directory завершается в немаршрутизируемый суффиксе, например. *Local* или *. LAN*, вместо суффикса с маршрутизацией в Интернете, например *. com* или *. org*, необходимо сначала настроить суффикс UPN локальных учетных записей пользователей, как описано в статье [Подготовьте домен, не поддерживающий маршрутизацию, для синхронизации службы каталогов](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). 

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Установка и настройка Azure AD Connect

Чтобы синхронизировать пользователей, группы и контакты из локальной службы Active Directory с Azure Active Directory, установите Azure Active Directory Connect и настройте синхронизацию службы каталогов. Чтобы узнать больше, ознакомьтесь со статьей [Настройка синхронизации каталогов для Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) .

> [!NOTE]
> Эти действия одинаковы для Microsoft 365 Business. 

При настройке параметров для Azure AD Connect рекомендуется включить **синхронизацию паролей** и **единый вход в систему**, а также функцию **обратной записи паролей** , которая также поддерживается в Microsoft 365 Business.

> [!NOTE]
> Существует несколько дополнительных действий для обратной записи пароля за пределами флажка в службе Azure AD Connect. Дополнительные сведения см. [в статье Настройка обратной записи пароля](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). 

## <a name="3-configure-hybrid-azure-ad-join"></a>3. Настройка гибридного подключения Azure AD

Прежде чем включить гибридные устройства с Windows 10 для гибридной службы Azure AD, убедитесь, что выполняются следующие условия:

   - Вы используете последнюю версию Azure AD Connect.

   - Azure AD Connect синхронизирует все объекты компьютеров устройств, которые вы хотите объединить в гибридную службу Azure AD. Если объекты компьютера принадлежат определенным подразделениям (OU), убедитесь, что эти подразделения настроены для синхронизации в Azure AD Connect.

Чтобы зарегистрировать существующие устройства Windows 10, присоединенные к домену, в качестве гибридного подключения к гибридной службе Azure AD, выполните действия, описанные в [руководстве по настройке гибридного подключения Azure Active Directory для управляемых доменов](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join). Это позволит включить гибридную среду для существующей локальной службы Active Directory на компьютеры с Windows 10 и обеспечить их готовность к облачному подключению.
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a>4. Включение автоматической регистрации для Windows 10

 Автоматическая регистрация устройств с Windows 10 для управления мобильными устройствами в Intune приведена в статье [Регистрация устройства Windows 10 автоматически с помощью групповой политики](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy). Вы можете настроить групповую политику на локальном уровне компьютера или для массовых операций, вы можете создать этот параметр групповой политики на контроллере домена с помощью консоли управления групповыми политиками и шаблонов ADMX.

## <a name="5-configure-seamless-single-sign-on"></a>5. Настройка беспрепятственного единого входа

  Единый единый вход автоматически подписывает пользователей в облачные ресурсы Microsoft 365 при использовании корпоративных компьютеров. Просто разверните один из двух параметров групповой политики, описанных в статье [Azure Active Directory, обеспечивающей единый вход: краткое](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature)руководство. Параметр **групповой политики** не разрешает пользователям изменять свои параметры, а параметр **групповой политики** задает значения, но также оставляет настраиваемые пользователи настраиваемыми.

## <a name="6-set-up-windows-hello-for-business"></a>6. Настройка Windows Hello для бизнеса

 Windows Hello для бизнеса заменяет пароли на строгую двухфакторную проверку подлинности (2FA) для входа на локальный компьютер. Один фактор является асимметричной, а другой — ПИН-кодом или другим локальным жестом, таким как "отпечаток пальца" или "распознавание лица", если устройство поддерживает его. Мы рекомендуем заменять пароли на 2FA и Windows Hello для бизнеса, где это возможно.

Чтобы настроить гибридную Windows Hello для бизнеса, изучите [необходимые условия для развертывания гибридных ключей в Windows Hello для бизнеса](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs). Затем следуйте инструкциям в статье [Настройка параметров доверия для гибридных ключей Windows Hello для бизнеса](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings). 
