---
title: Подготовка доступа к локальным ресурсам для компьютеров, управляемых Майкрософт
description: Важные действия, чтобы убедиться, что Azure AD может взаимодействовать с локальной AD для обеспечения проверки подлинности
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 6df23e0d7e3ea0ecd7ebacd96f00cb47b9e0aa84
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574599"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Подготовка доступа к локальным ресурсам для компьютеров, управляемых Майкрософт

В компьютеры, управляемые Майкрософт устройства автоматически присоединяются к Azure Active Directory (Azure AD). По этой причине, если вы используете локальное active Directory, вам придется проверить некоторые вещи, чтобы убедиться, что устройства, присоединились к Azure AD, могут взаимодействовать с локальной службой Active Directory. 

> [!NOTE]  
> *Гибрид* Регистрация Azure AD не поддерживается компьютеры, управляемые Майкрософт.

Azure Active Directory позволяет пользователям использовать single Sign-On (SSO), что означает, что им обычно не придется предоставлять учетные данные при каждом использовании ресурсов.

Сведения о присоединении Azure Active Directory ссылке на [How to: Plan your Azure AD join implementation.](/azure/active-directory/devices/azureadjoin-plan) Дополнительные сведения о Sign-On (SSO) на устройствах, присоединимых к Azure AD, см. в справке о том, как SSO с локальной ресурсами работает на устройствах [Azure AD.](/azure/active-directory/devices/azuread-join-sso#how-it-works)


В этой статье рассказывается о том, что необходимо проверить, чтобы приложения и другие ресурсы, зависят от локального подключения Active Directory, работали с компьютеры, управляемые Майкрософт.


## <a name="single-sign-on-for-on-premises-resources"></a>Единый Sign-On для локального ресурса

Единое Sign-On (SSO) с помощью UPN и пароля включено по умолчанию на компьютеры, управляемые Майкрософт Устройствах. Но пользователи также могут использовать Windows Hello for Business, что требует дополнительных действий по настройке. 

### <a name="single-sign-on-by-using-upn-and-password"></a>Единый Sign-On с помощью UPN и пароля

В большинстве организаций пользователи смогут использовать SSO для проверки подлинности с помощью UPN и пароля на компьютеры, управляемые Майкрософт Устройствах. Однако, чтобы убедиться, что эта функция будет работать, необходимо дважды проверить следующие вещи:

- Подтвердим, что Подключение Azure AD настроен и использует локальное сервер Active Directory, работающий Windows Server 2008 R2 или более поздней основе.
- Подтвердим, Подключение Azure AD работает с поддерживаемой версией и настроен на синхронизацию этих трех атрибутов с Azure AD: 
    - Доменное имя DNS локального Active Directory (где находятся пользователи)
    - NetBIOS локального каталога Active Directory (где находятся пользователи)
    - Имя учетной записи SAM пользователя


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Единый Sign-On с помощью Windows Hello для бизнеса

компьютеры, управляемые Майкрософт устройства также предоставляют пользователям быстрый и надежный доступ к паролям, используя Windows Hello for Business. Чтобы Windows Hello for Business будет работать без необходимости предоставлять пользователям соответствующие upN и пароль, посетите [веб-сайт Configure Azure AD joined devices for On on-premises Single-Sign On using Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) to check the requirements, and then follow the steps provided there.


## <a name="apps-and-resources-that-use-authentication"></a>Приложения и ресурсы, которые используют проверку подлинности

Чтобы получить [полное](/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) руководство по настройке приложений для работы с Azure Active Directory, обратитесь к приложению и ресурсам в наборе контента Azure. Сводка:


- Если вы используете **облачные** приложения, например приложения, добавленные в галерею приложений Azure AD, большинство из них не требуют дополнительной подготовки для работы с компьютеры, управляемые Майкрософт. Однако любые приложения Win32, которые не используют диспетчер веб-учетных записей (WAM), по-прежнему могут подсказыть пользователям проверку подлинности.

- Для приложений, которые **находятся** на локальном сайте, обязательно добавьте эти приложения в список надежных сайтов в браузерах. Этот шаг позволит Windows проверку подлинности без запроса пользователей на учетные данные. Чтобы добавить приложения, обратитесь к [доверенным сайтам](../working-with-managed-desktop/config-setting-ref.md#trusted-sites) в [ссылке Настраиваемые параметры](../working-with-managed-desktop/config-setting-ref.md).

- Если вы используете службы Federated Active Directory, проверьте, включена ли служба SSO с помощью действий в Verify и управления одним входом с [помощью AD FS.](/previous-versions/azure/azure-services/jj151809(v=azure.100)) 

- Для приложений, которые находятся на месте и используют старые протоколы, не требуется дополнительная настройка, если устройства имеют доступ к локальному контроллеру домена для проверки подлинности. Однако для обеспечения безопасного доступа к этим приложениям необходимо развернуть прокси-сервер Приложения Azure AD. Дополнительные сведения см. в удаленном доступе к локальному приложению [Azure Active Directory прокси-сервера приложения.](/azure/active-directory/manage-apps/application-proxy)

- Приложения, которые работают **локально** и полагаются на проверку подлинности машины, не поддерживаются, поэтому следует заменить их более новыми версиями.

### <a name="network-shares-that-use-authentication"></a>Сетевые акции, которые используют проверку подлинности

Дополнительная настройка не требуется пользователям для доступа к сетевым акциям, если устройства имеют доступ к локальному контроллеру домена с помощью пути UNC.

### <a name="printers"></a>Принтеры

компьютеры, управляемые Майкрософт устройства не могут подключаться к принтерам, опубликованным в локальном каталоге Active Directory, если только вы не настроили [гибридную облачную печать.](/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)

Хотя принтеры не могут быть автоматически обнаружены только в облачной среде, пользователи могут использовать локальное принтеры с помощью пути к принтеру или пути очереди принтера, если устройства имеют доступ к локальному контроллеру домена.

<!--add fuller material on printers when available-->
## <a name="steps-to-get-ready"></a>Действия, которые необходимо сделать, чтобы быть готовыми

1. Просмотрите [Необходимые условия для компьютеры, управляемые Майкрософт](prerequisites.md).
2. Используйте [средства оценки готовности.](readiness-assessment-tool.md)
3. [Предварительные требования для гостевых учетных записей](guest-accounts.md)
4. [Конфигурация сети для компьютеров, управляемых Майкрософт](network.md)
5. [Подготовка сертификатов и сетевых профилей для компьютеров, управляемых Майкрософт](certs-wifi-lan.md)
6. [Подготовка локального доступа к ресурсам для компьютеры, управляемые Майкрософт](authentication.md) (Эта статья)
7. [Приложения на компьютерах, управляемых Майкрософт](apps.md)
8. [Подготовка подключенных дисков для компьютеров, управляемых Майкрософт](mapped-drives.md)
9. [Подготовка ресурсов печати для компьютеров, управляемых Майкрософт](printing.md)
