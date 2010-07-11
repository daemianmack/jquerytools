[jQuery Tools](http://flowplayer.org/tools/) - The Missing UI library for the Web
================================

jQuery Tools is a collection of the most important user-interface components for modern websites. Used by large sites all over the world.

This fork includes a patch to allow a user to specify a *different*, non-next element to act as the tooltip for an element...

    <p class="needs_to_be_tooltipped" title="src:my_paragraph_tooltip">This paragraph should have a tooltip.</p>
    ...
    ...
    ...
    <div id="my_paragraph_tooltip" class="tooltip">Here I am, hovering above your paragraph, as a tooltip.</div>@

By default, the tooltip package lets the user specify a title attribute on elements he wants tooltipped; a new element will be generated with those contents and used as the tooltip. The user can also choose not to specify a title attribute, in which case the next element after the tooltippable element will be taken. This way one can avoid putting markup inside the title tag if one has complex tooltip markup.

However, in some instances (like the one I'm experiencing), the next element isn't a good choice, as it seems to retain some of the properties of its original position in the page flow; in this case, I'm using a non-trivial set of relatively-positioned DIVs thanks to YAML (www.yaml.de) and my next-element DIVs aren't responding well to becoming tooltips. 

My solution is to place them later in the document, unaffected by the flow issues.
