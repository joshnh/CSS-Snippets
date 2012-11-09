# Sublime Text 2 CSS Snippets

__UPDATE: The scope has been expanded to include LESS, Sass and Stylus files.__

Type the snippet shortcode and then press <kbd>Tab</kbd> to complete the snippet.

The snippets are listed below in alphabetical order. The '$1' indicates the initial position of the caret/s.
Some snippets have been set up so that pressing Tab jumps the caret/s to the next predefined spot.
It's a little tricky to explain, but any snippet that has a $1/$2/$3/etc. uses this technique.

Feel free to play with, alter, expand, or ruin these snippets as you please. I only ask that if you come up with an incredibly handy snippet, or simply one that I have missed,
that you let me know (via email, Twitter, GitHub or as a comment on the original [blog post][1]) so that I can
improve these for everybody. Thanks!
[1]: http://joshnh.com/2012/02/a-collection-of-css-snippets-for-sublime-text-2/ "The original blog post."

---

__`__

That's a backtick in case you were unsure (it's on the same key as the tilde (~), directly above Tab).

    /* $1 **************************************************/

__abs__

    position: absolute;

__act__

    $1:active {
      $2
    }

__aft__

    $1:after {
      content: '';
      $2
    }

__amp__

Wrap ampersand with <span class="amp"></span> to make them look sexy.

    .amp {
        font-family: Baskerville, 'Goudy Old Style', Palatino, 'Book Antiqua', serif;
        font-style: italic;
        font-weight: normal;
    }

__ani__

Animation shorthand: animation-name animation-duration animation-timing-function animation-delay
animation-iteration-count animation-direction.

    -webkit-animation: ${1:name} ${2:duration} ${3:ease|linear|ease-in|ease-out|ease-in-out|cubic-bezier(<number>,<number>,<number>,<number>)} ${4:delay} ${5:infinite|<number>} ${6:normal|alternate};
       -moz-animation: ${1:name} ${2:duration} ${3:ease|linear|ease-in|ease-out|ease-in-out|cubic-bezier(<number>,<number>,<number>,<number>)} ${4:delay} ${5:infinite|<number>} ${6:normal|alternate};
        -ms-animation: ${1:name} ${2:duration} ${3:ease|linear|ease-in|ease-out|ease-in-out|cubic-bezier(<number>,<number>,<number>,<number>)} ${4:delay} ${5:infinite|<number>} ${6:normal|alternate};
         -o-animation: ${1:name} ${2:duration} ${3:ease|linear|ease-in|ease-out|ease-in-out|cubic-bezier(<number>,<number>,<number>,<number>)} ${4:delay} ${5:infinite|<number>} ${6:normal|alternate};
            animation: ${1:name} ${2:duration} ${3:ease|linear|ease-in|ease-out|ease-in-out|cubic-bezier(<number>,<number>,<number>,<number>)} ${4:delay} ${5:infinite|<number>} ${6:normal|alternate};

__aut__

    margin: ${1:0} auto;

__bac__

    background: ${1:#fff} url('$2') ${3:0} ${4:0} ${5:repeat|repeat-x|repeat-y|no-repeat|inherit|round|space};

__bef__

    $1:before {
      content: '';
      $2
    }

__blo__

    display: block;

__bol__

    font-weight: bold;

__bor__

    border-radius: $1;

__bot__

    bottom: ${1:0};

__box__

    -webkit-box-sizing: border-box;
       -moz-box-sizing: border-box;
            box-sizing: border-box;

__cen__

    text-align: center;

__cf__

You should look at using inline-block for layouts instead of floats.

    .cf:after,
    .cf:before {
      content: '';
      display: table;
    }
    .cf:after {
      clear: both;
    }
    .cf {
      zoom: 1;
    }

__con__

    content: '$1';

__cur__

    cursor: ${1:auto|crosshair|default|pointer|move|e-resize|ne-resize|-resize|n-resize|se-resize|sw-resize|s-resize|w-resize|text|wait|help|progress};

__fil__

    -webkit-animation-fill-mode: ${1:none|forwards|backwards|both};
       -moz-animation-fill-mode: ${1:none|forwards|backwards|both};
        -ms-animation-fill-mode: ${1:none|forwards|backwards|both};
         -o-animation-fill-mode: ${1:none|forwards|backwards|both};
            animation-fill-mode: ${1:none|forwards|backwards|both};

__fix__

    position: fixed;

__fon__

You don't need to declare a value for the line-height unless using pixels (1.5 is the same as 1.5em
or 150%).

    font: ${1:normal|italic|oblique} ${2:normal|small-caps} ${3:normal|bold|bolder|lighter} ${4:1em}/${5:1.5} ${6:sans-serif};


__gra__
It's a good idea to define a background color, and use alpha transparency with your gradients, that
way you only need to alter a single value if you want to change the color of the background.

    background-image: -webkit-linear-gradient($1);
    background-image:    -moz-linear-gradient($1);
    background-image:     -ms-linear-gradient($1);
    background-image:      -o-linear-gradient($1);
    background-image:         linear-gradient($1);

__hid__

    overflow: hidden;

__hov__

It is good (for accessibility reasons) to use the focus pseudo-class alongside the hover pseudo-class
when defining styles for anchors, there is no need for :focus in most other cases.

    $1:hover,
    $1:focus {
      $2
    }

__h__

My preference over rgba(), and I have written [an article][2] explaining why
[2]: http://joshnh.com/2011/09/hsla-are-you-using-it-here-is-why-i-think-you-should-be/ "HSLA and You"

    hsla(${1:0},${2:0}%,${3:0}%,${4:1})

__hyp__

    -webkit-hyphens: auto;
       -moz-hyphens: auto;
        -ms-hyphens: auto;
            hyphens: auto;

__inl__

Comment out the whitespace between elements in your markup if you need pixel perfect alignment
(although pixel perfection is not realistic).

    display: inline-block;
    vertical-align: top;
    zoom: 1;${1: /* Fix for IE7 */}
    *display: inline;${1: /* Fix for IE7 */}

__ita__

    font-style: italic;

__key__

This snippet makes good use of Sublime Text 2's multiple selection capabilites. If you lose the
multiple selection, a quick way to regain it is to select 'keyframes', hit CMD+D (CTRL+D on Windows)
four times, and then use the arrow keys to navigate. Continuing to tab will reduce the caret back
down to a single selection, but you can also force it using ESC.

    @-webkit-keyframes $1 {
      0% { $2 }
      100% { $3 }
    }
    @-moz-keyframes $1 {
      0% { $2 }
      100% { $3 }
    }
    @-ms-keyframes $1 {
      0% { $2 }
      100% { $3 }
    }
    @-o-keyframes $1 {
      0% { $2 }
      100% { $3 }
    }
    @keyframes $1 {
      0% { $2 }
      100% { $3 }
    }

__lef__

    left: ${1:0};

__lin__

    line-height: ${1:1.5};

__mar__

    margin: ${1:0};

__med__

When designing with a focus on responsiveness, using min-width is recommended (it means that smaller
devices, such as mobiles, aren't applying styles that aren't being used).

    @media (min-width: $1) {
      $2
    }

__non__

    text-decoration: none;

__pad__

    padding: ${1:0};

__pla__

    -webkit-animation-play-state: ${1:running|paused};
       -moz-animation-play-state: ${1:running|paused};
        -ms-animation-play-state: ${1:running|paused};
         -o-animation-play-state: ${1:running|paused};
            animation-play-state: ${1:running|paused};

__r__

My preference is hsla(), and I have written [an article][2] explaining why.

    rgba(${1:0},${2:0},${3:0},${4:1})

__rel__

    position: relative;

__rig__

    right: ${1:0};

__san__

    font-family: ${1:<font-name>,} sans-serif;

__ser__

    font-family: ${1:<font-name>,} serif;

__sha__

    box-shadow: ${1:horizontal-offset} ${2:vertical-offset} ${3:blur-radius} ${4:spread-distance} ${5:hsla(0,0%,0%,.25)};

__t__

    transparent

__tap__

This overrides the highlight color on iPhones/iPads.

    -webkit-tap-highlight-color: ${1:hsla(0,0%,0%,.5)};
            tap-highlight-color: ${1:hsla(0,0%,0%,.5)};

__tex__

Use wisely, please keep readability in mind.

    text-shadow: ${1:horizontal-offset} ${2:vertical-offset} ${3:blur-radius} ${4:hsla(0,0%,0%,.25)};

__top__

    top: ${1:0};

__transform__

This is too complex to write out all options.

    -webkit-transform: $1;
       -moz-transform: $1;
        -ms-transform: $1;
         -o-transform: $1;
            transform: $1;

__transition__

Transition shorthand: transition-propery transition-duration transition-timing-function
transition-delay. The default values are: all 0 ease 0, this means that if you want to apply a
transition to all properties, using the ease timing-function, you only need to declare the duration
(e.g. transition: .5s;).

    -webkit-transition: ${1:all} ${2:.25s} ${3:ease|linear|ease-in|ease-out|ease-in-out|cubic-bezier(<number>,<number>,<number>,<number>)};
       -moz-transition: ${1:all} ${2:.25s} ${3:ease|linear|ease-in|ease-out|ease-in-out|cubic-bezier(<number>,<number>,<number>,<number>)};
        -ms-transition: ${1:all} ${2:.25s} ${3:ease|linear|ease-in|ease-out|ease-in-out|cubic-bezier(<number>,<number>,<number>,<number>)};
         -o-transition: ${1:all} ${2:.25s} ${3:ease|linear|ease-in|ease-out|ease-in-out|cubic-bezier(<number>,<number>,<number>,<number>)};
            transition: ${1:all} ${2:.25s} ${3:ease|linear|ease-in|ease-out|ease-in-out|cubic-bezier(<number>,<number>,<number>,<number>)};

__upp__

    text-transform: uppercase;

__wra__

For legacy reasons, UAs may also accept ‘word-wrap’ as an alternate name for the
'overflow-wrap' property. However this syntax non-conforming in author style sheets.
(http://www.w3.org/TR/css3-text/#overflow-wrap)

    overflow-wrap: break-word;
    word-wrap: break-word;
