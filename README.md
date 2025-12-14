# Instalar dependencia qifparse

1) Ver con qué usuario corre el servicio que buscas, en este caso odoo_nci

sudo systemctl show -p User -p Group odoo_nci


2) Entra como el usuario del servicio y activa el venv


Si el usuario es odoo_nci:


sudo -u odoo_nci -H bash

source /opt/odoo_nci/venv/bin/activate


Ahora instala:


pip install qifparse

python -c "import qifparse; print('qifparse OK')"

exit


Reinicia:


sudo systemctl restart odoo_nci

sudo systemctl status odoo_nci --no-pager
