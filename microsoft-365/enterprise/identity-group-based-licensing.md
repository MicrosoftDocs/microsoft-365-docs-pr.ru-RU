---
title: Шаг 12. Настройка автоматического лицензирования
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказывается о лицензировании на основе групп для групп Azure AD и о том, как его настроить.
ms.openlocfilehash: 82e4192f2ef9ba3d1d5ed7bd99a8cf603d7d4cc9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870421"
---
# <a name="step-12-set-up-automatic-licensing"></a>Шаг 12. Настройка автоматического лицензирования

*Этот шаг — необязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

На этом шаге вы настроите группы безопасности в Azure AD для автоматического назначения лицензий из набора подписок всем участникам группы. Эта возможность называется *лицензированием на основе групп*. При добавлении учетной записи пользователя в группу или удалении ее из группы происходит автоматическое назначение или удаление лицензий на подписки группы для учетной записи пользователя.

Вы настроите группы безопасности Azure AD для Microsoft 365 корпоративный, чтобы можно было назначать обе указанные ниже лицензии.

- Office 365 корпоративный, план E3 или E5
- Enterprise Mobility + Security (EMS), план E3 или E5.

Среди групп, которые вы определили на шаге 2, найдите группы, содержащие список учетных записей, в котором все пользователи группы обязаны иметь обе лицензии: и на Office 365, и на EMS. Убедитесь, что у вас достаточно лицензий для всех участников группы. Если у вас закончатся лицензии, то вам не удастся назначить лицензии новым пользователям, пока у вас не появится необходимое количество лицензий.

>[!Note]
>Не следует настраивать *лицензирование на основе групп* для групп, содержащих учетные записи типа "бизнес-бизнес" (B2B) в Azure.
>

См. дополнительные сведения в статье [Основы группового лицензирования в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).

См. статью с описанием [действий по настройке лицензирования на основе групп для группы безопасности Azure](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).

Ниже перечислены результаты, которые вы получите после выполнения данного шага.

- Вы определили группы безопасности, подходящие для лицензирования на основе групп.
- Вы настроили эти группы для лицензирования на основе групп.

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Руководства по лаборатории тестирования: автоматизация лицензий и членства в группах](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-group-license), при выполнении которых можно считать данный шаг завершенным.

## <a name="next-step"></a>Следующий шаг

|||
|:-------|:-----|
|![](./media/stepnumbers/Step13.png)| [Отслеживание действий в клиенте и при входе в систему](identity-azure-ad-access-usage-reporting.md) |

