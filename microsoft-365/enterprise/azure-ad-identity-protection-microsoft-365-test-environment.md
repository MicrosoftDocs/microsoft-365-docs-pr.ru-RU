---
title: Защита идентификации Azure AD для тестовой среды Microsoft 365 для предприятий
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Настройте защиту идентификации Azure AD и проанализируйте текущие учетные записи в тестовой среде Microsoft 365 для предприятий.
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487712"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>Защита идентификации Azure AD для тестовой среды Microsoft 365 для предприятий

*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для корпоративных тестовых сред.*

Вы можете использовать защиту идентификации Azure Active Directory (Azure AD) для обнаружения потенциальных уязвимостей, влияющих на удостоверения вашей организации, настройки автоматизированных ответов и изучения инцидентов. В этой статье описывается, как использовать защиту идентификации Azure AD для просмотра анализа учетных записей тестовой среды.

Настройка защиты идентификации Azure AD в тестовой среде Microsoft 365 для предприятий состоит из двух этапов:

- [Этап 1. Создание тестовой среды Microsoft 365 для предприятий](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Этап 2. Использование защиты идентификации Azure AD](#phase-2-use-azure-ad-identity-protection)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Чтобы получить визуальную карту со всеми статьями в руководстве по лаборатории тестирования Microsoft 365 для предприятий, перейдите в стек руководств по лаборатории тестирования [Microsoft 365 для предприятий.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Этап 1. Создание тестовой среды Microsoft 365 для предприятий

Если вы хотите протестировать защиту идентификации Azure AD в облегченом режиме с минимальными требованиями, следуйте инструкциям в базовой конфигурации с облегченной [базой.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Если вы хотите протестировать защиту идентификации Azure AD на имитированном предприятии, следуйте инструкциям в сквозной [проверке подлинности.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Для тестирования защиты идентификации Azure AD не требуется тестовая среда имитации предприятия, которая включает имитированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для леса доменных служб Active Directory (AD DS). Она предоставляется здесь в качестве варианта, чтобы вы могли протестировать защиту идентификации Azure AD и поэкспериментировать с ней в типичной для организации среде.
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Этап 2. Использование защиты идентификации Azure AD

1. Откройте частный экземпляр браузера и во sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.
2. На портале Azure введите защиту **удостоверений** в поле поиска, а затем выберите **"Защита идентификации Azure AD".**
3. В области **"Защита удостоверений — обзор"** выберите каждый отчет, чтобы узнать, что в нем сообщается.
4. Under **Notify**, select **Users at risk detected alerts**.
5. В области **оповещений** об обнаруженных пользователях с риском выберите **"Средний".**
6. Для **сообщений электронной почты отправляются** следующим пользователям, **выберите** "Включено" и убедитесь, что учетная запись глобального администратора включена в список выбранных участников.
7. Нажмите **Сохранить**.

В **области "Защита"** выберите различные отделы, чтобы узнать, как их настроить. Если вы создаете и активируете политику, убедитесь, что она не блокирует доступ для всех пользователей или вы не сможете войти в систему. Чтобы предотвратить это, исключить определенные учетные записи пользователей, например глобальных администраторов.

Для дальнейшего тестирования и экспериментов [см. моделирование событий риска.](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)

## <a name="next-step"></a>Следующий этап

Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.

## <a name="see-also"></a>См. также

[План удостоверений](identity-roadmap-microsoft-365.md)

[Руководства по лаборатории тестирования для Microsoft 365 для предприятий](m365-enterprise-test-lab-guides.md)

[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)

[Документация по Microsoft 365 для предприятий](https://docs.microsoft.com/microsoft-365-enterprise/)
