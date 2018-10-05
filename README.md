# version-control-visual-elements
Materials and experimentation for my talk "Human-proof Your Version Control With Visual Elements"

Can you remember the difference between two hex color values? Me neither! Entering visual representations of recently-changed elements into version control makes review of past changes easier & speeds acclimation to a new web project. Surprisingly, methods for doing so aren’t standardized and are rarely used outside of large companies, and the rest of us are left checking out every major commit and viewing changes locally! Join me for a review of methods currently in use and discuss the benefits and drawbacks of each. The audience will learn from a survey of tools used by both designers and web developers, what methods are most appropriate for individual projects, & how these methods differ from those used at some of the largest companies (Google, eBay, etc.). Finding a method to track changes in your visual elements will save our future contributors (and future selves!) the pain of having to distinguish #2dc651 (lime green) from #34a34e (darker(!) lime green) and ultimately make our commit histories cleaner and our repos easier to navigate in ways that many of us have never imagined!

Statement of problem ::

Version control is text-based: Text in code diffs, text in commits  
Text-based version control increases cognitive load for the programmer  
Example site change & associated tracking  
Online diff shows only hex color & any added comments  
Editor with plug-in to show color will display hex color, but need to be viewing locally to use  

The Hacks ::

Screenshots of before/after saved with a commit describing the change  
Limitations: when/how is this viewed, extra trouble of making the screenshots  
Great stuff: makes a record, faster than opening up Github or Git diff & plugging the hex into a hex-viewer  
Color changes can be viewed in-editor with a plug in  
Examples: Atom’s Pigments (view colors in editor) & Color Picker (select/add colors in editor), Sublime’s Color Highlighter (view colors in editor)  
Limitations:  
Doesn’t help with non-color changes, such as spacing, fonts, etc.  
Most useful for folks who have a terminal -> editor flow for reviewing past commits, not those who view in Github  

The Tools ::

Puppeteer (Node library API to control Chrome & Chromium)  
What / how Puppeteer works  
Best use / applications  
Steps to add to workflow  
Demo: https://try-puppeteer.appspot.com/   
Benefits: Screenshot is automated & can be entered into source control   
Alternative: Selenium/WebDriver (cross-browser)  
Testing for Screenshot & HTML diffing  
Common for companies (Google, eBay [documentation], Servo) to use an internal process for screenshot diffing, not a external tool  

Two strategies: Screenshot & HTML comparison  
Screenshots taken when tests fails, developer compares & confirms new screenshot should be committed  
HTML  
Benefits: Automated process  
Limitations: Screenshot is still one commit behind & inaccessible for most developers/projects  

Learn from other visual creators ::

Tools for designers  
Abstract’s Compare Mode  
Git-like functionality  
No integration  
Sketch’s Pages & Artboards (scroll through to see changes) [demo]  
Zeplin (for smaller, less easily spotted changes) [demo]  
Powerful to see Git-like functionality for visual design  

Lessons ::

This is a problem a lot of people think about & there are many different solutions  
Time is saved by improving clarity  
My winner was Puppeteer because I value the convenience of screenshots taken for me & don’t mind checking them in as part of my flow  
Pick the one that is best for you:  
Puppeteer/Selenium/WebDriver for screenshots taken at every change  
Abstract/Zeplin/Sketch for scroll-through visuals to be used alongside your version control  
Hand-created screenshots checked into version control  
Editor plugins that help you visualize the colors on your site  
