# dropdown-scroll-functionality
If you have a number of options in a select dropdown, it can be burdensome and push the options off the viewport. You can, however, add scroll options to allow users the intuitive ability to see more options.

## Tutorial
For detailed instruction's, view Solodev's [How to Add Scroll Functionality To Your Dropdowns](https://www.solodev.com/blog/web-design/how-to-add-scroll-functionality-to-your-dropdowns.stml) article.

## Demo
Try out a working example on [JSFiddle](https://jsfiddle.net/solodev/Lqf7ct5y/).

## HTML
The tutorial contains the following basic HTML markup.

```
<div class="header--nav col-lg-4">
      <ul class="list-unstyled mb-0 pl-0 d-lg-inline-block d-none float-right">
        <li>
          <div class="dropdown dropdown--scrollable">
            <button class="pointer dropdown-toggle dropdown-nav" type="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
              English<i class="fa fa-chevron-down fa-xs ml-2" aria-hidden="true" title="English languaged checked"></i>
            </button>
            <div class="dropdown-menu">
              <a class="dropdown-item up arrow" href="#"><i class="fa fa-chevron-up"></i></a>
              <div class="dropdown-menu__content" data-items="10" data-items-scroll="5">
                <a class="dropdown-item lang-select" href="#" aria-label="switch to Arabic language">Arabic</a>
                <a class="dropdown-item lang-select" href="" aria-label="switch to Bulgarian language">Bulgarian</a>
                <a class="dropdown-item lang-select" href="#" aria-label="switch to Czech language">Czech</a>
                <a class="dropdown-item lang-select" href="#" aria-label="switch to Chinese language">Chinese</a>
                <a class="dropdown-item check lang-select" href="#" aria-label="switch to English language">English</a>
                <a class="dropdown-item lang-select" href="#" aria-label="switch to French language">French</a>
                <a class="dropdown-item lang-select" href="#" aria-label="switch to German language">German</a>
                <a class="dropdown-item lang-select" href="#" aria-label="switch to Italian language">Italian</a>
                <a class="dropdown-item lang-select" href="#" aria-label="switch to Japanese language">Japanese</a>
                <a class="dropdown-item lang-select" href="#" aria-label="switch to Portuguese language">Portuguese</a>
                <a class="dropdown-item lang-select" href="#" aria-label="switch to Polish language">Polish</a>
                <a class="dropdown-item lang-select" href="#" aria-label="switch to Russian language">Russian</a>
                <a class="dropdown-item lang-select" href="#" aria-label="switch to Spanish language">Spanish</a>
              </div>
              <a class="dropdown-item down arrow" href="#" aria-label="scroll down to select"><i class="fa fa-chevron-down" aria-hidden="true" title="dropdown arrow"></i></a>
            </div>
          </div>
        </li>
      </ul>
</div>
```

## Javascript
The tutorial contains the following basic Javascript code:

```
    $('.dropdown--scrollable .dropdown-menu, .hero .tab-content .dropdown .dropdown-menu').click(function(e) {
      e.stopPropagation();
    });

    $('.dropdown--scrollable .dropdown-menu__content').each(function() {
      $(this).slick({
        infinite: false,
        vertical: true,
        slidesToShow: $(this).data('items'),
        slidesToScroll: $(this).data('items-scroll'),
        dots: false,
        prevArrow: $(this).parent().find('a.up'),
        nextArrow: $(this).parent().find('a.down'),
        responsive: [{
          breakpoint: 992,
          settings: {
            slidesToShow: 5,
            slidesToScroll: 1
          }
        }]
      });

      var carousel = $(this);

      $(this).parents('.dropdown--scrollable').on('click', 'button', function() {
        carousel.slick('refresh');
      })
    });
```

## CSS
All required CSS is contained with style.css

## External Resources
This tutorial includes the following third party resources.

```
<!-- Bootstrap CSS -->
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css" integrity="sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO" crossorigin="anonymous">
<!-- Font Awesome CSS -->
<link href="https://stackpath.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css" rel="stylesheet" integrity="sha384-wvfXpqpZZVQGK6TAh5PVlGOfQNHSoD2xbE+QkPxCAFlNEevoEH3Sl0sibVcOQVnN" crossorigin="anonymous">
<!-- Slick Slider CSS -->
<link rel="stylesheet" type="text/css" href="//cdn.jsdelivr.net/npm/slick-carousel@1.8.1/slick/slick.css"/>
<!-- jQuery first, then Popper.js, then Bootstrap JS -->
<script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.3/umd/popper.min.js" integrity="sha384-ZMP7rVo3mIykV+2+9J3UJ46jBk0WLaUAdn689aCwoqbBJiSnjAK/l8WvCWPIPm49" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/js/bootstrap.min.js" integrity="sha384-ChfqqxuZUCnJSK3+MXmPNIyE6ZbWh2IMqE241rYiqJxyMiZ6OW/JmZQ5stwEULTy" crossorigin="anonymous"></script>
<!-- Slick Slider Js -->
<script type="text/javascript" src="//cdn.jsdelivr.net/npm/slick-carousel@1.8.1/slick/slick.min.js"></script>
```