---
title: Azure AD защиту для вашего предприятия 365 Microsoft тестовой среды
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Настройка защиты удостоверения Azure AD и анализ текущих учетных записей в тестовой среде Microsoft 365 для предприятия.
ms.openlocfilehash: 165667ad2122839336ef0790ab5661cff53ca32b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870523"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Azure AD защиту для вашего предприятия 365 Microsoft тестовой среды

Azure AD защиту позволяет определить потенциальные, влияющие на удостоверения вашей организации, Настройка автоматических ответов и исследовать происшествия. В этой статье описывается, как включить защиту Azure AD и Просмотр анализа учетные записи тестовой среды.

Существует два этапа по настройке Azure AD защиту в тестовой среде Microsoft 365 для предприятия.

1. Создание тестовой среды Microsoft 365 для предприятия.
2. Включение и использование Azure AD защиту.

![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Этап 1: Создание масштабирование тестовой среды Microsoft 365 для предприятия

Если необходимо проверить Azure AD защиту в облегченный путь с минимальным требованиям, следуйте инструкциям в [упрощенной базовой конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Если вы хотите проверить Azure AD защиту в имитации enterprise, следуйте инструкциям в [сквозная проверка подлинности](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Тестирование защиту Azure AD не требует тестовой среды имитации предприятия, включающая имитации интрасети, подключенных к Интернету и синхронизации каталогов для леса Windows Server AD. Предоставляется здесь как вариант, чтобы проверить Azure AD защиту и экспериментировать с его в среде, которая представляет типичное организации. 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a>Этап 2: Включение и использование защиты удостоверения Azure AD

1. Откройте закрытый экземпляр браузера и войдите в портал Azure в [https://portal.azure.com](https://portal.azure.com) с учетной записью глобального администратора из тестовой среды Microsoft 365 для предприятия.
2. На портале Azure щелкните **всех служб > Marketplace**.
3. Введите **Azure AD защиту** и нажмите кнопку.
4. На blade **Приступая к работе** нажмите кнопку **Onboard** в разделе **Параметры**, выберите команду **прикрепить к панели мониторинга**и нажмите кнопку **Создать**.
5. На портале Azure щелкните **Azure AD защиту** на панели мониторинга. 

   Вы должны увидеть blade **Azure AD удостоверения защиты — Общие сведения о** панели мониторинга. В разделе **уязвимые места системы**Обратите внимание на то, что его определить число учетных записей пользователей без регистрации многофакторной проверки подлинности. Это число зависит от предыдущих Microsoft 365 Enterprise руководствах по лаборатории тестирования, необходимо выполнить.

6. Нажмите кнопку по категориям для **Проверить** изучить, если все пользователи или события, которые были обнаружены.

Для дальнейшего тестирования и экспериментов просмотра [событий риска Simulating](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).

См [защитить с учетными данными безопасности](identity-azure-ad-identity-protection.md) на этапе Identity сведения и ссылки на развертывание Azure AD защиту в рабочей среде.

## <a name="next-step"></a>Следующее действие

Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.

## <a name="see-also"></a>См. также

[Этап 2. Идентификация](identity-infrastructure.md)

[Руководства по лаборатории тестирования для Microsoft 365 корпоративный](m365-enterprise-test-lab-guides.md)

[Развертывание Microsoft 365 для предприятия](deploy-microsoft-365-enterprise.md)

[Документация по Microsoft 365 корпоративный](https://docs.microsoft.com/microsoft-365-enterprise/)
