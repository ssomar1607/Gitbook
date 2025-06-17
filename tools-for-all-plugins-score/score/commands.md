# Commands

#### Clear stuff from Score

* Command: /score clear {player} {ACTIONBARS|ALL|COOLDOWNS|DELAYEDCOMMANDS|WHILE}

#### Clear cooldowns&#x20;

* Command: /score cooldowns clear {cooldown\_id} \[UUID]
  * {cooldown\_id}: Example -> EI:myitem:myactivator

#### Inspect loops, useful for debug

* Command: /score inspect-loop

Reload SCore variables, projectiles and hardness configurations

* Command: /score reload

Send a message to discord via webhook

* /score webhook \<url> \<true|false> \<message...>
  * \<url> : url for the webhook
  * \<true|false> : whether to let the executor know if a webhook message is to be performed or not
  * \<message...> : the message that will be sent by the target webhook

#### [Hardnesses ](../blocks-hardnesses.md)

#### [Particles ](../score-particles.md)

#### [Projectiles](https://docs.ssomar.com/executableitems/questions-or-guides/custom-projectiles-implementation)

#### [run-{}-command](../../)

#### [Variables ](../score-variables.md#score-global-variables)

