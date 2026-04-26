# Инструкция по управлению пользователями (Ansible)

Проект автоматизирует создание системных пользователей, настройку SSH-доступа и добавление в группу `docker`.

## 🔐 Работа с секретами (Ansible Vault)

Все пароли пользователей хранятся в зашифрованном виде в файле `roles/users_setup/vars/vault.yml`. Для работы используется существующий ключ расшифровки `.vault_pass`.

### Зашифровать файл (если он в открытом виде):

```bash
ansible-vault encrypt roles/users_setup/vars/vault.yml --vault-password-file .vault_pass
Редактировать данные в зашифрованном файле:
Bash
ansible-vault edit roles/users_setup/vars/vault.yml --vault-password-file .vault_pass
Посмотреть содержимое без редактирования:
Bash
ansible-vault view roles/users_setup/vars/vault.yml --vault-password-file .vault_pass
🚀 Запуск плейбука
Для применения настроек на серверах выполните:

Bash
ansible-playbook -i inventory/hosts.ini site.yml --vault-password-file .vault_pass
🛠 Полезные команды проверки
Проверка синтаксиса и стандартов (Linter):
Bash
ansible-lint site.yml
```
