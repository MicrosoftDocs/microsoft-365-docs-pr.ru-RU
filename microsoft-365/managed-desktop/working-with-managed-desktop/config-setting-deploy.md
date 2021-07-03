---
title: Развертывание настраиваемых параметров в компьютеры, управляемые Майкрософт
description: Развертывание и отслеживание настраиваемых параметров в компьютеры, управляемые Майкрософт.
keywords: компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация, развертывание, поэтапное развертывание, настраиваемые параметры
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: aad4995f9c329b0fd8fcbcc8b1d13379453c2a76
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287805"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Развертывание и отслеживание настраиваемых параметров — компьютеры, управляемые Майкрософт

После внесения изменений в категории параметров и этапа развертывания страница состояния развертывания позволяет приступить к развертыванию параметров в группах. На этой странице показан сводка каждого настраиваемого параметра. Открыв категорию параметров, можно развернуть параметры для групп и отслеживать ход этих развертывание.

## <a name="deployment-statuses"></a>Состояния развертывания

Это состояния, которые вы увидите для каждого развертывания.

Status | Объяснение
--- | ---
Развертывание | Изменения ожидают развертывания в этой группе.
В процессе выполнения | Это изменение применяется к активным устройствам в этой группе.
Полностью | Изменение выполнено на всех активных устройствах в этой группе.
Не выполнено | Изменение не удалось на 10% активных устройств в группе, поэтому развертывание было остановлено.<br><br> Запрос на поддержку будет автоматически открыт с помощью компьютеры, управляемые Майкрософт для устранения неполадок развертывания.
Reverted | Изменение было отменено до последнего изменения, успешно развернутого во всех группах развертывания.

## <a name="deploy-changes"></a>Развертывание изменений

В этих инструкциях мы покажем фоновое изображение рабочего стола. После развертывания необходимо развернуть изменения со страницы состояния развертывания.

**Развертывание изменений**

1. Войдите в [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) и перейдите в меню **Devices**
2. Посмотрите раздел компьютеры, управляемые Майкрософт, выберите **Параметры**.
3. В **рабочей области состояния** развертывания выберите параметр, который необходимо развернуть, а затем выберите поэтапное развертывание для развертывания.
4. Выберите **Развертывание,** чтобы развернуть изменение в одной из групп развертывания.

> [!NOTE]
> Оранжевый значок предостережения указывает на то, что для развертывания доступна предыдущая группа, которая рекомендуется развертывать в порядке.

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

Рекомендуется развертывать группы развертывания в этом порядке: Test, First, Fast и Broad. 

Когда изменения завершались в каждой группе, состояние изменяется в **Complete**.

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a>Повторное развертывание

После развертывания изменения можно вернуться из состояния **Развертывания.** При повторном изменении, которое находится в **процессе или** **завершении,** текущее развертывание прекращается. Параметр вернется к последней версии, развернутой во всех группах.

В качестве примера покажем действия по повторному измене с помощью фоновой картинки desktop. 

**Чтобы отменить изменение**

1. Войдите в [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) и перейдите в меню **Devices**
2. Посмотрите раздел компьютеры, управляемые Майкрософт, выберите **Параметры**.
3. В **рабочей области состояния** развертывания выберите параметр, который необходимо вернуться, а затем выберите поэтапное развертывание для повторного развертывания.
4. В **статье Need to revert this change?,** select **Revert deployment**.

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a>Дополнительные ресурсы

- [Обзор настраиваемых параметров](config-setting-overview.md)
- [Справочник по настраиваемым параметрам](config-setting-ref.md) 
