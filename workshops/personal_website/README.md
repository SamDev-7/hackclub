# Personal Website

Prophet Orpheus is here to guide you to making your own personal website.
It will look something like this:

![](img/final_screenshot.png)

Open the [live demo][final_live_demo]. See the [final code][final_code]. This
workshop will take around 45 minutes.

[final_live_demo]: https://prophetorpheus.github.io
[final_code]: examples/

**Table of contents:**

- [Part I: Setup](#part-i-setup)
- [Part II: The HTML File](#part-ii-the-html-file)
- [Part III: The CSS File](#part-iii-the-css-file)
- [Part IV: Publishing](#part-iv-publishing)
- [Part V: Sharing with the Community](#part-v-sharing-with-the-community)
- [Part VI: Hacking](#part-vi-hacking)

## Part I: Setup

We'll be setting up GitHub and Cloud9 in this section.

### 1) Sign Up for GitHub

GitHub is a website used by millions of programmers to collaborate on code.
We'll be using it to store and manage our code in Hack Club.

1. Open https://github.com/join in a new tab and create a new account
  - Choose a username you won't regret. Your actual name is a solid bet.
  - Use an email that you have access to; you'll need to access it
    to verify your account
  - Make sure to remember your username and password; you'll need them at every
    club meeting
  - When prompted to choose a plan, choose the "Free" plan
2. Verify your email by checking the inbox of the email you used
3. Open https://gh.hackclub.com in a new tab and star the project by clicking
   the button that looks like this on the top right: ![](img/github_star.png)

### 2) Create Your First GitHub Repository

GitHub allows us to host our website using a service called GitHub Pages. This
means that we can put the files of our website on GitHub and GitHub will give
us a URL that we can share with the world.  

1. Go to https://github.com
2. Click the green "+ New repository" button
3. Under "Repository name" write `USERNAME.github.io` except instead of writing
   `USERNAME`, write your actual GitHub username. So if your username is
   `alice1337`, write `alice1337.github.io`. You have to name your repository
   this in order for GitHub Pages to work correctly (we'll talk more about
   GitHub Pages later)

   > ![](img/gh_create_new_repo.png)

4. After you've double checked that your repository is correctly named, click
   the green "Create repository" button at the bottom.
5. Yay! You've created your very first repository! Now, copy the "HTTPS link"
   at the top. You will need this link for the next step.

   > ![](img/gh_copy_new_repo_link.png)

### 3) Sign Up for Cloud9

We'll be using a service called Cloud9 to write, save, and organize all of the
code we'll write in Hack Club.

1. In a new tab, open https://c9.io/
2. In the top right hand corner, click the button that looks like this:

   > ![](img/c9_gh_icon.png)

3. Click the green "Authorize application" button
4. If there is a popup that asks for your email, go ahead and enter it
5. Click the gray box that says "Create a new workspace"
6. Set the "Workspace name" to `projects`

   > ![](img/c9_name_workspace.png)

7. Make sure your workshop is set to "Public"
8. Under "Clone from Git or Mercurial URL", paste the HTTPS Link that
   you copied from your GitHub repository

   > ![](img/c9_clone_from_existing.png)

9. Make sure that you're using the "Custom" template
10. Without changing anything else, scroll to the bottom and click the
    green "Create Workspace" button

You should now see a screen looks something like this:

![](img/c9_ide_loaded.png)

> Note:
>
> If you're waiting for a while (more than 10 seconds) and the above screen
> still doesn't load, try the following:
>
> 1. Open https://c9.io
> 2. Click on the green "Open" button
> 3. You should now see the screen shown above. If not, ask your facilitator for
>    help

Congratulations, you've officially set up all of your coding tools for the
semester!

Now we're ready to start the website!

## Part II: The HTML File

### 1) Creating the HTML file

We'll start by making an `index.html` file. Right click the sidebar, select
"New File," and name the file `index.html`.

![](img/c9_create_index_html.gif)

Now we'll add the basic HTML template. Type the following into `index.html`:

```html
<!DOCTYPE html>
<html>
    <head>
    </head>
    <body>
    </body>
</html>
```

This structure is common to all HTML pages. In fact, you can take a look for
yourself! Just right click on any web page, including this one, and click "View
source" to see what's going on behind the scenes. You'll find each of these
elements on every page-- the doctype, and an HTML tag wrapped around a head and
body.

Before proceeding, we'll briefly go over what this template means. HTML works
by storing information inside tags. `<html></html>` is an example of one such
tag. Inside `<html></html>`, we've placed two other sets of tags:
`<head></head>` (which wraps around the "head") and `<body></body>` (which
wraps around the "body"). The body holds everything you would see in the actual
tab/window when you open the page, while the head conveys information about the
page to the browser.
`<!DOCTYPE html>` tells the browser what version of HTML to expect. Since it is
a language, HTML is constantly growing and updating, so there are multiple
versions. In our case, we are going to use HTML5, the latest version.

### 2) Previewing the Page

Let's check out what our HTML file looks like in Live Preview! First, we'll
save the file by clicking "File" → "Save" (or use the shortcut CTRL+s /
Command+s). Then, preview what the website looks like by clicking "Preview" →
"Live Preview File"

![](img/c9_live_preview.gif)

As you can see, the page is blank. This is because we haven't added anything to
the `body` section yet. Let's add some content!

### 3) Adding Text to the Body

As mentioned before, all information is wrapped in tags. Tags are predefined in
the language; think of them as the words in the language. For text, HTML
provides a number of tags to store text. We'll be using two of the most basic
ones: the h1 tag (`<h1>`) and the paragraph tag (`<p>`). The h1 tag is the
first in a series of heading tags, with `h1` being the highest ranking, and
`h6` being the lowest ranking. Just as with the other tags, you can place
information within the these tags by surrounding your content with an opening
and closing tag. Go ahead and add your name in a heading tag, and your
description in a paragraph tag, like so:

```html
<h1>Prophet Orpheus</h1>
<p>Coder Dino
Will code for food</p>
```

If your description was a few paragraphs, or had line breaks, you may have
noticed that one `<p></p>` doesn't quite cut it. Adding extra blank lines or
spaces between words in HTML does not change the spacing of the content. We can
solve this by placing each paragraph in its own `<p></p>`.

```html
<h1>Prophet Orpheus</h1>
<p>Coder Dino</p>
<p>Will code for food</p>
```

### 4) Adding Images to the Body

First, find an image you would like to include in your page. You can find
something on Google Images, Facebook, or Imgur. We'll need the source URL of
the image, so right click and select "Copy Image Address."

Images are included in HTML via the image tag, or `<img />`. The image tag has
an attribute called `src`, which will hold the _source_ URL of the image you
want to display. As an example, if I were to add this picture of Prophet
Orpheus, I would right click it and get the source URL, which in this case is
https://github.com/hackclub/dinosaurs/raw/master/smart_dinosaur_docs.png, and
put it in an image tag like so:

```
<img src="https://github.com/hackclub/dinosaurs/raw/master/smart_dinosaur_docs.png" />
```

You may have noticed that the image tag doesn't have a closing tag like
`<h1></h1>` or `<body></body>`. That's because it is a self-closing tag. In
fact, the `/` that comes right before `>` is how it does this.

Go ahead and add this into your `index.html` now. I put my picture before my
heading, and my code looks like this:

```html
<!DOCTYPE html>
<html>
    <head>
    </head>
    <body>
        <img src="https://github.com/hackclub/dinosaurs/raw/master/smart_dinosaur_docs.png"/>
        <h1>Prophet Orpheus</h1>
        <p>Coder Dino</p>
        <p>Will code for food</p>
    </body>
</html>
```

![](img/c9_index_html.png)

Now, your image may either be too big, or too small. Fret not. CSS will allow
you to manipulate the styling of your page in all your needs.

## Part III: The CSS File

So what is CSS? CSS, also known as Cascading Style Sheets, is a language used for styling the tags on a web page, otherwise known as elements.

While HTML oversees the content and the way it's structured, CSS is how you'll
specify how you'd like your content to look, and with it, you can set things
like colors, spacing, and more.

### 1) Creating the CSS File

We'll now make an `styles.css` file. Right click the sidebar, select "New
File," and name the file `styles.css`.

![](img/c9_create_styles_css.gif)

This is called an external style sheet because the CSS file is external to the
HTML file (i.e., the stylesheet is not inside the HTML file).

### 2) Linking the CSS file to the HTML file

Although we've created a CSS file, until we explicitly tell the HTML file to
use the CSS file, it will not use it. We must explicitly link the CSS file in
the HTML. We'll do this by typing the following into the head of `index.html`,
because the head is where we tell information about the page to the browser.

```html
<link rel="stylesheet" href="styles.css"/>
```

`<link />` is the link tag, which describes relationships between the current
file (in this case, `index.html`), and some external file (`styles.css`). In
our example, `rel="stylesheet"` specifies what this relationship is, i.e., that
`styles.css` is a stylesheet, and `href` (hypertext reference) specifies where
the file can be found (in this case, it's just the filename `styles.css`). The
link tag, similar to the image tag, is a self-closing tag, once again denoted
by the `/` that precedes the `>`.

Our HTML file now looks like so:

```html
<!DOCTYPE html>
<html>
    <head>
        <link rel="stylesheet" href="styles.css"/>
    </head>
    <body>
        <img src="https://github.com/hackclub/dinosaurs/raw/master/smart_dinosaur_docs.png"/>
        <h1>Prophet Orpheus</h1>
        <p>Coder Dino</p>
        <p>Will code for food</p>
    </body>
</html>
```

### 3) Adding Styles to the Stylesheet

Now that we've linked our CSS file to our HTML file, let's write some CSS to
resize the image.

Open up `styles.css` and type the following:

```
img {
    width: 200px;
}
```

A CSS stylesheet contains "rules," each of which consists of a selector, and
attributes and values within brackets, known as a "declaration block."

In our case, the selector is `img`. This merely selects all image tags (and
thus, all images). The rule then says to set the `width` (width) of all things
selected (in our case, all the images) to `200px`. `px` refers to pixels, which
are a unit of measurement on the screen. When this rule is applied, all the
images on our page will have a width of 200 pixels.

Next, we're going to center-align the entire body section.

We'll add

```
body {
    text-align: center;
}
```

As with resizing the image, this rule specifies that every `body` tag should
have a `text-align` attribute of `center`. This centers everything on our page
because all of the content in our HTML file is written inside the body tag.

Now let's change the font of our text. We'll add another attribute,
`font-family`, to the `body` rule, and set the value to `"Arial"`. Now it will
look like this:

```
body {
    text-align: center;
    font-family: "Arial";
}
```

Here is the transformation that your stylesheet will have undergone at the end of your endeavors:

![](img/c9_css_progression.gif)

Ah, it is truly beautiful to behold.

![](img/celebrate_harry_potter.gif)

## Part IV: Publishing

Right now we can only see our website on our own computer. Let's get a link
that we can share with anyone on the internet! We'll use the previously
mentioned GitHub Pages to do this.

1. Open the terminal by pressing `alt + t` on the keyboard at the same time.
   Type in the following commands:
  - `git add --all`
  - `git commit -m "Initial commit"`
  - `git push`
2. GitHub will now ask for your username and password.
  - Go ahead and enter the username and press the enter.
  - Enter the password and press enter. _The characters won't show up on
    the screen, but rest assured, they are still being typed._
3. Now try to view the website by going to `USERNAME.github.io`
   (make sure to replace `USERNAME` with our actual GitHub username)

#### Celebrate!

![](img/celebrate_rush_hour.gif)

Yes! Our website is now public on the internet!

## Part V: Sharing with the Community

Now that we have finished building a website

1. In a new tab, open and follow [these directions][slack] to signup for our
   Slack.
2. Join your club's channel by asking your club leader for the name of the
   channel, and post the link to your website in your club's channel.
3. Then, post the link to the
   [`#shipit`](https://starthackclub.slack.com/messages/shipit) channel to
   share it with everyone!

[slack]: ../../SLACK.md

## Part VI: Hacking

In this section, your challenge is to add additional features to your website
to make it your own!

Want to use a different font? Google!  
Want to add more pictures? Google!  
Want to add more text? Your entire life story? Background image? Background
music? Video? More pages? Google!

A good way to get ideas for what to add to your website is to look at other
people's websites. Find a website that you like, either from the below list or
from somewhere else on the internet, pick one aspect of that website that
you would like on your own website, and Google for ways to make it happen!

**Websites Made by Other Hack Club Hackers:**

- [Alyssa Sun](http://output.jsbin.com/fopoxe)
- [Rebecca Jourard](https://mnefertiti.github.io/personalwhale/)
- [John Cena's](http://nguyenbrian.github.io/john-cenas-personal-website/)
  (created by Brian Nguyen)
- [Jevin Sidhu](http://jevinsidhu.com/)
- [Harrison Shoebridge](https://harrison.tech/zero-cool/)
- [Chaoyi Zha](https://cydrobolt.com/)

**Websites Made by Professionals:**

- [Alice Lee](http://byalicelee.com)
- [Yaron Schoen](http://yaronschoen.com)
- [Roxanne Ravago](http://www.roxanneravago.com)
- [Pushkar Modi](http://pushkarmodi.com)

### Additional Resources

Here are some additional resources that you can use to learn more about HTML &
CSS.

- [HTML Dog](http://www.htmldog.com/guides/html/beginner/): _Very beginner
focused. If you're not sure which one to choose, pick this one._
- [Free Code Camp](http://www.freecodecamp.com/map): _Interactive and very
methodical._
- [Treehouse](https://teamtreehouse.com/library/html/introduction/): _Their
videos are extremely comprehensive and thorough._