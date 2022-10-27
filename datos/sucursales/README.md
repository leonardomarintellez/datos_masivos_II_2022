## Sucursales Bancarias


Los datos se encuentran en el siguiente vínculo

https://drive.google.com/drive/folders/1ZvpXE1wDw373ZIZLbXnMlGnHAlKXZ6wF?usp=sharing


Los archivos que usaremos son:
- catálogo municipios sepomex
- sucursales por municipio aaaamm


**Descripción archivos**


* 'catalogo municipios sepomex': Listado de municipios por Estado.

* 'sucursales por municipio aaaamm': Número de sucrsales de cada banco por municipio
	- cve_periodo: identificador de periodo compuesto por año y mes en formato aaaamm
	- cve_institucion: identificador de la institución 
	- desc_institucion: nombre del banco
	- cve_edo: clave del estado
	- desc_edo: descriptivo del estado
	- desc_mun: descriptivo del municipio
	- llave: concatenación de los descriptivos de estado y municipio

---

Los datos fueron recopilados de las siguientes 2 ligas:

[Sepomex](https://www.correosdemexico.gob.mx/SSLServicios/ConsultaCP/CodigoPostal_Exportar.aspx)

[Portafolio de Informacion CNBV](https://www.cnbv.gob.mx/Paginas/PortafolioDeInformacion.aspx)

Sección : Banca Múltiple > Información Operativa
Identificador del reporte: 040-4A-R5 Número de sucursales: por estado y municipio


**Descripción Insumos fuente**


* CPDescarga: 
	- d_codigo: Código Postal asentamiento
	- d_asenta: Nombre asentamiento
	- d tipo_asenta: Tipo de asentamiento (Catálogo SEPOMEX)
	- D_mnpio: Nombre Municipio (INEGI, Marzo 2013)
	- d_estado: Nombre Entidad (INEGI, Marzo 2013)
	- d_ciudad: Nombre Ciudad (Catálogo SEPOMEX)
	- d_CP: Código Postal de la Administración Postal que reparte al asentamiento
	- c_estado: Clave Entidad (INEGI, Marzo 2013)
	- c_oficina: Código Postal de la Administración Postal que reparte al asentamiento
	- c_CP: Campo Vacio
	- c tipo_asenta: Clave Tipo de asentamiento (Catálogo SEPOMEX)
	- c_mnpio: Clave Municipio (INEGI, Marzo 2013)
	- id asenta_cpcons: Identificador único del asentamiento (nivel municipal)
	- d_zona: Zona en la que se ubica el asentamiento (Urbano/Rural)
	- c cve_ciudad: Clave Ciudad (Catálogo SEPOMEX)


* 040-4A-R5: Información operativa de sucrsales de la Banca Múltiple.



**Transformación de los archivos**

- 040-4A-R5 --> sucursales por municipio aaaamm

- CPDescarga --> catálogo municipios sepomex

