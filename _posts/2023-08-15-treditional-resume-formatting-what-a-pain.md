---
layout: post
tags: resume markdown
title:  "Treditional Resume Formatting what a pain."
---

Instead here is how you can keep your resume in markdown and generate a new copy when you need to update it.

Below is a formatting example a example resume for Peter Parker (Below).

```
# Peter Parker (Spider-Man)

**Objective:** To use my superhuman abilities and scientific knowledge to protect and serve the people of New York City.

Experience
---------

**Freelance photographer**
(2016-present)  
Utilized my photography skills to capture images of various events in the city.  
**Vigilante, Spider-Man**
(2016-present)  
  Utilized my superhuman abilities to fight crime and protect the citizens of New York City.  
**Member, Avengers**
(2019-present)  
 Contributed my unique abilities to the team's missions and operations.  

Skills
---------

- Superhuman strength, agility, and reflexes.  
- Expertise in chemistry, physics, and engineering.  
- Proficient in various forms of hand-to-hand combat and acrobatics.  

Education
---------
- High school diploma, Midtown School of Science and Technology  
- Bachelor's degree in science, Empire State University  

```

Using pandoc and some CSS it is possible to generate an html page using the above markdown. which you can them print into a PDF (or something similar).

`pandoc -o resume-output.html --css=resume-css-stylesheet.css resume.md -s -f markdown+smart --metadata pagetitle="Resume" --to=html5`

For my personal resume I am using css somewhat based on https://github.com/sdsawtelle/markdown-resume/blob/master/resume-css-stylesheet.css

I advise you to modify the CSS and make it your own rather then using it directly.

If you open up the html file in a web broswer (or something similar) you can them print into into a PDF.

{% include note.html content="Be careful as if you choose something that doesn't support JS the below example may not work." %}

If you want to take this a step further, try adding in line html and/or JS.

One example of this would be to append this to the example resume so that when you convert/print to a pdf it the date added.

So you will not have to guess as to which copy resume is newer.

```
<html>
<footer>
	<p>Resume last updated on:  <span id="date"></span></p>

    <script>
		var today = new Date();
		var date = today.toLocaleDateString();
		document.getElementById("date").innerHTML = date;
	</script>
</footer>
</html>
```

