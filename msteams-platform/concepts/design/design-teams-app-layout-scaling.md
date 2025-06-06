---
title: Design App Layout and Scaling
description: Learn about the layout and scaling for Microsoft Teams app such as layout design, scaling and responsive, and page orientation for desktop and mobile.
author: heath-hamilton
ms.localizationpriority: medium
ms.author: lajanuar
ms.topic: reference
ms.date: 02/06/2025
---
# Layout and scaling for your Microsoft Teams app

A grid layout allows your app to be consistent and guarantees recognizable relationships between design components. You can learn about your grid system and tips for scaling and zoom levels in your app to pass submission criteria.

Scaling and responsive design are essential to all Teams apps so that users can successfully interact with all interfaces with certainty. In order to pass Microsoft Teams Store review, the entire text must be visible and not truncated.

## Layout design

The 4-pixel base unit of grid allows components to scale consistently across all display sizes in Teams. In the following example, the corner radius of each button is 4 pixels.

:::image type="content" source="../../assets/images/design-guidelines/layout-pixel.png" alt-text="Example shows an example of pixels in layout." lightbox="../../assets/images/design-guidelines/layout-pixel.png":::

### Always follow the grid

:::image type="content" source="../../assets/images/design-guidelines/follow-grid.png" alt-text="Example shows the pixels in every dimension and space.":::

### Make it responsive

:::image type="content" source="../../assets/images/design-guidelines/make-it-responsive.png" alt-text="Example shows the guideline for responsive layout.":::

### Use white space

:::image type="content" source="../../assets/images/design-guidelines/use-white-space.png" alt-text="Example shows the usage of white space.":::

## Scaling and responsive

### Mobile

Mobile designs must be 320 pixels.

:::image type="content" source="../../assets/images/design-guidelines/responsive-mobile.png" alt-text="Example shows a responsive layout on mobile.":::

### Desktop

The minimum size for desktop is 550 pixels.

##### Example for 550 pixels

:::image type="content" source="../../assets/images/design-guidelines/responsive-minimum.png" alt-text="Example shows the minimum responsive layout on desktop.":::

##### Example for 2560 pixels

:::image type="content" source="../../assets/images/design-guidelines/responsive-desktop.png" alt-text="Example shows a responsive layout on desktop.":::

## Page orientation

### Mobile

> [!NOTE]
> Apps in Teams mobile support both landscape and portrait mode.

#### Portrait mode

:::image type="content" source="~/assets/images/design-guidelines/mobile-portrait-mode.png" alt-text="Example shows a portrait mode page orientation in Teams mobile.":::

#### Landscape mode

:::image type="content" source="~/assets/images/design-guidelines/mobile-landscape-mode.png" alt-text="Example shows a landscape mode page orientation in Teams mobile.":::

## Best practices

:::row:::
   :::column span="":::
:::image type="content" source="../../assets/images/design-guidelines/word-wrap-zoom-do.png" alt-text="Example shows a word wrap so that the text is legible at all zoom levels.":::

#### Do: Use word wrap so that text is legible at all zoom levels

Avoid text overlap and truncation.

   :::column-end:::
   :::column span="":::
:::image type="content" source="../../assets/images/design-guidelines/word-wrap-zoom-dont.png" alt-text="Example shows overlap of text and buttons that may not meet accessibility standards.":::

#### Don’t: Let text and buttons shift and overlap as zoom level changes

Overlapping text and buttons might not meet our accessibility standards.

   :::column-end:::
:::row-end:::

:::row:::
   :::column span="":::
:::image type="content" source="../../assets/images/design-guidelines/word-wrap-width-do.png" alt-text="Example shows a word wrap so that the text is legible at all width.":::

#### Do: Use word wrap so that text is legible at all widths

Avoid truncation with reflow, prioritizing call to actions (CTAs), and action items.

   :::column-end:::
   :::column span="":::
:::image type="content" source="../../assets/images/design-guidelines/word-wrap-width-dont.png" alt-text="Example shows that the text and CTAs aren't usable without word wrap.":::

#### Don’t: Let text or CTAs get cut off or become illegible as window width changes

Without word wrapping, the text and CTAs aren't usable.

   :::column-end:::
:::row-end:::

:::row:::
   :::column span="":::
:::image type="content" source="../../assets/images/design-guidelines/legible-scale-do.png" alt-text="Example shows a responsive design to avoid overlap at zoom level.":::

#### Do: Ensure your app is legible at 200% scale

Use responsive design to avoid text overlap and truncation.

   :::column-end:::
   :::column span="":::
:::image type="content" source="../../assets/images/design-guidelines/legible-scale-dont.png" alt-text="Example shows a truncated content at zoom level.":::

#### Don’t: Truncate and cut off content at any zoom level

It's recommended to test up to 200% zoom.

   :::column-end:::
:::row-end:::

:::row:::
   :::column span="":::
:::image type="content" source="../../assets/images/design-guidelines/text-colors-do.png" alt-text="Example shows how the text should be visible and accessible for users.":::

#### Do: Text and colors for accessibility

The entire text must be visible and used for all users, meaning that it must exceed certain color ratios, depending on its usage. To check your contrast levels, check out the WebAIM contrast checker.

   :::column-end:::
   :::column span="":::
:::image type="content" source="../../assets/images/design-guidelines/text-colors-dont.png" alt-text="Example shows a text that doesn't meet the contrast standards.":::

#### Don’t: Submit your app with text that doesn’t pass contrast standards

Teams apps need to be accessible to all users with any level of visual impairment or disability. Submissions with inaccessible text aren't accepted.

   :::column-end:::
:::row-end:::

:::row:::
   :::column span="":::
:::image type="content" source="../../assets/images/design-guidelines/resolution-do.png" alt-text="Example shows a resolution to avoid overlap and truncation.":::

##### Do: Test your app at 1920 x 1080 resolution

Avoid text overlap and truncation.

   :::column-end:::
   :::column span="":::
:::image type="content" source="../../assets/images/design-guidelines/resolution-dont.png" alt-text="Example shows a bad resolution that doesn't meet the standards.":::

##### Don’t: Submit your app for review without testing at Teams default resolution

Your app might not pass the submission process if there are issues at 1920 x 1080 resolution.

   :::column-end:::
:::row-end:::

:::row:::
   :::column span="":::
:::image type="content" source="../../assets/images/design-guidelines/responsive-mobile-do.png" alt-text="Example shows mobile app responsiveness.":::

##### Do: Test mobile app for responsiveness

Mobile view of your app must be responsive, similarly to the narrowest responsive breakpoint of a web app.

   :::column-end:::
   :::column span="":::
:::image type="content" source="../../assets/images/design-guidelines/responsive-mobile-dont.png" alt-text="Example shows cut off or illegible text on mobile app.":::

##### Don’t: Allow truncation on your mobile app

Nothing must be cut off or illegible on your mobile app.

   :::column-end:::
:::row-end:::

:::row:::
   :::column span="":::
:::image type="content" source="../../assets/images/design-guidelines/headers-do.png" alt-text="Example shows the headers that are legible at all zoom levels.":::

##### Do: Ensure headers are always legible at all zoom levels

If the headers truncate, use a tooltip so that users can read headers by hovering.

   :::column-end:::
   :::column span="":::
:::image type="content" source="../../assets/images/design-guidelines/headers-dont.png" alt-text="Example shows a truncated header without a hover feature.":::

##### Don’t: Truncate headers without a hover feature

Your app won't pass Teams submission if it has illegible headers without hover functionality.

   :::column-end:::
:::row-end:::

## See also

[Page orientation FAQ](../../teams-faq.md#page-orientation)
