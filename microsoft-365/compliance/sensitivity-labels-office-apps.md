---
title: Как метки конфиденциальности действуют в приложениях Office
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: С помощью меток конфиденциальности вы можете классифицировать и защищать конфиденциальное содержимое, не мешая совместной работе и производительности пользователей. Метки конфиденциальности можно использовать для применения параметров защиты, например шифрования или подложек для содержимого с метками.
ms.openlocfilehash: 1de7eadfcf95a54917c1d5e2cc0d42cc1ad486a5
ms.sourcegitcommit: c7f7ff463141f7d7f0970b64e5a04341db7e4fa8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "37378659"
---
# <a name="how-sensitivity-labels-work-in-office-apps"></a>Как метки конфиденциальности действуют в приложениях Office

## <a name="what-prerequisites-are-there-to-use-sensitivity-labels-in-office-applications"></a>Какие предварительные требования существуют для использования меток конфиденциальности в приложениях Office?

### <a name="common-requirements"></a>Общие требования 

- Унифицированные метки конфиденциальности должны быть [настроены и опубликованы в Центре безопасности и соответствия требованиям](https://aka.ms/managemip).
- Пользователи должны выполнить вход в Office с помощью рабочей учетной записи.
- Пользователям должны быть назначены лицензии Office 365 E3 или выше.

### <a name="additional-requirements-for-office-for-windows"></a>Дополнительные требования к Office для Windows 

- Клиент Azure Information Protection не должен быть запущен в Office. См. также: [Могут ли метки конфиденциальности одновременно использоваться в клиенте Azure Information Protection в Office для Windows?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows).

### <a name="additional-requirements-for-outlook-on-all-platforms"></a>Дополнительные требования для Outlook на всех платформах 

- Если при настройке меток отключена маркировка содержимого, требуется использовать Exchange Online, чтобы маркировка содержимого была добавлена при переносе.

## <a name="what-sensitivity-label-capabilities-are-supported-in-office-today"></a>Какие возможности меток конфиденциальности в настоящее время поддерживаются в Office? 

<table border="1" cellspacing="0" cellpadding="0">
<th><font size="-1">Возможность<th><font size="-1">Windows<th><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Интернет</tr>
<tr><td>

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint<br>
Outlook


<td><font size="-1"> Word<br>
Excel<br>
PowerPoint<br>
Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook </b>
</tr>

<tr>
<td><font size="-1">Применение, изменение или удаление метки вручную<td><font size="-1"><b>Да</b><br><font size="-1">1910 и выше</font>

<td><font size="-1"><b>Да</b><br><font size="-1">16.21.0 и выше</font>

<td><font size="-1"><b>Да</b><br><font size="-1">2.21 и выше</font>
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup>
<td><font size="-1"><b>Да</b><br><font size="-1">16.0.11231 и выше</font>
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup>
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup><td><font size="-1">Ожидается в ближайшее время<sup>3</sup>

<tr>
<td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Применение стандартной метки</a>
<td><font size="-1"><b>Да</b><br><font size="-1">1910 и выше</font>

<td><font size="-1"><b>Да</b><br><font size="-1">16.21.0 и выше</font>

<td><font size="-1"><b>Да</b><br><font size="-1">2.21 и выше</font>
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup>
<td><font size="-1"><b>Да</b><br><font size="-1">16.0.11231 и выше</font>
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup>
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup>
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Требование обоснования для изменения метки</a><sup>1</sup>
<td><font size="-1"><b>Да</b><br><font size="-1">1910 и выше</font>

<td><font size="-1"><b>Да</b><br><font size="-1">16.21.0 и выше</font>

<td><font size="-1"><b>Да</b><br><font size="-1">2.21 и выше</font>
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup>
<td><font size="-1"><b>Да</b><br><font size="-1">16.0.11231 и выше</font>
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup>
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup>
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Предоставление ссылки на страницу настраиваемой справки</a>
<td><font size="-1"><b>Да</b><br><font size="-1">1910 и выше</font>

<td><font size="-1"><b>Да</b><br><font size="-1">16.21.0 и выше</font>

<td><font size="-1"><b>Да</b><br><font size="-1">2.21 и выше</font>
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup>
<td><font size="-1"><b>Да</b><br><font size="-1">16.0.11231 и выше</font>
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup>
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup>
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Маркировка содержимого</a>
<td><font size="-1"><b>Да</b><br><font size="-1">1910 и выше</font>

<td><font size="-1"><b>Да</b><br><font size="-1">16.21.0 и выше</font>

<td><font size="-1"><b>Да</b><br><font size="-1">2.21 и выше</font>
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup>
<td><font size="-1"><b>Да</b><br><font size="-1">16.0.11231 и выше</font
><td><font size="-1">Ожидается в ближайшее время<sup>3</sup>
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup>
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup>

<tr><td><font size="-1">Назначение предопределенных разрешений
<td><font size="-1"><b>Да</b><br><font size="-1">1910 и выше</font>

<td><font size="-1"><b>Да</b><br><font size="-1">16.21.0 и выше</font>

<td><font size="-1"><b>Да</b><br><font size="-1">2.21 и выше</font>
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup>
<td><font size="-1"><b>Да</b><br><font size="-1">16.0.11231 и выше</font>
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup>
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup>
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">Предоставление пользователям возможности назначать разрешения</a>
<td><font size="-1"><b>Да</b><sup>2</sup><br><font size="-1">1910 и выше</font>

<td><font size="-1"><b>Да</b><sup>2</sup><br><font size="-1">16.21.0 и выше</font>

<td><font size="-1">Подлежит уточнению
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup>
<td><font size="-1">Подлежит уточнению<td
><font size="-1">Ожидается в ближайшее время<sup>3</sup>
<td><font size="-1">Подлежит уточнению
<td><font size="-1">Ожидается в ближайшее время<sup>3</sup>

<tr><td><font size="-1">Отправка данных <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">аналитики меток</a> для администраторов
<td><font size="-1">Подлежит уточнению

<td><font size="-1">Подлежит уточнению

<td><font size="-1">Подлежит уточнению
<td><font size="-1">Подлежит уточнению
<td><font size="-1">Подлежит уточнению
<td><font size="-1">Подлежит уточнению
<td><font size="-1">Подлежит уточнению
<td><font size="-1">Подлежит уточнению

<tr><td><font size="-1">Требование применения пользователями метки к электронной почте и документам
<td><font size="-1">Подлежит уточнению

<td><font size="-1">Подлежит уточнению

<td><font size="-1">Подлежит уточнению
<td><font size="-1">Подлежит уточнению
<td><font size="-1">Подлежит уточнению
<td><font size="-1">Подлежит уточнению
<td><font size="-1">Подлежит уточнению
<td><font size="-1">Подлежит уточнению

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">Автоматическое применение метки конфиденциальности к содержимому</a>
<td><font size="-1">Подлежит уточнению

<td><font size="-1">Подлежит уточнению

<td><font size="-1">Подлежит уточнению
<td><font size="-1">Подлежит уточнению
<td><font size="-1">Подлежит уточнению
<td><font size="-1">Подлежит уточнению
<td><font size="-1">Подлежит уточнению
<td><font size="-1">Подлежит уточнению
</table>

<br><sup>1</sup>Если настроено, пользователям потребуется обосновать понижение уровня метки. Однако данные обоснования пока недоступны администраторам. Они станут доступны, когда будет поддерживаться функция "Отправка данных аналитики меток для администраторов".
<br><sup>2</sup>Возможность назначения разрешений пользователями в настоящее время доступна только в Outlook для Windows и Mac. Доступность для Word, Excel и PowerPoint подлежит уточнению.
<br><sup>3</sup>Ожидается в 4 квартале 2019 г.

## <a name="when-do-content-marks-or-encryption-get-applied-after-content-is-given-a-sensitivity-label"></a>Когда к содержимому применяется маркировка или шифрование после присвоения метки конфиденциальности?

| Приложение | Маркировка содержимого | Шифрование
| --- | --- | --- |
| Word, Excel, PowerPoint на всех платформах | Сразу | Сразу |
| Outlook для ПК и Mac | После отправки сообщения электронной почты службой Exchange Online | Сразу |
| Word, Excel, PowerPoint на всех платформах | После отправки сообщения электронной почты службой Exchange Online | После отправки сообщения электронной почты службой Exchange Online |

## <a name="can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows"></a>Могут ли метки конфиденциальности одновременно использоваться в клиенте Azure Information Protection в Office для Windows?

Нет. Метки конфиденциальности отключены, если клиент Azure Information Protection загружен в Office для Windows.

Если у вас установлен клиент Azure Information Protection, но вы хотите вместо него использовать метки конфиденциальности, можно выполнить следующие действия:

1. Настройте параметр групповой политики  **Использование функции "Конфиденциальность" в Office для применения и просмотра меток конфиденциальности**, находящийся в разделе **Конфигурация пользователя/Административные шаблоны/Microsoft Office 2016/Параметры безопасности**.

  >Примечание. Этот параметр можно развернуть с помощью традиционных механизмов развертывания групповой политики или с помощью [службы политики облака Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service). 
 
  Кроме того, вы можете удалить или  [отключить](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) клиент Azure Information Protection. 

2. Перезапустите все приложения Office.

## <a name="will-sensitivity-labels-be-supported-in-non-subscription-versions-of-office-like-office-2016-or-office-2019"></a>Поддерживаются ли метки конфиденциальности в версиях Office без подписки, таких как Office 2016 и Office 2019?

Нет. Метки конфиденциальности поддерживаются только в версии Office 365 с подпиской и не поддерживаются в версиях без подписки. Однако в версиях Office без подписки можно использовать клиент унифицированных меток Azure Information Protection. 

## <a name="i-previously-deployed-protection-templates-before-setting-up-sensitivity-labels-where-did-they-go"></a>Перед настройкой меток конфиденциальности я развернул шаблоны защиты. Куда они делись?

Определяемые администратором [шаблоны защиты](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) скрываются из пользовательского интерфейса Office, когда включаются метки конфиденциальности, так как они являются избыточными при применении меток конфиденциальности, в которых включено шифрование. 

## <a name="can-a-file-or-email-have-more-than-one-classification"></a>Может ли файл или сообщение электронной почты иметь несколько классификаций?

Пользователь может одновременно выбрать только одну метку для каждого документа или сообщения электронной почты, что часто приводит к применению только одной классификации. Однако если пользователь выбирает подчиненную подметку, это приводит к одновременному применению двух меток: основной и вспомогательной. Путем использования подчиненных меток файлу могут присваиваться две категории, обозначающие родительскую/дочернюю связь для дополнительного уровня управления. 

Например, метка  **Конфиденциально**  может содержать подчиненные метки, такие как  **Юридическая**  и  **Финансовая**. К этим подчиненным меткам можно применять различную наглядную маркировку классификации и разные шаблоны управления правами. Пользователь не может выбрать саму метку  **Конфиденциально** ; доступна только одна из ее подчиненных меток, например  **Юридическая**. В итоге отображается набор меток  **Конфиденциально** / **Юридическая**. Метаданные для этого файла включают одно настраиваемое текстовое свойство для значения  **Конфиденциально**, одно настраиваемое текстовое свойство для значения  **Юридическая** и другое свойство, содержащее оба значения (**Конфиденциально Юридическая**). 

При использовании подчиненных меток не настраивайте наглядную маркировку, защиту и условия для основной метки. При использовании подчиненных уровней настраивайте эти параметры только для подчиненной метки. Если вы настроили эти параметры для основной и подчиненной метки, приоритет будут иметь параметры подчиненной метки.

## <a name="when-an-email-is-labeled-do-any-attachments-automatically-get-the-same-labeling"></a>Когда метка присваивается сообщению электронной почты, получают ли все вложения такую же метку автоматически?

Нет. Если метка присваивается сообщению электронной почты с вложениями, эти вложения не наследуют такую же метку. Вложения остаются без метки или сохраняют отдельно присвоенную метку. Однако если метка для сообщения электронной почты обеспечивает применение защиты, эта защита применяется к вложениям Office.

## <a name="additional-resources"></a>Дополнительные ресурсы

[Вопросы и ответы о классификации и присвоении меток в Azure Information Protection](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)<br>
[Применение меток конфиденциальности к документам и сообщениям электронной почты в Office](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)