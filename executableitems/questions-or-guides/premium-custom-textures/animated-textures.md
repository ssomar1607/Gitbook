# Animated textures



{% embed url="https://youtu.be/IAAj2a2dBQo" %}

{% hint style="info" %}
The same I said before, this requires previous knowledge, check [<mark style="color:blue;">**General Items**</mark>](general-items.md) for basic stuff
{% endhint %}

## Idea

* I'll make a rainbow sword, it will have 6 states, so 6 textures, each one moving a little the rainbow so it looks like it has a rainbow animation

### Textures

The texture size is something important because we must do some maths after creating them, I will make them 16x16 each one.

* They will have a order, so take care your animation makes sense for you.

![](<../../../.gitbook/assets/image (373).png>)

In this case they are 16x16, we have to make a texture file where they all are in a row, so it will have 16x(6x16) -> 16x96 , then put all them in row in correct order and it will look like this

![](<../../../.gitbook/assets/image (233).png>)

### Files

* Create your admin json file of the sword, then link it to the sub-admin, and when that sub-admin links the texture, you will have to add a new file, that will have a extension of **mcmeta** (if it doesn't have it, it won't work)

```json
{
	"animation":
		{"frametime": 4
	}
}
```

{% hint style="info" %}
frametime is how much frames it will show you in 20 ticks, in this case, the sword will display 1 frame per 5 ticks, I think that's fine, you can set a faster or lower speed as you want.
{% endhint %}

{% hint style="warning" %}
The name of the file .mcmeta should be equals as the name of the png texture, so it will look like this
{% endhint %}

![](<../../../.gitbook/assets/image (128).png>)

{% hint style="info" %}
Both files must be together, so if the animatedtexture<mark style="color:purple;">.png</mark> is inside "customtextures" folder, the animatedtexture.png<mark style="color:purple;">.mcmeta</mark> must be there too
{% endhint %}

* then just save your texture pack and test.

![](<../../../.gitbook/assets/2022-07-15 16-52-08.gif>)

* And that's it, make the thing you would want, it is the same for blocks if you want animated blocks. I hope you understood everything and if have any question (that wasn't explained in the last tutorials) feel free to ask it in Discord. Have a nice day !!
