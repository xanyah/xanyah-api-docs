---
description: >-
  To allow users import existing data, we allow them to import variants from
  their existing system. The can import either a JSON or a CSV file.
---

# Variant imports

## Formatting the file

Each file must have a specific format in order to be well processed. To do so, we require each variant to have some attributes to prevent the data corruption.

### Required data

* `product_name` 
* `product_category` 
* `product_manufacturer` 
* `product_store` 
* `variant_original_barcode` 
* `variant_buying_price` 
* `variant_tax_free_price` 
* `variant_provider` 
* `variant_ratio` 

### CSV

The CSV file must have the following headers on its first line.

{% embed data="{\"url\":\"https://gist.github.com/sofianegargouri/db4a0238f1e8f64e1e39ec176819cbf2\",\"type\":\"rich\",\"title\":\"Example of variants import\",\"description\":\"Example of variants import · GitHub\",\"icon\":{\"type\":\"icon\",\"url\":\"https://gist.github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars3.githubusercontent.com/u/4323986?s=400&v=4\",\"width\":400,\"height\":400,\"aspectRatio\":1},\"embed\":{\"type\":\"reader\",\"html\":\"<script type=\\"text/javascript\\" src=\\"https://gist.github.com/db4a0238f1e8f64e1e39ec176819cbf2.js\\"></script>\",\"aspectRatio\":0},\"caption\":\"Example of CSV file\"}" %}

### JSON

The JSON must be an array of objects with the required keys.

{% embed data="{\"url\":\"https://gist.github.com/sofianegargouri/269dcfbb2fef391c5e67fd882503fad7\",\"type\":\"rich\",\"title\":\"Example of variants import\",\"description\":\"Example of variants import · GitHub\",\"icon\":{\"type\":\"icon\",\"url\":\"https://gist.github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars3.githubusercontent.com/u/4323986?s=400&v=4\",\"width\":400,\"height\":400,\"aspectRatio\":1},\"embed\":{\"type\":\"reader\",\"html\":\"<script type=\\"text/javascript\\" src=\\"https://gist.github.com/269dcfbb2fef391c5e67fd882503fad7.js\\"></script>\",\"aspectRatio\":0},\"caption\":\"Example of JSON file\"}" %}

{% api-method method="post" host="" path="/file\_imports" %}
{% api-method-summary %}
Creating a variant import
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to create a file import.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" required=true %}
multipart/form-data
{% endapi-method-parameter %}

{% api-method-parameter name="Expiry" type="integer" required=true %}
Authentication token expiry date
{% endapi-method-parameter %}

{% api-method-parameter name="Access-Token" type="string" required=true %}
Authentication token
{% endapi-method-parameter %}

{% api-method-parameter name="Client" type="integer" required=true %}
Authentication token client ID
{% endapi-method-parameter %}

{% api-method-parameter name="Token-Type" type="string" required=true %}
Authentication token type
{% endapi-method-parameter %}

{% api-method-parameter name="Uid" type="string" required=true %}
Authentication token user ID
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="file" type="object" required=true %}
The file to import
{% endapi-method-parameter %}

{% api-method-parameter name="store\_id" type="string" required=true %}
The ID of the store to import the variants to
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Import successfully created
{% endapi-method-response-example-description %}

```javascript

```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=422 %}
{% api-method-response-example-description %}
Either the store\_id param is missing, or the file isn't a CSV or JSON.
{% endapi-method-response-example-description %}

```javascript

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

