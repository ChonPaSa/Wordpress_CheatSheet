# Wordpress Reference
## A compilation of some useful Wordpress Functions

- [Add Custom Logo Support](#add-custom-logo-support)

## Add Custom Logo Support

```php
// Add Logo support
     add_theme_support( 'custom-logo', array(
        'height'      => 100,
        'width'       => 400,
        'flex-height' => false,
        'flex-width'  => true,
        'header-text' => array( 'site-title', 'site-description' ),
    ) );

// Link it in the frontend
      <a class="navbar-brand" href="<?php echo get_home_url();?>">
      <?php $custom_logo_id = get_theme_mod( 'custom_logo' );
         $custom_logo_url = wp_get_attachment_image_url( $custom_logo_id , 'full' );
         if ($custom_logo_url):?>
       <div class="navbar-brand-logo">
            <img src="<?php echo esc_url( $custom_logo_url );?>" alt=""> 
       </div>
        <?php else: ?> <?php bloginfo('name');?>
        <?php endif; ?>

      </a>

```

