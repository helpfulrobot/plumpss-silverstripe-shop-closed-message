# SilverStripe Shop Closed Message

Add-on module for SilverStripe shop that allows the shop to be temporarily closed with a message. Useful, for example, when taking a break from selling online.

## Requirements

 * [Shop module](https://github.com/burnbright/silverstripe-shop)

## Installation

```sh
composer require plumpss/silverstripe-shop-closed-message
```

## Usage

This module adds closed option and message fields to `SiteConfig` under Settings > Shop > Shop Closed.

Include `ClosedMessage` wherever you'd like the message to appear. If the shop is not closed, nothing will be output. For example, in the main template `Page.ss`:

```
<body>
	<div class="header">
		...
	</div>
	<% include ClosedMessage %>
	<div role="main">
		...
	</div>
</body>
```

If you do not want to allow orders to be placed, replace the use of `$Form` in your product page template with an include of `FormOrClosedMessage`:

```
<% include FormOrClosedMessage %>
```

You can create your own versions of `ClosedMessage.ss` and/or `FormOrClosedMessage.ss` in your theme's `templates/Includes` directory for complete control of the markup. 