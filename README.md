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
- split your site to independent modules and keep them in seperate files. 
  Don't create files with a hundreds of lines
- keep your css structure flat. Try to not nest selectors deeper than 3 levels.

`.comment_author` - good

`.comments .comment .author` - worse

`.container .content .comments .comment .author` - the worst

- don’t use id attribute to apply styles.
- prefer classes in selectors than tag names
- don't abuse operators like > ~ +
- don’t make selectors more strict than they need it. Use: `.comments_form .save-button` instead of `form.comments_form button.save-button`
- use helpers like `.clearfix`, `.hidden`, `.pull-left`, `text-center`

##SMACSS principles

##SMACSS with AngularJS

##CSS frameworks

##CSS preprocessors

##Responsive and Media queries

- Use % units for layouts
- When specifing fixed size in px add `max-width:100%` / `max-height:100%`
- Adjust your breakpoints to the content, not strict values like `320px`, `480px`, `768px` etc.

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
http://smacss.com/
