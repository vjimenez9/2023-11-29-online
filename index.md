---
layout: workshop      # DON'T CHANGE THIS.
root: .               # DON'T CHANGE THIS EITHER.  (THANK YOU.)
venue: "FIXME"        # brief name of the institution that hosts the workshop without address (e.g., "Euphoric State University")
address: "online"     
country: "FIXME"      # "W3" for centrally organized online trainings or lowercase two-letter ISO country code such as "fr" of the host institution if applicable (see https://en.wikipedia.org/wiki/ISO_3166-1)
language: "spa"     
latitude: "45"        # decimal latitude of training venue (use https://www.latlong.net/)
longitude: "-1"       # decimal longitude of the training venue (use https://www.latlong.net)
humandate: "Nov 11-Dec 8, 2023"
humantime: "FIXME"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: FIXME      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: FIXME        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Verónica Jiménez Jacinto", "Heladia Salgado", "Paula Pappalardo", "Macarena Quiroga"] 
helper: ["FIXME"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
contact: ["macarenasolquiroga@gmail.com"]
etherpad:             # optional: URL for the workshop Etherpad if there is one
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

<!-- See instructions in the comments below for how to edit specific sections of this workshop template. -->

<!--
  HEADER

  Edit the values in the block above to be appropriate for your workshop.
  If the value is not 'true', 'false', 'null', or a number, please use
  double quotation marks around the value, unless specified otherwise.
  And run 'tools/check' *before* committing to make sure that changes are good.
-->

<!--
  EVENTBRITE

  This block includes the Eventbrite registration widget if
  'eventbrite' has been set in the header.  You can delete it if you
  are not using Eventbrite, or leave it in, since it will not be
  displayed if the 'eventbrite' field in the header is not set.
-->
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="248px"
  scrolling="auto">
</iframe>
{% endif %}

<h2 id="general">General Information</h2>

<!--
  INTRODUCTION

  Edit the general explanatory paragraph below if you want to change
  the pitch.
-->

<p>
<a href="{{ site.carpentries_site }}">The Carpentries</a> es una comunidad de práctica centrada en la enseñanza de fundamentos
   habilidades de código y ciencia de datos a investigadores de todo el mundo. Este evento de formación de instructores
   está diseñado para preparar a los aprendices para certificarse y participar como Instructores de Carpentries. Sin embargo, gran parte de nuestro plan de estudios se centra en principios educativos que pueden aplicarse en una amplia variedad de contextos. También damos la bienvenida a los participantes que no planean
   certificarse pero simplemente desea convertirse en mejores profesores.
</p>

<p>El Entrenamiento de Instructores de Carpentries tiene los siguientes objetivos:</p>

* Presentar las prácticas de enseñanza basadas en evidencia.
* Enseñar cómo crear un ambiente positivo para los alumnos en sus talleres.
* Brindar oportunidades de práctica y desarrollo de sus habilidades de enseñanza.
* Ayudar en la integración en la comunidad de Carpinterías.
* Preparar para utilizar estas habilidades didácticas en el dictado de talleres de Carpintería.

<p> Debido a que tenemos un tiempo limitado, algunas cosas están más allá del alcance de esta capacitación. No estaremos aprendiendo:</p>

* Cómo programar en R o Python, usar Git o SQL, o cualquiera de los otros temas que se enseñan en <a href="{{ site.dc_site }}">Data Carpentry</a>,
   <a href="{{ site.lc_site }}">Library Carpentry</a>, o
   Talleres de <a href="{{ site.swc_site }}">Software Capernetry</a>.
* Cómo crear tus propias lecciones desde cero (aunque tendrás un buen comienzo en los principios detrás de ese tipo de trabajo si te inspiras a aprender más).


<p>
Los eventos de formación de instructores son prácticos en todo momento: lecciones breves se alternan con ejercicios prácticos individuales y en grupo, incluidas sesiones de enseñanza práctica.
Este evento de formación de instructores es el primer paso hacia la certificación como Instructor de Carpentries. Para obtener más detalles sobre los otros 3 pasos, consulte la página <a href="{{ site.training_site }}/checkout.html">Instrucciones de Checkout</a>.
Para obtener más información, consulte nuestro <a href="{{ site.training_site }}">Plan de estudios de formación de instructores</a>.
</p>

<h3>Código de Conducta</h3>

Todos los participantes deben atenerse al <a href="{{
site.swc_site }}/conduct/">Código de Conducta</a> de Carpentries.



{% assign begin_address = page.address | slice: 0, 4 | downcase  %}
{% if page.address == "online" %}
{% assign online = "true_private" %}
{% elsif begin_address contains "http" %}
{% assign online = "true_public" %}
{% else %}
{% assign online = "false" %}
{% endif %}
<!--
  LOCATION

  This block displays the address and links to maps showing directions
  if the latitude and longitude of the workshop have been set.  You
  can use http://itouchmap.com/latlong.html to find the lat/long of an
  address.
  -->
<h3 id="where">Where</h3>


