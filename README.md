A program written in Lua for Open Computers designed to automatically manage a Draconic Reactor.

# Setup

You can install this program by either copy-pasting it into a file on an Open Computer, or download it using an Internet Card.

## Requirements

-An Open Computer and a Draconic Reactor(obviously)

-Having the Draconic Reactor connected to the computer via an adapter(connected to the energy injector or a stabilizer)

-Having two flux gates : One for the energy injector, and one for the output, on one of the stabilizers. 
Of course also have them plugged in to the computer using adapters

## Changing the gates' address

Because two flux gates are plugged into a single computer, we have to identify each one by their address.

However, this value changes every time it is unplugged and plugged back in, so it is different in each setup.

To fix that, connect the gate for the input to the computer(connected to the energy injector) and run "components" in the shell.

You should see a component named "flux_gate". On its right, you'll have a random combination of letters and numbers; that's its address. Remember the first 4 characters, we'll need them later on.

Edit the program by running "edit filename.lua" (of course replace "filename" with the name you gave to the file)

Find the line that starts with "local ingate". At the end of the line, you will see "component.get("f4ef","flux_gate")".

Replace f4ef with the first 4 characters of the address of the flux gate used for inputting energy into the reactor.

Now plug in the flux gate for outputting the energy to the computer.

Once more, run the "components" program and you should this time, see two flux gates. Locate the once that has a different address from the once you already used, which is for the input.

Again, remember the first 4 characters of the new flux gate, edit the program, and locate the line starting with "local outgate". At the end, you'll see "component.get("8a19","flux_gate")". Once more, replace 8a19 with the first 4 characters of the address from the new flux gate.

And you're all set! If the reactor isn't up already, turn it on, activate it, and once it's activated, run the script!

# Features

## Functions:

-A graphical interface to keep track of all the important stats of your reactor at a glance, with numbers progress bars.

-Adjust the desired temperature of the reactor using the touchscreen(precision of ~ 250°C)

-(SOON) Adjust the desired shield strengh of the reactor using the touchscreen

## Security:

-Automatically shuts down the reactor if it goes above 8200°C (customizable value)

-Automatically injects a user-defined amount of energy(I use 300k RF/t) into the reactor if the shield level goes below 0.8 % (customizable value)