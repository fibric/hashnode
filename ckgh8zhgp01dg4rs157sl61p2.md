## How I created Polis - a theme for Nova

How I came to create my own theme [Nova](https://nova.app).

> A color scheme that is easy on the eyes by day and night.

### Nova.app by Panic - creators of Firewatch (game), Transmit (FTP), and Coda (editor)

Not too long ago, Panic introduced Nova that follows Coda but is not a new infusion; instead, it is an entirely new developed editor.

![Nova.app welcome screen](https://cdn.hashnode.com/res/hashnode/image/upload/v1602940296388/jcFYv4ex1.gif)
Nova is a native macOS app, and as such, boots very quickly, almost as fast as Sublime Text. Nova is also very light on memory usage compatible with Sublime Text.

Nova looks promising, and after reading the documentation [Library](https://library.panic.com/nova/) and also briefly checked out the [Extension Library](https://docs.nova.app), I decided to give Nova a try.

Nova is fast, and it comes with a CLI tool and allows me to open files quickly, just like Sublime Text. The single window editor appears instantly. Scrolling through huge files feels buttery smooth.

The list of extensions is short, but someone releases a plugin I felt missing almost daily. I installed some of the available themes to check how themes affect the editor and its performance when scrolling through large files.

Soon I noticed that even Nova's themes often have a weakness that I can't accept. Namely, using the warning color red for syntax highlighting. For me, red indicates invalid code and linting errors. I can't get enthusiastic about other themes in which keywords are colored reddish, for example. I reread the Extension Library and decided I want to create my own theme.

### Creating a Nova theme

![List of extension templates (Nova v1.2)](https://cdn.hashnode.com/res/hashnode/image/upload/v1603140773322/vur-hyeGa.png)

The list of extensions you can create is quite extensive for an application released only a short while ago. It's easy to get going with Actions, Themes, Sidebar, Keyboard bindings, Language definitions, Code Completion, and more. I picked Themes, and I was surprised by seeing an (almost) complete collection of CSS selectors ready to be modified.

#### (1) How to define a color palette

Defining a color palette is not easy – at least not for me.

There are several ways to get theme colors.

-   You can 'help yourself' by finding inspiration in other themes.
-   You can open a drawing program and copy their color palette.
-   You can have randomly generated colors displayed on various websites,
-   Or you can define the colors in a complicated way and get lucky in the process.

I tried all these possibilities, and in the end, luck was the deciding factor. I never noticed the colorful glowing LEDs; but, I also never before wanted to create a Nova theme.

A friend works as a digital designer. She regularly takes pictures of things to determine the photo's color value. I had an idea of how to do it too.

![Images show the glowing LEDs.](https://cdn.hashnode.com/res/hashnode/image/upload/v1602939874967/EZvWCdzLI.png)

I took some photos of the LEDs, also at different times of the day, and then I loaded all the pictures into the App [Spectrum](http://www.eigenlogik.com/spectrum/mac) by Eigenlogik.

![Spectrum app by Eigenlogik showing Polis color palette.](https://cdn.hashnode.com/res/hashnode/image/upload/v1603142694501/XYamSLo1e.png)

#### (2) Collection thoughts and stay focused

I had now invested enough time and made a series of decisions that still needed documenting.

![Polis mindmap outlining some of the key parts such as README.md content, colors, and themes for other applications](https://cdn.hashnode.com/res/hashnode/image/upload/v1602974327336/nkKyVPfzV.png)

As usual, I used Xmind and filled a mind map with everything that seemed important to me. It helped me concentrate on the important parts rather than on the nice-to-have parts.

#### (3) Stylus savior of the ... CSS

Nova supports only a subset of CSS and, unfortunately, no CSS variables. I found working with copy and paste not very productive and decided to go another way.

I went with [Stylus](https://stylus-lang.com) and started converting the CSS file. Nova's CSS file contains color values in the [HSB](https://learnui.design/blog/the-hsb-color-system-practicioners-primer.html) format, while Stylus only understands [HEX](https://en.wikipedia.org/wiki/RGB_color_model#Numeric_representations), [RGB(A)](https://en.wikipedia.org/wiki/RGB_color_model), and [HSL(A)](https://en.wikipedia.org/wiki/HSL_and_HSV).

After converting color formats, I created a source code example using the colors I just finished converting.

<div align="center">
<iframe style="border: 1px solid rgba(0, 0, 0, 0.1);" width="732" height="450" src="https://www.figma.com/embed?embed_host=share&url=https%3A%2F%2Fwww.figma.com%2Ffile%2FSIycd4x8o2cE57hLgMlBuv%2FPolis-Syntax%3Fnode-id%3D77%253A2" allowfullscreen></iframe>
</div>


#### (4) Working with the Syntax Inspector

Identifying CSS scopes is easy with Nova's Inspector.

![Using the CSS inspector to gather information about how to target the syntax element under the mouse cursor.](https://cdn.hashnode.com/res/hashnode/image/upload/v1603140293905/ffCBx9CJW.png)

The scopes are sorted by priority, and the scope shown at the top has overwritten all conflicting properties of the scopes below.

![For debugging, I use a white font on a red background.](https://cdn.hashnode.com/res/hashnode/image/upload/v1603140940443/QsLmrztVk.png)

For debugging, I use white font on a red background.

#### (5) Eureka effect

I didn't save the extracted colors in a swatch or palette, so I had to use Affinity Photo again. I couldn't find the exact places where I initially took the color values. A bit in anger and frustration about myself, I almost just carelessly 'clicked' on the LED colored areas in the pictures and copied the HSL format values to get it done.

I created a [Victor Mono](https://rubjo.github.io/victor-mono/) font powered code style example in Figma for testing purposes.

<div align="center">
<iframe style="border: 1px solid rgba(0, 0, 0, 0.1);" width="732" height="450" src="https://www.figma.com/embed?embed_host=share&url=https%3A%2F%2Fwww.figma.com%2Ffile%2FSIycd4x8o2cE57hLgMlBuv%2FPolis-Syntax%3Fnode-id%3D80%253A0" allowfullscreen></iframe>
</div>


On my MacBook, I have True Tone and Night Shift enabled. On my LG 34UM95, both are not available. Surprisingly, the colors were still legible on both displays. Even after several hours, I had no problems reading the colored code.

I had discovered a marketing-capable feature of my theme. **Easy on the eyes by day and night.**

#### (6) Finding a project name

Now I needed a name for the theme as I started to develop the impression that I could create an excellent theme. When I started creating this theme, my local project folder was called 'test-nova-theme'.

I have sunglasses with polarized lenses. When I wear these sunglasses, some colors change behind safety glass, shop windows, or computer monitors.

However, all colors remain identifiable and visible. I had the spontaneous idea to find a name that is maybe derived from 'polarized'.

I found many name generators on the Internet and fed each of them the word 'polarized'. I don't remember which page exactly displayed 'Polisis', but I knew it sounded quite good, but the last two letters bothered me, so I made it **Polis** — time to go public!

#### What is done so far

Polis has now reached a significant milestone, and coloring of all CSS selectors as specified in the theme template is done. 

Polis has a logo that I created in Figma.

<div align="center">
<iframe style="border: 1px solid rgba(0, 0, 0, 0.1);" width="732" height="450" src="https://www.figma.com/embed?embed_host=share&url=https%3A%2F%2Fwww.figma.com%2Ffile%2FOzVXye4kp1qNd90DWcVJzr%2FPolis-Logo%3Fnode-id%3D3%253A10" allowfullscreen></iframe>
</div>


Within the project, I defined two custom tasks and three steps.

![A short video showing the execution of custom tasks](https://cdn.hashnode.com/res/hashnode/image/upload/v1603142171969/9_qHBOgCe.gif)

- Tasks `Prepare Environment`
    - `Build`-Step - Installs Stylus if `yarn` and `node` is found. Tells you to install both `node` and `yarn` if not found.
- `Polis Theme`
    - `Clean`-step - Removes the `build` folder and `Polis.novaextension` folder if present
    - `Build`-step - Runs Stylus to generate `Polis.css` then creates `Polis.novaextension` folder and copies files as defined in project settings `Arguments` tab.

With the current release [v0.4.0](https://gitlab.com/fibric/polis-nova-theme/-/milestones/3), Every single color shade is mathematically generated. I only defined a few primary colors, and a color-function generates all the other colors.

```less
// helper function to turn colors dark/light or add alpha
polis( $color, $shade = 1.0, $alpha )
    $alpha = $shade if $shade is a 'unit'
    $c = get_color( $color, $colors )

    /* code shortened to focus on the important part */

    $c = l( de( $c, 50% ), 25 ) if 'light_50' in $shade
    $c = l( de( $c, 30% ), 15 ) if 'light_30' in $shade
    $c = l( de( $c, 10% ), 5 ) if 'light_10' in $shade
    $c = da( s( $c, 25% ), 50% ) if 'dark_50' in $shade
    $c = da( s( $c, 15% ), 30% ) if 'dark_30' in $shade
    $c = da( s( $c, 5% ), 10% ) if 'dark_10' in $shade
    return hsla( $c, $alpha )
```

#### What will be done

The next releases will target specific languages as Polis should support all of Nova's 27 integrated languages.

After releasing version v1.0, Polis will begin supporting language extensions - mainly [LSP](https://microsoft.github.io/language-server-protocol/) based.

#### What could be done

The `polis()` function could check if shading makes sense. Calling `white( 'light_90' )` makes no sense as every value above `light_50` is already pure white `#fff`. I plan to develop a color map generator which generates X dark shades and Y light shades. `light_90` and `dark_90` should never be `#fff` or `#000` for any other color than white for black.

I envision people fork Polis, replace `magenta` with say `violet`, generate their theme, and the generated color shades don't shift into `white` when calling, for example `magenta( 'light_90' )`.

### Improve Polis, fork it or make it your own

Give Polis a try and install it right away by clicking on the link below:

- nova://extension/?id=fibric.polis&name=Polis

I host the project source code on GitLab under the permissive MIT license. Fork Polis and help improve it or make it your own.

- https://gitlab.com/fibric/polis-nova-theme

### Polis derivatives

- Polis for iTerm2 already exists but needs fine-tuning because bold-text in green and yellow is not readable in some situations. The Starship prompt I'm using injects a darker blue for commands, which conflicts with the cursor guide color.
    ![Polis colors used in iTerm2](https://cdn.hashnode.com/res/hashnode/image/upload/v1603014997551/84IDer8Ha.png)
- Polis for Typora should also be no problem since Typora uses [CSS](http://theme.typora.io/doc/Write-Custom-Theme/) too.

### Kudos

Polis's `README.me` is heavily inspired by:

%[https://github.com/tjkohli/Nebula.novaextension]

— Kudos to TJ Kohli.

</br>

-----

```
Useless Markdown stats:
      190 Lines
     1564 Words
    11307 Characters
```