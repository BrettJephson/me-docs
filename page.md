---
description: >-
  This page details how the healthcare amounts breakdown is handled in Connect
  Express (Verifone POS).
---

# Healthcare Support

{% include "../../../.gitbook/includes/enter-amount-simple.md" %}

***

{% columns %}
{% column width="33.33333333333333%" %}
<figure><img src="../../../.gitbook/assets/healthcare_other_options (2).png" alt=""><figcaption></figcaption></figure>
{% endcolumn %}




{% column width="66.66666666666667%" %}
#### **Description**

Merchant is prompted to select a transaction option.

Healthcare option is only enabled when the business type is set to `Healthcare` and at least one of the healthcare amount categories in enabled in VPOS.

#### **Merchant/Customer action**

Selecting an `Healthcare` option will take the merchant to the Healthcare breakdown screen.

#### **Configuration Parameters**

`Merchant.MerchantBusinessType` - To enable Healthcare options, merchant business type should be set to 2 (Healthcare).

`Application.healthcare_enable_prescription` - When enabled, the healthcare amount breakdown includes prescription category.

`Application.healthcare_enable_vision` - When enabled, the healthcare amount breakdown includes vision category.

`Application.healthcare_enable_clinic` - When enabled, the healthcare amount breakdown includes clinic category.

`Application.healthcare_enable_dental` - When enabled, the healthcare amount breakdown includes dental category.
{% endcolumn %}
{% endcolumns %}

***

{% columns %}
{% column width="33.33333333333333%" %}
<figure><img src="../../../.gitbook/assets/healthcare_breakdown_init.png" alt=""><figcaption><p>Healthcare breakdown</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/healthcare_prescription_enter.png" alt=""><figcaption><p>Entering amount in category</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/healthcare_breakdown_updated.png" alt=""><figcaption><p>Updated healthcare amount breakdown</p></figcaption></figure>
{% endcolumn %}

{% column width="66.66666666666667%" %}
#### **Description**

The total transaction amount entered on the initial screen is displayed here. As the merchant selects each of the category and updates the amount the remaining amount gets distributed accordingly.

#### **Merchant/Customer action**

Merchant distributes the total transaction amount in the corresponding healthcare categories.

Selecting any category, would open up a numeric pad to enter amount.

Updating the amount in any healthcare category automatically reallocates the corresponding amount from the non-healthcare portion to that category.

#### **Configuration Parameters**

`Merchant.MerchantBusinessType` - To enable Healthcare options, merchant business type should be set to 2 (Healthcare).

`Application.healthcare_enable_prescription` - When enabled, the healthcare amount breakdown includes prescription category.

`Application.healthcare_enable_vision` - When enabled, the healthcare amount breakdown includes vision category.

`Application.healthcare_enable_clinic` - When enabled, the healthcare amount breakdown includes clinic category.

`Application.healthcare_enable_dental` - When enabled, the healthcare amount breakdown includes dental category.
{% endcolumn %}
{% endcolumns %}

***

{% columns %}
{% column width="33.33333333333333%" %}
<figure><img src="../../../.gitbook/assets/healthcare_other_options_after_allocation.png" alt=""><figcaption><p>Other options after healthcare amounts allocation</p></figcaption></figure>
{% endcolumn %}

{% column width="66.66666666666667%" %}
#### **Description**

Initiating a transaction after healthcare amount allocation.

#### **Merchant/Customer action**

After allocating the amounts in their categories the merchant has the option to to hit `Card` to proceed with a sale, or to hit `Other` to proceed with other eligible options such as refunds, manual entry flow or pre-authorization (if enabled).

#### **Configuration Parameters**

`Merchant.MerchantBusinessType` - To enable Healthcare options, merchant business type should be set to 2 (Healthcare).

`Application.healthcare_enable_prescription` - When enabled, the healthcare amount breakdown includes prescription category.

`Application.healthcare_enable_vision` - When enabled, the healthcare amount breakdown includes vision category.

`Application.healthcare_enable_clinic` - When enabled, the healthcare amount breakdown includes clinic category.

`Application.healthcare_enable_dental` - When enabled, the healthcare amount breakdown includes dental category.
{% endcolumn %}
{% endcolumns %}
