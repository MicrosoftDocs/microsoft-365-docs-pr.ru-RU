---
title: Центр развертывания компьютеров
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 06/01/19
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Обзор центра развертывания компьютеров.
ms.openlocfilehash: 222a7a565a48a39aa7701ab4a737cf404ebaa548
ms.sourcegitcommit: dd0d99d2ff930cd1777d6704f4d88a70adc9ca74
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "35853178"
---
# <a name="desktop-deployment-center"></a>Центр развертывания компьютеров

<strong>Переход с Windows 7 на Windows 10 </strong>
<p>Расширенная поддержка Windows 7 завершается 14 января 2020 г. Обновление на месте с Windows 7 до Windows 10 — это самый быстрый способ развертывания. Вы можете <a href="https://docs.microsoft.com/ru-RU/microsoft-365/enterprise/windows-7-to-windows-10-upgrade-manual">обновить один компьютер</a> или <a href="https://docs.microsoft.com/ru-RU/microsoft-365/enterprise/windows-7-to-windows-10-upgrade-automated">тысячи компьютеров с помощью System Center Configuration Manager</a>. При обновлениях на месте вам не нужно беспокоиться о доставке приложений, переносе файлов, настраиваемых образах и включении облачных служб. Для обновления существующих компьютеров можно использовать имеющиеся инструменты и сосредоточиться на следующих шагах развертывания: </p>

<p>
<table>
     <tr>
     <td>
        <table border="0">
             <tr>
                  <td>
                  <img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-5.png" alt="Upgrade ConfigMgr" height="100" width="100" />
              </td>
              <td>
              <strong>Обновление Configuration Manager до Current Branch</strong>
                  </td>
                 </tr>
                </table>
    </td>
        <td>
        <table border="0">
             <tr>
                  <td>
                  <img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Device and App Readiness" height="100" width="100" />
              </td>
              <td>
              <strong>Проверка готовности устройств и приложений</strong>
                  </td>
                 </tr>
                </table>
    </td>
        <td>
        <table border="0">
             <tr>
                  <td>
                  <img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-9.png" alt="Upgrade Windows 7 PCs" height="100" width="100" />
              </td>
              <td>
              <strong>Обновление компьютеров с Windows 7 до Windows 10</strong>
                  </td>
                 </tr>
                </table>
    </td>
    </tr>
    <tr>
    <td>
Часть этапа проверки готовности каталогов и сети для организаций, использующих System Center Configuration Manager </td>
    <td>
Часть этапа проверки готовности устройств и приложений; справка доступна в службе Assure для классических приложений </td>
    <td>
Часть этапа развертывания ОС и обновления компонентов для компьютеров пользователей </td>
    </tr>
</table>
</p>

<img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-2.png" alt="Desktop Deployment Wheel" height="450" width="802" align="middle" style="background-color: #fff;" />

