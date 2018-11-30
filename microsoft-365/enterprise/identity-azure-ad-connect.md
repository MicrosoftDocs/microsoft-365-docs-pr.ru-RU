---
title: 'Шаг 7: Синхронизация удостоверений'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/09/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается о параметрах удостоверений и настройке Azure AD Connect для синхронизации локального Windows Server AD с Azure AD.
ms.openlocfilehash: 2391ee11a1706bbbfdeb248c5967822d3ea68f72
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870513"
---
# <a name="step-7-synchronize-identities"></a>Шаг 7: Синхронизация удостоверений

*Этот шаг — обязательный для гибридных развертываний; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

На данном шаге вы синхронизируете локальную версию Windows Server Active Directory (AD) с клиентом Azure Active Directory (AD), используемым в ваших подписках на Office 365 и Enterprise Mobility + Security (EMS).

Azure AD Connect — это поддерживаемое Корпорацией Майкрософт средство, с помощью которого вы сможете синхронизировать только те удостоверения, которые вам действительно нужны, из одного или нескольких лесов сред Windows Server AD в свой клиент Azure AD.

![Сведения о том, как Azure AD Connect синхронизирует локальный каталог с Azure AD](./media/identity-azure-ad-connect/azure-ad-connect.png)

*Сведения о том, как Azure AD Connect синхронизирует локальный каталог с Azure AD*

Первое решение, которое необходимо принять касательно гибридного решения для работы с удостоверениями, связано с требованием проверки подлинности. Ниже перечислены возможные варианты.

- С помощью **управляемой проверки подлинности** Azure AD выполняет процесс проверки подлинности при входе пользователей в систему. Существует два указанных ниже метода управляемой проверки подлинности. 
    - **Синхронизация хэша пароля (PHS)**. [Рекомендованный и обязательный метод для некоторых премиум-функций.] Это самый простой способ включения проверки подлинности для объектов локального каталога в Azure AD. Microsoft Azure AD Connect извлекает хэшированный пароль из Windows Server AD, выполняет дополнительную обработку пароля для повышения безопасности и сохраняет его в Microsoft Azure AD. Дополнительные сведения см. в статье [Реализация синхронизации хэшированных паролей в службе синхронизации Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization).
    - **Сквозная проверка подлинности** — это простое решение для проверки подлинности паролей для служб на основе Azure AD. При сквозной проверке подлинности используется агент, работающий на одном или нескольких локальных серверах и проверяющий операции проверки подлинности пользователей непосредственно с помощью вашего локального Windows Server AD. Дополнительные сведения см. в статье [Вход пользователей с помощью сквозной проверки подлинности Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).
- При использовании **федеративной проверки подлинности** процесс проверки подлинности перенаправляется другому поставщику удостоверений через сервер федерации удостоверений, например через службы федерации Active Directory (AD FS), для входа пользователя в систему. Поставщик удостоверений может использовать дополнительные методы проверки подлинности, например проверку подлинности на основе смарт-карт. Дополнительные сведения см. в статье [Выбор подходящего метода проверки подлинности для вашего гибридного решения для работы с удостоверениями Azure Active Directory](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).

После того как вы определили гибридное решение для работы с удостоверениями, скачайте и запустите [средство устранения ошибок синхронизации каталогов IdFix](https://www.microsoft.com/download/details.aspx?id=36832), чтобы проанализировать Windows Server AD на наличие проблем.

После устранения всех проблем, найденных средством IdFix, прочитайте статью [Реализация синхронизации хэшей паролей](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) с рекомендациями по установке средства Azure AD Connect и настройке синхронизации каталогов между вашим локальным Windows Server AD и клиентом Azure AD для ваших подписок на Office 365 и EMS. После начала синхронизации вы будете обслуживать свои учетные записи пользователей и группы с помощью своего локального поставщика удостоверений, например Windows Server AD.

Корпорация Майкрософт предоставляет набор рекомендаций для [удостоверений и доступа к устройству](microsoft-365-policies-configurations.md) с целью обеспечения безопасности и эффективности работы сотрудников. 
- Данные о рекомендуемых требованиях для гибридных сред см. в колонке **Active Directory с синхронизацией хэша пароля** [предварительных требований](identity-access-prerequisites.md#prerequisites). 

- Данные о рекомендуемых требованиях для исключительно облачных сред см. в колонке **Только в облаке** [предварительных требований](identity-access-prerequisites.md#prerequisites).

|||
|:-------|:-----|
|![Руководства для лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Руководство по лаборатории тестирования: синхронизация хэшей паролей](password-hash-sync-m365-ent-test-environment.md)<br> [Руководство по лаборатории тестирования: сквозная проверка подлинности](pass-through-auth-m365-ent-test-environment.md) |
|||

Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-sync), при выполнении которых можно считать данный шаг завершенным.

## <a name="next-step"></a>Следующее действие

|||
|:-------|:-----|
|![](./media/stepnumbers/Step8.png)| [Отслеживание работоспособности функции синхронизации](identity-azure-ad-connect-health.md) |

