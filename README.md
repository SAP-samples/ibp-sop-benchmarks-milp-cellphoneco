# SAP-samples/repository-template
This default template for SAP Samples repositories includes files for README, LICENSE, and .reuse/dep5. All repositories on github.com/SAP-samples will be created based on this template.

# Containing Files

1. The LICENSE file:
In most cases, the license for SAP sample projects is `Apache 2.0`.

2. The .reuse/dep5 file: 
The [Reuse Tool](https://reuse.software/) must be used for your samples project. You can find the .reuse/dep5 in the project initial. Please replace the parts inside the single angle quotation marks < > by the specific information for your repository.

3. The README.md file (this file):
Please edit this file as it is the primary description file for your project. You can find some placeholder titles for sections below.

# Mixed-Integer Linear Programming (MILP) Benchmarks Based on a Multilevel Supply Chain of a Fictive Cellphone Company

<!--- Register repository https://api.reuse.software/register, then add REUSE badge:
[![REUSE status](https://api.reuse.software/badge/github.com/SAP-samples/REPO-NAME)](https://api.reuse.software/info/github.com/SAP-samples/REPO-NAME)
-->

## Description
The underlying benchmark instances model the supply chain of a fictive company producing and selling cellphones and accessories of different types. The instances are formulated as typical mixed-integer linear optimization problems in the standard MPS format.

### Detailed Scenario Description
The planning horizon is subdivided into time periods (also called time buckets) of one week. A network of different locations such as warehouses, factories, distribution centers and customers with a flow of products (components and final products) is the basis. After procurement of components and transport to the factory, the final products are produced consuming the components and additional restricted resources. Via a main distribution center, the products are further transported to local distribution centers where they are stored until they are delivered to satisfy customers' demand. Late delivery or non-delivery is possible. The objective is to minimize the sum of all costs.

### Instance Sets
Currently there are two sets of generated instances available. The variable and constraint names in these MPS files are generic, i.e., *x0, x1, x2, ...*, and *c0, c1, c2, ...*. 

**public_mps**: 
These instances differ mainly in the size of the network. They are named in the format *a_b_c_d.mps*. The first number *a* specifies the number of time periods, whereby the decisions of the first *b* periods must be discrete. The number of customers is given by *c*. The last number *d* is used as factor for lot sizes. For this set of instances exist also decompositions in *.dec*-format, which can be found in folder *public_dec*. They are decomposed according to time periods (b), locations (L), and products (P). The number of blocks is either determined by the number of different time periods, locations or products (0), or they are remerged in two (2) or four (4) blocks.

**vary_matrix_rhs_bounds**: 
These instances are similar to the above-mentioned *public_mps* instances, with specific values of *a=6*, *b=3*, *c=40*, and *d=20*. Accordingly, all these instances contain the same number of variables (27710, among which 400 are binary, 400 are general integers, and 26910 are continuous), the same number of constraints (16288), and the same ordering of these variables and constraints. Some entries of the constraint matrix, right-hand side vector, and variable upper bound vector vary across these 50 instances.

## Requirements
The benchmark instances are compressed in the .gz format, thus you will need a file archiver software to unpack them. Furthermore, you will need a mathematical solver program that is able to read and to solve files in the MPS format. For further information on the MPS format, please refer to this [website]( https://en.wikipedia.org/wiki/MPS_(format)).

## Download and Installation
Download and unpack the archive files. Then try to solve the resulting .mps files with a mathematical programming solver.

## Known Issues
No known issues.

## How to obtain support
[Create an issue](https://github.com/SAP-samples/<repository-name>/issues) in this repository if you find a bug or have questions about the content.
 
For additional support, [ask a question in SAP Community](https://answers.sap.com/questions/ask.html).

## Contributing
If you wish to contribute code, offer fixes or improvements, please send a pull request. Due to legal reasons, contributors will be asked to accept a DCO when they create the first pull request to this project. This happens in an automated fashion during the submission process. SAP uses [the standard DCO text of the Linux Foundation](https://developercertificate.org/).

## License
Copyright (c) 2023 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSE) file.
