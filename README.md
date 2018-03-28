# **RETO : DISTRIBUCIÓN DE SQUADS**

## **Descripción del reto**

Aprender en squads nos trae muchos beneficios, sin embargo, generar estos squads cada sprint es una tarea tediosa para las Training Managers. Creemos que esta distribución de squads puede ser más automática y así le facilitar la vida a las Training Managers. 

Es por eso que se solicitó rediseñar y modificar parte del flujo, creando una herramienta que redistribuya los squads de cada sprint, teniendo en cuenta distintas variables.

## **1. DESCUBRIMIENTO E INVESTIGACIÓN**
* Actualmente tenemos un producto de **Distribución de Squads** creado por las alumnas durante el 1er TalentFest-2018.

### **Planing**
* Teniendo 03 días  nuestro planing fue el siguiente:

[Link a Trello](https://trello.com/b/sTSWw4Hu/squads-laboratoria)

### **Entrevistas**
* Se realizó una entrevista con la TM de la Sede Lima **Alejandra**.

**Resumen de Entrevista**
- Editar el Nombre del Squad.
- Editar el Nombre del Jedi Master.
- Editar y ver Premios del Squad.
- Editar y ver premios de cada alumna.
- Ver squads de Sprints anteriores.

### **Variables**
  - % tech skills
  - % soft skills:
    - Comunicación eficaz
    - Manejo del tiempo
  - Nivel de inglés
  - Perfil(Ux-Designer/FE-Developer)
  - Que no hayan estado en un mismo squad antes.

### **Consideraciones**

Los squads son de 6 estudiantes, y su distribución debería incluir como mínimo:

  - 1 estudiante con nota tech mayor a 70%
  - 1 estudiante con comunicación eficaz mayor a 70%
  - 1 estudiante con nivel de inglés 2  o 3
  - 1 estudiante con nivel de inglés 0 o 1

### **Datos adicionales**

**A. Los niveles de inglés se miden así:**
  - 0: Sin conocimientos
  - 1: Básico
  - 2: Intermedio
  - 3: Avanzado

<!-- 
### **Conclusiones**
* Según lo que tenemos del *producto anterior*, más la *entrevista* realizada, más las *indicaciones* que debe tener el producto actual se ideó una **Plataforma de Distribución de Squads** teniendo en cuenta lo siguiente: -->



## **2. SÍNTESIS Y DEFINICIÓN**

### **Journey Map**
![jcm](https://user-images.githubusercontent.com/32301249/38036457-5edf84a0-326c-11e8-9ab8-f1dfe4f0ab37.png)

### **User Persona**
![userperson](https://user-images.githubusercontent.com/32301249/38040607-7a541dfa-3275-11e8-82dc-450fa6265b85.png)


### **Feature List**

**Plataforma Web de Organización de Squads**

**1. Home:**

    -  Fecha.
    - Nombre/número del sprint actual.
    - Sede de la Training Manager loggeada. 
    - Distribuir los squads para el sprint. 
    - Si es que ya hay sprints distribuidos del sprint anterior estos no serán ‘draggeables’.

**1.1 Home con organización:**

      - Boards tipo trello. 
      - MENSAJES: sobre los squads, este aparecerá en la parte superior del board. 
      - En cada board habrán cards que representen a las estudiantes (1 card por estudiante). 
    - La TM podrá mover una estudiante a otro squad. Al mover una estudiante a otro squad, la aplicación hará la verificación con ese nuevo squad y lanzará los mensajes de alerta necesarios, por ejemplo:
      - El número de personas del squad es 7 (este mensaje solo desaparecerá cuando la ™ haya movido a otra estudiante al squad del que provino la primera. 
      - Hay 2 estudiantes que ya han estado juntas antes. Estudiante 1 y 2. 
      - Hay 2 estudiantes con nivel de inglés mayor de 3. 
    - La ™ tendrá que aceptar los warnings para que estos desaparezcan. - - 
    Mientras haya warnings el botón de “Confirmar squads” estará desactivado.
    - Cuando la ™ confirme los squads, le aparecerá un mensaje de confirmación, avisándole que al aceptar le enviarán un email a las estudiantes.
    - Al confirmar: 
      - Se les envía un email a las estudiantes notificándoles qué su nuevo squad está confirmado. Para ello pueden usar el API de Sendgrid.
      - Se bloqueará la opción de “dragging” de los cards de los squads. 
      - Se guardará la data final de los squads en firabase o en un googlesheets
      - En el json de cada estudiante se guardarán los ids de las compañeras de su squad de este nuevo sprint.

**2. Mensajes**

    * Si haces ese cambio habrán 2 estudiantes con más de 70% en HSE
    * Si haces ese cambio no habrá ninguna estudiante con nivel de inglés 1 o 2
    * [“Los squads quedaron muy bien!“ , “estos squads la van a romper”, “Wow! Excelente manera de armar squads”]. ¿Lista para confirmarle los squads a las estudiantes? - Confirmar.


**Herramientas :**  
- Framework: Materialize
- Jquery
- React
- Firebase
- Css3
- Html5

## **3. IDEACIÓN**
### **Lo que existe**
![squads-1](https://user-images.githubusercontent.com/32301249/37995647-cf26942a-31da-11e8-9d75-590a425cef6b.png)

### **Nuestra Propuesta**
![Modelo prototipo 1](https://user-images.githubusercontent.com/32301249/37998411-21a1e98a-31e4-11e8-876b-de99d2ceff76.png)



## **4. PROTOTIPADO**
Se realizó un prototipo en figma y marvel se testeó 2 veces.

[Prototipo Alta fidelidad 1](https://marvelapp.com/3bc6eae)

[Prototipo Alta fidelidad 2](https://marvelapp.com/5084fe7)

## **5. TESTING**

* **Testing 1:**

  Usuario: Alejandra Ramírez(TM - Lima)

  Feedback:
  - Me gustan más 02 cards en la pantalla completa.
  - Prefiría otros colores.
  - Que sólo se vea el % de Soft y Tech Skills e Inglés.
  - Que no se vean los premios al inicio, sino yo poder editarlos.
  - Prefiero un lista desplegable para seleccionar los premios de cada alumna e igual con los premios de squads.

* **Testing 2:** 

  Usuario: Mariana Guerra(Talento y Cultura/Formación - Lima)

  Feedback:
  - Me parece mejor los cards horizontales porque me confunden mucho así en vertical.
  - Me gustaría ver cada squad con un color diferente.
  - Me gusta que se vea el % de soft y tech, e inglés. Mas no de comnuicación y manejo de tiempo.
  - Quisiera agregar la opción de dar una condición: "Juanita y Pepita que no estén juntas"

**Iteración:**

En base a los 02 testings anteriores se realizaron cambios modificándose y quedando el flujo de esta manera:

[PRODUCTO FINAL - Marvel](https://marvelapp.com/5084fe7)

[PRODUCTO FINAL - GH-PAGES]()

**PROYECTO REALIZADO POR:**

**Frontend:**
  - Lucero Hospina
  - Anny Gutierrez
  - Jennifer Carmen

**Ux-Designer:**
  - Silvia Puente de la Vega Vilca.
  - Molly Siesquén.
