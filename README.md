# griddly
What's up nerds.

One reason the distribution grid is fascinating is because of how its geometry and topology interact. Both are important in their own right, and they interact in some interesting ways.

## Distribution grid 101

Distribution is what gets electricity from the substation to end users - whether residential, commercial or industrial. It is the original "last (few) miles".

Unlike transmission, which is pretty easy to map, visualize, and analyze, distribution is a black hole. Distribution infrastructure is owned and operated by many different utilities, municipalities, and other entities.

*Distribution substations* transform electricity from the very high voltages used in transmission lines to the merely high voltages used to carry electricity _most_ of the way to homes and businesses.

![Substation Image](https://upload.wikimedia.org/wikipedia/commons/c/c0/Electrical_Substation.JPG)

Substations are where our story will start - they are the "leaf nodes" of the transmission grid, and they will serve as the root nodes for our efforts.

For our purposes, the most important property of a substation is its output voltage(s), since this determines the voltage carried by the primary distribution lines that it serves. Substation output voltages vary from 3kV up to about 35kV.

*Primary distribution lines*, aka *feeders*, carry electricity most of the way from substations to homes, buildings, and businesses. They are often found at the top of utility poles, frequently on a crossbar marked with a yellow HIGH VOLTAGE sign. 

Feeders carry whatever voltage their substation provides - therefore these distribution voltages also range from 3kV to 35kV.

*Distribution transformers* step down the voltage carried by primary distribution lines to that used in the secondary distribution lines. In residential and other low-density areas, most of these are found as cylinders at the top of utility poles; in other cases they are mounted on concrete pads or in vaults under metal plates.

The most important property of a distribution transformer is its voltage-amperes rating, which often appears stenciled on its side. The higher the VA rating, the bigger the load the transformer can support.

*Secondary distribution lines* carry electricity from a distribution transformer to a point very near the service address.

*Service drops* are the last segment of distribution line, carrying power from the nearest pole or underground line to the service meter(s) at an address.

*Meters* are where the grid ends and the customer's electrical network begins.
