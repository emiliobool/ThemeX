---
title: "Hooks"
layout: single
sitemap: false
permalink: /hooks
---
## theme 

``Example: hook-theme-after-head.liquid``

- head
- body
    - header
    - inside-header
    - footer
        - top-footer
        - bottom-footer

## product

``Example: hook-product-after-cart-button.liquid``

- images
    - image
    - thumbnails
        - thumbnail
- product
    - title
    - vendor
    - meta // prices and reviews badge
    - fields
    - top-description
    - description
    - cart-button
    - badges
    - timer
    - bottom-description
    - social
- related-products
- reviews

## collection

- container
    - inside-container
        - sidebar
        - main
            - description
            - header
            - products
                - product


### product-grid-item

- container
    - image-container
        - image
    - title
    - price-container
        - price
        - sale
    - reviews

## Cart
