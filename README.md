# CSS Style Guide

- [General-rules](#general-rules)
- [SMACSS principles](#smacss-principles)
- [SMACSS with AngularJS](#smacss-with-angularjs)
- [CSS frameworks](#css-frameworks)
- [CSS preprocessors](#css-preprocessors)
- [Responsive and Media queries](#responsive-and-media-queries)
- [Graceful Degradation vs Progressive Enhancement](#graceful-degradation-vs-progressive-enhancement)

##General rules

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