{% if online == "false" %}
<p id="venue">
  {{page.address}}.
  {% if page.latitude and page.longitude %}
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latitude}}&mlon={{page.longitude}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latitude}},{{page.longitude}}">Google Maps</a>.
  {% endif %}
</p>
{% elsif online == "true_public" %}
<p id="venue">
  En línea en <a href="{{page.address}}">{{page.address}}</a>.
   La capacitación se llevará a cabo utilizando la plataforma de videoconferencia Zoom. No es necesario iniciar sesión. Sin embargo, si no ha utilizado Zoom antes, haga clic en el enlace unos minutos antes, ya que puede solicitarle que instale la aplicación Zoom o la extensión del navegador. Debería haber recibido un enlace de conexión en el mismo correo electrónico que lo dirigió a este sitio web. Si encontró esta página por otro medio y no recibió el enlace de conexión, revise su carpeta de correo no deseado y envíe un correo electrónico a instructor.training@carpentries.org con sus capacitadores (detalles de contacto a continuación) en cc.
</p>
{% elsif online == "true_private" %}
<p id="venue">
  Este entrenamiento se llevará a cabo en línea.
  Los instructores le enviarán la información necesaria para conectarse a esta reunión.
</p>
{% endif %}

{% if online == "false" %}

<h4 id="accessibility">Accessibility</h4>

We are committed to making this workshop
accessible to everybody.
Workshop organisers have checked that:

<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>

Materials will be provided in advance of the workshop.
If we can help make learning easier for you in any way by
providing additional support, accommodations, or assistance,
please get in touch (using contact details below) and we will attempt to provide them.

{% endif %}

<h3>Cómo prepararse para la formación de instructores</h3>

Antes de su capacitación, visite nuestra página Preparación para la capacitación de instructores para obtener instrucciones completas. Un breve resumen de estas instrucciones es el siguiente:
<ol>
   <li>Complete nuestra encuesta previa a la capacitación. Recibirás un enlace personalizado para tu evento cuando recibas tu información de conexión.</li>
   <li>Seleccione una lección para usar en sesiones de práctica de enseñanza y prepare un segmento de 3 minutos, sin dedicar más de 20 a 30 minutos a prepararla.</li>
   <li>Por favor lea lo siguiente:</li>
     <ul>
       <li><a href="https://carpentries.github.io/instructor-training/files/papers/science-of-learning-2015.pdf">La ciencia del aprendizaje</a></li>
       <li><a href="https://carpentries.org/files/reports/2021%20Carpentries%20Annual%20Report_Final.pdf">Informe anual de Carpentries</a></li>
     </ul>
</ol>

<h3> Checkout: El proceso de certificación de instructores</h3>
Después del evento de capacitación, le pedimos que complete tres tareas de seguimiento para convertirse en un instructor certificado. Estos requisitos se detallan en nuestra
   <a href="{{ site.training_site }}/checkout.html">Instrucciones de checkout</a> y se analizarán en nuestra capacitación.
{% if online == "false" %}
<h3>What to Bring to an In-Person Event</h3>

Participants should bring a laptop that is Internet connected and has a
functioning browser. If you have it, a device for recording audio and video
(mobile phones and laptops are OK) is useful as we
are going to record one another teaching in pairs or threes. It does not have
to be high-quality, but it should be good enough that you can understand what
someone is saying.
{% endif %}

<h3>Asistencia y Cancelaciones</h3>
Los alumnos que pierdan más de 1 hora de la capacitación podrán ser marcados como ausentes. La certificación de instructor no se puede completar sin la asistencia completa a un evento de capacitación de instructores. Si inesperadamente necesita perderse más de 1 hora de su evento, comuníquese con sus Entrenadores (información de contacto a continuación).

Para eventos en los que la inscripción se realice a través de The Carpentries a través de Eventbrite, la cancelación se podrá realizar en Eventbrite hasta el inicio del evento. Los asientos cancelados no se pueden llenar después de la fecha límite de inscripción de 1 semana para estos eventos, por lo que le pedimos que cancele solo si es absolutamente necesario.

Más información sobre nuestra <a href="https://docs.carpentries.org/topic_folders/instructor_training/cancellations_and_makeups.html">política de cancelación y recuperación</a> está disponible en The Carpentries Handbook.

<h3 id="contact">Contacto</h3>
<p>
Por favor envíe un correo electrónico a
{% if page.contact %}
  {% for contact in page.contact %}
    {% if forloop.last and page.contact.size > 1 %}
      or
    {% else %}
      {% unless forloop.first %}
      ,
      {% endunless %}
    {% endif %}
    <a href='mailto:{{contact}}'>{{contact}}</a>
  {% endfor %}
{% else %}
  to-be-announced
{% endif %}
para más información.</p>
<hr/>

<h2 id="preparation" name="preparation">Preparación</h2>

<p>
  Por favor, lea las siguientes instrucciones antes del comienzo del taller:
</p>
<ol>
  <li><a href="{{ site.training_site }}/papers/science-of-learning-2015.pdf">The Science of Learning</a></li>
  <li><a href="https://carpentries.org/files/reports/2021%20Carpentries%20Annual%20Report_Final.pdf">The Carpentries 2021 Annual Report</a></li>
