# Mention Me Referral Tag

**Add Mention Me's referral programme to your store via Google Tag Manager. One template, five tag types.**

This Google Tag Manager template installs the Mention Me referral tag on the five pages where it runs: product, checkout, post-purchase, landing, and dashboard. Pick a tag type, map your data layer values into the fields, and the template injects the matching Mention Me script for that page.

## Features

- **One template, five tag types**: Product, Checkout (referee), Post-purchase (referrer), Landing, Dashboard
- **Live and Test environments**: switch between production and sandbox (`tag-demo.mention-me.com`) with a single radio
- **Customer data passthrough**: name, email, customer ID, phone, segment fed straight into the tag
- **Order and product context**: pass order ID, total, currency, coupon, products array, basket value, and product attributes (id, sku, name, price)
- **Locale-aware**: defaults to `en_GB`, override per tag for international stores
- **No coding required**: every field accepts a GTM variable via the built-in picker

## Tag Types

### Product page
Adds the Mention Me share widget to product detail pages so customers can refer friends to a specific product.

### Checkout (referee)
Renders the referee experience on the basket or checkout page so referred customers can claim their reward.

### Post-purchase (referrer)
Renders the referrer experience on the order confirmation page to invite customers to refer their friends.

### Landing page
Powers dedicated referral landing pages.

### Dashboard (customer account)
Renders the branded referral dashboard inside the customer account area so referrers can track their referral status, see rewards, and re-share. Fire on the page in your account/profile section where you want the dashboard to appear.

**[View Mention Me GTM setup guide](https://docs.mention-me.com/knowledge/tags/google-tag-manager)**

## Installation

### Prerequisites

1. Active Mention Me account ([sign up](https://app.mention-me.com/))
2. Your **partner code**. Find it at app.mention-me.com → Settings → Installation
3. Google Tag Manager installed on your website
4. A `<div id="mmWrapper"></div>` element on any page running the **Checkout**, **Post-purchase**, **Landing**, or **Dashboard** tag (GTM templates cannot inject DOM, so the div must be in your page markup before the tag fires)

### Setup Instructions

#### Step 1: Install the Mention Me Referral Tag template

1. In Google Tag Manager, go to the **Templates** section in the sidebar
2. Under **Tag Templates**, click **Search Gallery**
3. Search for **Mention Me Referral Tag**
4. Click **Add to workspace**

#### Step 2: Store your partner code as a Constant variable (recommended)

Partner code is the same across all five tag instances. Storing it once means a partner-code rotation is a single edit instead of five.

1. Go to **Variables** → **New** → **Constant**
2. Name it `Constant - Mention Me Partner Code`
3. Paste your partner code as the value
4. Save

#### Step 3: Create a tag

1. Go to **Tags** → **New**
2. Click **Tag Configuration**
3. Select **Mention Me Referral Tag** from your templates
4. Configure the fields:

   **Required:**
   - **Partner code**: point at `{{Constant - Mention Me Partner Code}}`
   - **Environment**: `Live` for production, `Test` for sandbox/QA
   - **Tag type**: pick `Product`, `Checkout`, `Post-purchase`, `Landing`, or `Dashboard`
   - **Locale**: defaults to `en_GB`; override for non-UK stores

   **Per tag type**: map your data layer values into the customer, order, and product fields shown for the selected tag type.

5. **Triggering**: fire on the matching page (e.g. Post-purchase tag fires on order confirmation pages, Product tag on product detail pages).

#### Step 4: Publish and test

1. Click **Save**
2. Use **GTM Preview Mode** to walk through the customer journey
3. Verify the Mention Me widget renders on each page
4. Submit your GTM container

## Configuration

### Finding your partner code

1. Sign in at app.mention-me.com
2. Go to **Settings** → **Installation**
3. Copy your **Partner code** and paste it into the GTM tag (or the `Constant - Mention Me Partner Code` Constant variable)

### Choosing an environment

- **Live**: sends events to `tag.mention-me.com` (production). Use on your live site.
- **Test**: sends events to `tag-demo.mention-me.com` (sandbox). Use in staging or for QA. Switch back to Live before going to production.

### Mapping data layer values

Every text field accepts a GTM variable via the built-in variable picker (`{{ }}`). Map your existing data layer values straight in. No transformations required. Phone numbers should be comma-separated with non-digit characters URL-encoded; segment values are capped at 50 characters.

## Browser Compatibility

- All modern browsers (Chrome, Firefox, Safari, Edge)
- Mobile browsers supported

## Performance

- Asynchronous script loading
- No blocking operations
- Minimal impact on page load

## Need Help?

- Documentation: [docs.mention-me.com / Google Tag Manager](https://docs.mention-me.com/knowledge/tags/google-tag-manager)
- Email: support@mention-me.com

## Resources

- [Mention Me homepage](https://www.mention-me.com/)
- [Mention Me documentation](https://docs.mention-me.com/)
- [Google Tag Manager Help](https://support.google.com/tagmanager)

## License

Apache-2.0. See [LICENSE](./LICENSE).

---

**Maintained by**: Mention Me
