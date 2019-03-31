# Griddly
What's up nerds.

The electric grid is both amazing and shabby, finely tuned and haphazard. It is also uncharted: even the organizations that own and maintain its various pieces do not have a clear picture of the grid they oversee.

One reason the distribution grid is fascinating is how its geometry and topology relate. Both are important in their own right, and they interact in some interesting ways. Geometry matters because distance matters in electric transmission - power is lost as electricity is conducted, and the infrastructure that is efficient for long-distance transport is very impractical for local delivery. The topology is also crucial, because it determines everything from reliability to flexibility to construction and maintenance costs.

**Griddly** is a collective project to collect and continuously maintain a complete map of the electricity distribution grid - the part of the grid that typically carries power from a substation to each location or address that receives electricity service.

* **Why do we need to know so much about the distribution grid?**

    In other words, why is Griddly worth the effort? The answer to this question can be divided into two buckets: existing applications that we already know about, and applications that will emerge as a consequence of the data being available. While the first category of uses is easier to talk about, it is the second bucket that we believe will bring the most important impacts.
    
    To anchor the discussion, consider the problem of [hosting capacity analysis](https://www.utilitydive.com/news/why-are-the-newest-distribution-system-buzzwords-hosting-capacity-analysis/514219/) - basically, the task of determining how much more generation and storage each bit of the grid can handle. This layer of information would inform a huge number of decisions about where to build new solar, where to add batteries, and so on.
    
    > To DER [Distributed Energy Resource] advocates, [hosting capacity analysis] is the holy grail and should be implemented yesterday because it opens access to right-now marketing.

    But HCA requires very granular understanding of the distribution system, and even when utilities have this information (which they may not), they are reluctant to share - even when required to by regulation.

* **How is the griddly data licensed? Is the data free? Open?**

    The Griddly data is dual-licensed. For research, academic, NGO, philanthropic, and non-profit work, the data is available under the Creative Commons Attribution Non-commercial Share-Alike license. While pricing for this kind of usage is TBD, the intention in these cases is simply to cover the costs of delivering the data.
    
    For commercial use, the data is covered under a conventional proprietary license. This license permits a broad range of business uses, though it does prohibit reselling of the data.

    Griddly is designed to balance two requirements. First, we want the distribution network data to be available and useful for as many applications as possible. In many ways, Griddly was born from frustration with the fact that this level of grid data is typically hidden away in the computer and paper records of individual utilities; the last thing we want to do is to replicate that state of affairs.
    
    But second, let's acknowledge that even the most open dataset does no good if it is not complete and of high quality. So any collection and delivery system for this data must be able to motivate the significant effort it will take to collect, verify, and maintain it. 

* **Why would people contribute observations to Griddly?**

    Because it's fun and satisfying, and because you get paid. Coloring in uncharted regions of the grid is oddly rewarding for the right kind of person.



* Distribution 101
* Gridspotter's Guide
* Design and Development Guide

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

* What are the risks and potential downsides of this project? What is the worst that could happen?

    > Your scientists were so preoccupied with whether or not they could, they didn’t stop to think if they should.

* Why does griddly have a commercial component? Why not adopt a fully open model like OpenStreetMap or Wikipedia?

* Can't Google just do this?

* Isn't this a perfect job for computer vision and deep learning? Why do we need people to go out and collect the data at all?

## Menagerie
