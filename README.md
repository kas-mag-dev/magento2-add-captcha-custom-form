
# Magento 2: Adding CAPTCHA to a Custom Form

## Step 1: Create `config.xml`

Create the file `Vendor/Module/etc/config.xml` with the following content:

```xml
<default>
        <customer>
            <captcha>
                <shown_to_logged_in_user>
                    <custom_form>1</custom_form>
                </shown_to_logged_in_user>
                <always_for>
                    <custom_form>1</custom_form>
                </always_for>
            </captcha>
        </customer>
        <captcha translate="label">
            <frontend>
                <areas>
                    <custom_form>
                        <label>Custom Form</label>
                    </custom_form>
                </areas>
            </frontend>
        </captcha>
    </default>

```

## Step 2: Configure CAPTCHA in Admin Panel

1. Log in to the Magento Admin Panel.
2. Navigate to `Stores -> Configuration -> Customer -> Customer Configuration -> CAPTCHA`.
3. Configure the CAPTCHA settings. You should see a new form option labeled **Custom Form**.

## Step 3: Define the Layout XML for the Custom Route

Create the file `Vendor/Module/view/frontend/layout/yourroutid_index_index.xml` with the following content:

```xml

                <arguments>
                    <argument name="formId" xsi:type="string">custom_form</argument>
                </arguments>

```

---

By following these steps, you will enable CAPTCHA for your custom form in Magento 2.
