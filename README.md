# griddly
What's up nerds.

One reason the distribution grid is fascinating is because of how its geometry and topology interact. Both are important in their own right, and they interact in some interesting ways.

## Distribution grid 101

Distribution is what gets electricity from the substation to end users - whether residential, commercial or industrial. It is the original "last (few) miles".

Unlike transmission, which is pretty easy to map, visualize, and analyze, distribution is a black hole. Distribution infrastructure is owned and operated by many different utilities, municipalities, and other entities.

**Distribution substations** transform electricity from the very high voltages used in transmission lines to the merely high voltages used to carry electricity _most_ of the way to homes and businesses.

![Substation Image](https://upload.wikimedia.org/wikipedia/commons/c/c0/Electrical_Substation.JPG)

Substations are where our story will start - they are the "leaf nodes" of the transmission grid, and they will serve as the root nodes for our efforts.

For our purposes, the most important property of a substation is its output voltage(s), since this determines the voltage carried by the primary distribution lines that it serves. Substation output voltages vary from 3kV up to about 35kV.

**Primary distribution lines**, aka **feeders**, carry electricity most of the way from substations to homes, buildings, and businesses. They are often found at the top of utility poles, frequently on a crossbar marked with a yellow HIGH VOLTAGE sign. 

Feeders carry whatever voltage their substation provides - therefore these distribution voltages also range from 3kV to 35kV.

**Distribution transformers** step down the voltage carried by primary distribution lines to that used in the secondary distribution lines. In residential and other low-density areas, most of these are found as cylinders at the top of utility poles; in other cases they are mounted on concrete pads or in vaults under metal plates. 

The most important property of a distribution transformer is its voltage-amperes (VA) rating, which often appears stenciled on its side. The higher the VA rating, the bigger the load the transformer can support. A little 15 KVA transformer will serve a few houses, while a larger 50 KVA unit is common for small and medium apartment buildings. 

![Pole mounted transformer](https://upload.wikimedia.org/wikipedia/commons/thumb/1/1c/Polemount-singlephase-closeup.jpg/256px-Polemount-singlephase-closeup.jpg)

Many larger residential units and commercial buildings will have their own transformer enclosed in a metal cabinet and mounted on a concrete pad on the property. 

![Pad mounted transformers](https://upload.wikimedia.org/wikipedia/commons/thumb/8/8c/CERN_Computer_Centre_for_LHC_-_Transformers.jpg/512px-CERN_Computer_Centre_for_LHC_-_Transformers.jpg)

**Secondary distribution lines** carry electricity from a distribution transformer to a point very near the service address.

**Service drops** are the last segment of distribution line, carrying power from the nearest pole or underground line to the service meter(s) at an address. These are the lines that, in typical residential areas, hang laterally from the nearest utility pole to the "weather head" on each house.

![Weather head](https://upload.wikimedia.org/wikipedia/commons/thumb/8/87/Weatherhead.JPG/256px-Weatherhead.JPG)

**Meters** are where the grid ends and the customer's own electrical network begins; this is where our job ends as well. Depending on the nature of the building(s) at an address (single family home, duplex, apartment building, commercial), there may be multiple meters. For example, many smaller apartment buildings have one meter for each unit, so that each renter can pay for their own usage separately.

![Smart meter](https://upload.wikimedia.org/wikipedia/commons/thumb/1/12/Elster_A3_Alpha_Type_A30_electricity_meter_collector.jpeg/256px-Elster_A3_Alpha_Type_A30_electricity_meter_collector.jpeg)

![Smart meter bank](https://upload.wikimedia.org/wikipedia/commons/thumb/b/ba/Electric-meter-boxes-4625.jpg/256px-Electric-meter-boxes-4625.jpg)

## Mapping the distribution grid

Griddly is a project to map every utility pole, transformer, and power line in the distribution grid - first in the US, and eventually on a global basis. In some ways, this is a really big task: there are between 100 and 200 million utility poles in the United States, for example. In our big data era, though, this amount of data is barely even a blip. 

Both the geometry (i.e., coordinates and distances) and topology (connectivity) of the grid network matter - and both may appear complex at casual observation. But there is a saving grace: the network architecture is both *regular* and *shallow*, meaning that local observations can be straightforwardly used to construct a complete and accurate map of the system as a whole.

What do we need to do to map the distribution grid?

1. Trace the feeder lines out of every substation, from pole to pole, including capacitor banks and voltage regulators
2. Capture the size and connection point of every distribution transformer
3. Identify the addresses and meters that are served by each distribution transformer

While there are lots of each of these things to be observed and captured, there aren't that many *kinds* of things to capture; what's more, these objects are connected in very stereotyped structures.

## Making the data available

## FAQ

## Menagerie
