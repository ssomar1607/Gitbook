---
description: >-
  This page is all about setting up a kill counter, a milestone system and a
  limit on how many times it would execute the activator
---

# Run commands after killing x amount of mobs



## 1) Create SCore variables



<figure><img src="https://imgur.com/ktpvy5T.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://imgur.com/cyk8yKt.png" alt=""><figcaption></figcaption></figure>

## 2) Set the values of the two SCore variables

* Set the `TYPE` to `NUMBER`

![](<../../../.gitbook/assets/image (12) (1).png>)

* Set the `FOR` to `PLAYER`

![](<../../../.gitbook/assets/image (13) (1).png>)

* Set the `Default Value` to `0`

![](<../../../.gitbook/assets/image (14) (1).png>)

* Save the settings

![](<../../../.gitbook/assets/image (15) (1).png>)

## 4) Create the first EE event

<figure><img src="../../../.gitbook/assets/image (5) (1) (1).png" alt=""><figcaption></figcaption></figure>

* This will add value to the KILL-COUNT SCore variable every time we kill a mob

## 5) Create a PLAYER\_KILL\_ENTITY activator

<figure><img src="../../../.gitbook/assets/image (6) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (7) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (8) (1) (1).png" alt=""><figcaption></figcaption></figure>

### > Set detailed entities

<figure><img src="../../../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

### > Add the command

<figure><img src="../../../.gitbook/assets/image (11) (1) (1).png" alt=""><figcaption></figcaption></figure>

`score variables modification player KILL-COUNT 1 %player%`



### > Create a placeholder condition

For this one, let's say, we want to do a 10-kill milestone.

<figure><img src="../../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

### > Create another placeholder condition

<figure><img src="../../../.gitbook/assets/image (47).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (48).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (49).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (50).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (51).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (52).png" alt=""><figcaption></figcaption></figure>

## 6) Create the second EE event

<figure><img src="../../../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

## 7) Create a PLAYER\_KILL\_ENTITY activator

<figure><img src="../../../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

### > Set detailed entities

<figure><img src="../../../.gitbook/assets/image (46).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>

### > Add the commands

<figure><img src="../../../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

* `score variables set player KILL-COUNT 0 %player%`
* `score variables modification player OBJ-COUNT 1 %player%`

{% hint style="info" %}
This is where you start adding commands like `ei give %player% diamond 1` for custom rewards
{% endhint %}

The OBJ-COUNT SCore variable will be explained later in the guide

### > Create a placeholder condition

<figure><img src="../../../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (34).png" alt=""><figcaption></figcaption></figure>

To why part2 is equals to 9, unlike the milestone/objective/action counter method used in executable items, executable events does not have a proper in-built variable system and running score variables commands doesn't finish fast enough for the next activators to run.

What happens actually in the technical side is, when the activator runs, it sees the placeholder as 0 then turns it into 1. when the activator runs the activator agian, it sees 1 then turns it into 2.

<figure><img src="../../../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>

### > Create another placeholder condition

<figure><img src="../../../.gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (37).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

The number here must be the same as the one in the previous activator

<figure><img src="../../../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>

