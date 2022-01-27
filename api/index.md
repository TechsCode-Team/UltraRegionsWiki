## Usage
The API of **Ultra Regions** can be used to make addons for the marketplace. To use the API the Ultra Regions jar and the Spigot jar must be added to the library of the workspace. Your main class should extend `Flag`.
<br>

## Initialization
To make the flag work the you first have to add the following code:
```java
public class FlagName extends Flag {
	public FlagName(UltraRegions plugin) {
		super(plugin, "FLAG_NAME");
	}
```
<br>

## Get Name
The next thing to add is the flag name.
```java
public String getName() {
	return "Flag Name";
}
```
<br>

## Get Description
This will get the description your flag will have in the selection gui.
```java
public String[] getDescription() {
	return new String[] { "Lore Description" };
}
```
The value can only be a string
<br>

## Get Material
This will return the icon the flag will have.
```java
public XMaterial geIcon() {
	return XMaterial.BARRIER;
}
```
<br>

## Get Default Value
This means when you did not add the flag it will be allowed or not.
```java
public FlagValue getDefaultValue() {
	return FlagValue.ALLOW;
}
```
<br>

## Player Specific Flag
This will indicate if the flag is player specific.
```java
public boolean isPlayerSpecificFlag() {
	return true;
}
```
<br>

## Event Handler
This is what will listen for a minecraft event that flag will run off. To find what events you can listen for, check the spigot [javadocs](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/package-summary.html).
```java
@EventHandler
public void ClassName(EventToListenFor e) {
 
    if (e.getPlayer() instanceof Player) {
            Player player = e.getPlayer();
            Optional<ManagedWorld> optional = this.plugin.getWorlds().find(player.getWorld());
            if (optional.isPresent()) {

				Your Code Here

			}

}
```
<br>

## addon.yml File
You need an addon.yml in order to convey 3 important peices of info about the plugin; who made it, what version the addon is, and its name.

```java
name: AddonTest
version: 1.0.0
author: Fedee
```

*Make sure the version is x.x.x and the name matches the jar file name and the upload name*
