---

title: Trainers
layout: event_noheader
permalink: /trainers/

---

# {{page.title}}
<br>

{% if site.data.trainings.size > 0 %}
{% assign trainings = site.data.trainings | sort: 'Title' %}
{% for training in trainings %}
{% for trainer in training.Trainers %}
<section id="{{trainer.TrainerId}}">
<hr>
<ul>
    <li>
        <div class="training-header">
            <div class="training-container no-margin">
                <div class="training-image" style="background-image:url('{{trainer.Image}}');"></div>
                <div class="trainer-header">
                <h2>{{ trainer.Name }}</h2><br>
                    <div class="info-container">
                    <a href="mailto:{{trainer.Email}}">{{ trainer.Email }}</a><br>
                    <a href="https://www.twitter.com/{{trainer.Twitter}}">@{{ trainer.Twitter }}</a><br>
                    <strong>Class:</strong><a href="/trainings/#{{training.SectionId}}">{{ training.Title }}</a>
                    </div>
                </div>
            </div>
        </div>
    </li>
    <li class='bio-container'>{{trainer.Biography}}</li>
</ul>
</section>
{% endfor %}
{% endfor %}
{% endif %}
