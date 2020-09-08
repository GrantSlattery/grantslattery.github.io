## Welcome

You can visit my personal website [here](https://grantslattery.github.io/my-app/) to learn more about me and connect.

This page is meant for testing coding projects.

### helloworld.py  

Basic Python code that returns text.

```python

#Testing Python code
print("This line will be printed.")


```

For more details see [helloworld.py](https://github.com/GrantSlattery/helloworld.py).




### BitsConverter  

This program converts Twitch Bits to United States Dollars.
1 Bit is equal to 0.01 USD
The result is displayed in a GUI.

```python

# This program converts Twitch Bits to United States Dollars
# The result is displayed in a label in the main window.

import tkinter

class BitsConverter:
    def __init__(self):


        # Create the main window.
        self.main_window = tkinter.Tk()
        # Create three frames to group widgets.
        self.top_frame = tkinter.Frame()
        self.mid_frame = tkinter.Frame()
        self.bottom_frame = tkinter.Frame()
        # Create the widgets for the top frame.
        self.prompt_label = tkinter.Label(self.top_frame, \
                                          text='Enter an amount in Twitch Bits:')
        self.bits_entry = tkinter.Entry(self.top_frame, \
                                        width=10)

       # Pack the top frame's widgets.
        self.prompt_label.pack(side='left')
        self.bits_entry.pack(side='left')

        # Create the widgets for the middle frame.
        self.descr_label = tkinter.Label(self.mid_frame, \
                                         text='Converted to dollars ($ USD):')


        self.value = tkinter.StringVar()

        self.dollars_label = tkinter.Label(self.mid_frame, \
                                         textvariable=self.value)
        # Pack the middle frame's widgets.
        self.descr_label.pack(side='left')
        self.dollars_label.pack(side='left')
        # Create the button widgets for the bottom frame.
        self.calc_button = tkinter.Button(self.bottom_frame, \
                                          text='Convert', \
                                          command=self.convert)
        self.quit_button = tkinter.Button(self.bottom_frame, \
                                          text='Quit', \
                                          command=self.main_window.destroy)
        # Pack the buttons.
        self.calc_button.pack(side='left')
        self.quit_button.pack(side='left')

        # Pack the frames.
        self.top_frame.pack()
        self.mid_frame.pack()
        self.bottom_frame.pack()
        # Enter the tkinter main loop.
        tkinter.mainloop()

        # The convert method is a callback function for
        # the Calculate button.

    def convert(self):
    # Get the value entered by the user into the
    # bits_entry widget.
        try:
            twitchBits = float(self.bits_entry.get())
            # Convert bits to dollars.
            bitDollarAmount = twitchBits * .01
            
            f_dollars = "$" + format(bitDollarAmount,'.1f') + " USD"
        except:
            f_dollars = "invalid"
        # Convert dollars to a string and store it
        # in the StringVar object. This will automatically
        # update the dollars_label widget.
        self.value.set(f_dollars)


# Create an instance of the BitsConverter class.
bits_conv = BitsConverter()


```
<iframe src="https://raw.githubusercontent.com/GrantSlattery/BitsConverter/master/BitsConverter.png" width=700 height=600></iframe>
    
For more details see [BitsConverter](https://github.com/GrantSlattery/BitsConverter).
