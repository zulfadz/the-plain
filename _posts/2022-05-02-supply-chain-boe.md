---
layout: post
title: "Constructing a supply chain index"
comments: true
description: "Replicating BOE"
keywords: "dummy content"
---


The Bank of England[^1] has this interesting chart in its Monetary Policy Report:

### Image
<img src="https://raw.githubusercontent.com/zulfadz/zulfadz.github.io/master/pictures/BOE.png" width="400" height="400" />

which turns out to be pretty easy to replicate following the instructions from the footnote.[^2] Below is the replication code in eviews:


```html
for %y backlog inputprice_
stockfinished stockpurchase delivery2
	equation eq{%y}.ls {%y} c neworder
	eq{%y}.makeresid res_{%y}
next


group pca res_backlog res_inputprice _
res_stockfinished res_stockpurchase_
res_delivery2

freeze(pca_table) pca.pcomp

pca.makepcomp(eigval=eval, eigvec=evec) c1 c2 c3

```

<div class="divider"></div>


### Findings


Note that there is another [supply chain index](https://libertystreeteconomics.newyorkfed.org/2022/03/global-supply-chain-pressure-index-march-2022-update/) which is similar, except that it uses more information by allowing for cross-country linkages and more measures of transportation costs.

Footnote:

[^1]: [Monetary Policy Report February 2022](https://www.bankofengland.co.uk/-/media/boe/files/monetary-policy-report/2022/february/monetary-policy-report-february-2022.pdf).
[^2]: Make sure to invert the delivery times. Thanks to my friend Eilyn for pointing this out.





