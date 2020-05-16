---
title: Настройка многофакторной проверки подлинности для пользователей
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Узнайте, как использовать параметры безопасности по умолчанию для настройки многофакторной проверки подлинности для пользователей.
monikerRange: o365-worldwide
ms.openlocfilehash: c4ea6037b34d29f2d1e05e248e03e49ee6b06f56
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262379"
---
# <a name="set-up-multi-factor-authentication"></a>Настройка многофакторной проверки подлинности
  
> [!IMPORTANT]
> Если вы приобрели подписку или пробную версию после 21 октября 2019 г., а вы неожиданно запрашиваете многофакторную проверку подлинности (MFA), для вашей подписки автоматически включена поддержка [по умолчанию для безопасности](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) .

Для каждой новой подписки Microsoft 365 автоматически будут включены [Параметры безопасности по умолчанию](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) . Это означает, что каждый пользователь должен будет настроить многофакторную проверку подлинности (MFA) и установить приложение Microsoft Authenticator на мобильном устройстве. Дополнительные сведения см. [в разделе Настройка MFA для учетной записи Microsoft 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).

Потребуются следующие девять ролей администраторов для дополнительной проверки подлинности при каждом входе:

- Глобальный администратор
- Администратор SharePoint
- Администратор Exchange
- Администратор условного доступа
- Администратор безопасности
- Администратор службы технической поддержки и администратор паролей
- Администратор выставления счетов
- Администратор пользователей
- Администратор проверки подлинности

У всех остальных пользователей дополнительная проверка подлинности будет запрашиваться при необходимости.

> [!NOTE]
> Для настройки и изменения MFA необходимо быть глобальным администратором. <br><br>
> Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.

Если вы уже настроили MFA с помощью базовых политик, [необходимо отключить их, чтобы включить параметры по умолчанию для безопасности](#move-from-baseline-policies-to-security-defaults). Однако если у вас есть Microsoft 365 бизнес или ваша подписка включает [Azure Active Directory Premium P1 или Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), вы также можете настроить политики [условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) . Чтобы использовать политики условного доступа, необходимо убедиться в том, что параметры безопасности по умолчанию отключены, а [современная проверка подлинности](#enable-modern-authentication-for-your-organization) включена.

> [!TIP]
> Чтобы объяснить пользователям, как настроить приложение для проверки подлинности (Майкрософт), ознакомьтесь со статьей [Использование средства проверки подлинности Майкрософт в Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411).

## <a name="manage-security-defaults"></a>Управление параметрами безопасности по умолчанию

1. Войдите в [центр администрирования](https://go.microsoft.com/fwlink/p/?linkid=834822) с учетными данными глобального администратора.
2. Перейдите на [страницу "свойства Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)".
3. В нижней части страницы щелкните **Управление параметрами безопасности по умолчанию**.
4. Нажмите кнопку **Да** , чтобы включить параметры безопасности по умолчанию и **нет** для отключения параметров безопасности по умолчанию, а затем нажмите кнопку **сохранить**.

## <a name="move-from-baseline-policies-to-security-defaults"></a>Переход с базовых политик на параметры безопасности по умолчанию

1. Перейдите на [страницу условного доступа — политики](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2. Выберите каждую базовую политику, **On** включенную в **параметр** , и установите для **нее значение отключено**.
3. Перейдите на [страницу "свойства Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)".
4. В нижней части страницы выберите **Управление параметрами безопасности по умолчанию**, а затем в области **включить** параметры безопасности по умолчанию установите переключатель **включить параметры безопасности по умолчанию** в значение **Да**, а затем нажмите кнопку **сохранить**. 

## <a name="enable-modern-authentication-for-your-organization"></a>Включение современной проверки подлинности в Организации

Все клиентские приложения Office 2016 поддерживают многофакторную проверку подлинности с помощью библиотеки проверки подлинности Active Directory (ADAL). Это означает, что для клиентов Office 2016 пароли приложений необязательны. Для получения дополнительных сведений обратитесь к [этой статье](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords) .

Тем не менее, необходимо убедиться, что для подписки Microsoft 365 включена поддержка ADAL или современная проверка подлинности.

1. Чтобы включить современные проверки подлинности, в [центре администрирования](https://go.microsoft.com/fwlink/p/?linkid=834822) **выберите параметры** \> **Организации** параметры и затем на вкладке **службы** выберите в списке пункт **современная проверка подлинности** .

2. Установите флажок **включить современная проверка подлинности (рекомендуется)** на панели **современная проверка подлинности** и нажмите кнопку **сохранить изменения**. 

    ![Область "Современная проверка подлинности" с установленным флажком включения.](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> В августе 2017 г. все новые подписки на Microsoft 365, в которые входит Skype для бизнеса Online и Exchange Online, по умолчанию включены современные проверки подлинности. Чтобы проверить состояние современной проверки подлинности для Skype для бизнеса Online, можно использовать PowerShell в Skype для бизнеса Online с учетными данными глобального администратора. Выполните команду Get-CsOAuthConfiguration, чтобы проверить значение параметра -ClientADALAuthOverride. Если у параметра -ClientADALAuthOverride значение "Разрешено", современная проверка подлинности включена.
Чтобы узнать состояние современной проверки подлинности для Exchange Online, см. статью [Включение современной проверки подлинности в Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).

## <a name="related-articles"></a>Статьи по теме

[10 основных способов защиты Microsoft 365 для бизнес-планов](secure-your-business-data.md)

[Включение современной проверки подлинности для Office 2013 на устройствах с Windows](enable-modern-authentication.md)
