---
title: Настройка Microsoft 365 бизнес премиум
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Узнайте, как настроить Microsoft 365 бизнес премиум, включая добавление домена и пользователей, настройку политик безопасности и т. д.
ms.openlocfilehash: e7ebe179c67077dc71ae4873b0711d0e810c701a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044737"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a>Настройка Microsoft 365 бизнес премиум в мастере настройки

Просмотрите это видео, чтобы просмотреть обзор настройки Microsoft 365 бизнес премиум.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a>Добавление домена, пользователей и настройка политик

При покупке Microsoft 365 бизнес премиум вы можете использовать собственный домен или приобрести его во время [регистрации.](sign-up.md)

- Если вы приобрели новый домен во время регистрации, он уже полностью настроен и можно перейти к пункту [Добавление пользователей и назначение лицензий](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Добавление домена для персонализации входа

1. Войдите в [Центр администрирования Microsoft 365](https://admin.microsoft.com) с учетными данными глобального администратора. 

2. Выберите **Перейти к установке**, чтобы запустить мастер установки.

    ![Выберите "Перейти к установке".](../media/gotosetupinadmincenter.png)

3. Со страницы **Установка приложений Office** можно также, если необходимо, установить приложения на своем компьютере.
    
4. На шаге **Добавить домен** введите имя домена, который вы хотите использовать (например, contoso.com).

    > [!IMPORTANT]
    > Если вы приобрели домен во время регистрации, шаг **Добавить домен** не будет отображаться. Вместо этого перейдите в раздел [Добавить пользователей](#add-users-and-assign-licenses).

    ![Screenshot of the Personalize your sign-in page.](../media/adddomain.png)

    
4. Следуйте шагам мастера, чтобы создать записи DNS у любого поставщика услуг размещения DNS для [Microsoft 365,](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) который проверяет владение доменом. Если вы знаете свой узел домена, см. также [инструкции для узла](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Если ваш поставщик услуг размещения — GoDaddy или другой узел, поддерживающий [подключение доменов](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), все просто: вам будет автоматически предложено войти в систему и разрешить Майкрософт проверить подлинность от вашего имени.

    ![На странице GoDaddy "Подтверждение доступа" выберите "Авторизовать".](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Добавление пользователей и назначение лицензий

Вы можете добавить пользователей в мастере или [позднее](add-users-m365b.md) в Центре администрирования. Кроме того, если у вас есть локальный контроллер домена, вы можете добавить пользователей с помощью [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

#### <a name="add-users-in-the-wizard"></a>Добавление пользователей в мастере

Все пользователи, добавленные в мастере, автоматически получают лицензию Microsoft 365 бизнес премиум.

![Снимок экрана: страница "Добавление новых пользователей" в мастере](../media/addnewuserspage.png)

1. Если ваша подписка на Microsoft 365 бизнес премиум имеет существующих пользователей (например, если вы использовали Azure AD Connect), вы можете назначить им лицензии. Добавьте лицензии и для них.

2. После добавления пользователей у вас также будет возможность предоставить им учетные данные. Вы можете распечатать их, отправить по электронной почте или скачать.

### <a name="connect-your-domain"></a>Подключение домена

> [!NOTE]
> Если вы решили воспользоваться доменом .onmicrosoft или использовали Azure AD Connect для настройки пользователей, этот шаг отображаться не будет.
  
Для настройки служб вам необходимо обновить некоторые записи узла DNS или регистратора доменных имен.
  
1. Мастер настройки обычно обнаруживает регистратор и предоставляет ссылку на пошаговые инструкции по обновлению записей NS на его сайте. Если это не так, измените регистраторы доменных имен, чтобы настроить [Microsoft 365 у любого регистратора доменных имен.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar) 

    - Если у вас уже есть записи DNS, например для существующего веб-сайта, но узел DNS поддерживает [подключение доменов](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), выберите пункт **Автоматическое добавление записей**. На странице **Выберите веб-службы** примите все условия по умолчанию, нажмите **Далее**, а затем на странице узла DNS выберите **Авторизовать**.
    - Если у вас уже есть записи DNS для других узлов DNS (не поддерживающих подключение доменов), вам потребуется управлять своими записями DNS, чтобы убедиться в наличии подключения существующих служб. Дополнительные сведения см. в статье [Основные сведения о доменах](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics).

        ![Активировать страницу записей.](../media/activaterecords.png)

2. Выполните шаги, описанные в мастере, чтобы настроить электронную почту и другие службы.

### <a name="protect-your-organization"></a>Защита организации 

Политики, которые вы настроили в мастере, автоматически применяются к группе [безопасности "Все](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) *пользователи".* Вы также можете создать дополнительные группы для назначения политик в Центре администрирования.

1. При **повышении** защиты от расширенных киберугроз рекомендуется принять значения по умолчанию, чтобы [позволить Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) сканировать файлы и ссылки в приложениях Office.

    ![Снимок экрана: страница "Повышение защиты".](../media/increasetreatprotection.png)


2. На  странице "Предотвращение утечек конфиденциальных данных" примите значения по умолчанию, чтобы включить службу защиты от потери данных (DLP) в Office 365 для отслеживания конфиденциальных данных в приложениях Office и предотвращения случайного совместного использования этих данных за пределами организации.

3. На странице **"Защита данных в Office** для мобильных устройств" оставьте управление мобильными приложениями в сети, разоберите параметры и просмотрите их, а затем выберите "Создать политику управления **мобильными приложениями".**

    ![Снимок экрана: страница "Защита данных в Office для мобильных устройств".](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>Защита компьютеров с Windows 10

On the left nav, select **Setup** and then, under **Sign-in and security,** choose **Secure your Windows 10 computers**. Choose **View** to get started. Полные инструкции см. в инструкциях по обеспечению безопасности компьютеров с [Windows 10.](secure-win-10-pcs.md)

## <a name="deploy-office-365-client-apps"></a>Развертывание клиентских приложений Office 365

Если вы решили автоматически установить приложения Office во время установки, они будут устанавливаться на устройства с Windows 10 после того, как пользователи воберутся в Azure AD со своих устройств с Windows, используя свои учетные данные.

Чтобы установить Office на мобильных устройствах с iOS или Android, см. "Настройка мобильных устройств для [пользователей Microsoft 365 бизнес премиум".](set-up-mobile-devices.md)

Вы также можете установить Office по отдельности. Инструкции см. в инструкциях по установке Office на [компьютере с Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) или компьютере Mac.

## <a name="see-also"></a>См. также

[Обучающие видеоролики по Microsoft 365 для бизнеса](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
