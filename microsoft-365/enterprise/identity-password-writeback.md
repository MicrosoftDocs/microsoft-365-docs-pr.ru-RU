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
# <a name="step-9-simplify-password-updates"></a><span data-ttu-id="273c2-103">Шаг 9. Упрощение процедуры обновления паролей</span><span class="sxs-lookup"><span data-stu-id="273c2-103">Step 9: Simplify password updates</span></span>

<span data-ttu-id="273c2-104">*Этот шаг — необязательный для гибридных развертываний; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="273c2-104">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="273c2-p101">На данном шаге вы разрешите пользователям сбрасывать их пароли с помощью Azure Active Directory (AD), которые затем будут реплицированы в ваш локальный Windows Server Active Directory (AD). Этот процесс называется обратной записью паролей. Благодаря функции обратной записи паролей пользователям не нужно обновлять свои пароли на локальном Windows Server AD, в котором хранятся учетные записи пользователей и их атрибуты. Это ценная функция для удаленных пользователей и пользователей, находящихся в пути, у которых нет подключения для удаленного доступа к сети локальной среды.</span><span class="sxs-lookup"><span data-stu-id="273c2-p101">In this step, you'll allow users to reset their passwords through Azure Active Directory (AD), which is then replicated to your local Windows Server Active Directory (AD). This process is known as password writeback. With password writeback, users don’t need to update their passwords through the on-premises Windows Server AD where user accounts and their attributes are stored. This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="273c2-109">Функция обратной записи пароля необходима, чтобы полностью использовать возможности функции Identity Protection, например чтобы требовать от пользователей изменять свои локальные пароли при высоком риске компрометации учетной записи.</span><span class="sxs-lookup"><span data-stu-id="273c2-109">Password writeback is required to fully utilize Identity Protection feature capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="273c2-110">Дополнительные сведения и инструкции по настройке см. в статье о [SSPR с функцией обратной записи паролей в Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span><span class="sxs-lookup"><span data-stu-id="273c2-110">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="273c2-p102">Выполните обновление до последней версии Azure AD Connect, чтобы использовать лучшие новые функции по мере их выпуска. Дополнительные сведения см. в статье [Выборочная установка Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span><span class="sxs-lookup"><span data-stu-id="273c2-p102">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

<span data-ttu-id="273c2-113">Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-pw-writeback), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="273c2-113">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="273c2-114">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="273c2-114">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step10.png)| [<span data-ttu-id="273c2-115">Упрощение входа в систему для пользователей</span><span class="sxs-lookup"><span data-stu-id="273c2-115">Simplify user sign-in</span></span>](identity-single-sign-on.md) |

