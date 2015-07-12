**Deploy_ANSIBLE-CAPISTRANO**
============================

Установка Ansible:на Mac OS:
> brew install ansible

Установка Ansible на Ubuntu:

> sudo apt-get install software-properties-common sudo
> apt-add-repository ppa:ansible/ansible 
> sudo apt-get update sudo
> apt-get install ansible

----------
Проверка установленной версии Ansible: 
> ansible --version

Залейте себе настройки для деплоя
> git clone https://github.com/METALLURG/Deploy_ANSIBLE-CAPISTRANO.git

Замените эти заначения на ваши перед выполнением: 

 - YOU_NAME - имя вашего аккаунта на github.com/YOU_NAME/ 
 - YOU_NAME_APP - название вашего приложения
 - YOU_IP_SERVER - IP адресс вашего сервера

Теперь можно запустить установку. Вместо моего IP вставьте ваш:

> cd config/provision && ansible-playbook -iYOU_IP_SERVER, playbook.yml
> cd ../../

Добавим в Gemfile следующее:
> gem 'capistrano-rails' 
> gem 'capistrano-bundler' 
> gem 'capistrano-rbenv' 
> gem 'capistrano3-puma'

> group :production do 
> gem 'pg' 
> gem 'puma' 
> end

Выполним установку всех новых гемов и установку capistrano:
> bundle install 
> cap install

Теперь, когда установка выполнена, можно задеплоить само приложение
> cap production deploy

Чудесным образом должно всё заработать.