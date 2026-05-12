# 

# **Desafío de Consultoría "Gobernanza Digital"**

**Alumnos:** Ismael Frías, Marcos Martínez, Jordi Bascón  
**Módulo:** Lenguaje de Marcas  
**Fecha de entrega:** 12/05/26

**Índice:**

[**Bloque A: Análisis de Mercado y Selección	3**](#bloque-a:-análisis-de-mercado-y-selección)

[**Bloque B: Diseño de Seguridad RBAC	3**](#bloque-b:-diseño-de-seguridad-rbac)

[**Bloque C: Documentación de Explotación	3**](#bloque-c:-documentación-de-explotación)

## Bloque A: Análisis de Mercado y Selección  {#bloque-a:-análisis-de-mercado-y-selección}

En nuestro caso, para la empresa Aceites del Aljarafe S.L. hemos elegido Odoo Community ya que se adapta perfectamente a las necesidades y al perfil de la empresa  
Algunos de los motivos de esta elección son:  
**1.-** La empresa cuenta con 25 empleados y necesita controlar los costes, al tener tan solo 25 empleados SAP tiene un coste demasiado elevado para una PYME  
**2.-** Odoo permite modificar módulos fácilmente ya que cuenta con una estructura modular  y open source (código abierto).  
**3.-** Odoo  es fácil de aprender y los empleados de la empresa se podrán adaptar fácilmente.  
**4.-** Odoo tiene una gran escalabilidad a largo plazo por lo que podrán ir añadiendo apartados conforme crezca la empresa.

**El cálculo de TCO estimado a 3 años sería:**

	**Licencias:** 0€ ya que Odoo es completamente gratuito.  
	Coste cada 3 años: 0€

**Implantación:** podemos estimar 100 horas de desarrollo costando aproximadamente 25€ por hora.  
Coste: 2.500€

**Coste operativo:** se utilizará un servidor en nube (cloud) de AWS (Amazon Web Services) que tendrá un coste estimado de 80€ mensuales.  
Coste cada 3 años: 2.880€.

## Bloque B: Diseño de Seguridad RBAC  {#bloque-b:-diseño-de-seguridad-rbac}

**RBAC(control de acceso en roles):** Cada usuario tendrá permisos según su función dentro de la empresa.

**Diseño de matriz:**   
**Administrador** tiene el acceso total al sistema ya sea los usuarios, configuracion, inve

## 

## Bloque C: Documentación de Explotación  {#bloque-c:-documentación-de-explotación}

1. El fragmento de *docker-compose.yml* necesario.

2. El comando para realizar un backup de la base de datos PostgreSQL.

	

[https://www.paloaltonetworks.es/cyberpedia/what-is-the-principle-of-least-privilege](https://www.paloaltonetworks.es/cyberpedia/what-is-the-principle-of-least-privilege)

[https://www.cloudflare.com/es-es/learning/access-management/role-based-access-control-rbac/](https://www.cloudflare.com/es-es/learning/access-management/role-based-access-control-rbac/)

