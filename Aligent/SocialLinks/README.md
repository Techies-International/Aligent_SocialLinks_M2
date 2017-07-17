# Aligent SocialLinks Magento 2 Module

This module will allow you to specify links to the social accounts for a particular website.

## Installing

*Need to make sure the correct repository is added to the composer.json file, so the following require will resolve as expected*

`composer require aligent/sociallinks`

## Enable the module

`bin/magento module:enable Aligent_SocialLinks`

An instance of the Widget will be automatically created and assigned to the currently active theme.

## Adding module to page

The module will then need to be added to a page/s using XML. The following line, place inside a `referenceContainer` will
achieve this

`<block class="Aligent\SocialLinks\Block\SocialLinks" name="aligent.social.links" as="aligentSocialLinks"/>`

## Styling the links

The links aren't styled at all, and will just display the name of the social network inside an <a> tag. This makes it
very straightforward for you to use any styling you would like, along with any icons.

The links are contained in the following HTML structure

```
<div class="aligent-social-links-container">
    <div class="aligent-social-links-inner-container">
        <ul class="aligent-social-links">
            <li>
                <a class="aligent-social__link social__link--facebook" href="http://www.facebook.com/username">
                    <span class="aligent-social__text">Facebook</span>
                </a>
            </li>
        </ul>
    </div>
</div>
```

## Using your own custom template

If you would like to overwrite the default template, and display the links in another way, you can do that very easily.

Create a new `social-links.phtml` file in your your themes folder inside `design`, E.g.
`app/design/frontend/Magento/{your_theme_name}/Aligent_SocialLinks/templates/social-links.phtml`

Inside the template `$block` will be an instance of `Aligent\SocialLinks\Block\SocialLinks`, and you simply call
`$block->getUrls()` to get the URLs set in the database