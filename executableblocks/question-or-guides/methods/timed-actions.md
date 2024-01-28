# Timed actions

In this page you will learn how to timer stuff to happen in your block, for example:

* Summoning an item each "x" second
* Triggering an activator and displaying the cooldown on top of the block
* Or executing whatever you want and siplaying it on the block.

## Method

### Variable

* You first have to create a variable, let's call this timer
  * ![](<../../../.gitbook/assets/image (331).png>)
  * ![](<../../../.gitbook/assets/image (368).png>)
  * ![](<../../../.gitbook/assets/image (90).png>)
  * TYPE: NUMBER because it it will be a TIMER, so it is an integer value.
  * ![](<../../../.gitbook/assets/image (243).png>)
  * ![](<../../../.gitbook/assets/image (376).png>)

### TITLE

*   Go to Title features and display the variable there using the placeholder %var\_\<variablename>\_int%

    * ![](<../../../.gitbook/assets/image (301).png>)
    * ![](<../../../.gitbook/assets/image (283).png>)



### LOOP ACTIVATOR

* Now create a LOOP activator with variableModification timer -1 and placeholderCondition %var\_timer% GREATER than 0.
  * ![](<../../../.gitbook/assets/image (311).png>)
  * ![](<../../../.gitbook/assets/image (339).png>)
  * ![](<../../../.gitbook/assets/image (314).png>)

### ACTION

* Here is UP TO YOU, and will depend on your needs, in this case let's make a couple of examples
  *   RIGHT CLICK and take an ITEM

      * activator RIGHT CLICK
      * placeholderCondition %var\_timer% EQUALS 0
      * command:&#x20;
        * execute in <<%block\_world%>> run summon item %block\_x% %block\_y%+1 %block\_z% {Item:{id:"minecraft:IDOFTHEITEM",Count:1b\}}
      * variableModification: timer SET 10


  * Each time the timer goes to 0 summon an item
    * activator LOOP
    * placeholderCondition %var\_timer% EQUALS 0
    * command:&#x20;
      * execute in <<%block\_world%>> run summon item %block\_x% %block\_y%+1 %block\_z% {Item:{id:"minecraft:IDOFTHEITEM",Count:1b\}}
    * variableModification: timer SET 10
