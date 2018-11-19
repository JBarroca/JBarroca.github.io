---
layout: post
title:  "Trying out CSS preprocessors"
date:   2018-11-15 12:20:00 +0100
categories: Sass
---

I'm not a huge fan of styling webpages. There, I've said it. But that doesn't mean I don't want to learn how it's done! By doing this project, I've now tried using CSS preprocessors for the first time by using Jekyll's built-in support for [Sass](https://sass-lang.com/).

### Some discoveries along the way ###

The first noticeable gain in simplicity and flexibility was the use of variables. Unlike regular CSS, where one has to repeat font-stacks or RGB values each and every time one wants to refer to the same font / color, Sass allows us to store these values in variables and then refer to them throughout the stylesheets. Thus, one only has to change the value in the variable assignement statement and that change will reflect itself throughout the entire stylesheet. I used variables for font-stacks, text color, backgrounds and distance measurements.

The other feature one notices right from the start is the use of partials. Because the starting point for this Jekyll website was the default [Minima theme](https://github.com/jekyll/minima), its scss files were already organized into partials, i.e. several scss files, each with a specific set of style rules, which are not rendered themselves by Jekyll but are instead imported by the main `minima.scss` file via `@import` statements, which in turn is imported into the `main.scss` file. This file has a YAML front matter and is therefore rendered by Jekyll into a single `main.css` file in the static site, which will contain the generated CSS code from all the different scss files. After grasping this convoluted circuit the style rules navigate through until they are compiled to CSS code in the final file, this becomes really simple to use. Having different partial files allows us to separate different kinds of style rules into different files, thus improving readability and organization a lot.

Some other syntactic advantages of Sass became more and more apparent as I started editing the style rules more deeply. Using nesting and the parent selector `&` makes it much easier to both write and read style rules. The addition of single line comments `//` is also a nice tool to have when starting from preexisting scss files, to see the effects of commenting-out some style rule which isn't to clear at first sight. The use of inheritance between style rules via `@extend` is also very helpful to minimize code repetition and maintain coherence between related rules.

Finally, the use of functions and operators is also a huge step towards flexibility. For example, being able to refer to a color variable, use it as an argument to a `lighten()` function and thereby test different values of the site's brand color made it much easier to have a coherent style thoughout the whole website.

### Examples of changes I performed on the base theme via Sass ###

#### header ####
+ removed the solid borders of the base theme.
+ used `@extends` to create a new header-specific wrapper class which inherited from the general wrapper class.
+ changed the header's color and typographic formatting.
+ added logo image with usual link to homepage.
+ used nested pseudo-selectors on `<span>` elements to change the color of the first letter of each word in the site title, as well as adding a media-query to decrease the title size and letter spacing on smaller screens.

#### body ####
+ removed padding between header, body and footer wrappers.
+ changed background colors, size and padding of the wrapper and added a box-shadow
+ added style rules for floating images.
+ changed the typographic formatting of title and heading elements.
+ used pseudo-selectors to decorate posts' date metadata in different ways depending on the website one is in.
+ added media queries to adjust the post list display on smaller screens.

#### footer ####
+ applied color formatting to both text and background in coherence with the changes done to the header.
+ used `@extends` to create a footer-specific wrapper class inheriting from the general wrapper class.

### Pros, cons and final thoughts ###

I don't have that much experience with 'normal' CSS styling, other than a few websites I built for an introductory webdesign course. But even so, having now tested styling with all these extra functionalities, I must say the gain in productivity and flexibility feels huge. It's much, much easier to have the styling code organized in different partial files, and all the syntactic improvements help a lot when creating or adjusting style rules.

There are, however, disadvantages. I've already mentioned one, which is the increased complexity of having to deal with many different files and manage different tools (Sass files, Jekyll, gem-based themes, etc.) in order to compile a single CSS file. Debugging is also made more difficult, because if an error is noted in the final compiled CSS file, there will be no direct mention to the error's source is the Sass files. Another disadvantage is worse performance due to compilation time, which can be relevant on larger projects or slower machines or the file sizes of the generated CSS files.

Just yet, my perspective is quite narrow to discuss the merits of precompiled CSS vs. standart CSS in 'real-world' projects, but I must say that these extra functionalities have been a pleasant surprise. I don't think I would welcome back the restrictions of 'normal' CSS now that I have seen the possibilities Sass has to offer. We'll see.