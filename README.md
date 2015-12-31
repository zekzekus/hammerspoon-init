# Hammerspoon 

I'm not going to explain what is **Hammerspoon** or teach you Lua.

I'll just explain how to use my "init.lua" file, if you don't want spending time on it.

# Download

The source of this init.lua is [here](https://github.com/rtoshiro/hammerspoon-init/blob/master/init.lua). I just forked and modified with my own taste.

# Configuration

Open ```init.lua``` file and edit lines 12 and 13 with the name of your first and second monitor. You can get the name openning MacOS display settings.

```
12		local main_monitor = "Color LCD"
13		local second_monitor = "DELL E2310H"
```

# Shortcuts

    Different from toshiro's approach, i am using ```fn``` key as ```hyper```
    key. I used Karabiner for this purpose. Now i am using ```hyper``` as my
    primary modifier and ```cmd+alt+ctrl``` for shortcuts that i use less.

	hyper + right key
	hyper + left key
	hyper + up key
	hyper + down key
	ctrl + cmd + alt + right key
	ctrl + cmd + alt + left key
	ctrl + cmd + alt + up key
	ctrl + cmd + alt + down key
	hyper + c
	ctrl + cmd + alt + c
	hyper + f
	ctrl + cmd + alt + f

	hyper + r (reloads init.lua file)
	hyper + 1 (moves focused window to second_monitor)
	hyper + 2 (moves focused window to main_monitor)
	hyper + 3 (applies all layouts)
	hyper + 4 (applies only one layout (focused one))

	ctrl + cmd + alt + P (closes all applications defined by closeAll variable at line 205)
	ctrl + cmd + alt + O (open all applications defined by openAll variable at line 222)

# Layouts:

You can configure the variable "layouts" (line 32) according your monitor configuration.

### The syntax is:

```
  {
    name = "App name" ou { "App name", "App name" }
    func = function(index, win)
      COMMANDS
    end
  },
```

### Example

```
  {
    name = {"Firefox", "iTunes"},
    func = function(index, win)
      win:moveToScreen(hs.screen.get("Color LCD"))
      win:maximize()
    end
  },
```

If you call "hyper + 3", it will apply all layouts you defined.

If you call "hyper + 4", the layout will be applied only on the focused application.

