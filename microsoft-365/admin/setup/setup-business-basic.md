---
title: Настройка Microsoft 365 бизнес базовый
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: Узнайте, как настроить подписку на Microsoft 365 бизнес базовый.
ms.openlocfilehash: 43ae19b24058429c9276bd44dd4c3960c792ca0d
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126189"
---
# <a name="set-up-microsoft-365-business-basic"></a>Настройка Microsoft 365 бизнес базовый

 Посмотрите короткое видео о настройке Microsoft 365 бизнес базовый.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vk3W]

Если это видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="add-your-domain-to-personalize-sign-in"></a>Добавление домена для персонализации входа

При покупке Microsoft 365 бизнес базовый вы можете воспользоваться принадлежащим вам доменом или купить домен во время регистрации.

- Если вы приобрели новый домен во время регистрации, он уже полностью настроен и можно перейти к пункту [Добавление пользователей и назначение лицензий](#add-users-and-assign-licenses).

 ::: moniker range="o365-worldwide"

1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Если вы используете Office 365 Germany, перейдите в [этот Центр администрирования](https://go.microsoft.com/fwlink/p/?linkid=848041).

::: moniker-end

::: moniker range="o365-21vianet"

1. Если вы используете Службу Office 365 компании 21Vianet, перейдите в [этот Центр администрирования.](https://go.microsoft.com/fwlink/p/?linkid=850627)

::: moniker-end 

2. Выберите **Перейти к установке**, чтобы запустить мастер установки.
    
3. На шаге **Добавить домен** введите имя домена, который вы хотите использовать (например, contoso.com).

    > [!IMPORTANT]
    > Если вы приобрели домен во время регистрации, шаг **Добавить домен** не будет отображаться. Вместо этого перейдите в раздел [Добавить пользователей](#add-users-and-assign-licenses).

    
4. Выполните шаги, описанные в мастере, по [созданию записей DNS для Office 365 у любого поставщика услуг размещения DNS](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider), который проверяет, являетесь ли вы владельцем домена. Если вы знаете свой узел домена, см. также [инструкции, связанные с узлом](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Если ваш поставщик услуг размещения — GoDaddy или другой узел, поддерживающий [подключение доменов](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), все просто: вам будет автоматически предложено войти в систему и разрешить Майкрософт проверить подлинность от вашего имени.

    ![На странице GoDaddy "Подтверждение доступа" выберите "Авторизовать".](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>Добавление пользователей и назначение лицензий

Вы можете добавить пользователей в мастере или [позднее](../add-users/add-users.md) в Центре администрирования. Кроме того, если у вас есть локальный контроллер домена, вы можете добавить пользователей с помощью [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

## <a name="add-users-in-the-wizard"></a>Добавление пользователей в мастере

Всем пользователям, которых вы добавляете в мастере, автоматически назначается лицензия Microsoft 365 бизнес базовый.

1. Если в вашей подписке на Microsoft 365 бизнес базовый уже есть пользователи (например, если вы использовали Azure AD Connect), вы можете назначить им лицензии прямо сейчас. Добавьте лицензии и для них.

2. После добавления пользователей у вас также будет возможность предоставить им учетные данные. Вы можете распечатать их, отправить по электронной почте или скачать.

## <a name="connect-your-domain"></a>Подключение домена

> [!NOTE]
> Если вы решили воспользоваться доменом .onmicrosoft или использовали Azure AD Connect для настройки пользователей, этот шаг отображаться не будет.
  
Для настройки служб вам необходимо обновить некоторые записи узла DNS или регистратора доменных имен.
  
1. Мастер настройки обычно обнаруживает регистратор и предоставляет ссылку на пошаговые инструкции по обновлению записей NS на его сайте. В противном случае [измените серверы доменных имен для настройки Office 365 у любого регистратора доменных имен](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar). 

    - Если у вас уже есть записи DNS, например для существующего веб-сайта, но узел DNS поддерживает [подключение доменов](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), выберите пункт **Автоматическое добавление записей**. На странице **Выберите веб-службы** примите все условия по умолчанию, нажмите **Далее**, а затем на странице узла DNS выберите **Авторизовать**.
    - Если у вас уже есть записи DNS для других узлов DNS (не поддерживающих подключение доменов), вам потребуется управлять своими записями DNS, чтобы убедиться в наличии подключения существующих служб. Дополнительные сведения см. в статье [Основные сведения о доменах](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics).

2. Выполните шаги, описанные в мастере, чтобы настроить электронную почту и другие службы.

    По завершении процесса регистрации вы будете перенаправлены в Центр администрирования, где можно добавить пользователей и назначить лицензии. Выполнив первоначальные настройки, вы сможете продолжить настраивать службы, входящие в состав подписок, на странице **Настройка** в Центре администрирования.

    Дополнительные сведения о мастере настройки и странице **Настройка** в Центре администрирования см. в статье [Различия между мастером настройки и страницей "Настройка"](o365-setup-wizard-and-setup-page.md).