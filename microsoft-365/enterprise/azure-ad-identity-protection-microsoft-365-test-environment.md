---
title: Защита удостоверений Azure AD для тестовой среды Microsoft 365 корпоративный
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Настройка защиты идентификации Azure AD и анализ текущих учетных записей в тестовой среде Microsoft 365 Enterprise.
ms.openlocfilehash: d267bb9dff94acfec46fa1275887f9cade2a7285
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074089"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Защита удостоверений Azure AD для тестовой среды Microsoft 365 корпоративный

Защита удостоверений Azure AD позволяет обнаруживать потенциальные уязвимости, затрагивающие удостоверения вашей организации, настраивать автоматические ответы и изучению инцидентов. В этой статье описывается включение защиты удостоверений Azure AD и Просмотр анализа учетных записей тестовой среды.

Настройка защиты идентификации Azure AD в тестовой среде Microsoft 365 Enterprise состоит из двух этапов:

1. Создайте среду тестирования Microsoft 365 корпоративный.
2. Включение и использование защиты удостоверений Azure AD.

![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Этап 1: создание тестовой среды Microsoft 365 Enterprise

Если вы хотите просто протестировать защиту удостоверения Azure AD в упрощенном виде с минимальными требованиями, следуйте инструкциям, приведенным в разделе [облегченная базовая конфигурация](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Если вы хотите протестировать защиту удостоверения Azure AD в имитируемой Организации, следуйте инструкциям в [сквозной проверке](pass-through-auth-m365-ent-test-environment.md)подлинности.
  
> [!NOTE]
> Для тестирования защиты удостоверений Azure AD не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS). Он предоставляется в качестве варианта, чтобы можно было протестировать защиту удостоверения Azure AD и поэкспериментировать с ним в среде, представляющей типичную организацию. 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a>Этап 2: Включение и использование средства защиты удостоверений Azure AD

1. Откройте частный экземпляр браузера и войдите на портал Azure, [https://portal.azure.com](https://portal.azure.com) используя учетную запись глобального администратора вашей тестовой среды Microsoft 365 Enterprise.
2. На портале Azure выберите **все службы > Marketplace**.
3. Введите **Azure AD Identity Protection** , а затем щелкните ее.
4. В колонке **Приступая к работе** щелкните Встроенная **Настройка**, нажмите кнопку закрепить **** **на панели мониторинга**, а затем нажмите кнопку **создать**.
5. На портале Azure выберите на панели мониторинга **защиту удостоверений Azure AD** . 

   Вы должны увидеть колонку " **Защита удостоверений Azure AD** " с панелью мониторинга. Обратите внимание, что в разделе **уязвимости**было определено количество учетных записей пользователей без регистрации многофакторной проверки подлинности. Этот номер зависит от предыдущих руководств по лаборатории тестирования Microsoft 365 Enterprise.

6. Щелкните категории для проверки, **** чтобы проверить наличие обнаруженных пользователей или событий.

Дополнительные сведения о тестировании и экспериментах приведены в разделе [моделирование событий риска](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).

Чтобы получить сведения и ссылки на странице "Защита удостоверений Azure AD" в рабочей среде, ознакомьтесь со статьей " [Защита от кражи учетных данных](identity-multi-factor-authentication.md#identity-ident-prot) " на этапе идентификации.

## <a name="next-step"></a>Следующий шаг

Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.

## <a name="see-also"></a>См. также

[Шаг 2. Идентификация](identity-infrastructure.md)

[Руководства по лаборатории тестирования для Microsoft 365 корпоративный](m365-enterprise-test-lab-guides.md)

[Развертывание Microsoft 365 корпоративный](deploy-microsoft-365-enterprise.md)

[Документация по Microsoft 365 корпоративный](https://docs.microsoft.com/microsoft-365-enterprise/)
