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
ms.openlocfilehash: f6b1e257fd767fa112fddb41d773065b8002a2a3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909194"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Подготовка доступа к локальным ресурсам для компьютеров, управляемых Майкрософт

В Microsoft Managed Desktop устройства автоматически присоединяются к Azure Active Directory (Azure AD). По этой причине, если вы используете локальное active Directory, вам придется проверить некоторые вещи, чтобы убедиться, что устройства, присоединились к Azure AD, могут взаимодействовать с локальной службой Active Directory. 

> [!NOTE]  
> *Гибрид* Регистрация Azure AD не поддерживается Microsoft Managed Desktop.

Azure Active Directory позволяет пользователям использовать single Sign-On (SSO), что означает, что им обычно не придется предоставлять учетные данные при каждом использовании ресурсов.

Сведения о присоединении к Azure Active Directory можно найти в ссылке [How to: Plan your Azure AD join implementation.](/azure/active-directory/devices/azureadjoin-plan) Дополнительные сведения о Sign-On (SSO) на устройствах, присоединимых к Azure AD, см. в справке о том, как SSO с локальной ресурсами работает на устройствах [Azure AD.](/azure/active-directory/devices/azuread-join-sso#how-it-works)


В этой статье рассказывается о том, что необходимо проверить, чтобы обеспечить бесперебойную работу приложений и других ресурсов, зависят от локального подключения Active Directory к Microsoft Managed Desktop.


## <a name="single-sign-on-for-on-premises-resources"></a>Единый Sign-On для локального ресурса

Единое Sign-On (SSO) с помощью UPN и пароля включено по умолчанию на управляемых настольных устройствах Майкрософт. Но пользователи также могут использовать Windows Hello для бизнеса, что требует дополнительных действий по настройке. 

### <a name="single-sign-on-by-using-upn-and-password"></a>Единый Sign-On с помощью UPN и пароля

В большинстве организаций пользователи смогут использовать SSO для проверки подлинности с помощью UPN и пароля на управляемых настольных устройствах Microsoft. Однако, чтобы убедиться, что эта функция будет работать, необходимо дважды проверить следующие вещи:

- Подтвердим, что Azure AD Connect настроен и использует локальное сервер Active Directory, Windows Server 2008 R2 или более поздней основе.
- Подтверди, что Azure AD Connect работает с поддерживаемой версией и должен синхронизировать эти три атрибута с Azure AD: 
    - Доменное имя DNS локального Active Directory (где находятся пользователи)
    - NetBIOS локального каталога Active Directory (где находятся пользователи)
    - Имя учетной записи SAM пользователя


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Единый Sign-On с помощью Windows Hello для бизнеса

Устройства Microsoft Managed Desktop также предоставляют пользователям быстрый и без пароля опыт, используя Windows Hello для бизнеса. Чтобы убедиться, что Windows Hello для бизнеса будет работать без необходимости предоставлять пользователям соответствующие upN и пароль, посетите приложения [Configure Azure AD,](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) присоединившись к устройствам для локальной Single-Sign Использование Windows Hello для бизнеса для проверки требований, а затем выполните предусмотренные там действия.


## <a name="apps-and-resources-that-use-authentication"></a>Приложения и ресурсы, которые используют проверку подлинности

Чтобы получить полное руководство по настройке приложений для работы с Azure Active Directory, обратитесь к приложению Understand considerations for [applications and resources](/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) in the Azure content set. В сводке:


- Если вы **используете** облачные приложения, например приложения, добавленные в галерею приложений Azure AD, большинство из них не требуют дальнейшей подготовки к работе с Microsoft Managed Desktop. Однако любые приложения Win32, которые не используют диспетчер веб-учетных записей (WAM), по-прежнему могут подсказыть пользователям проверку подлинности.

- Для приложений, которые **находятся** на локальном сайте, обязательно добавьте эти приложения в список надежных сайтов в браузерах. Этот шаг позволит обеспечить бесперебойную работу проверки подлинности Windows без запроса пользователей на учетные данные. Чтобы добавить приложения, обратитесь к [доверенным сайтам](../working-with-managed-desktop/config-setting-ref.md#trusted-sites) в [ссылке Настраиваемые параметры](../working-with-managed-desktop/config-setting-ref.md).

- Если вы используете службы Federated Active Directory, проверьте, включена ли служба SSO с помощью действий в Verify и управления одним входом с [помощью AD FS.](/previous-versions/azure/azure-services/jj151809(v=azure.100)) 

- Для приложений, которые находятся на месте и используют старые протоколы, не требуется дополнительная настройка, если устройства имеют доступ к локальному контроллеру домена для проверки подлинности. Однако для обеспечения безопасного доступа к этим приложениям необходимо развернуть прокси-сервер Приложения Azure AD. Дополнительные сведения см. в видеоролике Удаленный доступ к локальному приложению [через прокси-сервер приложения Azure Active Directory.](/azure/active-directory/manage-apps/application-proxy)

- Приложения, которые работают **локально** и полагаются на проверку подлинности машины, не поддерживаются, поэтому следует заменить их более новыми версиями.

### <a name="network-shares-that-use-authentication"></a>Сетевые акции, которые используют проверку подлинности

Дополнительная настройка не требуется пользователям для доступа к сетевым акциям, если устройства имеют доступ к локальному контроллеру домена с помощью пути UNC.

### <a name="printers"></a>Принтеры

Устройства Microsoft Managed Desktop не могут подключаться к принтерам, опубликованным в локальном каталоге Active Directory, если только вы не настроили [гибридную облачную печать.](/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)

Хотя принтеры не могут быть автоматически обнаружены только в облачной среде, пользователи могут использовать локальное принтеры с помощью пути к принтеру или пути очереди принтера, если устройства имеют доступ к локальному контроллеру домена.

<!--add fuller material on printers when available-->