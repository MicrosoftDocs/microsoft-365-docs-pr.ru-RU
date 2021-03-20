---
title: Azure AD Identity Protection для Microsoft 365 для корпоративной тестовой среды
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
description: Настройка azure AD Identity Protection и анализ текущих учетных записей в Microsoft 365 для корпоративной тестовой среды.
ms.openlocfilehash: 0cb0acf3faee13676573b04178bd6b4d3d36da4d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905348"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>Azure AD Identity Protection для Microsoft 365 для корпоративной тестовой среды

*Это руководство по тестовой лаборатории можно использовать только для Microsoft 365 для корпоративных тестовых сред.*

Вы можете использовать Azure Active Directory (Azure AD) Identity Protection для обнаружения потенциальных уязвимостей, влияющих на удостоверения организации, настройки автоматизированных ответов и расследования инцидентов. В этой статье описывается использование Azure AD Identity Protection для просмотра анализа учетных записей тестовой среды.

Настройка azure AD Identity Protection в Microsoft 365 для корпоративной тестовой среды включает два этапа:

- [Этап 1. Создание microsoft 365 для корпоративной тестовой среды](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Этап 2. Использование защиты удостоверений Azure AD](#phase-2-use-azure-ad-identity-protection)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Чтобы получить визуальную карту для всех статей в стеке Руководство по корпоративной тестовой лаборатории Microsoft 365, перейдите в [Microsoft 365 для](../downloads/Microsoft365EnterpriseTLGStack.pdf)корпоративного руководства по тестовой лаборатории.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Этап 1. Создание microsoft 365 для корпоративной тестовой среды

Если вы хотите протестировать Azure AD Identity Protection в легком режиме с минимальными требованиями, следуйте инструкциям в [базовой конфигурации Lightweight.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Если вы хотите протестировать Azure AD Identity Protection в смоделированном предприятии, следуйте инструкциям в сквозной [проверке подлинности.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Тестирование Azure AD Identity Protection не требует имитации тестовой среды предприятия, которая включает смоделированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для леса служб домена Active Directory (AD DS). Он предоставляется здесь в качестве параметра, чтобы можно было протестировать Azure AD Identity Protection и поэкспериментировать с ним в среде, которая представляет типичную организацию.
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Этап 2. Использование защиты удостоверений Azure AD

1. Откройте частный экземпляр браузера и вопишитесь на портал Azure с учетной записью глобального администратора [https://portal.azure.com](https://portal.azure.com) microsoft 365 для корпоративной тестовой среды.
2. На портале Azure введите защиту **удостоверений** в поле поиска и выберите **Azure AD Identity Protection**.
3. В **лезвии Защита удостоверений — обзор** выберите каждый отчет, чтобы узнать, какие отчеты он представляет.
4. В **статье Notify** выберите **оповещений пользователей,** которые находятся в опасности.
5. В области **обнаружения оповещений** о рисках выберите **Medium**.
6. Для **отправки электронных сообщений** следующим пользователям выберите **Включено** и убедитесь, что ваша учетная запись глобального администратора находится в списке выбранных членов.
7. Нажмите **Сохранить**.

В **статье Protect** выберите различные полицейские органы, чтобы узнать, как их настроить. Если вы создаете и активируете политику, убедитесь, что она не блокирует доступ для всех пользователей, или вы не сможете войти. Чтобы предотвратить это, исключить определенные учетные записи пользователей, например глобальные администраторы.

Дополнительные проверки и эксперименты см. в этой ленте [Simulating risk events.](/azure/active-directory/active-directory-identityprotection-playbook)

## <a name="next-step"></a>Следующий шаг

Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.

## <a name="see-also"></a>См. также

[Дорожная карта удостоверений](identity-roadmap-microsoft-365.md)

[Руководства по лаборатории тестирования для Microsoft 365 для предприятий](m365-enterprise-test-lab-guides.md)

[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)

[Документация по Microsoft 365 для предприятий](/microsoft-365-enterprise/)