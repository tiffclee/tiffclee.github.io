---
permalink: /schoolandwork
---
<div>
	<div class="resume">
		<h2>Resume</h2>
		If you want to see my resume, click here:<br><br>
		<a href="/resume.pdf">resume</a>
	</div>
	<div class="coding section">
		<h2 class="sectiontitle">Experience + Projects</h2>
		<p class="sectioninfo">Here are some projects I've done related to coding!</p><br><br>
		{% for project in site.data.projects %}
		<div class="col2 project">
			<img class="projectimage" src="/assets/images/projects/{{ project.link }}" alt="{{ project.name }}">
			<p>{{ project.name }}</p>
			<p>{{ project.from }} to {{ project.to }}</p>
			<p>tech: {{ project.tech }}</p>
			<p>info: {{ project.description }}</p>
		</div>
		{% endfor %}
	</div>
	<div class="coursework">
		<h2>Coursework</h2>
		These are the relevant courses I've taken at UCLA!
		{% for course in site.data.coursework %}
			<h3>{{ course.name }}</h3>
			<p>tech: {{ course.tech }}</p>
			<p>topics: {{ course.topics }}</p>
		{% endfor %}
	</div>
</div>