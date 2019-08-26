add_filter( 'hestia_header_wrapper_background_filter','your_child_theme_header_wrapper' );

function your_child_theme_header_wrapper( $args ) {

	if( is_category() ) {
		
		if ( function_exists('z_taxonomy_image_url') ) {
			$z_taxonomy_image_url = z_taxonomy_image_url();
			
			if ( ! empty($z_taxonomy_image_url) ) {
				return '<div data-parallax="active" class="header-filter" style="background-image: url(' . $z_taxonomy_image_url . ');" ></div>';
			}
		}
		
	}
	return $args;
}
