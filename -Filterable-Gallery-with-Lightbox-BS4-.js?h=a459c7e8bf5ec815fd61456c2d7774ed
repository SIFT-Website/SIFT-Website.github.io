// imagesLoaded PACKAGED v4.1.3
// https://imagesloaded.desandro.com
// fiterizr http://yiotis.net/filterizr/
// simplelightbox 1.12.0 https://github.com/andreknieriem/simplelightbox
$(document).ready(function(){
    $('.filtr-container').css('visibility','hidden');
    $('.filtr-controls').after('<div class="filtr-loading"></div>');
    
    // init filterizr when images are loaded
    options = {
        callbacks: {
      onFilteringEnd: function() {
            // only visible items
            var gall = $('.filtr-controls span.active').attr('data-filter');
            $('.filtr-item').each( function() {
                if($(this).css('opacity') != 0) {
                    $(this).find('a').attr('data-simplelightbox',gall);
                } else {
                    $(this).find('a').removeAttr('data-simplelightbox');
                }
            });
            // init simplelightbox
          //var lightbox = $('a[data-simplelightbox').simpleLightbox();
          //lightbox.destroy();
            var lightbox = $('a[data-simplelightbox="'+gall+'"]').simpleLightbox({
                showCounter : false,
                history : false,
                captionType : 'data',
                captionsData : 'caption'
            });
            lightbox.refresh();
           
      }
        },
        layout: 'sameWidth'
    }
    
    $('.filtr-container').imagesLoaded( function() {
        var filterizd = $('.filtr-container').filterizr(options);
        $('.filtr-container').css('visibility','visible');
        $('.filtr-loading').remove();
    });
    
    // active class for controls
    $('.filtr-controls').on('click','span',function(){
        $('.filtr-controls').find('span').removeClass('active');
        $(this).addClass('active');
    });
    
});

