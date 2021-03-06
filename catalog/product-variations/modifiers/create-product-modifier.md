# Create Product Modifier

{% api-method method="post" host="https://api.moltin.com" path="/v2/variations/:variationId/options/:optionId/modifiers" %}
{% api-method-summary %}
Create a new product modifier
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="variationId" type="string" required=true %}
The **ID** of the variation belonging to this modifier.
{% endapi-method-parameter %}

{% api-method-parameter name="optionId" type="string" required=true %}
The **ID** of the option belonging to the modifier.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
The Bearer token used to grant access to the API.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="type" type="string" required=false %}
Represents the type of object being created \(should be **modifier**\).
{% endapi-method-parameter %}

{% api-method-parameter name="modifier\_type" type="string" required=false %}
`price_increment`, `price_decrement`, `price_equals`, `sku_builder`, `slug_builder`, `description_equals`, `description_prepend`, `description_append`, `commoditytype`, `name_equals`, `name_prepend`, `name_append`, `slug_equals`, `slug_append`, `sku_equals`, `sku_prepend`, `sku_append`, `status`
{% endapi-method-parameter %}

{% api-method-parameter name="value" type="string" required=false %}
A payload specific to the type of modifier.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "data": {
        "type": "product-variation",
        "id": "0c02ca9f-27be-48a8-89d9-cd7c30699343",
        "name": "Colour",
        "options": [
            {
                "id": "9000b3bb-4626-4521-9b1a-e89def0ca44a",
                "name": "Blue",
                "description": "Our most popular color",
                "modifiers": [
                    {
                        "id": "74004ddf-4521-4d4b-8c86-04fcd45294b0",
                        "type": "name_equals",
                        "value": "Promotional product"
                    }
                ]
            }
        ],
        "relationships": {
            "options": {
                "data": [
                    {
                        "type": "option",
                        "id": "9000b3bb-4626-4521-9b1a-e89def0ca44a"
                    }
                ]
            }
        }
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl -X "POST" https://api.moltin.com/v2/variations/:variationId/options/:optionId/modifiers \
     -H "Authorization: Bearer XXXX" \
     -H "Content-Type: application/json" \
     -d $'{
      "data": {
        "type": "modifier",
        "modifier_type": "name_equals",
        "value": "Promotional product"
      }
    }'
```
{% endtab %}
{% endtabs %}

