# Defer Javascript

- This code will add `defer` attribute to all Javascript scripts except for JQuery scripts.

- Add this code to the wordpress `functions.php`.


```
// Defer all Javascript codes except for JQuery codes
// It won't defer Javascript codes when the user is logged in

function defer_parsing_of_javascript( $url ) {
    // do nothing if the user is logged in
    if ( is_user_logged_in() ) return $url; 
    // do nothing if the file is NOT JavaScript file
    if ( FALSE === strpos( $url, '.js' ) ) return $url;
    // do nothing if the file is JQuery file.
    if ( strpos( $url, 'jquery.js' ) ) return $url;
    // add defer attribute
    return str_replace( ' src', ' defer src', $url );
}
// add the function the script_loader_tag hook
add_filter( 'script_loader_tag', 'defer_parsing_of_javascript', 10 );
```
