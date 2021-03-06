---
layout: default
title: Argento upgrade instructions
description: Argento for Magento2 upgrade instructions
category: Argento
---

# Upgrade Instructions

### Version 1.3.0 - 1.3.1

This update changes markup of the homepage content to prevent "jumping" syles during
script initialization.

The main changes are:

 1. `slick-slider` class addded:

    ```diff
    - <div data-mage-init='{"slick": {...}}'>
    + <div class="slick-slider" data-mage-init='{"slick": {...}}'>
    ```

 2. `argento-tabs` class added:

    ```diff
    - <div data-mage-init='{"argentoTabs": {}}'>
    + <div class="argento-tabs" data-mage-init='{"argentoTabs": {}}'>
    ```

You can find updated homepage markup in our docs:

 - [Essence Homepage](/m2/argento/essence/page-structure/homepage/#whole-homepage-code)
 - [Flat Homepage](/m2/argento/flat/page-structure/homepage/#whole-homepage-code)
 - [Mall Homepage](/m2/argento/mall/page-structure/homepage/#whole-homepage-code)
 - [Pure2 Homepage](/m2/argento/pure2/page-structure/homepage/#whole-homepage-code)
 - [Luxury Homepage](/m2/argento/luxury/page-structure/homepage/#whole-homepage-code)
 - [Stripes Homepage](/m2/argento/stripes/page-structure/homepage/#whole-homepage-code)

### Version 1.2.0 - 1.3.0

 1. Backup all changes you've made
 2. Put the store to the maintenance mode
 3. [Unpack new Argento version][unpack_package] over the old one
 4. Run upgrades:

    ```bash
    # activate new modules
    php bin/magento module:enable Swissup_FeaturedAttributes Swissup_Rtl Swissup_ThemeEditorArgentoStripes

    # run upgrades
    php bin/magento setup:upgrade

    # regenerate static content
    rm -rf pub/static/_requirejs var/view_preprocessed pub/static/frontend/ pub/static/adminhtml/
    # for magento 2.2.x
    rm -rf pub/static/_requirejs var/view_preprocessed pub/static/frontend/ pub/static/adminhtml/ generated/code/

    php bin/magento setup:static-content:deploy en_US [your_locale]
    ```

5. That's all. You are now using Argento 1.3.0

### Version 1.1.0 - 1.2.0

 1. Backup all changes you've made
 2. Put the store to the maintenance mode
 3. [Unpack new Argento version][unpack_package] over the old one
 4. Run upgrades:

    ```bash
    # remove old easybanner css file
    rm app/code/Swissup/Easybanner/view/frontend/web/css/easybanner.css

    # activate new modules
    php bin/magento module:enable Swissup_SeoPager

    # run upgrades
    php bin/magento setup:upgrade

    # regenerate static content
    rm -rf pub/static/_requirejs var/view_preprocessed pub/static/frontend/ pub/static/adminhtml/
    # for magento 2.2.x
    rm -rf pub/static/_requirejs var/view_preprocessed pub/static/frontend/ pub/static/adminhtml/ generated/code/

    php bin/magento setup:static-content:deploy en_US [your_locale]
    ```

5. That's all. You are now using Argento 1.2.0

### Version 1.0.0 - 1.1.0

 1. Backup all changes you've made
 2. Put the store to the maintenance mode
 3. [Unpack new Argento version][unpack_package] over the old one
 4. Run upgrades:

    ```bash
    # activate new modules
    php bin/magento module:enable Swissup_Lightboxpro Swissup_SeoCore Swissup_SeoHtmlSitemap Swissup_SeoUrls

    # run upgrades
    php bin/magento setup:upgrade

    # regenerate static content
    rm -rf pub/static/_requirejs var/view_preprocessed pub/static/frontend/ pub/static/adminhtml/
    # for magento 2.2.x
    rm -rf pub/static/_requirejs var/view_preprocessed pub/static/frontend/ pub/static/adminhtml/ generated/code/

    php bin/magento setup:static-content:deploy
    ```

5. That's all. You are now using Argento 1.1.0

### Version 0.9.10 - 1.0.0

 1. Backup all changes you've made
 2. Put the store to the maintenance mode
 3. [Unpack new Argento version][unpack_package] over the old one
 4. Run upgrades:

    ```bash
    # activate new modules
    php bin/magento module:enable Swissup_Navigationpro

    # run upgrades
    php bin/magento setup:upgrade

    # regenerate static content
    rm -rf pub/static/_requirejs var/view_preprocessed pub/static/frontend/Swissup
    php bin/magento setup:static-content:deploy
    ```

5. That's all. You are now using Argento 1.0.0

### Version 0.9.7 - 0.9.9

 1. Backup all changes you've made
 2. Put the store to the maintenance mode
 3. [Unpack new Argento version][unpack_package] over the old one
 4. Run upgrades:

    ```bash
    # activate new modules
    php bin/magento module:enable Swissup_ThemeEditorArgentoLuxury Swissup_HoverGallery

    # run upgrades
    php bin/magento setup:upgrade

    # regenerate static content
    rm -rf pub/static/_requirejs var/view_preprocessed pub/static/frontend/Swissup
    php bin/magento setup:static-content:deploy
    ```

5. That's all. You are now using Argento 0.9.9

### Version 0.9.6 - 0.9.7

 1. Backup all changes you've made
 2. Put the store to the maintenance mode
 3. [Unpack new Argento version][unpack_package] over the old one
 4. Cleanup Magento's cache:

    ```bash
    bin/magento cache:flush
    ```

 5. That's all. You are now using Argento 0.9.6

### Version 0.9.5 - 0.9.6

 1. Backup all changes you've made
 2. Put the store to the maintenance mode
 3. [Unpack new Argento version][unpack_package] over the old one
 4. Run upgrades:

    ```bash
    # activate new modules
    php bin/magento module:enable Swissup_ThemeEditorArgentoMall Swissup_Suggestpage Swissup_Ajaxpro

    # run upgrades
    php bin/magento setup:upgrade

    # regenerate static content
    rm -rf pub/static/_requirejs var/view_preprocessed pub/static/frontend/Swissup
    php bin/magento setup:static-content:deploy
    ```

5. That's all. You are now using Argento 0.9.6

### Version 0.9.4 - 0.9.5

 1. Backup all changes you've made
 2. Put the store to the maintenance mode
 3. [Unpack new Argento version][unpack_package] over the old one
 4. Run upgrades:

    ```bash
    # activate new modules
    php bin/magento module:enable Swissup_ThemeEditorArgentoPure2

    # run upgrades
    php bin/magento setup:upgrade

    # regenerate static content
    rm -rf pub/static/_requirejs var/view_preprocessed pub/static/frontend/Swissup
    php bin/magento setup:static-content:deploy
    ```

5. That's all. You are now using Argento 0.9.5


### Version 0.9.3 - 0.9.4

1. Backup all changes you've made
2. Put the store to the maintenance mode
3. [Unpack new Argento version][unpack_package] over the old one
4. Run upgrades:

   ```bash
   # run upgrades
   php bin/magento setup:upgrade

   # remove old FontAwesome files
   rm -rf app/code/Swissup/FontAwesome/etc/frontend app/code/Swissup/FontAwesome/view/frontend

   # regenerate static content
   rm -rf pub/static/_requirejs var/view_preprocessed
   php bin/magento setup:static-content:deploy
   ```

5. That's all. You are now using Argento 0.9.4

### Version 0.9.2 - 0.9.3

 1. Backup all changes you've made
 2. Put the store to the maintenance mode
 3. [Unpack new Argento version][unpack_package] over the old one
 4. Run upgrades:

    ```bash
    # run upgrades
    php bin/magento setup:upgrade

    # remove old css files
    rm app/code/Swissup/Ajaxsearch/view/frontend/web/css/ajaxsearch.css
    rm app/code/Swissup/Askit/view/frontend/web/css/askit.css

    # regenerate static content
    rm -rf pub/static/_requirejs var/view_preprocessed
    php bin/magento setup:static-content:deploy
    ```

 5. That's all. You can now install ArgentoFlat from
    `Backend > Swissup > Module Manager` page.

### Version 0.9.1 - 0.9.2

 1. Backup all changes you've made
 2. Put the store to the maintenance mode
 3. [Unpack new Argento version][unpack_package] over the old one
 4. Run upgrades:

    ```bash
    # activate new modules
    php bin/magento module:enable Swissup_Askit Swissup_ThemeEditor Swissup_ThemeEditorArgentoEssence
    # run upgrades
    php bin/magento setup:upgrade
    # regenerate static content
    rm -rf pub/static/_requirejs var/view_preprocessed
    php bin/magento setup:static-content:deploy
    ```

 5. Run Argento upgrades:
    1. Navigate to `Backend > Swissup > Module Manager`
    2. Find `ArgentoEssence` and click on actions link
    3. Click `Run Upgrades` option.

![Run Upgrades Link](/images/m2/argento/upgrade/run-upgrades.png)

### Version 0.9.0 - 0.9.1

 1. Backup all changes you've made
 2. Put the store to the maintenance mode
 3. [Unpack new Argento version][unpack_package] over the old one
 4. Run upgrades:

    ```bash
    bin/magento cache:flush
    bin/magento setup:upgrade

    # remove deprecated files
    rm -rf app/design/frontend/Swissup/argento-blank/Magento_LayeredNavigation

    # regenerate static content
    rm -rf pub/static/_requirejs var/view_preprocessed
    bin/magento setup:static-content:deploy
    ```

### Version 0.8.1 - 0.9.0

 1. Backup all changes you've made
 2. Put the store to the maintenance mode
 3. [Unpack new Argento version][unpack_package] over the old one
 4. Enable new extensions

    ```bash
    bin/magento module:enable\
        Swissup_Attributepages\
        Swissup_Easybanner

    bin/magento cache:flush
    bin/magento setup:upgrade

    # regenerate static content
    rm -rf pub/static/_requirejs
    rm -rf var/view_preprocessed
    bin/magento setup:static-content:deploy
    ```

 5. Update cms pages and blocks:

    Unfortunately this changes is very hard to apply in manual mode, so we recommend
    you to use automated [Argento Installer][run_installer] to backup previous
    and create new theme content.

    The main reasons for these massive changes:

    - We switched from our own simple 16 columns grid system to 12 columns
      Boostrap powered version
    - A new Easybanner content was added to the homepage instead of static banners
    - Brands slider improves it's settings for manual scrolling mode

[unpack_package]: /m2/argento/installation/#unpack-argento-package-into-magento-root-folder
[run_installer]: /m2/argento/installation/#setup-configuration-and-theme-content
