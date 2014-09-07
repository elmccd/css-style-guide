# CSS Style Guide

- [General-rules](#general-rules)
- [SMACSS principles](#smacss-principles)
- [SMACSS with AngularJS](#smacss-with-angularjs)
- [CSS frameworks](#css-frameworks)
- [CSS preprocessors](#css-preprocessors)
- [Responsive and Media queries](#responsive-and-media-queries)
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

##SMACSS with AngularJS

##CSS frameworks

##CSS preprocessors

##Responsive and Media queries

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
