# Change-Function-from-D7-to-D9
Most of the Function are deprecated from Drupal 7 to Drupal 8 or 9


drupal_set_message(), drupal_get_message() functions removed.

    instead use:-
      \Drupal::service('messenger')->addMessage('Hello Drupal');
      
EntityManager has been split into 11 classes.

    instead use:-
        \Drupal::entityTypeManager()->getStorage('node')->load(1);
        More info:- Services like entity_type.manager, entity_type.repository, entity_display.repository etc to be used instead. 
        See change records for more info.
      
      
drupal_render() and drupal_render_root()  functions

    instead use:-
      \Drupal::service('renderer')->render($elements,$is_recursive_call);


node_load(), entity_load(), file_load() etc removed.

    instead use:-
      use \Drupal\node\Entity\Node;
      $node = Node::load(1);
      or
      $file = \Drupal::entityTypeManager()->getStorage('file')->load(1);
      
      
entity_view(), entity_view_multiple(), comment_view() etc removed.

    instead use:-
    Use entity view builder handler
      $builder = \Drupal::entityTypeManager()->getViewBuilder('node'); 
      $build = $builder->view($node, 'teaser');



format_date()
hook_date_formats()
hook_date_formats_alter()
system_get_date_format()
system_get_date_format() etc.

    instead use:-
    Use date.formatter service
      \Drupal::service('date.formatter')->format()
