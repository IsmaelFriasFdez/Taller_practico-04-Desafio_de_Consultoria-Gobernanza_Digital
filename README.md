
# **Desafío de Consultoría "Gobernanza Digital"**

## Bloque A: Análisis de Mercado y Selección  

En nuestro caso, para la empresa Aceites del Aljarafe S.L. hemos elegido Odoo Community ya que se adapta perfectamente a las necesidades y al perfil de la empresa  
Algunos de los motivos de esta elección son:

**1.-** La empresa cuenta con 25 empleados y necesita controlar los costes, al tener tan solo 25 empleados SAP tiene un coste demasiado elevado para una PYME

**2.-** Odoo permite modificar módulos fácilmente ya que cuenta con una estructura modular  y open source (código abierto).

**3.-** Odoo  es fácil de aprender y los empleados de la empresa se podrán adaptar fácilmente.

**4.-** Odoo tiene una gran escalabilidad a largo plazo por lo que podrán ir añadiendo apartados conforme crezca la empresa.

**El cálculo de TCO estimado a 3 años sería:**

**Licencias:** 0€ ya que Odoo es completamente gratuito.  
**Coste cada año:** 0€  
**Coste cada 3 años:** 0€

**Implantación:** podemos estimar 100 horas de desarrollo costando aproximadamente 40€ por hora.  
**Coste de implantación:** 4.000€

**Coste operativo:** se utilizará un servidor en nube (cloud) de AWS (Amazon Web Services) que tendrá un coste estimado de 80€ mensuales.  
**Coste cada año:** 960€  
**Coste cada 3 años:** 2.880€.

## Bloque B: Diseño de Seguridad RBAC  

| Acceso | Administrador | Comercial | Operario Almacen | Contable |
| :---- | :---- | :---- | :---- | :---- |
| **Clientes** | Editor | Solo clientes | Sin permiso | Lector |
| **Presupuesto** | Acceso total | Editor | Sin Permiso | Lector |
| **Factura** | Acceso total | Lector | Sin Permiso | Lector |
| **Inventario** | Acceso total | Lector | Acceso al stock | Lector |
| **Compras** | Acceso total | Sin permisos | Lector | Sin Permiso |
| **Configuración** | Acceso total | Sin permisos | Sin Permiso | Sin Permiso |

**Los beneficios que encontramos para esta implantación son:**

- Centralización de la información  
- Menos errores  
- Más seguridad  
- Automatizar procesos  
- Mejor control del inventario  
- Aumento de productividad  
- Se puede trabajar desde cualquier lugar desde el control remoto  
- Escalabilidad futura

## Bloque C: Documentación de Explotación  

1. El fragmento de *docker-compose.yml* necesario.

services:

  odoo:

    image: odoo:latest

    container\_name: odoo

    restart: unless-stopped

    depends\_on:

      \- db

    ports:

      \- "8200:8069"

    volumes:

      \- odoo\_data:/var/lib/odoo

      \- ./config:/etc/odoo

      \- ./addons:/mnt/extra-addons

    environment:

      \- HOST=db

      \- USER=odoo

      \- PASSWORD=odoo

    command: odoo \-d odoo \--db\_user=odoo \--db\_password=odoo \-i base

  db:

    image: postgres:latest

    container\_name: db

    restart: unless-stopped

    environment:

      \- POSTGRES\_USER=odoo

      \- POSTGRES\_PASSWORD=odoo

      \- POSTGRES\_DB=odoo

      \- PGDATA=/var/lib/postgresql/data/pgdata

    volumes:

      \- db\_data:/var/lib/postgresql/data

volumes:

  db\_data:

  odoo\_data:

2. El comando para realizar un backup de la base de datos PostgreSQL.

	Copia de seguridad de los datos de PostgreSQL utilizando un volcado SQL:

	pg\_dump dbname \> dumpfile

	Para restaurarlo:

	creadob dbname

psql dbname \< dumpfile

## Bibliografía

p. paloalto, "¿Qué es el principio del mínimo privilegio?", paloalto, . \[Online\]. Available: https://www.paloaltonetworks.es/cyberpedia/what-is-the-principle-of-least-privilege. \[Accessed: 05-12-2026\].

C. CLOUDFLARE, "¿Qué es el control de acceso basado en roles (RBAC)?", CLOUDFLARE, . \[Online\]. Available: https://www.cloudflare.com/es-es/learning/access-management/role-based-access-control-rbac/. \[Accessed: 05-12-2026\].

R. Red Hat, "8.3.4. Copia de seguridad de los datos de PostgreSQL", Red Hat, . \[Online\]. Available: https://docs.redhat.com/es/documentation/red\_hat\_enterprise\_linux/8/html/deploying\_different\_types\_of\_servers/backing-up-postgresql-data\_using-postgresql. \[Accessed: 05-12-2026\].  
