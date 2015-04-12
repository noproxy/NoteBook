# Keyboard Ninja With Intellij *IDEA*

## How To Explore

- [Help](https://www.jetbrains.com/idea/help/intellij-idea.html)
- Find Action *Ctrl+Shift+A*
- Productivity Guide
- Default keymap reference
- Keymap

 

## Seach Everywhere

- Serch Everywhere *Shift+Shift*
- Find Action *Ctrl+Shift+A*
- Find Class *Ctrl+N*
- Find File *Ctrl+Shift+A*
- Find Symbol *Ctrl+Alt+Shift+N*
- Find *Ctrl+F* Replace
- Incremental Search
- Find In Path *Ctrl+Shift+F*
- Search Structural

## Context& Windows Navigation

- Switcher *Ctrl+(Shift)+TAB*
- Recent files *Ctrl+E* Recent Edited file *Ctrl+Shift*
- Project *Alt-1*
- TODO *Alt+6*
- Structure *Alt+7* (一下打开，两下获取焦点)

- Favorites *Alt+2*  
>- mark *F11* 
>- mark and assgin shortcuts *Ctrl+F11* 
>- show bookmarks *Shift+F11*

- Hide Active Tool Window *Shift+Esc*
- Jump to last tool windows *F12*

>- Store Current Layout as Default
>- Restore Default Layout *Shift+F12*

- Tool window mode: Pinned, Floating, as Tabs, Docked

>- UI preview: Pinned, Floating
>- Project, TODO: Unpinned, Floating
  
- No Tab, Distraction Free Mode
- Split Windows(Recommand: Ctrl+Shift+Alt+V/H)
- Previous/Next Project Windows *Ctrl+Alt+[* *Ctrl+Alt+]* 


## Edit& Text Navigation

- Move and Selection:
>- Use "CamelHumps" words
>- Extend Selection *Ctrl+W*
>- Move caret by word *Ctrl+Up/Down/Left/Right* (shift: select)
>- Move caret by method *Alt+Up/Down/Left/Right* (shift: move line)
>- Copy, Cut, Duplicate line *Ctrl+C,X,D* 
>- Join line *Ctrl+Shift+J*
>- Home, End, PaDn, PaUp
>- Fold/Unfold *Ctr+-* *Ctrl+=* (shift:all) *Ctrl+.*
>- Next hightlighted error *F2* *Shift+F12* 

- Structure Navigation:
>- Declaration/Usage *Ctrl+B*
>- Implementations *Ctrl+Alt+B*
>- Super Method/Class *Ctrl+U*
>- File Structure *Ctrl+F12*


- Multip Caret (Alt+J)
- Scratch

- Format:
>- Optimize Imports
>- Rearrange code
>- Reformat code*Ctrl+Alt+L*

- Reference:
>- Documentation *Ctrl+Q*
>- Parameters *Ctrl+P*

## Version Control

- Local History
- Rollback on Gutter


## Code Generator

- Insert Live Templates *Ctrl+J*
- Surround with Live Templates *Ctrl+Alt+J/T*
- Intent Action *Alt+Enter*
- Postfix Completion
- Copyright Profiles
- Generate:
>- Override methods *Ctrl+O*
>- Delegate methods 
>- Setter
>- Getter
>- Constructor
>- toString(), hashCode(), equals()

## Vmoptions

- x64 idea
- Xmx 最大可用内存
- Xms 初始化内存栈

```
-server
-Xms2g
-Xmx4g
-XX:MaxPermSize=512m
-XX:ReservedCodeCacheSize=512m
-XX:+UseConcMarkSweepGC
-XX:SoftRefLRUPolicyMSPerMB=50
-XX:ParallelGCThreads=12
-XX:+DisableExplicitGC
-XX:+UseStringCache 
-XX:+UseFastAccessorMethods 
-ea
-Dsun.io.useCanonCaches=false
-Djava.net.preferIPv4Stack=true
```


## Awesome

- add library by maven
- Power Save Mode
- Website: [IDEA Color Theme](http://www.ideacolorthemes.org/)
- Plugin: 
>- Key Promoter
>- Settings Repository
>- Browse word at caret
>- AceJump
- Font: [Adobe Source Code Pro](https://github.com/adobe-fonts/source-code-pro)
- Font Render:[Infinality](http://infinality.net) 
>- jdk8-openjdk-infinality 
>- openjdk-fontfix

 ![](font_bad.png)
 ![](font_good.png)

## Even More

- Rename, move
- Extract Variable/Constant/Field/Parameter/Method/Interface/Inline
- Convert anonymous class to inner
- Replace Inheritance With Delegation
- Encapsulate Fields
- Factory Method