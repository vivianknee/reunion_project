<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
    h1 {
        font-family: "Kanit", sans-serif;
        font-size: 30px;
        color: white;
    }
    select {
        -webkit-appearance:none;
        -moz-appearance:none;
        -ms-appearance:none;
        appearance:none;
        outline:0;
        box-shadow:none;
        border:0!important;
        background: #5c6664;
        background-image: none;
    }

    select:: -ms-expand {
        display: none;
    }
    
    p {
        text-align:center
    }
</style>

<html>
    <h1> Wishlist </h1>
        <p>Take a look at what you like!</p>
{
  "tasticType": "commercetools/ui/wishlist",
  "name": "commercetools UI wishlist",
  "icon": "list",
  "category": "Wishlist",
  "schema": [
    {
      "name": "Empty State Data",
      "fields": [
        {
          "label": "Page Title",
          "field": "pageTitle",
          "translatable": true,
          "type": "string"
        },
        {
          "label": "Empty State Image",
          "field": "emptyStateImage",
          "type": "media",
          "required": true
        },
        {
          "label": "Empty State Title",
          "field": "emptyStateTitle",
          "translatable": true,
          "type": "string"
        },
        {
          "label": "Empty State Subtitle",
          "field": "emptyStateSubtitle",
          "translatable": true,
          "type": "string"
        },
        {
          "label": "Call to Action Label",
          "field": "emptyStateCTALabel",
          "translatable": true,
          "type": "string"
        },
        {
          "label": "Call to Action Link",
          "field": "emptyStateCTALink",
          "type": "reference",
          "required": true
        }
      ]
    }
  ]
}

import React from 'react';
import { LineItem } from '@Types/wishlist/LineItem';
import WishList from 'components/commercetools-ui/wishlist';
import { useWishlist } from 'frontastic/provider';

const WishlistTastic = ({ data }) => {
  const { data: wishlist, removeLineItem } = useWishlist();

  const removeLineItems = async (item: LineItem) => {
    await removeLineItem(item.lineItemId);
  };

  return (
    <WishList
      pageTitle={data.pageTitle}
      emptyStateImage={data.emptyStateImage}
      emptyStateTitle={data.emptyStateTitle}
      emptyStateSubtitle={data.emptyStateSubtitle}
      emptyStateCTALabel={data.emptyStateCTALabel}
      emptyStateCTALink={data.emptyStateCTALink}
      items={wishlist}
      removeLineItems={removeLineItems}
    />
  );
};

export default WishlistTastic;