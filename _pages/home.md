---
title: "Guide"
layout: single
sitemap: false
permalink: /
---

## Setup



## Facebook Pixel Conversion
### Prior Version 1.4 

{% raw %}
```html
<!-- Facebook Pixel Code -->
{% if first_time_accessed %}
<script>
!function(f,b,e,v,n,t,s){if(f.fbq)return;n=f.fbq=function(){n.callMethod?
n.callMethod.apply(n,arguments):n.queue.push(arguments)};if(!f._fbq)f._fbq=n;
n.push=n;n.loaded=!0;n.version='2.0';n.queue=[];t=b.createElement(e);t.async=!0;
t.src=v;s=b.getElementsByTagName(e)[0];s.parentNode.insertBefore(t,s)}(window,
document,'script','https://connect.facebook.net/en_US/fbevents.js');

fbq('init', 'xxxxxxxxxxxx');

var content_ids = []

{% for line in checkout.line_items %}
  productId = {{line.variant_id | json}};
  content_ids.push(productId);
{% endfor %}

totalPrice = {{ checkout.total_price | money_without_currency }};
fbq('track', 'Purchase', {
   content_ids: content_ids,
   value: totalPrice,
   currency:'{{shop.currency}}',
   content_type: 'product'
});

</script>
<noscript><img height="1" width="1" style="display:none"
src="https://www.facebook.com/tr?id=xxxxxxxxxxx&ev=Purchase&cd[value]={{ checkout.total_price | money_without_currency }}&noscript=1"
/></noscript>
{% endif %}
<!-- End Facebook Pixel Code -->
```
{% endraw %}

### Hide Paypal Button on Checkout Page
```html
<script type="text/javascript">
(function(fn){
    var d = document;
    (d.readyState == 'loading') ? d.addEventListener('DOMContentLoad', fn) : fn();
})(function(){
    document.getElementById("paypal-express-checkout-btn").style.visibility = "hidden";
    var toHide = document.querySelectorAll('.alt-payment-list-container, .alternative-payment-separator');
    for(var i = 0; i < toHide.length; i++){
        toHide[i].style.display = 'none';
    }
});
</script>
```



## Updating




