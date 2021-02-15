---
title: Эффективный единый вход Azure AD для тестовой среды Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: Сводка. Настройте и протестируйте эффективный единый вход Azure AD для тестовой среды Microsoft 365.
ms.openlocfilehash: f98f82de50feb2a9f92d1ecc4775c5307b314a72
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487610"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>Эффективный единый вход Azure AD для тестовой среды Microsoft 365

*Это руководство по лаборатории тестирования можно использовать для тестовых сред Microsoft 365 для предприятий и Office 365 корпоративный.*

Бесшовный единый Sign-On Azure AD автоматически подключается к пользователям, когда они находятся на своих ПК или устройствах, подключенных к сети организации. Простой SSO Azure AD предоставляет пользователям простой доступ к облачным приложениям без необходимости в дополнительных локальном компоненте.

В этой статье описывается настройка тестовой среды Microsoft 365 для простого SSO Azure AD.

Настройка простого SSO Azure AD состоит из двух этапов:
- [Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Этап 2. Настройка эффективного единого входа Azure AD через Azure AD Connect на APP1](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Чтобы получить визуальную карту со всеми статьями в руководстве по лаборатории тестирования Microsoft 365 для предприятий, перейдите в стек руководств по лаборатории тестирования [Microsoft 365 для предприятий.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365

Следуйте инструкциям по [синхронизации паролей для Microsoft 365.](password-hash-sync-m365-ent-test-environment.md) 

Итоговая конфигурация выглядит так:
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Конфигурация состоит из следующих компонентов:
  
- Пробная или платная подписка Microsoft 365 E5
- Упрощенная интрасеть организации, подключенная к Интернету, состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети виртуальной сети Azure.
- Azure AD Connect работает на APP1 для периодической синхронизации домена TESTLAB доменных служб Active Directory (AD DS) с клиентом Azure AD подписки на Microsoft 365.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>Этап 2. Настройка эффективного единого входа Azure AD через Azure AD Connect на APP1

На этом этапе настройте azure AD Connect на APP1 для простого SSO Azure AD, а затем убедитесь, что он работает.

### <a name="configure-azure-ad-connect-on-app1"></a>Настройка Azure AD Connect на виртуальной машине APP1

1. На [портале Azure](https://portal.azure.com) выполните вход с помощью учетной записи глобального администратора и затем подключитесь к виртуальной машине APP1 с учетной записью TESTLAB\User1.

2. На рабочем столе APP1 запустите Azure AD Connect.

3. На странице **приветствия выберите** **"Настроить".**

4. На странице **"Дополнительные задачи"** выберите "Изменить **вход пользователя"** и выберите **"Далее".**

5. На странице **"Подключение к Azure AD"** введите учетные данные глобального администратора и выберите **"Далее".**

6. На странице **"Вход пользователя"** выберите **"Включить** единый вход", а затем выберите **"Далее".**

7. На странице **"Включить единый вход" выберите** **"Ввести учетные данные".**

8. В **диалоговом окне "Безопасность Windows"** введите **user1** и пароль учетной записи user1, выберите "ОК", а затем выберите **"Далее".**

9. На странице **"Готово к настройке"** выберите **"Настроить".**

10. На странице **"Настройка завершена"** выберите **"Выход".**

11. На портале Azure в левой области выберите **Azure Active Directory**  >  **Azure AD Connect.** Убедитесь, что функция **простого** единого входа отображается как **включенная.**

Затем проверьте возможность войти в свою подписку с помощью <strong>user1@testlab.</strong>\<*your public domain*> на имя пользователя учетной записи User1.

1. В Internet Explorer на APP1 выберите значок параметров, а затем выберите **"Параметры браузера".**
 
2. В **меню "Параметры браузера"** выберите **вкладку "Безопасность".**

3. Выберите **местную интрасеть,** а затем выберите **"Сайты".**

4. В **локальной интрасети** выберите **"Дополнительные".**

5. In **Add this website to the zone**, enter **https <span>://</span>autologon.microsoftazuread-sso.com,** select **Add**  >  **Close**  >    >  **OK**.

6. Выйдите и повторно войдите, используя другую учетную запись.

7. При запросе на вход укажите <strong>user1@testlab.</strong>\<*your public domain*> name, а затем выберите **"Далее".** Вход в учетную запись User1 будет выполнен без запроса пароля. Это доказывает, что эффективный единый вход работает.

Обратите внимание, что хотя у пользователя User1 есть разрешения администратора для домена AD DS TESTLAB, он не является глобальным администратором для Azure AD. Следовательно, значок **Администратор** не будет отображаться.

Ниже показана итоговая конфигурация.

![Смоделированная организации с тестовой средой сквозной проверки подлинности](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Конфигурация состоит из следующих компонентов:

- Пробная или платная подписка Microsoft 365 E5 с доменом DNS testlab.\<*your domain name*> -
- Упрощенная интрасеть организации, подключенная к Интернету, состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети виртуальной сети Azure.
- Azure AD Connect работает на APP1 для синхронизации списка учетных записей и групп из клиента Azure AD, связанного с подпиской на Microsoft 365, с доменом AD DS TESTLAB.
- Бесшовный SSO Azure AD включен, чтобы компьютеры в имитированной интрасети могли вводить данные в облачные ресурсы Microsoft 365 без указания пароля учетной записи пользователя.

## <a name="next-step"></a>Следующий этап

Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.

## <a name="see-also"></a>См. также

[Руководства по лаборатории тестирования для Microsoft 365 для предприятий](m365-enterprise-test-lab-guides.md)

[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)

[Документация по Microsoft 365 для предприятий](https://docs.microsoft.com/microsoft-365-enterprise/)
