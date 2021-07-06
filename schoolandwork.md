---
permalink: /schoolandwork
---
<div>
	<div class="resume section">
		<h2 class="sectiontitle">Resume</h2>
		<p class="sectioninfo">If you want to see my resume, click here:<br><br></p>
		<a style="grid-column: 3 / span 3; text-align: center;" href="/resume.pdf">resume</a>
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
	<div class="coursework section">
		<h2 class="sectiontitle">Coursework</h2>
		<p class="sectioninfo">These are the courses I've taken at UCLA that are relevant to software engineering.</p>
		<button id="allbutton" onclick="expand(this.innerText)">Expand All</button>
		{% for course in site.data.coursework %}
			<div class="col3 courseworkcard">
				<h3 class="cardname">{{ course.num }}<br>{{ course.name }}</h3>
				<button class="openbutton cardbutton" id="{{ course.id }}" onclick="card(this.id)">&#709;</button>
				<p class="cardinfo" id="tech-{{ course.id }}">tech: {{ course.tech }}</p>
				<p class="cardinfo" id="topic-{{ course.id }}">topics: {{ course.topics }}</p>
				<button class="collapse cardbutton" id="collapse-{{ course.id }}" onclick="collapse(this.id)">&#94;</button>
			</div>
		{% endfor %}
	</div>
</div>

<script>
	function card(name) {
		console.log(name);
		var x = document.getElementsByClassName("openbutton");
		for (i = 0; i < x.length; i++) {
			x[i].style.display = "inline-block";
			document.getElementById("tech-" + x[i].id).style.display = "none";
			document.getElementById("topic-" + x[i].id).style.display = "none";
			document.getElementById("collapse-" + x[i].id).style.display = "none";
		}
		document.getElementById(name).style.display = "none";
		document.getElementById("tech-" + name).style.display = "block";
		document.getElementById("topic-" + name).style.display = "block";
		document.getElementById("collapse-" + name).style.display = "inline-block";
	}

	function collapse(buttonid) {
		var name = buttonid.substring(9);
		console.log(name);
		document.getElementById(name).style.display = "inline-block";
		document.getElementById("tech-" + name).style.display = "none";
		document.getElementById("topic-" + name).style.display = "none";
		document.getElementById("collapse-" + name).style.display = "none";
	}

	function expand(text) {
		if (text == "Expand All") {
			document.getElementById("allbutton").innerText = "Collapse All";
			var x = document.getElementsByClassName("openbutton");
			for (i = 0; i < x.length; i++) {
				x[i].style.display = "none";
				document.getElementById("tech-" + x[i].id).style.display = "block";
				document.getElementById("topic-" + x[i].id).style.display = "block";
				document.getElementById("collapse-" + x[i].id).style.display = "inline-block";
			}
		} else {
			document.getElementById("allbutton").innerText = "Expand All";
			var x = document.getElementsByClassName("openbutton");
			for (i = 0; i < x.length; i++) {
				x[i].style.display = "inline-block";
				document.getElementById("tech-" + x[i].id).style.display = "none";
				document.getElementById("topic-" + x[i].id).style.display = "none";
				document.getElementById("collapse-" + x[i].id).style.display = "none";
			}
		}
		// var x = document.getElementsByClassName("openbutton");
	}
</script>