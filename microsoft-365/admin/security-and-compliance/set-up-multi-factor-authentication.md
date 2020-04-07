---
title: Настройка многофакторной проверки подлинности для Office 365
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
description: Сведения об использовании параметров безопасности по умолчанию с целью настройки многофакторной проверки подлинности для пользователей Office 365.
monikerRange: o365-worldwide
ms.openlocfilehash: 331552a4de21198fe7fbc9980e89bfcd87449ffa
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153560"
---
# <a name="set-up-multi-factor-authentication"></a>Настройка многофакторной проверки подлинности
  
> [!IMPORTANT]
> Если вы приобрели подписку или пробную версию после 21 октября 2019 г., а вы неожиданно запрашиваете многофакторную проверку подлинности (MFA), для вашей подписки автоматически включена поддержка [по умолчанию для безопасности](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) .

В каждой новой подписке на Office 365 для бизнеса или Microsoft 365 бизнес автоматически включены параметры безопасности по умолчанию. Это означает, что каждый пользователь должен настроить MFA и установить приложение Microsoft Authenticator на мобильном устройстве. Дополнительные сведения см. в статье [Настройка двухфакторной проверки подлинности для Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).  

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

У всех остальных пользователей дополнительная проверка подлинности будет запрашиваться при необходимости. Дополнительные сведения см. в статье [Что такое параметры безопасности по умолчанию?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

> [!NOTE]
> Для установки или изменения MFA необходимо быть глобальным администратором Office 365. <br><br>
> Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.

Если вы ранее настроили MFA с использованием базовых политик, [потребуется отключить их и включить параметры безопасности по умолчанию](#move-from-baseline-policies-to-security-defaults). Однако если у вас есть Microsoft 365 бизнес или ваша подписка включает [Azure Active Directory Premium P1 или Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), вы также можете настроить политики [условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) . Чтобы использовать политики условного доступа, необходимо убедиться, что включена [современная проверка подлинности](#enable-modern-authentication-for-your-organization) .

> [!TIP]
> Чтобы объяснить пользователям, как настроить приложение Authenticator, посетите раздел [Использование Microsoft Authenticator для Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).

## <a name="manage-security-defaults"></a>Управление параметрами безопасности по умолчанию

1. Войдите в [Центр администрирования](https://go.microsoft.com/fwlink/p/?linkid=834822) с учетными данными глобального администратора.
2. Перейдите в раздел [свойств Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).

3. В нижней части страницы щелкните **Управление параметрами безопасности по умолчанию**.
4. Нажмите кнопку **Да** , чтобы включить параметры безопасности по умолчанию или **нет** , чтобы отключить параметры безопасности по умолчанию, а затем нажмите кнопку **сохранить**.

## <a name="move-from-baseline-policies-to-security-defaults"></a>Переход с базовых политик на параметры безопасности по умолчанию

1. В [Центре администрирования](https://go.microsoft.com/fwlink/p/?linkid=834822) выберите пункт **Установка**.

2. Рядом с надписью **Вход и безопасность** в разделе **Повышение безопасности входа** нажмите кнопку **Просмотреть**.

3. В разделе **Повышение безопасности входа** нажмите **Управление**. 

4. На странице **Условный доступ — Политики** портала Azure выберите все базовые политики со значением **Вкл** и присвойте им значение **Выкл**.
5. Откройте страницу [свойств Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
6. В нижней части страницы щелкните ссылку **Управление параметрами безопасности по умолчанию** и в области **Включение параметров безопасности по умолчанию** установите переключатель **Включение параметров безопасности по умолчанию** в положение **Да**. 

## <a name="enable-modern-authentication-for-your-organization"></a>Включение современной проверки подлинности в Организации

Все клиентские приложения Office 2016 поддерживают многофакторную проверку подлинности с помощью библиотеки проверки подлинности Active Directory (ADAL). Это означает, что для клиентов Office 2016 пароли приложений необязательны. Однако необходимо убедиться, что ваша подписка на Office 365 поддерживает ADAL или современную проверку подлинности.

1. Чтобы включить современную проверку подлинности, в [Центре администрирования](https://go.microsoft.com/fwlink/p/?linkid=834822) выберите **Параметры** \> **Параметры**, затем на вкладке **Службы** выберите в списке **Современная проверка подлинности**.

2. Установите флажок **Включить функцию "Современная проверка подлинности"** в области **Современная проверка подлинности‎**. 

    ![Область "Современная проверка подлинности" с установленным флажком включения.](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> С августа 2017 года во всех новых клиентах Office 365, включающих Skype для бизнеса Online и Exchange Online, современная проверка подлинности включена по умолчанию. Чтобы проверить состояние современной проверки подлинности для Skype для бизнеса Online, можно использовать PowerShell в Skype для бизнеса Online с учетными данными глобального администратора. Выполните команду Get-CsOAuthConfiguration, чтобы проверить значение параметра -ClientADALAuthOverride. Если у параметра -ClientADALAuthOverride значение "Разрешено", современная проверка подлинности включена.
Чтобы узнать состояние современной проверки подлинности для Exchange Online, см. статью [Включение современной проверки подлинности в Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).

## <a name="related-articles"></a>Статьи по теме

[10 основных способов защиты планов Office 365 и Microsoft 365 для бизнеса](secure-your-business-data.md).

[Включение современной проверки подлинности для Office 2013 на устройствах с Windows](enable-modern-authentication.md)
