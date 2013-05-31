# SplitDropButton

SplitDropButton is a simple, easily stylable, split button dropdown jQuery plugin similar to those you can find on:

+ [twitter boostrap](http://twitter.github.io/bootstrap/components.html#buttonDropdowns)
+ [zurb foundation](http://foundation.zurb.com/docs/components/split-buttons.html)

Why another one then? Both the boostrap and foundation versions weren't easily stylable, there wasn't a good standalone verison, and I didn't want to include big chuncks of either framework just for that one simple widget.

## Demo

See it in action [here](#).

## Usage

#### HTML

    <div class="split-btn">
      <a href="#">Primary Link</a>
      <a href="#">Secondary Link</a>
      <a href="#">Secondary Link</a>
      <a href="#">Secondary Link</a>
    </div>

#### Javascript

    $(document).ready(function(){
      $('.split-btn').splitdropbutton({
        toggleDivContent: '<i class="icon-reorder"></i>' // optional html content for the clickable toggle div
      })
    });

Caveat: Since this plugin calculates element widths on page load, if you are using font-face (for example, [font-awesome](http://fortawesome.github.io/Font-Awesome/)) or images within your links, you should use `$(window).load()` instead of `$(document).ready()` See this [stackoverflow answer](http://stackoverflow.com/a/3698214/781704) for why.

#### Generated HTML

    <div class="split-btn">
      <div class="spb-toggle">
        <i class="icon-reorder"></i>
      </div>
      <div class="spb-primary">
        <a href="#">Primary Link</a>
      </div>
      <div class="spb-secondary">
        <a href="#">Secondary Link</a>
        <a href="#">Secondary Link</a>
        <a href="#">Secondary Link</a>
      </div>
    </div>

(inline styles were not inlcuded for the sake of this illustration)

#### Stylesheet

    .split-btn .spb-toggle {
      padding:  5px 6px;
      background: gray;
      color: black;
    }

    // it's important to style the links with .split-btn a instead of '.spb-primary a' or
    // '.spb-secondary a' because those divs have widths based on the length of '.split-btn a'

    .split-btn a {
      padding:  8px;
      background: black;
      color: white;
    }

## License

This software is released under the MIT license
http://opensource.org/licenses/MIT