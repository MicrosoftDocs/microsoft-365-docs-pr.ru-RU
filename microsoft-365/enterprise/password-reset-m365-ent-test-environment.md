---
title: Сброс пароля для тестовой среды Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/13/2019
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
description: 'Сводка: сведения о том, как настроить и проверить сброс пароля для тестовой среды Microsoft 365.'
ms.openlocfilehash: 5d98dcc50f16bc08da787a928beeeacf825201c9
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487428"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Сброс пароля для тестовой среды Microsoft 365

*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для корпоративных тестовых сред.*

Функция самостоятельного сброса паролей (SSPR) Azure Active Directory (Azure AD) позволяет пользователям сбрасывать пароли и разблокировать учетные записи.

В этой статье описывается настройка и проверка сброса паролей в тестовой среде Microsoft 365.

Настройка SSPR состоит из трех этапов:
- [Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Этап 2. Включений обратной записи паролей](#phase-2-enable-password-writeback)
- [Этап 3. Настройка и проверка сброса паролей](#phase-3-configure-and-test-password-reset)
    
![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Чтобы получить визуальную карту со всеми статьями в руководстве по лаборатории тестирования Microsoft 365 для предприятий, перейдите в стек руководств по лаборатории тестирования [Microsoft 365 для предприятий.](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365

Сначала следуйте инструкциям в синхронизации [паролей.](password-hash-sync-m365-ent-test-environment.md) 

Итоговая конфигурация выглядит так:
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Конфигурация состоит из следующих компонентов:
  
- Пробная или платная подписка Microsoft 365 E5
- Упрощенная интрасеть организации, подключенная к Интернету, состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети виртуальной сети Azure.
- Azure AD Connect работает на APP1 для синхронизации домена TESTLAB доменных служб Active Directory (AD DS) с клиентом Azure AD, связанным с подпиской Microsoft 365.

## <a name="phase-2-enable-password-writeback"></a>Этап 2. Включений обратной записи паролей

Выполните инструкции [этапа 2 руководства по лаборатории тестирования для обратной записи пароля](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

Чтобы использовать сброс пароля, необходимо включить обратную запись пароля.
  
## <a name="phase-3-configure-and-test-password-reset"></a>Этап 3. Настройка и проверка сброса паролей

На этом этапе настройте сброс пароля в клиенте Azure AD с помощью членства в группах, а затем убедитесь, что он работает.

Сперва включите сброс паролей для учетных записей в определенной группе Azure AD.

1. Откройте браузер в приватном режиме, откройте [https://portal.azure.com](https://portal.azure.com), а затем выполните вход, используя учетную запись глобального администратора.
2. На портале Azure выберите новую **группу групп Azure Active Directory.**  >    >  
3. Для параметра **Тип группы** настройте значение **Безопасность**, для параметра **Имя группы** — значение **PWReset**, а для параметра **Тип членства** — значение **Назначено**.
4. Select **Members**, find and select **User 3,** select **Select**, and then select **Create**.
5. Закройте панель **Группы**.
6. В области Azure Active Directory выберите сброс пароля **в** области навигации слева.
7. На панели **Сброс пароля - Свойства** щелкните **Выбрано** в разделе **Разрешен самостоятельный сброс пароля**.
8. Выберите **"Выбрать группу",** выберите группу **PWReset** и выберите **"Сохранить".**  >  
9. Закройте браузер, открытый в приватном режиме.

Затем протестировать сброс пароля для учетной записи User 3.

1. Откройте новое окно браузера в приватном режиме и перейдите к [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).
1. Войдите с помощью учетной записи "Пользователь 3".
1. In **More information required,** select **Next**. 
1. В разделе **Не утратьте доступ к учетной записи** укажите в качестве телефона для проверки подлинности свой номер мобильного телефона, а в качестве электронной почты для проверки подлинности — свою личную учетную запись электронной почты.
1. После проверки обоих окей выберите **"Выглядит хорошо"** и закроет частный экземпляр браузера.
1. В новом экземпляре частного браузера перейдите к [https://aka.ms/sspr](https://aka.ms/sspr) .
1. Введите имя учетной записи User 3, введите символы из CAPTCHA и выберите **"Далее".**
1. Для **проверки на шаге 1** выберите "Отправить по **электронной почте"** альтернативное сообщение электронной почты, а затем выберите "Электронная **почта".** Когда вы получите сообщение электронной почты, введите код проверки и выберите **"Далее".**
1. In **Get back into your account,** enter a new password for the User 3 account, and then select **Finish**. Запишите измененный пароль учетной записи пользователя 3 и храните его в безопасном месте.
1. На отдельной вкладке того же браузера перейдите к [https://portal.office.com](https://portal.office.com), а затем выполните вход, используя новый пароль и имя учетной записи "Пользователь 3". Откроется **Домашняя страница Microsoft Office**.

## <a name="next-step"></a>Следующий этап

Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.

## <a name="see-also"></a>См. также

[Руководства по лаборатории тестирования для Microsoft 365 для предприятий](m365-enterprise-test-lab-guides.md)

[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)

[Документация по Microsoft 365 для предприятий](https://docs.microsoft.com/microsoft-365-enterprise/)
