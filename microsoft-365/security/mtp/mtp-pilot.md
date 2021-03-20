---
title: Запуск пилотного проекта Microsoft 365 Defender
description: Запустите пилотный проект Microsoft 365 Defender в производстве, чтобы эффективно определить преимущества и принятие Microsoft 365 Defender.
keywords: Пилот microsoft Threat Protection, запуск пилотного проекта Microsoft Threat Protection, оценка microsoft Threat Protection в производстве, пилотный проект Microsoft Threat Protection, кибербезопасность, расширенные постоянные угрозы, безопасность предприятия, устройства, устройства, удостоверения, пользователи, данные, приложения, инциденты, автоматическое расследование и исправление, продвинутая охота
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c6c373d084c7f7cf12073c6402695af644944bad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910874"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>Запуск пилотного проекта Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender


Это руководство поможет вам запустить пилотный проект, предоставив указатели, чтобы убедиться, что у вас есть хорошо структурированный план, направляя вас с помощью функции имитации атаки, и, наконец, заключение пилота с ключом take-aways для вас, чтобы размышлять и документировать результаты.

![Этапы запуска пилотного проекта Microsoft 365 Defender](../../media/pilotphases.png)


Запуск пилотного проекта поможет эффективно определить преимущества принятия Microsoft 365 Defender. Прежде чем включить Microsoft 365 Defender в производственную среду и начать использовать кейсы, лучше спланировать определение задач, которые необходимо выполнить для пилотного проекта, и установить критерии успешности. 


## <a name="how-to-use-this-pilot-playbook"></a>Использование этой экспериментальной книги воспроизведения

В этом руководстве представлен обзор инструкций по пошаговой работы с Защитником Microsoft 365 и инструкций по настройкам пилотного проекта. 

Microsoft 365 Defender — это единый пакет защиты предприятия до и после нарушения, который в основном координирует защиту, обнаружение, предотвращение, расследование и ответные действия между конечными точками, удостоверениями, электронной почтой и приложениями для обеспечения комплексной защиты от сложных атак. Это делается путем объединения и оркестровки следующих возможностей в единое решение безопасности:
  - Microsoft Defender для конечной точки — новое имя для расширенных угроз (конечные точки) для Microsoft Defender Advanced Threat Protection (конечные точки)
  - Microsoft Defender для Office 365 — новое имя ATP Office 365 (электронная почта) 
  - Microsoft Defender for Identity — новое имя для Azure ATP (удостоверение) 
  - Microsoft Cloud App Security (apps)

![Решение of_Microsoft 365 Defender для пользователей, Microsoft Defender for Identity, для конечных точек Microsoft Defender для конечной точки, для облачных приложений, microsoft Cloud App Security и для данных, Microsoft Defender для Office 365](../../media/mtp/m365pillars.png)

С интегрированным решением Microsoft 365 Defender специалисты по безопасности могут сшить сигналы угрозы, которые получают Microsoft Defender для конечной точки, Microsoft Defender для Office 365, Microsoft Defender for Identity и Microsoft Cloud App Security, а также определить всю область и влияние угрозы, как она попала в среду, на что она влияет и как она в настоящее время влияет на организацию. Microsoft 365 Defender принимает автоматические меры для предотвращения или остановки атаки и самостоятельного заживления затронутых почтовых ящиков, конечных точек и удостоверений пользователей. Подробные сведения см. [в обзоре Защитника Microsoft 365.](./microsoft-threat-protection.md)



Следующая временная шкала выборки зависит от написания нужных ресурсов в вашей среде. Некоторым обнаружениям и рабочего процессам может потребоваться больше времени на обучение, чем другим.

![Пример временной шкалы при запуске пилотного проекта Microsoft 365 Defender](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>Чтобы получить оптимальные результаты, выполните пилотные инструкции как можно ближе.


### <a name="pilot-playbook-phases"></a>Пилотные этапы воспроизведения 

Пилот microsoft 365 Defender работает четыре этапа:

|Этап | Описание | 
|:-------|:-----|
| [Планирование](mtp-pilot-plan.md)<br> ~ 1 день| Узнайте, что необходимо учитывать перед запуском пилотного проекта Microsoft 365 Defender: <br><br>- Область <br> - Использование случаев <br>- Требования <br>- План тестирования <br> - Критерии успешности <br> - Система показателей 
| [Подготовка](mtp-evaluation.md) <br>~2 дня|  Чтобы настроить пилотную среду Microsoft 365 Defender, необходимо получить доступ к Центру безопасности Microsoft 365. Вы будете руководствоваться:<br><br>- Определите заинтересованных лиц и обратитесь за входом для пилота <br> - Соображения среды <br>- Доступ <br>- Установка Azure Active Directory <br> - Порядок конфигурации <br> - Зарегистриройся на microsoft 365 E5 Trial <br> - Настройка домена <br>- Назначение лицензий Microsoft 365 E5 <br> - Завершите мастер установки на портале|
| [Имитация атаки](mtp-pilot-simulate.md) <br>~2 дня| Чтобы смоделировать атаку, вы будете руководствоваться:<br><br>- Проверка требований к тестовой среде <br>- Запуск моделирования <br>- Расследование инцидента <br>- разрешить инцидент 
| [Закрытие и сводка](mtp-pilot-close.md) <br>~ 1 день| По завершении процесса вы будете руководствоваться:<br><br>- Перейдите через конечный вывод<br>- Презентуйте результаты заинтересованным лицам <br>- Предоставление обратной связи <br>- Предпринять следующие действия 

## <a name="next-step"></a>Следующий шаг
|[Этап планирования](mtp-pilot-plan.md) | Планирование пилотного проекта Microsoft 365 Defender 
|:-------|:-----|