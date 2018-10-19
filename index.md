---
layout: workshop      # DON'T CHANGE THIS.
carpentry: "swc"    # what kind of Carpentry (must be either "lc" or "dc" or "swc")
venue: "Western Cape Carpentries Community Event"        # brief name of host site without address (e.g., "Euphoric State University")
address: "TBC, University of the Western Cape"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "za"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/ISO_639-1)
latlng: "-33.9335158,18.625764"       # decimal latitude and longitude of workshop venue (e.g., "41.7901128,-87.6007318" - use http://www.latlong.net/)
humandate: "16 November 2018"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "10:00  - 13:00"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2018-11-16      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2018-11-16        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Danielle Quinn", "Anelda van der Walt"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["TBC"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["anelda.vdwalt@gmail.com"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes:    http://pad.software-carpentry.org/2018-11-16-WC-CommunityEvent         # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}

{% comment %}
  HEADER

  Edit the values in the block above to be appropriate for your workshop.
  If the value is not 'true', 'false', 'null', or a number, please use
  double quotation marks around the value, unless specified otherwise.
  And run 'make workshop-check' *before* committing to make sure that changes are good.
{% endcomment %}

{% comment %}
  EVENTBRITE

  This block includes the Eventbrite registration widget if
  'eventbrite' has been set in the header.  You can delete it if you
  are not using Eventbrite, or leave it in, since it will not be
  displayed if the 'eventbrite' field in the header is not set.
{% endcomment %}
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

{% comment %}
  INTRODUCTION

  Edit the general explanatory paragraph below if you want to change
  the pitch.
{% endcomment %}
{% comment %}
  General description of Software and Data Carpentry.
{% endcomment %}
<div class="row">
  <div class="col-md-2" align="center">
    <a href="{{ site.swc_site }}"><img src="https://doit.missouri.edu/wp-content/uploads/2017/09/Software-Carpentry-Workshop-Icon-264x200.png" alt="Software Carpentry logo"
    /></a>
  </div>
  <div class="col-md-8">
    Since 1998,
    <a href="{{ site.swc_site }}">Software Carpentry</a>
    has been teaching researchers in science, engineering, medicine, and related disciplines
    the computing skills they need to get more done in less time and with less pain.
    Its volunteer instructors have run hundreds of events
    for thousands of learners in the past two and a half years.
  </div>
</div>
<br/>
<div class="row">
  <div class="col-md-2" align="center">
    <a href="{{ site.dc_site }}"><img src="{{ page.root }}/assets/img/dc-icon-black.svg" alt="Data Carpentry logo" /></a>
  </div>
  <div class="col-md-8">
    <a href="{{ site.dc_site }}">Data Carpentry</a> develops and teaches workshops on the fundamental data skills needed to conduct research.
    Its target audience is researchers who have little to no prior computational experience,
    and its lessons are domain specific,
    building on learners' existing knowledge to enable them to quickly apply skills learned to their own research.
  </div>
</div>
<br/>
<div class="row">
  <div class="col-md-2" align="center">
    <a href="{{ site.lc_site }}"><img src="{{ page.root }}/assets/img/lc-icon-black.png" alt="Library Carpentry logo" /></a>
  </div>
  <div class="col-md-8">
    <a href="{{ site.lc_site }}">Library Carpentry</a> is made by librarians to help librarians
    automate repetitive, boring, error-prone tasks;
    create, maintain and analyse sustainable and reusable data;
    work effectively with IT and systems colleagues;
    better understand the use of software in research;
    and much more.
    Library Carpentry was the winner of the 2016
    <a href="http://labs.bl.uk/British+Library+Labs+Awards">British Library Labs Teaching and Learning Award</a>.
  </div>
</div>


{% comment %}
  AUDIENCE

  Explain who your audience is.  (In particular, tell readers if the
  workshop is only open to people from a particular institution.
{% endcomment %}
{% if page.carpentry == "swc" %}
  {% include sc/who.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/who.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/who.html %}
{% endif %}

{% comment %}
  LOCATION

  This block displays the address and links to maps showing directions
  if the latitude and longitude of the workshop have been set.  You
  can use http://itouchmap.com/latlong.html to find the lat/long of an
  address.
{% endcomment %}
{% if page.latlng %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latlng | replace:',','&mlon='}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latlng}}">Google Maps</a>.
</p>
{% endif %}

{% comment %}
  DATE

  This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
  SPECIAL REQUIREMENTS

  Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong> Participants are required to abide by the 
  <a href="https://docs.carpentries.org/topic_folders/policies/code-of-conduct.html">Carpentries' Code of Conduct</a>.
</p>

{% comment %}
  ACCESSIBILITY

  Modify the block below if there are any barriers to accessibility or
  special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong> We are committed to making this event
  accessible to everybody.
  The workshop organizers will check that:
</p>
<ul>
  <li>Accessible restrooms are available.</li>
</ul>

<p>Please get in touch if you have any specific mobility or other needs.
</p>


{% comment %}
  CONTACT EMAIL ADDRESS

  Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact</strong>:
  Please email
  {% if page.email %}
    {% for email in page.email %}
      {% if forloop.last and page.email.size > 1 %}
        or
      {% else %}
        {% unless forloop.first %}
        ,
        {% endunless %}
      {% endif %}
      <a href='mailto:{{email}}'>{{email}}</a>
    {% endfor %}
  {% else %}
    to-be-announced
  {% endif %}
  for more information.
</p>

<hr/>

{% comment %}
  SCHEDULE

  Show the workshop's schedule.  Edit the items and times in the table
  to match your plans.  You may also want to change 'Day 1' and 'Day
  2' to be actual dates or days of the week.
{% endcomment %}
<h2 id="schedule">Schedule</h2>

{% comment %} DO NOT EDIT SURVEY LINKS {% endcomment %}



{% if page.carpentry == "swc" %}
  {% include sc/schedule.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/schedule.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/schedule.html %}
{% endif %}

{% comment %}
  Collaborative Notes

  If you want to use an Etherpad, go to

      http://pad.software-carpentry.org/YYYY-MM-DD-site

  where 'YYYY-MM-DD-site' is the identifier for your workshop,
  e.g., '2015-06-10-esu'.
{% endcomment %}
{% if page.collaborative_notes %}
<p id="collaborative_notes">
  We will use this <a href="{{page.collaborative_notes}}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
{% endif %}

<hr/>