Выполните эти инструкции для планирования и выполнения крупномасштабного развертывания Windows 10 и Office 365 профессиональный плюс. Все приведенные ниже шаги являются частью общего процесса планирования и развертывания и обычно выполняются параллельно в рамках поэтапного развертывания. Загрузите бесплатный [комплект для анализа развертывания компьютеров и управления ими](https://aka.ms/howtoshiftlabs), чтобы попрактиковаться с инструментами, применяемыми в процессе развертывания. Также вы можете [обратиться за помощью](https://aka.ms/mddhelp) по развертыванию компьютеров к партнерам Майкрософт и службам FastTrack.

<br>

<table>
<tr class="even">
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-1.png" alt="Getting Started" height="144" width="144" /></td>
<td><p><strong><a href="https://aka.ms/mdd0">Начало работы. Руководство по пользователям, процессу и технологии</a></strong></p>
<p>Узнайте о преимуществах перехода на Windows 10 и Office 365 профессиональный плюс, значительных изменениях и рекомендациях по сравнению с предыдущими развертываниями, а также советах по обеспечению плавного перехода на Windows 10 и Office 365 профессиональный плюс.</p></td>
<td><a href="https://aka.ms/ddev0" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-13.png" alt="Getting Started" height="130" width="231" /></a></td>
</tr>
<tbody>
<tr class="odd">
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Step 1" height="144" width="144" /></td>
<td><p><strong><a href="https://aka.ms/mdd1">Шаг 1. Проверка готовности устройств и приложений</a></strong></p>
<p>Начните проект развертывания компьютера с инвентаризации устройств и приложений, определите приоритеты, протестируйте приоритетные приложения и устройства, а затем исправьте необходимые элементы, чтобы подготовиться к развертыванию.</p></td>
<td><a href="https://aka.ms/ddev1" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-14.png" alt="Step 1" height="130" width="231" /></a></td>
</tr>
<tr class="even">
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-5.png" alt="Step 2" height="144" width="144" /></td>
<td><p><strong><a href="https://aka.ms/mdd2">Шаг 2. Проверка готовности каталогов и сети</a></strong></p>
<p>Облачные службы в Office 365 профессиональный плюс и новые возможности развертывания, например Windows Autopilot, требуют Azure Active Directory. Сеть и подключение также важны для планирования при перемещении изображений, приложений, драйверов и соответствующих файлов Windows на ваш компьютер. Узнайте, как новые инструменты и возможности развертывания уменьшают и оптимизируют сетевой трафик.</p></td>
<td><a href="https://aka.ms/ddev2" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-15.png" alt="Step 2" height="130" width="231" /></a></td>
</tr>
<tr class="odd">
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-6.png" alt="Step 3" height="144" width="144" /></td>
<td><p><strong><a href="https://aka.ms/mdd3">Шаг 3. Доставка приложений Office и бизнес-приложений</a></strong></p>
<p>Убедитесь, что приложения упакованы и готовы к автоматической установке. Узнайте, какие новые возможности для настройки, установки и обновления приложений Office предлагает упаковка по технологии "нажми и работай" с использованием Office 365 профессиональный плюс.</p></td>
<td><a href="https://aka.ms/ddev3" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-16.png" alt="Step 3" height="130" width="231" /></a></td>
</tr>
<tr class="even">
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-7.png" alt="Step 4" height="144" width="144" /></td>
<td><p><strong><a href="https://aka.ms/mdd4">Шаг 4. Файлы и параметры пользователей</a></strong></p>
<p>При обновлении или замене компьютеров можно сэкономить время, автоматизировав резервное копирование и обновление состояния пользователя. Новые возможности облачной синхронизации файлов позволяют выполнять для каждого пользователя синхронизацию с OneDrive папок рабочего стола, документов и изображений для удобного доступа к файлам из новых экземпляров Windows.</p></td>
<td><a href="https://aka.ms/ddev4" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-17.png" alt="Step 4" height="130" width="231" /></a></td>
</tr>
<tr class="odd">
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-8.png" alt="Step 5" height="144" width="144" /></td>
<td><p><strong><a href="https://aka.ms/mdd5">Шаг 5. Вопросы по безопасности и соответствию требованиям</a></strong></p>
<p>Windows 10 и Office 365 профессиональный плюс предлагают новые способы защиты данных, устройств и пользователей, а также быстрого обнаружения и сдерживания угроз. Кроме того, вы научитесь реагировать на типичные проблемы, связанные с шифрованием дисков, работать с приложениями для защиты от вредоносных программ и политиками при переходе на Windows 10.</p></td>
<td><a href="https://aka.ms/ddev5" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-18.png" alt="Step 5" height="130" width="231" /></a></td>
</tr>
<tr class="even">
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-9.png" alt="Step 6" height="144" width="144" /></td>
<td><p><strong><a href="https://aka.ms/mdd6">Шаг 6. Обновления компонентов и развертывание ОС</a></strong></p>
<p>Развертывание на основе последовательности задач позволяет автоматизировать крупномасштабное поэтапное развертывание для начальной установки системы, обновления и замены компьютеров. Последовательность задач при обновлении также помогает не забывать об установке крупных полугодичных обновлений. Windows Autopilot — это недавнее обновление, оптимизирующее процесс переноса образов операционной системы на новые и существующие устройства.</p></td>
<td><a href="https://aka.ms/ddev6" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-19.png" alt="Step 6" height="130" width="231" /></a></td>
</tr>
<tr class="odd">
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-10.png" alt="Step 7" height="144" width="144" /></td>
<td><p><strong><a href="https://aka.ms/mdd7">Шаг 7. Обслуживание Windows и Office</a></strong></p>
<p>В Windows 10 и Office 365 профессиональный плюс постоянно добавляются новые функции с целью развития пользовательского интерфейса и средства безопасности в соответствии с последними инновациями. Узнайте, как обеспечивать актуальность с помощью полугодичных и ежемесячных обновлений, как работают новые модели обслуживания и какие у вас есть инструменты и возможности.</p></td>
<td><a href="https://aka.ms/ddev7" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-20.png" alt="Step 7" height="130" width="231" /></a></td>
</tr>
<tr class="even">
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-11.png" alt="Step 8" height="144" width="144" /></td>
<td><p><strong><a href="https://aka.ms/mdd8">Шаг 8. Информирование и обучение пользователей</a></strong></p>
<p>Убедитесь, что пользователи уведомлены о новых возможностях и способах работы при переходе на Windows 10 и Office 365 профессиональный плюс. Узнайте, как воспользоваться помощью по адаптации пользователей с применением Microsoft FastTrack, обучающими материалами, шаблонами для общения, а также новыми способами отслеживать принятие и использование продуктов пользователями.</p></td>
<td><a href="https://aka.ms/ddev8" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-21.png" alt="Step 8" height="130" width="231" /></a></td>
</tr>
<tr class="odd">
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-12.png" alt="Value Discovery and Business Case" height="144" width="144" /></td>
<td><p><strong><a href="https://transform.microsoft.com" target="_blank">Обеспечение поддержки руководителей: определение ценности и экономическое обоснование</a></strong></p>
<p>Если вы изучили развертывание, оценили готовность приложения и устройства, подготовили план развертывания и начали процесс развертывания, но не имеете поддержки и необходимых ресурсов от руководства для соблюдения сроков развертывания, вам могут помочь программы Business Value корпорации Майкрософт. Узнайте, как выполнить экономическое обоснование для перехода на Windows 10 и Office 365 профессиональный плюс и привлечь сотрудников к проекту.</p></td>
<td><a href="https://transform.microsoft.com" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-22.png" alt="Value Discovery and Business Case" height="130" width="231" /></td>
</tr>
</tbody>
</table>
