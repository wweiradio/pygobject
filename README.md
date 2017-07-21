# pygobject
demo of python gi object

https://python-gtk-3-tutorial.readthedocs.io/en/latest/entry.html

# Notes
1. Gtk.EventBox 可以给没有界面窗口的控件提供界面，接受事件等等。
2. widget.props.prop_name = value, 不用setter和getter的方法
3. 查看一个widget有哪些属性
widget = Gtk.Box()
print(dir(widget.props))

>>> print(dir(widget.props))
['app_paintable', 'baseline_position', 'border_width', 'can_default', 'can_focus', 'child', 'composite_child', 
'double_buffered', 'events', 'expand', 'halign', 'has_default', 'has_focus', 'has_tooltip', 'height_request', 
'hexpand', 'hexpand_set', 'homogeneous', 'is_focus', 'margin', 'margin_bottom', 'margin_end', 'margin_left', 
'margin_right', 'margin_start', 'margin_top', 'name', 'no_show_all', 'opacity', 'orientation', 'parent', 
'receives_default', 'resize_mode', 'scale_factor', 'sensitive', 'spacing', 'style', 'tooltip_markup', 
'tooltip_text', 'valign', 'vexpand', 'vexpand_set', 'visible', 'width_request', 'window']

4. How to Deal With Strings
python2: str and unicode

 Unicode standard describes how characters are represented by code points
 In order to convert this abstract representation into a sequence of bytes the Unicode string must be encoded. 
  
   抽象到字节串就是encoding， 编码

5. GTK+ uses UTF-8 encoded strings for all text。 value returned is str instance, which is utf-8 encoded bytes.
推荐不使用unicode objects


### Layout Containers

 #### Boxes:
    Gtk.Box.pack_start()
    Gtk.Box.pack_end()
 
 ####Grid:
    The Gtk.Grid.attach() method takes five parameters:

        The child parameter is the Gtk.Widget to add.
        left is the column number to attach the left side of child to.
        top indicates the row number to attach the top side of child to.
        width and height indicate the number of columns that the child will span, 
        and the number of rows that the child will span, respectively.

    grid.attach_next_to(button3, button1, Gtk.PositionType.BOTTOM, 1, 2)
    
    child is the Gtk.Widget to add, as above.
    sibling is an existing child widget of self (a Gtk.Grid instance) or None. The child widget will be placed next to sibling, or if sibling is None, at the beginning or end of the grid.
    side is a Gtk.PositionType indicating the side of sibling that child is positioned next to.
    width and height indicate the number of columns and rows the child widget will span, respectively.

 
 ####ListBox
    vertical container that contains Gtk.ListBoxRow childre
    rows can be dynamically sorted and filtered. 
    headers can be added dynamically
    keyboard navigation
    
    先加 Gtk.ListBoxRow()， 再加其它widget
    
    
            
 
 ####Stack and StackSwitcher
    1. shows one of its children at a time
    2. work with StackSwitcher together to change the visible children.
    3. transition:  Gtk.Stack.set_transition_type().  
        gtk-enable-animations” setting.
    4. transition speed: Transition speed can be adjusted with Gtk.Stack.set_transition_duration()
    5. add element: stack.add_titled()
    6. add stack for stackswitcher .set_stack(stack)
 
 
 ####HeaderBar
    1. window.set_titlebar() 
    2. top, 
    3. set_show_close_button(True)
    
 
 ####FlowBox
    positions child widgets in sequence according to its orientation.
     Gtk.FlowBox
      Gtk.FlowBoxChild c
      
 #### NoteBook
    children are pages that can be switched between using tab labels along one edge.
    Gtk.Notebook.set_tab_pos()
    Gtk.Notebook.set_scrollable()
    Gtk.Notebook.popup_enable(), Gtk.Notebook.popup_disable()).
      
    append_page()
    
    
### Other widgets
 label:
    set_text(), set_markup() Pango Markup syntax    https://developer.gnome.org/pango/stable/PangoMarkupFormat.html
    set_selectable()
    set_justify()
    set_line_wrap()
 entry:
    allows input.
    set_text(), get_text(), set_max_length(),set_editable(), set_visibility(), set_progress_fraction.
    
  button:
  Toglebutton
  checkbutton
  
  Gtk.CheckButton inherits from Gtk.ToggleButton. The only real difference between the two is Gtk.CheckButton‘s appearance. A Gtk.CheckButton places a discrete Gtk.ToggleButton next to a widget, (usually a Gtk.Label). The “toggled” signal, Gtk.ToggleButton.set_active() and Gtk.ToggleButton.get_active() are inherited.
  
  RadioButton:
    create:
    Gtk.RadioButton.new_from_widget(), 
    Gtk.RadioButton.new_with_label_from_widget() or 
    Gtk.RadioButton.new_with_mnemonic_from_widget(). 
        set_active()
 SbinButton:
    click on one of two arrows to increment or decrement the displayed value
    Gtk.Adjustment.
    
    
    
 Switch
 Gtk.CheckButton()
 Gtk.Label()
 Gtk.ComboBoxText()
 Gtk.TextView()

 Gio.ThemedIcon
 



## references 
https://github.com/sebp/PyGObject-Tutorial
https://pygobject.readthedocs.io/en/latest/ users are encournaged to use pygtk through pygobject.

https://lazka.github.io/pgi-docs/
https://developer.gnome.org/gtk3/stable/
http://blog.csdn.net/a87b01c14/article/details/52053367
http://www.pygtk.org/pygtk2tutorial/index.html  Pygtk2.0 tutorial



## Cario是一个2D图形库，支持多种输出设备。
