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
