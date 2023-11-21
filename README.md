
# GPT-Commerce

GPT-Commerce allows you to create GPTs in OpenAI that turns your GPT into an _"AI-based E-Commerce system"_,
allowing users to purchase products by writing things such as:

* _"What products do you have?"_
* _"How much is your 'xyz' product?"_
* _"I want to buy 'xyz'"_
* Etc ...

## Installation

You can use Manage/Endpoints and filter on _"openapi"_ for the to invoke it with a filter of _"gpt-commerce/public"_.
Then copy the OpenAPI specification link, and paste into a custom GPT as an _"action"_.

In order to make your GPT perform correctly you'll have to add an instruction to it resembling the following:

> If I tell you I want to purchase something, then unless you know the product I want, ask me what product,
> for then to lookup the price_reference using my products GET action, and pass in the price_reference into
> the purchase action for then to display the returned link as a Markdown hyperlink.

## Administrating products

If you wish you can create another GPT which is private only for you, where you repeat the process from above except
you should use _"gpt-commerce"_ as your invocation filter to the `openapi` endpoint. This allows you to create another
GPT that only you can access allowing you to administrate your products using phrases such as:

* _"Change the price of product 'xyz' to 67.50"_
* _"Create a new product named 'qwerty' with a price of 99 and a price reference of 'price_xyz'"_
* _"Delete the product named 'xyz'"_
* Etc ...

To administrate your products in your private GPT you would probably want it to have a system message resembling the following:

> If I tell you to do CRUD operations towards my products, assume I want to use the products action.
> If I provide you with incomplete information, ask me questions until you've got everything you need.
> If my endpoint don't return anything, then inform me that nothing was returned.

