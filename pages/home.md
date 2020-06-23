---
layout: layouts/home.njk
title: Home
date: 2016-01-01T00:00:00.000Z
permalink: /
eleventyNavigation:
  key: Home
  order: 0
---
# Welcome

[Sukhi Grewal's](https://www.sukhikgrewal.com) soccer training site for parents and players.

Field and weather conditions under [Announcements](https://sclub.netlify.app/announcements/).

For more info on training or booking, use the [contact form](https://sclub.netlify.app/contact/), or click below to pay for your next two sessions.

<div id="paypal-button-container"></div>
<script src="https://www.paypal.com/sdk/js?client-id=sb&currency=USD" data-sdk-integration-source="button-factory"></script>
<script>
  paypal.Buttons({
      style: {
          shape: 'rect',
          color: 'gold',
          layout: 'horizontal',
          label: 'paypal',
          
      },
      createOrder: function(data, actions) {
          return actions.order.create({
              purchase_units: [{
                  amount: {
                      value: '100'
                  }
              }]
          });
      },
      onApprove: function(data, actions) {
          return actions.order.capture().then(function(details) {
              alert('Transaction completed by ' + details.payer.name.given_name + '!');
          });
      }
  }).render('#paypal-button-container');
</script>
