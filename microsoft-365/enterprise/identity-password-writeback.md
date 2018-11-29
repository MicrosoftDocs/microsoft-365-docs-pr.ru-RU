---
title: Шаг 9. Упрощение процедуры обновления паролей
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
description: В этой статье рассказывается, как настроить функцию обратной записи паролей для гибридных развертываний.
ms.openlocfilehash: 55da101ca729de804ae76dafbe35a46969af9d8d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870621"
---
# <a name="step-9-simplify-password-updates"></a>Шаг 9. Упрощение процедуры обновления паролей

*Этот шаг — необязательный для гибридных развертываний; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

На данном шаге вы разрешите пользователям сбрасывать их пароли с помощью Azure Active Directory (AD), которые затем будут реплицированы в ваш локальный Windows Server Active Directory (AD). Этот процесс называется обратной записью паролей. Благодаря функции обратной записи паролей пользователям не нужно обновлять свои пароли на локальном Windows Server AD, в котором хранятся учетные записи пользователей и их атрибуты. Это ценная функция для удаленных пользователей и пользователей, находящихся в пути, у которых нет подключения для удаленного доступа к сети локальной среды.

Функция обратной записи пароля необходима, чтобы полностью использовать возможности функции Identity Protection, например чтобы требовать от пользователей изменять свои локальные пароли при высоком риске компрометации учетной записи.

Дополнительные сведения и инструкции по настройке см. в статье о [SSPR с функцией обратной записи паролей в Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).

>[!Note]
>Выполните обновление до последней версии Azure AD Connect, чтобы использовать лучшие новые функции по мере их выпуска. Дополнительные сведения см. в статье [Выборочная установка Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).
>

Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-pw-writeback), при выполнении которых можно считать данный шаг завершенным.

## <a name="next-step"></a>Следующий шаг

|||
|:-------|:-----|
|![](./media/stepnumbers/Step10.png)| [Упрощение входа в систему для пользователей](identity-single-sign-on.md) |

