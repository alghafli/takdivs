:Date: 2024-05-08
:Version: 0.0.0
:Authors:
    * Mohammad Alghafli <thebsom@gmail.com>

takdivs, styles for your web page layout

takdivs is a css style sheet that gives you css classes to layout your webpage.

why i made takdivs:
  before i used html, css and js, i programmed using Gtk 3. Gtk 3 provides
  awesome layout methods like box and grid.
  
  i wanted layout methods similar to Gtk. css provides such layout methods but
  you need to write your styles yourself to apply these layout methods.
  
  takdivs provides css class layout styles, some of which are similar to what
  you find in Gtk. i assign most of the classes to divs only to control layout.
  i implemented what i commonly use and hope you will find it useful too.
  
what is inside takdivs:
  takdivs is split into multiple files, most of which provide styles related to
  a single css class. below is a brief documentation of each file. you can check
  each file for a more detailed but still brief documentation. i should write
  full documentation to show how things work together.
  
  inside takdivs are the follwing:
    * takdivs-min.css: this is the minified version of takdivs and provides all
      styles provided by other takdivs files. this is the only file you should
      use in your web page.
      
    * takdivs-vars.css: css custom properties used in takdivs.
    
    * takdivs-window.css: .takdivs-window styles which makes the element occupy
      the whole viewport and can contain a single child (like Gtk window).
      should be used for the <body> element.
      
    * takdivs-box.css: .takdivs-box class which makes the element behaves like a
      Gtk.Box. it is basically a css flexbox which can:
      * pack children horizontally or vertically.
      * pack children at the end similar to Gtk.Box.pack_end().
      * pack some children stretched like the expand parameter in
        Gtk.Box.pack_start().
      * pack in normal or reverse direction.
      
    * takdivs-imgbox.css: .takdivs-imgbox class makes an element suitable to
      contain a replaced element, mainly <img> or <video>.
      
      usually, elements such as <img> take space based on the image size. i do
      not like that. an image should take the space given to it by the parent.
      
      .takdivs-imgbox should have only one child which is a replaced element.
      
    * takdivs-overlay.css: .takdivs-overlay class stacks the children on top of
      each other. at its current implementation, it is basically a
      .takdivs-imgbox with the single difference that it shows children on top
      of each other instead of showing only the first child and hiding the rest.
      
    * takdivs-scrolledwindow.css: .takdivs-scrolledwindow class makes the
      element behave like a Gtk.ScrolledWindow. it should only contain a single
      child and behaves as follows:
      * the child will occupy the size given to the .takdivs-scrolledwindow by
        the parent of .takdivs-scrolledwindow.
      * the .takdivs-scrolledwindow will provide scrolling functionality to the
        child if it overflows.
    
    * takdivs-table.css: not really used for layout. it is just a table whose
      header stays visible at the top even if you scroll down. i usually put it
      in a .takdivs-scrolledwindow.
    
    * takdivs.css: this file just imports the other files. you are better using
      takdivs-min.css instead of this one.
