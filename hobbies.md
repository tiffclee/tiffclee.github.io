---
permalink: /hobbies
---

<div class="design section">
	{% comment %}
	<h2>design</h2>
	{% for item in site.data.designs %}<img src="/assets/images/designs/{{ item.link }}" alt="{{ item.name }}" style="height: 300px;">
    	<p>{{ item.name }}</p>
	{% endfor %}
	{% endcomment %}
	<h2 class="sectiontitle">Designs</h2>
	<p class="sectioninfo">These are some designs I've done for my two clubs, ACM Design and 3D4E.<br>
	I collaborated on some, but they're all original designs.</p>
	<div class="slideshow">
		{% for design in site.data.designs %}
		<div class="slides">
			<img class="slideimage" src="/assets/images/designs/{{  design.link }}" alt="{{ design.name }}"><br><br>
			<p class="designtitle">{{ design.name }}</p><br><br>
			<p class="designbody">{{ design.description }}</p>
		</div>
		{% endfor %}
		<button class="prev" onclick="addIndex(-1)">&#10094;</button>
		<button class="next" onclick="addIndex(1)">&#10095;</button>
	</div>
</div>

<div class="photography section">
	<h2 class="sectiontitle">Photography</h2>
	<p class="sectioninfo">These are some pictures I took with my Nikon D5600 and Sony ZV-1 while I was traveling or with friends.</p>
	{% for photo in site.data.photos %}
		<img class="col2" src="/assets/images/photos/{{ photo.link }}" alt="{{ photo.name }}">
	{% endfor %}
</div>

<div class="calligraphy section">
	<h2 class="sectiontitle">Calligraphy</h2>
	<p class="sectioninfo">I learned calligraphy when I was a senior in HS and I've continued to use calligraphy while using my planner.</p>
	{% for pic in site.data.calligraphy %}
		<img class="col2" src="/assets/images/calligraphy/{{ pic.link }}" alt="{{ photo.name }}">
	{% endfor %}
</div>

<div class="printing section">
	<h2 class="sectiontitle">3D Printing</h2>
	<p class="sectioninfo">I was interested in 3D modeling and printing so I worked on a few small projects.</p>
	{% for pic in site.data.printing %}
		<img class="col4" src="/assets/images/3dprinting/{{ pic.link }}" alt="{{ pic.name }}">
	{% endfor %}
	<p class="description">To familiarize myself with Autodesk Fusion 360, I designed all the chess pieces.<br>Above are the king, queen, bishop, and knight.</p><br>
	<img class="col2" src="/assets/images/3dprinting/chessproject.png" alt="chess project">
	<img class="col2" src="/assets/images/3dprinting/checkersproject.jpg" alt="checkers project">
	<p class="description">This was the completed print and project of my 3D modeled chess pieces. The board was also designed and laser cut by me. The left picture is a chess set up and the right picture is a checkers set up with laser cut pieces.</p>
</div>

<div class="misc section">
	<h2 class="sectiontitle">Misc</h2>
	<p class="sectioninfo">These are other things I've done that don't necessarily fit in a category.</p>
	{% for pic in site.data.misc %}
		<img class="col3" src="/assets/images/misc/{{ pic.link }}" alt="{{ pic.name }}">
	{% endfor %}
	<p class="description">Most of the shirt designs I made were for my clubs in high school and college. I think it's pretty awesome that I've made shirts that 500+ people have worn!</p>
</div>

<div class="art section">
	<h2 class="sectiontitle">(art)</h2>
	<p class="sectioninfo">I'm trying to get better at art right now, but I am definitely not proud of the artwork yet. Maybe you'll se some soon :)</p>
</div>

<script>
var index = 1;
showIndex(index);

function addIndex(n) {
  showIndex(index += n);
}

function showIndex(n) {
	var i;
	var x = document.getElementsByClassName("slides");
	if (n > x.length) {
		index = 1;
	}
	if (n < 1) {
		index = x.length;
	}
	for (i = 0; i < x.length; i++) {
		x[i].style.display = "none";  
	}
	x[index-1].style.display = "inline-block";
}
</script>