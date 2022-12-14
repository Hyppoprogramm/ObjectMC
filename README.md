# ObjectMC
Object oriented datapacks in Python for Minecraft.
https://youtu.be/yBetnG_R02o

## What is it?
It's a program that compiles Python bytecode to Minecraft commands.

## How do I use it?
First, download source code or use `pip install objectmc` to install module. Then import it and create a base class:
```python
from objectmc import *

@ObjectMC(name="Datapack", id="objectmcdatapack") # id and name are optional
class ObjectMCClass:
    description = "Datapack description"
    
    @load
    def onLoad(): pass # This function will be called on datapack load.
    
    @tick
    def onTick(): pass  # This function will be called on tick.
    
    @mcfunction # You can remove this line because functions have mcfunction mode by default.
    def testFunction(): pass  # This function only can be callled using /function command.
    
    @ignore
    def anotherFunction(): pass # This function will not compiled to datapack.
```
After creating class you can export it:
```python
ObjectMCClass.export(".minecraft/saves/world/datapacks")
```

### Updates
### v0.2
- Added bool.
- Now functions are technically objects: `myfunc(1, 2, "Bob", print)`
### v0.3
- Added getblock().
- Fixed bugs.

## Support
ObjectMC v0.3 supports
- Python 3
- - Python types
- - - str
- - - int
- - - bool
- - - NoneType
- - Python built-in functions
- - - print
- - - len
- - - min
- - - max
- - - exit
- - Python operations
- - - Add
- - - Subtract
- - - Multiply
- - - Divide
- - - Modulo
- - - Power
- - Python constructions
- - - Nothing yet :(
- Minecraft 1.16+
- - Minecraft API
- - - getblock()
