# combobulator
Full service configuration management and validation for Mudlet packages

## What is the combobulator?

The combobulator is the fever dream of a devops/configuration management/MUD nerd. I see so many packages reinventing the wheel for storing, referencing, saving, loading, and validating configuration and I know from experience that it takes a lot of time and energy to lay out your configuration data, create aliases for interacting with them, saving and loading it to/from disk, and validating that everything is the right type and within specified bounds.

And then if you want to facilitate plugins for your package from other people, it gets even more convoluted. What if instead you could pass a table describing what your options should look like, and then have the combobulator do the rest? HAve it generate aliases for setting/getting the configuration or usage information, serialization and validation all handled any time an option is set, and dynamically create a settings GUI for your users to view and change their configuration. For plugins, the plugin author can pass a table describing their options to your package's combobulator and it will generate everything needed for it also, including sub-menus in the settings GUI.

The combobulator is my attempt to make this dream a reality.

## How does it combobulate?

It turns a table describing your configuration items into a schema using luaschema which is then used for verifying the configuration items themselves. It also uses this information to generate one tempAlias for setting the value of each configuration item as well as some utility aliases for usage and the like. This information can also be used to generate individual UI elements for adjusting each configuration item which are assembled into a tabbed userwindow or adjustable container.

## Why the combobulator?

Because the bigger the package and the more it does, the more things there are likely to be to configure. Which means more time spent making aliases for them. Most packages never even bother with a configuration UI because it's so much work to make one at all. And the amount of validation being done is spotty at best in my experience. It is my hope that if you can just feed a description to the combobulator and let it do the work for you, more packages will come with a robust and complete configuration system.

## No, no... I mean like, what call it the combobulator?

Oh... because my first kid was super into Phineas and Ferb and I've largely adopted the Doofenschmirtz naming convention. Plus I feel like the word combobulate should see more use.

## Tools in use

This project is making use of a few tools to try and make things a little easier. 

1. [lua-schema](https://github.com/sschoener/lua-schema)
  * for validating the configuration items themselves
1. [squish](https://github.com/LuaDist/squish)
  * for turning it all into a single lua file for ease of requiring
