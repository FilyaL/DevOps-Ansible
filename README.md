ТЗ: Написание Ansible скрипта для настройки openldap на Ubuntu LTS

Функии скрипта:
 1. устанавливает OpenLDAP сервер
 2. задаёт LDAP domain (example.com) и organization (ExampleOrg)
 3. задаёт администратора (cn=admin,dc=example,dc=com)
 4. добавляет 2 пользователя (user1, user2)
 5. добавляет 2 группы (group1, group2)

Файлы проекта:

playbook.yml — основной Ansible playbook
inventory.ini — inventory для запуска

Требования:

Ubuntu LTS
Ansible
Python 3

Комада для запуска скрипта:

ansible-playbook -i inventory.ini playbook.yml

Команда для проверки результата:

ldapsearch -x -LLL -D "cn=admin,dc=example,dc=com" -w AdminPass123 -b "dc=example,dc=com"