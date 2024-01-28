
# TPZ-CORE Menu Base

Credits to https://github.com/RedEM-RP/redemrp_menu_base

# Information

A Menu Base for TPZ-CORE.

qadr version has changed CSS, image compatibility, and add nui focus control.

This resource has been adopted for use by the RedEMRP Framework "reboot" of 2022.

![image](https://github.com/TPZ-CORE/tpz_menu_base/assets/152554963/ba532f32-db8c-4421-a8de-7ae10e1bb258)


# Installation

1. Rename `tpz_menu_base-master` to `tpz_menu_base`

2. Add `ensure tpz_menu_base` before ensure `tpz_core` in the resources.cfg or server.cfg, depends where your scripts are located.


# Usage

## Add this on the top of your Client :

```lua
MenuData = {}
TriggerEvent("tpz_menu_base:getData",function(call)
    MenuData = call
end)
```

## Example :

```lua
MenuData.CloseAll()
local elements = {
    {
     label = "Test Option",
     value = 'test' ,
     desc = "Press if you want print text",
     image="items/weapon_melee_hammer.png",
     descriptionimages = {
      {
       src = "nui://tpz_menu_base/html/items/cloth.png",
       text = "Kumaş",
       count = "x1"
      },

      {
       src = "nui://tpz_menu_base/html/items/woodenplanks.png",
       count = "x5",
       text = "Ahşap"
      }
     },
    },
    {label = "Hop Test", value = 0  ,desc = "Look its so fast" , type = "slider" , min =0 , max =100, hop= 5},
}

MenuData.Open('default', GetCurrentResourceName(), 'test_menu',
{
    title   = 'TestMenu',
    subtext = 'There is a subtext',
    align   = 'top-left',
    elements = elements,
},
function(data, menu)
    if(data.current.value == 'test') then
        print("test")
    end
end,
function(data, menu)
    menu.close()
end)
```
