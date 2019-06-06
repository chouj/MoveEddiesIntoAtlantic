# What If moving all oceanic mesoscale eddies into the vast domain of the Atlantic Ocean ?

This idea results from a discussion with one of my colleagues who did not believe oceanic mesoscale eddies cover nearly a third of the ocean surface at any time. The data calculation such as summing up all the areas of eddies is effective but sometimes boring. Thus, how about visualizing it by gathering them together in one place ? The vast Atlantic Ocean covers about 29 percent of the Earth's water surface area according to [Wikipedia](https://www.wikiwand.com/en/Atlantic_Ocean), making it the perfect domain for this kind of demonstration. 

## Data
[Global Mesoscale Eddy Track Atlas Product released by AVISO](https://www.aviso.altimetry.fr/en/data/products/value-added-products/global-mesoscale-eddy-trajectory-product.html) (See its breif introduction [here](http://cioss.coas.oregonstate.edu/eddies/), including data structures.)

## Eddy Moving Strategy
- Generate property matrix for eddies already in the Atlantic Ocean. Use it as a eddy list for both the original ones that not need to move and those after moved.
- Generate property matrix for eddies outside the Atlantic Ocean which have to moved. So, a moving waiting list.
- Randomly generate a lon/lat coordinate for eddy center after moved.
- Diagnose whether the generated position fall within the region of the Atlantic Ocean and whether it is on land or not.
- Calculate the distances from generated coordinate to 1) the boundary of the Atlantic ocean, 2) the coastline and 3) all existing eddy circles (not eddy centers).
- Continue if the generated coordinate does not fall within any existing eddy circles.
- Find whether there are eddies in the moving waiting list that can be fit into the minimum distance calculated above.
- If so, move the largest one to the generated position. Then, keep moving until all eddies outside the Atlantic Ocean domain have been moved into the domain.

## Dependency
- Lon/Lat coordinate data for [the boundary of the Atlantic Ocean](http://www.marineregions.org/gazetteer.php?p=details&id=1902), including islands. Here's a [*.mat* version](https://github.com/chouj/MoveEddiesIntoAtlantic/raw/master/AtlanticOceanBoundary.mat).
- **[The M_Map toolbox](https://www.eoas.ubc.ca/~rich/map.html)** and associated Lon/Lat coordinate data **m_coasts.mat**
- [land_or_ocean.m](https://ww2.mathworks.cn/matlabcentral/fileexchange/45268-land_or_ocean-m)

## Compatibility
#### MATLAB Release Compatibility
Created with R2015a

## Acknowledgement
- [如何生成多个互不重叠的不同半径圆？](https://www.zhihu.com/question/53012468)

## Final Figure
[![19921014_MoveEddiesIntoAtlanticOcean](https://github.com/chouj/MoveEddiesIntoAtlantic/blob/master/19921014_MoveEddiesIntoAtlanticOcean.png?raw=true)]

## Support ME !

[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.me/Mesoscale)
[![Donate](https://img.shields.io/badge/Donate-WeChat-brightgreen.svg)](https://github.com/chouj/donate-page/blob/master/simple/images/WeChatQR.jpg?raw=true)
[![Donate](https://img.shields.io/badge/Donate-AliPay-blue.svg)](https://github.com/chouj/donate-page/blob/master/simple/images/AlipayQR.jpg?raw=true)
