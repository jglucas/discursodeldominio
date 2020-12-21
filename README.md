# 

create table prematuro(
id integer,
nombre_bebe character varying,
fecha_de_ingreso date,
genero varchar,
primary key(id)
);

create table medicina(
id integer,
descripcion_medicina varchar,
unidad varchar,
presentacion varchar,
vacuna varchar,
fecha_de_dosis date,
dosis character varying,
primary key(id)
);


create table doctor(
id integer,
nombre_doc varchar,
cedula varchar,
especialidad character varying,
primary key (id)
);

create table consulta(
id integer,
nombre_pacientes varchar,
control_visitas_fechas date,
visita_1 varchar,
visita_2 varchar,
visita_3 varchar,
visita_4 varchar,
visita_5 varchar,
primary key (id)
);

create table cliente(
id integer,
cedula varchar,
nombre_pacientes varchar,
apellido varchar,
direccion varchar,
telefono character varying,
fecha_de_registro date,
primary key	(id)
);

insert into prematuro values
(0255,'samuel','11/03/2020','masculino'),
(0528,'issac','10/01/2020','masculino'),
(0782,'liam','14/02/2020','masculino'),
(0236,'camila','15/06/2020','femenino'),
(0896,'salome','16/08/2020','femenino');

insert into doctor values
(0255,'dr.samuel',1304800259,'pediatra'),
(0528,'dr.enrique',1305956211,'pediatra'),
(0782,'dr.miguel',1309632887,'pediatra'),
(0236,'dr.jose',1304800251,'pediatra'),
(0896,'dr.jimmy',1308598773,'pediatra');

insert into cliente values
(489,1306945628,'selena','zambrano','calle16av29',0985741259,'03/03/2020'),
(569,1316689742,'maria','vera','calle12av18',095622214,'05/01/2020'),
(751,1305520111,'belen','sanchez','calle11av10',0856412433,'07/02/2020'),
(165,1318927888,'belinda','rodriguez','calle24av12',0956622571,'02/06/2020'),
(395,1305522162,'roxana','velez','calle26av8',0936555987,'20/08/2020');

insert into consulta values
(489,'selena','03/03/2020','23_de_diciembre_de_2020','3_de_julio_de_2020','21_de_agosto_de_2020','9_de_septiembre_de_2020','5_de_octubre_de_2020'),
(569,'maria','05/01/2020','22_de_marzo_de_2020','5_de_junio_de_2020','20_de_septiembre_de_2020','6_de_octubre_de_2020','3_de_mayo_de_2020'),
(751,'belen','07/02/2020','25_de_junio_de_2020','8_de_marzo_de_2020','19_de_febrero_de_2020','8_de_febrero_de_2020','9_de_agosto_de_2020'),
(165,'belinda','02/06/2020','2_de_julio_de_2020','7_de_abril_de_2020','21_de_abril_de_2020','5_de_septiembre_de_2020','20_de_junio_de_2020'),
(395,'roxana','20/08/2020','19_de_septiembre_de_2020','10_de_julio_de_2020','21_de_julio_de_2020','1_de_mayo_de_2020','1_de_septiembre_de_2020');

insert into medicina values
(0255,'tetano','miligramos','frasco','hepatitis_b','23/07/2020','1dosis'),
(0528,'difteria','miligramos','frasco','hib','24/01/2020','3dosis'),
(0782,'pertussis','miligramos','frasco','pertussis','22/02/2020','5dosis'),
(0236,'hib','miligramos','tetano','frasco','25/06/2020','4dosis'),
(0896,'poliomielitis','miligramos','frasco','difteria','30/08/2020','2dosis');

select cliente.nombre_pacientes,visita_1,visita_2,visita_3,visita_4 from 
consulta inner join cliente
on cliente.id = consulta.id

select nombre_bebe,vacuna,dosis  from prematuro
inner join medicina
on prematuro.id = medicina.id

select nombre_doc,dosis from medicina
inner join doctor
on doctor.id =medicina.id

select count (*)
from medicina;
