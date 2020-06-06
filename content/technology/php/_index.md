+++
title = "PHP"
date = 2020-06-06T20:11:37+02:00
draft = true
+++

## Calling methods dynamically with a For loop

```php
class ICSEvent {

    private $userId;
    private $eventId;
    private $subject;
    private $description;

    function setUserId($userId){
        $this->userId = $userId;
    }
    function setEventId($eventId){
        $this->eventId = $eventId;
    }
    function setSubject($subject){
        $this->subject = $subject;
    }
    function setDescription($description){
        $this->description = $description;
    }
}

$ics_event = new ICSEvent();

$modified_fields = array();
$modified_fields['setUserId'] = 'userid231';
$modified_fields['setEventId'] = 'event84784';

/*
This foreach loop will call the methods of the ics_event that are placed in the modified_fields array. This is a good way of saving the methods to call in an array and then executing them in a for loop
*/
foreach ($modified_fields as $key => $value) {
    $ics_event->$key($value);
}

```

## Time Handling

```php

$currentTime = current_time('timestamp');

$countryTimeZones = [
    '17' => '0',
    '23' => '0',
    '24' => '0',
    '22' => '-1',
    '25' => '7'
];

$country = get_the_terms($postId, 'country');
$countryId = $country[0]->term_id;

$currentTime = current_time('timestamp') + ($countryTimeZones[$countryId ] * 3600);

$signUpStartTime = $signUpStart ? str_replace('/', '-', get_field('sign_up_start_time', $eventId)) . ':00' : null;

```