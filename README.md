# Zip Code Mapping from Social Science Datasets

## Introduction

The goal of this repository is to provide an easy to use Python script which converts zip code data from primarily cross-sectional data. This script/method is for data that non-temporal (i.e., one observation per person). This is common for social science datasets that are survey based. 

## Pre-requisites

The ideal dataset that we want to convert from looks like the following,

obs, zip;
1, 98101;
2, 98106;
3, 98139;
4, 98101;

In this format, there are multiple observations for zip codes. We want the data to look like the following if we were going to map using the Census Bureau's Zip Code Tabulation Areas.

zip, count;
98101, 2;
98106, 1;
98139, 1;

From this data, you can use a join table in your favorite GIS software to plot a graduated color scheme of the number of responses for each zip code. The major issue is that this data looks terrible unless you have many ovservations for most zip codes. It is often preferred to upscale from the zip code resolution to the county level. To do this, you need a lookup table of which zip codes apply to which counties. The best table that I could find was from Nic Colley on [data.world](https://data.world/niccolley/us-zipcode-to-county-state). The dataset is open and requires a login, but is hosted here as lookup.csv.

The Jupyter notebook shows exactly how Python can be used to convert data into county data for mapping in GIS.
