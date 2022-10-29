# interpolating sequencer

<img src="interpolation.jpg" width=400>

Set four of the steps manually -- steps 1, 3, 5, 7 -- and it will interpolate the other four steps randomly (up/down a 5th or up/down an octave). The steps are offset, so (for example) step 6 is interpolated randomly based on step 1, etc.

The source of randomness is analog noise. The "random bits" board produces noise, four random voltages, and four random bits which are the result of comparing the random voltages with control voltage. It is designed to be reused in other modules.

The random bits control the interpolated steps, and are stored in a set of flip-flops. There's a "lock" knob, borrowed shamelessly from Tom Whitwell's Turing Machine, which allows you to lock in a sequence that you're enjoying. 

There are three trimmers -- two on the main board, and one on the random bits board. The two on the main board set the 1v and .583333v offset voltage sources. There are spots on the board near the trimmers labeled with those voltages which you can poke with your voltmeter.

The trimmer on the random bits board sets the amplitude of the noise source, which in turn affects the distribution of random voltages output by the sample and holds. I usually let the module warm up for 10 minutes, apply a clock to the clock input, & then adjust it so that the random voltages present on header H3 seem evenly distributed between 0 and 5 volts. Or you can set all of the step pots to zero, set the 5th/oct pot full over, set hi/lo to the midpoint, and then watch the output & adjust the trimmer until you're getting roughly equal numbers of highs and lows on the even steps.

This module, like many of my modules, uses 2mm-pitch male/female headers. Be sure you order/use the right thing!

Most ICs are SOIC 8/14/16; all passives are 0805. The BOMs prefixed with `fixed` are easier to read; the others can be used along with the Pick-and-place and gerber files to order PCBs.
