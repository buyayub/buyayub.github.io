---

title: Project Ideas
excerpt: A list of personal project ideas that come to me, and that I wish I could do but don't have the time to do. 
layout: single
header: "/assets/posts/projectideas.jpg"

---

## 0. Introduction

NOTE: (This page has a lot of perspective shift as I'm converting this to first person perspective for a more passive voice; just a disclaimer)

A problem I frequently see with programming project ideas are the lack of useful ideas. Things you would actually want to make that would feel useful both to me and others, so I've made a list here of things I think would be useful.

This has FOSS in mind, as many of these ideas are implemented through proprietary software, but not yet through FOSS projects. It's an indicator of difficulty though, so beware.

## 1. UML ( HARD )

UML (Unified Modelling Language) is a graphical language used to describe software models, aimed primarily for systems architects, engineers, and so on to describe large software systems. 

It's overkill for smaller projects, but a useful map/blueprint for larger ones where you really need the organization and understanding, especially in a team.

Because it's fairly esoteric to programmers who think they're too cool for school, there isn't much stuff for it. At least not enough that a useful project can't be made.

Most of this probably requires a fair bit of knowledge on compiling. [The Dragon Book](https://suif.stanford.edu/dragonbook/) is what I think I'd need to figure most of this out. I've read a little on it before, enough to create my own parser, but I'd have to read it again more completely.

### Textual UML in C/C++

There are already textual representations of UML available, but they're either proprietary, made in Java, or are web apps.

I just want a simple `tex`-like program that can take textual UML, and convert it into a UML file (XMI file, XML format)

What is textual UML? It's a textual representation of UML, that gets turned into the normal graphical UML. It'd sort of be like what Verilog is for standard circuits diagrams.

I don't have to create a new one, as there are various forms. [PlantUML](https://plantuml.com/) is free, but it's one of the Java ones I talked about. [txtUML](http://txtuml.inf.elte.hu/wiki/doku.php) is also another one that uses Java, with documentation on the language.

Java is cumbersome to download, and I should be able to run a simple binary for this type of app. 

I want to use C for it, since it'd make it intepreter independant. There's already [one for Javascript](https://github.com/skanaar/nomnoml), but not one in Python as I can find it.

### Code to UML / UML to Code compiling

This one's more exciting, it takes software architecture defined in UML and converts it to actual source code, or vice-versa.

There's a lot of this already done for python, because of course, but you can do a lot yourself for your own preferred language.

## 2. Document Viewing/Editing on the Web 

You'd expect widespread support for this as well, but FOSS libraries are really lacking. You'll find plenty of proprietary document readers, but no (good) open source ones. 

The lack of support indicates that this is a very tedious problem to solve, enough that people won't do it for free, so I'd focus on a specific doc type with good libraries already behind it rather than create an all in one document reader.

### A worthwhile PDF Annotation Library for Javascript and React  (MEDIUM)

This one had me annoyed when I was researching possibilities for Monalect. You'd think someone somewhere would've programmed a worthwhile FOSS PDF annotation+reader, but no good one exists.

Javascript spoiled me enough, it seems. This one would be really useful to everyone if made.

Features you should include:

+ Highlighting
+ Notemaking
+ Saving the annotations to the annotation layer of the PDF

You can build off of PDF.js's viewer because it's technically under a free license, but they request you don't w/o significant modification, and they're saints for dealing with the PDF spec so I'd respect their wishes.

### Create a performant scrollable PDF viewer for Javascript and React (MEDIUM)

Web-workers, async, and lazy loading w/ pdf.js.

It should be for everyone to use. Again, pdf.js doesn't like their viewer being used for some reason. Or rather, they don't like it being used unmodified or reskinned, so if you can traverse the source code, which is pretty well documented, and build upon their base viewer with your own, then it should be an easy task all-in-all.

You can also use pdfium instead of pdf.js, which is google's SSR solution to pdf rendering on the web, but they have an experimental wasm build to look forward to and use for frontend programming.

## 3. Web Audio API 

There are a lot of underrated javascript APIs and libraries, especially when it comes to audio programming. Tone.js, and the Web Audio API can have you make your own suprisingly complicated and emulation-capable synthesizers for free.

You also have two other APIs that integrate well with them:

+ MIDI API - for all your MIDI integration needs (firefox has poor support for now)
+ Mediastream Recording APIs - can do audio recording

And plenty of more creative ways to integrate others.

These projects can also be ported to other languages rather easily. C++ has the VST SDK that audio programmers use to make professional synthesizers.

### Modular Synth Environment

Modular synthesis involves many modular synth parts that come together to create highly variable synthesizers.

In this project, you'd basically create a platform for it to work. Use Tone.js to save many headaches.

### Keyboard Bard

I've always wanted to see the keyboard as a musical instrument. Take inspiration from keyboard-only command apps like vi, and create a musical instrument that takes significant skill and complexity to operate. 

Musicians are very haughty about the ability for computer keyboards to play music, with their fancy pressure-sensitive keyboards. Prove them wrong.

Personally, I wouldn't try and simulate them and try to play to the strength of a computer keyboard. Various toggles, commands, modes, extra keys. 

You can play music in stream. Each key doesn't have to be assigned to a certain key, instead you can "toggle" the octave you want to play at. There should be a way to play at multiple octaves at the same time as well.

You should be able to do some chord fun. Macroing chords, would be really fun, automating certain progressions and intervals. You'd essentially be playing with a mixer and instrument all in one.

## 4. Political Apps

### What's my government doing?

People are sorely ignorant about government processes, but at the same time want to know more about their government. Create a way they can access government bills, get updates on their submissions and passings. Get summaries on those bills because nobody can read those things. 

You can expand to include electoral information. I'm Canadian, so you can represent parliament in graphics, see what MPs are doing, what they've done. What they've passed, and what they're promoting.

People want an easy and factual way to check out their government without having to deal with mass media.

Government websites usually do this already, but they do it ugly, and there's no mobile app.

The only downside is if it catches on and you get a bunch of people using your app to get information on the government, then a lot of groups become interested in you. I'd stick to pure apolitical representation of fact.

But eventually you'll have to deal with things like the Trump election scandal, and choosing either to show or not show the success of a candidate becomes a political choice.

Even deciding how to summarize bills will be a political decision that can be scrutinized.

Good luck!

## 5. Artistic Projects

### Memoir Site

I want to create a curated list of memoirs and people of history. Much like wikipedia's biographies, but including self-reports, quotes, etc. Basically collect as much information as you can on historical peoples.

One can imagine the privacy nightmare, so I'd stick with historical figures.

## 6. Literate Programming

The great Donald Knuth coined the term "literate programming" to denote a program which represents source code in a textual yet compiliable/interpretable manner. Basically imagine if your comp-sci textbook had executable code-blocks. A famous example of its implementation can be seen in Jupyter notebook and Mercury for python. 

### My Requirements

I'd love for the ability to create a pure frontend literate programming interface that is SSR and SPA/MPA independant. This is how it would work; the user simply creates a code block like this:

```
<pre id="blah" language="javascript" module="stuff.html#moduleName" ref="#specialfunction .listoffunctions">

do stuff

</pre>

```

Which executes on trigger, I guess after the modules load. I'd use local storage to make execution quicker, so you have a quick-to-access copy of the code, rather than having to fetch it. And I'd download it asynchronously, immediately at the start of web load if you do.

It must be purely frontend. The Javascript interprets/compiles it, which there are plenty of libraries for (Brython, JS-Interpreter, etc.).

My at-most minimum here is that it's able to execute with jekyll. Maybe instead of attributes, it would use meta imports. It'd be fun to create for my portfolio.

---

## Non-programming Ideas

### Worthwhile assembly guides and tutorials that include information on low-level architecture.

It's hard to find a low-level systems tutorial that's as rich as the textbook Computer Organization and Design by Patterson and Hennessey.

The only one I've found is nand2tetris, and while I enjoy it, it's not up to the complexity and depth of HTML guides of real software, like those of the linux documentation project, or the many GNU manuals and reference texts, something I'd really enjoy for low-level systems.

There's something nice about reading through something that has the capacity to explain everything about what you learn. The fact that x86 doesn't have something like that online is annoying to me. 

Many of the usual problems with learning assembly is that they also disclude explanations on low-level architecture, jumping straight into assembly.

It's a fair assumption to make, but I'd wager a lot of the people who want to learn assembly are higher level programmers who know little about low-level systems.

They can learn about low-level systems seperately, but there's no better way to interface with instruction architecture than by using assembly.

#### Building the Guide (or any)

You don't need to know much about assembly or low-level systems architecture (hear me out), you'll learn it as you develop the guide. You'll only have to heavily rely on good sources, and be wise about the information you choose so you don't propagate misinformation. 

Those are skills that pertain to journalism, not whatever it is you're teaching. And teachers who know a whole lot do not necessarily teach better.

You just have to understand what you're teaching. **Don't** write about *anything* you don't come to understand or comprehend. Neither come to any premature conclusions.

Coming at it from a blank slate will help you see it from a student's perspective. As you create it, write down questions you have of what confused you learning something, and what illuminated you, and use that in your guide.

As you go further into it, you can always come back and improve upon earlier sections with more accurate and useful info. Accept feedback but never reply to it. Don't make it edutainment, because edutainment loves to talk about things they don't understand or comprehend. Make it a serious and deep exploration of the topic you teach, doing deep research into the area.

Basically, you're tutoring as you learn. 

The beauty of HTML based guides is that they're destructured and refactorable by nature. You can explain a thing in many different ways, and link them together. Come back later, update it, etc. It's never static.

A few notes:

**Diagrams:** Humans like imagining things visually. The art of making beautiful diagrams to represent what you teach is essential to creating a good guide.

**Writing Style:** Ungendered, polite. If you want to go all out, you can use style guides.

**Accessible:** Other people will want to read your stuff too, so if you include things like abbreviation tags, make sure you add labels and what not. You'll have to go through the trouble of figuring out how accessibility works. If you want to go all out, you can check up on WCAG2.0 and MDN has a lot of good stuff on accessibility as well, but unless you're a company or organization, it's not a hard requirement.

**Draft then edit:** Never edit prematurely like you wouldn't optimize prematurely. Put a note somewhere as you write through of any changes you want to make, and come back to it when you edit it later.

