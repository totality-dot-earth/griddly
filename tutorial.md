# Gleaming the grid

> When eating an elephant take one bite at a time. --Creighton Abrams

With griddly, grid explorers like you work together to map every inch of the electricity distribution grid. This is a huge task. 

> When mapping the grid look at one pole at a time.

## Find a place to map

## Find a pole

The best place to start a collection session is to find a pole that is connected to a mapped pole - that way your new observations will be a direct extension of the already-mapped territory. But don't worry if that's not possible - much better to just start making observations, even if it will be an island for now.

## Add a pole

First we'll take note of a pole's "vitals". Switch to the `Pole` tab if needed, and note whether the new pole symbol (⬇️) is in the right spot.

1. Use the map to adjust the position of the new pole cursor as needed
2. Enter the pole's ID tag number, if the utility uses them.
3. Note whether the pole has a streetlight and/or a riser connecting its wires to an underground conduit.
4. Save the pole

## Identify the high and low voltage connections.

Each pole can host zero, one, or more separate sets of primary / high voltage and secondary / low-voltage lines. Use the buttons at the bottom of the `Pole` tab to add the appropriate number of each.

## Add transformer(s), if any

Pole-top transformers are very obvious, but in some cases it can be a bit tricky to determine their size and how they are connected.

1. Enter whether the transformer is single-phase (by far the most common in the US), or three-phase.
2. Enter the transformer's size rating in KVA. This is sometimes stenciled in large numbers on the side of the cylinder, and other times must be guessed from the size. If the size is guessed, be sure to check the `Size Unsure` box.
3. In the US, three-phase transformers are usually created by grouping three single-phase transformers of the same size. If this is the case, enter all three transformers as described here, and additionally check the `Grouped` box for each.

## Add Lines

Now we add connections to any poles that were previously added to the system, whether those observations occurred during this collection session or a previous one.

1. Add 

## Tricky Parts

### Is this a primary or secondary line?

Sometimes it can be tough to tell whether lines are primary (high voltage) or secondary (low voltage). Oddly, this often happens on the simplest poles - i.e., those that host a single set of lines, and do not have transformers or service drops to provide clues. Here are a couple ways to disambiguate:

1. Look for the signs. In at least some jurisdictions, all primary lines must be marked with a yellow "High Voltage" sign. If you see one on a crossbar, then those are primaries. If you see such a sign on the pole itself, then all lines _above_ the sign are primaries and any below are secondaries.

2. Check the size and style of insulator. Primary lines typically have larger insulators than secondaries, and this can be particularly helpful once you're used to the equipment that is used in a certain area.

3. Trace the line back to another, more informative pole. Because secondaries can only run a few hundred yards at most, you shouldn't have to look too far to find a pole that hosts both primary and secondary lines; then it's just a matter of tracing these to the confusing pole.

### What size is this transformer?

Transformers are rated according to the kilovolt-amperes they can deliver - this is like a wattage rating for alternating current. For the most part, this rating varies directly with the volume of the transformer, though there are some variations. If the rating is not indicated on the side of the transformer, or the markings are too faded to read reliably, it may be necessary to guesstimate the size.

1. Use your judgment and experience. Once you've recorded a few dozen transformers, you'll have a pretty good sense of the approximate sizes that correspond to each rating.

2. Think about the context. You may have noticed patterns in the neighborhood, or common sizes that show up frequently. You can also use the number and size of the service drops - the higher the potential load on the transformer, the higher its rating will need to be.

### How many separate connections are on this pole?

One of the trickiest aspects of reading poles is determining which lines are connected and which aren't. Often, the patch cables that tie lines together can be easy to miss, or it can be hard to ascertain from the ground which wires are being bridged.

1. Move around the pole. Often, a different angle can make all the difference.
