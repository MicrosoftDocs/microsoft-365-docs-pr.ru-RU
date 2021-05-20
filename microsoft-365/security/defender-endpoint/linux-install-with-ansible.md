---
title: Развертывание Microsoft Defender для конечной точки на Linux с помощью Ansible
ms.reviewer: ''
description: Описывает, как развернуть Microsoft Defender для конечной точки на Linux с помощью Ansible.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, Linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 36095f14ad3ed71c6a8d4707522c08c07ea738c4
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572733"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a>Развертывание Microsoft Defender для конечной точки на Linux с помощью Ansible

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

В этой статье описывается развертывание Defender для конечной точки на Linux с помощью Ansible. Успешное развертывание требует выполнения всех следующих задач:

- [Скачайте пакет onboarding](#download-the-onboarding-package)
- [Создание файлов YaML ansible](#create-ansible-yaml-files)
- [Развертывание](#deployment)
- [References](#references)

## <a name="prerequisites-and-system-requirements"></a>Необходимые условия и требования к системе

Перед началом работы см. в главной странице [Defender for Endpoint](microsoft-defender-endpoint-linux.md) на странице Linux описание необходимых условий и системных требований к текущей версии программного обеспечения.

Кроме того, для развертывания Ansible необходимо ознакомиться с задачами администрирования Ansible, настроить ansible и уметь развертывать книги и задачи. Ansible имеет множество способов выполнения одной и той же задачи. Эти инструкции предполагают доступность поддерживаемых модулей Ansible, таких как *apt* и *unarchive* для развертывания пакета. Ваша организация может использовать другой рабочий процесс. Дополнительные сведения можно найти в [документации Ansible.](https://docs.ansible.com/)

- Ansible необходимо установить по крайней мере на одном компьютере (Ansible вызывает этот узел управления).
- SSH необходимо настроить для учетной записи администратора между узлом управления и всеми управляемыми узлами (на устройствах, на которых будет установлен Защитник для конечной точки), и рекомендуется настраивать с помощью проверки подлинности общедоступных ключей.
- Следующее программное обеспечение должно быть установлено на всех управляемых узлах:
  - curl
  - python-apt

- Все управляемые узлы должны быть указаны в следующем формате в `/etc/ansible/hosts` соответствующем файле:

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- Тест Ping:

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a>Скачайте пакет onboarding

Скачайте бортовой пакет из Центр безопасности в Microsoft Defender:

1. В Центр безопасности в Microsoft Defender перейдите **к Параметры > управления устройствами > onboarding**.
2. В первом выпадаемом меню выберите **Linux Server** в качестве операционной системы. Во втором выпадаемом меню выберите предпочтительный инструмент управления конфигурацией **Linux** в качестве метода развертывания.
3. Выберите **пакет загрузки.** Сохраните файл как WindowsDefenderATPOnboardingPackage.zip.

    ![Центр безопасности в Microsoft Defender скриншот](images/atp-portal-onboarding-linux-2.png)

4. С командной подсказки убедитесь, что у вас есть файл. Извлечение содержимого архива:

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-ansible-yaml-files"></a>Создание файлов YaML ansible

Создайте подзадачу или файлы ролей, которые вносят вклад в книгу или задачу.

- Создайте задачу на `onboarding_setup.yml` борту:

    ```bash
    - name: Create MDATP directories
      file:
        path: /etc/opt/microsoft/mdatp/
        recurse: true
        state: directory
        mode: 0755
        owner: root
        group: root

    - name: Register mdatp_onboard.json
      stat:
        path: /etc/opt/microsoft/mdatp/mdatp_onboard.json
      register: mdatp_onboard

    - name: Extract WindowsDefenderATPOnboardingPackage.zip into /etc/opt/microsoft/mdatp
      unarchive:
        src: WindowsDefenderATPOnboardingPackage.zip
        dest: /etc/opt/microsoft/mdatp
        mode: 0600
        owner: root
        group: root
      when: not mdatp_onboard.stat.exists
    ```

- Добавьте репозиторий Defender для конечной точки и `add_apt_repo.yml` ключ:

    Защитник для конечной точки на Linux можно развернуть с одного из следующих каналов (обозначается ниже как *[канал]):* *инсайдеры-быстрые,* инсайдеры-медленные или *prod*.  Каждый из этих каналов соответствует репозиторию программного обеспечения Linux.

    Выбор канала определяет тип и частоту обновлений, предлагаемых вашему устройству. Устройства в *инсайдерской* быстрой являются первыми, которые получают обновления и новые функции, а затем инсайдеры *медленно* и, *наконец, prod*.

    Для предварительного просмотра новых функций и обеспечения ранней обратной связи рекомендуется настроить  некоторые устройства в вашем предприятии, чтобы использовать как инсайдеры-быстрые, так и *инсайдеры-медленные*.

    > [!WARNING]
    > Переключение канала после начальной установки требует повторной установки продукта. Чтобы переключить канал продукта: удалить существующий пакет, перенастройте устройство для использования нового канала и выполните действия в этом документе, чтобы установить пакет из нового расположения.

    Обратите внимание на рассылку и версию и определите ближайшую запись для нее в `https://packages.microsoft.com/config/` статье .

    В следующих командах *замените [distro]* *и [версию]* данными, которые вы идентифицировали.

    > [!NOTE]
    > В случае Oracle Linux *замените [дистрибутив]* на "rhel".

  ```bash
  - name: Add Microsoft APT key
    apt_key:
      keyserver: https://packages.microsoft.com/
      id: BC528686B50D79E339D3721CEB3E94ADBE1229CF
    when: ansible_os_family == "Debian"

  - name: Add Microsoft apt repository for MDATP
    apt_repository:
      repo: deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/[distro]/[version]/prod [channel] main
      update_cache: yes
      state: present
      filename: microsoft-[channel].list
    when: ansible_os_family == "Debian"

  - name: Add Microsoft DNF/YUM key
    rpm_key:
      state: present
      key: https://packages.microsoft.com/keys/microsoft.asc
    when: ansible_os_family == "RedHat"

  - name: Add  Microsoft yum repository for MDATP
    yum_repository:
      name: packages-microsoft-com-prod-[channel]
      description: Microsoft Defender for Endpoint
      file: microsoft-[channel]
      baseurl: https://packages.microsoft.com/[distro]/[version]/[channel]/
      gpgcheck: yes
      enabled: Yes
    when: ansible_os_family == "RedHat"
  ```

- Создание установок Ansible и удалить файлы YAML.

    - Для apt-дистрибутивов используйте следующий файл YAML:

        ```bash
        cat install_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_apt_repo.yml
            - name: Install MDATP
              apt:
                name: mdatp
                state: latest
                update_cache: yes
        ```

        ```bash
        cat uninstall_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              apt:
                name: mdatp
                state: absent
        ```

    - Для дистрибутивов на основе dnf используйте следующий файл YAML:

        ```bash
        cat install_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_yum_repo.yml
            - name: Install MDATP
              dnf:
                name: mdatp
                state: latest
                enablerepo: packages-microsoft-com-prod-[channel]
        ```

        ```bash
        cat uninstall_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              dnf:
                name: mdatp
                state: absent
        ```

## <a name="deployment"></a>Развертывание

Теперь запустите файлы задач в `/etc/ansible/playbooks/` соответствующем каталоге.

- Установка:

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> Когда продукт запускается в первый раз, он скачивает последние определения противомалярийных программ. В зависимости от подключения к Интернету это может занять до нескольких минут.

- Проверка/конфигурация:

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- Uninstallation:

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a>Проблемы с установкой журнала

Дополнительные [сведения о](linux-resources.md#log-installation-issues) том, как найти автоматически созданный журнал, созданный установщиком при ошибке, см. в дополнительных сведениях о проблемах установки журнала.

## <a name="operating-system-upgrades"></a>Обновления операционной системы

При обновлении операционной системы до новой основной версии необходимо сначала удалить Defender для конечной точки на Linux, установить обновление и, наконец, перенастроить Defender для конечной точки на Linux на вашем устройстве.

## <a name="references"></a>Ссылки

- [Добавление или удаление репозиториев YUM](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [Управление пакетами с помощью диспетчера пакетов dnf](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [Добавление и удаление репозиториев APT](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [Управление пакетами apt](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)

## <a name="see-also"></a>См. также
- [Исследование проблем работоспособности агента](health-status.md)
