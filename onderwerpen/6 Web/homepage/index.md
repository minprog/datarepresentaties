# Homepage

Build a simple profile page using HTML, CSS, and JavaScript.

> Je uitwerking voor deze opdracht wordt beoordeeld op de minmumeisen (1 punt) en hoe ver je daarna bent gegaan (maximaal 3 punten voor de hele opdracht).

## Background

The internet has enabled incredible things: we can use a search engine to research anything imaginable, communicate with friends and family members around the globe, play games, take courses, and so much more. But it turns out that nearly all pages we may visit are built on three core languages, each of which serves a slightly different purpose:

1. HTML, or _HyperText Markup Language_, which is used to describe the content of websites;
1. CSS, _Cascading Style Sheets_, which is used to describe the aesthetics of websites; and
1. JavaScript, which is used to make websites interactive and dynamic.

Create a simple profile page that introduces yourself, your favorite hobby or extracurricular, your interests (music, books, food) and/or your motivation to study programming.


## Getting Started

Execute `curl -OL https://github.com/minprog/webprogrammeren/raw/2020/Problems/2%20profile/profile.zip` to download a (compressed) ZIP file with this problem's distribution.

Open `index.html` in your web browser to see what it currently looks like.


## Specification

Implement in your `profile` directory a website that must:

*   Contain at least four different `.html` pages, at least one of which is `index.html` (the main page of your website), and it should be possible to get from any page on your website to any other page by following one or more hyperlinks.

*   `index.html` should include a profile picture, your name, and a short description of you and your interests. During the course we'll create a face book of sorts that combines all these pages. This face book will be shared among this year's cohort of students. Do note that if you feel uncomfortable sharing personal images or details, you are welcome to use an avatar picture instead, or to opt-out all together by mailing the staff at <help@mprog.nl>.

*   The other pages should contain information about you or anything that you might be interested in. Don't overdo it, a few paragraphs with a picture would be great, or an image gallery page, or some kind of Javascript demo (customized by yourself), just about anything will do!

*   Use at least ten (10) distinct HTML tags besides `<html>`, `<head>`, `<body>`, and `<title>`. Using some tag (e.g., `<p>`) multiple times still counts as just one (1) of those ten!

*   Integrate one or more features from Bootstrap into your site. Bootstrap is a popular library (that comes with lots of CSS classes and more) via which you can beautify your site. See [Bootstrap's documentation](https://getbootstrap.com/docs/4.5/) to get started. In particular, you might find some of [Bootstrap's components](https://getbootstrap.com/docs/4.5/components/) of interest. To add Bootstrap to your site, it suffices to include

        <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.5.3/dist/css/bootstrap.min.css" integrity="sha384-TX8t27EcRE3e/ihU7zmQxVncDAy5uIKz4rEkgIXeMed4M0jlfIDPvg6uqKI2xXr2" crossorigin="anonymous">
        <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js" integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous"></script>
        <script src="https://cdn.jsdelivr.net/npm/bootstrap@4.5.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ho+j7jyWK8fNQe+A12Hb8AhRq26LrZ/JpcUGGOn+Y7RsweNrtN/tE3MoK7ZeZDyx" crossorigin="anonymous"></script>

    in your pages' `<head>`, below which you can also include

        <link href="styles.css" rel="stylesheet">

    to link your own CSS.

*   Have at least one stylesheet file of your own creation, `styles.css`, which uses at least five (5) different CSS selectors (e.g. tag (`example`), class (`.example`), or ID (`#example`)), and within which you use a total of at least five (5) different CSS properties, such as `font-size`, or `margin`.

Optional:

*   Integrate one or more features of JavaScript into your site to make your site more interactive. For example, you can use JavaScript to add alerts, to have an effect at a recurring interval, or to add interactivity to buttons, dropdowns, or forms. Feel free to be creative!

*   Ensure that your site looks nice on browsers both on mobile devices as well as laptops and desktops.


## Testing

If you want to view how your site looks while you work on it, keep it open in your browser.

Recall also that by opening Developer Tools in Google Chrome, you can _simulate_ visiting your page on a mobile device by clicking the phone-shaped icon to the left of **Elements** in the developer tools window, or, once the Developer Tools tab has already been opened, by typing `Ctrl`+`Shift`+`M` on a PC or `Cmd`+`Shift`+`M` on a Mac, rather than needing to visit your site on a mobile device separately!


## Assessment

Your site's correctness will be assessed based on whether you meet the requirements of the specification as outlined above, and whether your HTML is well-formed and valid. To ensure that your pages are, you can use this [Markup Validation Service](https://validator.w3.org/#validate_by_input), copying and pasting your HTML directly into the provided text box. Take care to eliminate any warnings or errors suggested by the validator before submitting!

Consider also:

* whether the aesthetics of your site are such that it is intuitive and straightforward for a user to navigate;
* whether your CSS has been factored out into a separate CSS file(s); and
* whether you have avoided repetition and redundancy by "cascading" style properties from parent tags.

It is incumbent upon you to indent and align your HTML tags cleanly. Know also that you can create an HTML comment with:

        <!-- Comment goes here -->

but commenting your HTML code is not as imperative as it is when commenting code in, say, C or Python. You can also comment your CSS, in CSS files, with:

        /* Comment goes here */

## Hints

For fairly comprehensive guides on the languages introduced in this problem, check out these tutorials:

* [HTML](https://www.w3schools.com/html/)
* [CSS](https://www.w3schools.com/css/)
* [JavaScript](https://www.w3schools.com/js/)

## Vraag

Beschrijf twee problemen die je bent tegengekomen tijdens het maken van je Homepage en hoe je die problemen toen hebt opgelost (proces, met verwijzingen naar inhoud van de stof; het gaat niet om problemen met het begrijpen van de opdracht zelf, maar met de stof).

<textarea name="form[q1]" rows="8" required></textarea>
