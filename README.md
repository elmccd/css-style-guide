# CSS Style Guide

- [General-rules](#general-rules)
- [SMACSS principles](#smacss-principles)
- [SMACSS with AngularJS](#smacss-with-angularjs)
- [CSS frameworks](#css-frameworks)
- [CSS preprocessors](#css-preprocessors)
- [Responsiveness and Media queries](#responsiveness-and-media-queries)
- [Graceful Degradation vs Progressive Enhancement](#graceful-degradation-vs-progressive-enhancement)
- [Sources](#sources)

##General rules
- use your project's [EditorConfig](http://editorconfig.org/) (with extension to your editor), or create it. Preferable configuration:
```
[*.css, *.scss, *.less, *.styl]
indent_style = space
indent_size = 2
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true
```
- split your site to independent modules and keep them in seperate files. 
  Don't create files with hundreds of lines. 
- keep your css structure flat. Try to not nest selectors deeper than 3 levels. <sup>[more #1](http://thesassway.com/intermediate/avoid-nested-selectors-for-more-modular-css) </sup>  <sup> [more #2](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Writing_efficient_CSS)</sup>
  - `.comment_author` - good

  - `.comments .comment .author` - worse

  - `.container .content .comments .comment .author` - the worst
- don’t use id attribute to apply styles. <sup>[more](http://oli.jp/2011/ids/)</sup>
- prefer classes in selectors than tag names
- don't abuse operators like > ~ +
- don’t make selectors more strict than they need it. Use: `.comments_form .save-button` instead of `form.comments_form button.save-button`
- sets of helpers like `.clearfix`, `.hidden`, `.pull-left`, `text-center`, `mt10`(margin-top: 10) etc. are good. <sup>[more](http://www.smashingmagazine.com/2013/10/21/challenging-css-best-practices-atomic-approach/)</sup>
- don't repeat your declaration with prefixes like `-webkit-`, `-moz-`, use [autoprefixer](https://github.com/postcss/autoprefixer) for building cross browser release.
- always use [normalize.css](normalize.css) or framework with build in normalize
- avoid @import
- building release
  - marge and minify your CSS files
  - use [uncss](https://github.com/giakki/uncss) to remove redundant styles (especially with css frameworks)
  - use gulp or grunt for above tasks
  - you can [gulp-uncache](https://github.com/elmccd/gulp-uncache) css files, to force refresh user's cache

##SMACSS principles <sup>[more #1](http://smacss.com/) </sup> <sup> [more #2](https://github.com/jonathanpath/SASS-SMACSS)</sup>

Seperate css beetween
- Base
  - normalize css
  - default/global styles 
- Layout
  - css for scaffold main section of website
  - most common used properties: width, float, clear, margin
  - if you are using grid system (e.g. in bootstrap) it does layout's job
- Module
  - everything that is repeating or can be repeated in the future. 
  - Single file - single module. 
  - module can be nested in another module.
  - module cannot have impact to another module (except of module inheritance)
  - modules should can work everywhere. Don’t apply specific properties like ‘float’ this should be applied in layout section or by grid system / helpers (e.g. pull-left in bootsrap).
- State
  - all dynamicaly styles that can be applied both for layout and modules
  - often with !important
- Theme
  - variables with all colors, fonts, padding values.

##SMACSS with AngularJS
- Kepp directive styles as SMACSS module
- Partial(Controller) styles are related to SMACSS layout

##CSS frameworks
 - Choose your favourite and suitable for project type (e.g., Twitter Bootstrap, Zurb Foundation, Semantic UI, Pure CSS)
 - always use it for applications with rich user interface like admin panels.
 - If you need dedicated graphic layout, make theme for your framework.
 - Use build in helpers whenever it's possible rather than writing own css
 
##CSS preprocessors
- stop writing css
- choose your favourite preprocessor (Sass Less, Stylus)
- while using stylus choose one style and stick to it. (braces, colons, semicolons).
```stylus
a
  color red
  background: blue; //bad
```

##Responsiveness and Media queries

- Use % units for layouts
- When specifing fixed size in px add `max-width:100%` both for layout and images
- Adjust your breakpoints to the content, not strict values like `320px`, `480px`, `768px` etc. <sup>[more](http://bradfrostweb.com/blog/post/7-habits-of-highly-effective-media-queries/)</sup>

Graceful Degradation way:
```stylus
.contact
  float left
  @media all and (max-width: 345px)
    float none
```
Progressive Enhancement
```stylus
.contact
  @media all and (min-width: 346px)
    float left
```
##Graceful Degradation vs Progressive Enhancement
- use Progressive Enhancement whenever you can

##Sources