</ol>
<p>
  Por favor, también lea detenidamente <em>un</em> episodio de las lecciones de Carpentries listadas debajo, para poder realizar algunos ejercicios basados en ellas durante el primer día del taller. Un episodio es una página de una lección.
</p>

  <ul>
  <li><a href="{{ site.dc_site }}/lessons">Lecciones de Data Carpentry</a></li>
  <li><a href="{{ site.lc_site }}/lessons">Lecciones de Library Carpentry</a></li>
  <li><a href="{{ site.swc_site }}/lessons">Lecciones de Software Carpentry</a></li>
  </ul>


<hr/>

<h2 id="materials" name="materials">Materiales del Entrenamiento y Agenda</h2>

<p>
  Por favor, lea el <a href="{{ site.training_site }}/instructor/index.html#schedule">Curriculum del Entrenamiento de Instructores</a> para los materiales del curso y para una agenda del evento de 4 días.
</p>


<hr/>

<div class="row">
  <div class="col-md-6">
    <h3>Día 1</h3>
    <table class="table table-striped">
      <tr> <td>09:00</td> <td>Bienvenida </td> </tr>
      <tr> <td>09:30</td> <td>Building Skill with Practice </td> </tr>
      <tr> <td>10:30</td> <td>Break </td> </tr>
      <tr> <td>10:45</td> <td>Expertise and Instruction </td> </tr>
      <tr> <td>11:30</td> <td>Memory and Cognitive Load </td> </tr>
      <tr> <td>12:15</td> <td>Building Skill with Feedback </td> </tr>
      <tr> <td>12:35</td> <td>Final del día 1 </td> </tr>
    </table>
  </div>
  <div class="col-md-6">
    <h3>Día 2</h3>
    <table class="table table-striped">
      <tr> <td>13:35</td> <td>Motivation and Demotivation </td> </tr>
      <tr> <td>14:35</td> <td>Equity, Inclusion, and Accessibility </td> </tr>
      <tr> <td>15:15</td> <td>Break </td> </tr>
      <tr> <td>15:30</td> <td>Teaching Is a Skill </td> </tr>
      <tr> <td>16:30</td> <td>Wrap-up and Homework </td> </tr>
      <tr> <td>16:50</td> <td>Final del día 2</td> </tr>
    </table>
  </div>
  <div class="col-md-6">
    <h3>Día 3</h3>
    <table class="table table-striped">
      <tr> <td>09:00</td> <td>Welcome Back </td> </tr>
      <tr> <td>09:10</td> <td>Getting Started on Instructor Certification </td> </tr>
      <tr> <td>09:40</td> <td>The Carpentries: How We Operate </td> </tr>
      <tr> <td>10:25</td> <td>Break </td> </tr>
      <tr> <td>10:40</td> <td>Live Coding Is a Skill </td> </tr>
      <tr> <td>11:45</td> <td>Preparing to Teach </td> </tr>
      <tr> <td>12:30</td> <td>Final del día 3 </td> </tr>
    </table>
  </div>
  <div class="col-md-6">
    <h3>Día 4</h3>
    <table class="table table-striped">
      <tr> <td>13:30</td> <td>More Practice Live Coding </td> </tr>
      <tr> <td>14:15</td> <td>Working with Your Team</td> </tr>
      <tr> <td>15:25</td> <td>Break </td> </tr>
      <tr> <td>15:40</td> <td>Launches and Landings </td> </tr>
      <tr> <td>16:20</td> <td>Putting it Together </td> </tr>
      <tr> <td>16:40</td> <td>Wraping Up </td> </tr>
      <tr> <td>16:50</td> <td>Post-Training Survey </td> </tr>
      <tr> <td>17:05</td> <td>Final </td> </tr>
    </table>
  </div>
</div>




<!--
  ETHERPAD

  At `_misc/etherpad.txt` you will find a template for the etherpad.

  Display the Etherpad for the workshop.  You can set this up in
  advance or on the first day; either way, make sure you push changes
  to GitHub after you have its URL.  To create an Etherpad, go to

      http://pad.software-carpentry.org/YYYY-MM-DD-site

  where 'YYYY-MM-DD-site' is the identifier for your workshop,
  e.g., '2015-06-10-esu'.
-->
{% if page.etherpad %}
<hr/>

<p id="etherpad">
  <strong>Etherpad:</strong> <a href="{{page.etherpad}}">{{page.etherpad}}</a>.
  <br/>
  Usaremos este Etherpad para chatear, tomar notas y compartir URLs y fragmentos de código.
</p>

{% endif %}

<h2 id="pre_workshop_survey">Encuestas</h2>

<p>
  Antes del taller, por favor llene nuestra <a href="{{ site.instructor_pre_survey }}{{ site.github.project_title }}">encuesta pre-entrenamiento</a>.
</p>


<p>
  Luego del taller, por favor llene nuestra <a href="{{ site.instructor_post_survey }}{{ site.github.project_title }}">encuesta post-taller</a>.
</p>
