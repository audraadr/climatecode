# ECO Game
# All code was created using PixelPad.io, this is a copy of our completed code

# CLASSES
# game start
set_room('Home')

# button start
self.sprite = sprite('button.png')

# Player start
self.sprite = sprite('player.png')
self.speed = 8

# Background start
self.set_size = 3
self.sprite = sprite_new('home.png')

# bin start
self.sprite = sprite('cans.png')

self.scoreText = new_text('Score: 0', )
self.scoreText.color = "white"

self.yes = new_sound('correct.wav')
self.no = new_sound('wrong.mp3')

# bin loop
if get_collision(self, 'trash'):
    newFloor = get_collision(self, 'trash')
    destroy(newFloor)
    play_sound(self.yes)
    # self.scoreText +=1

if get_collision(self, 'can'):
    newFloor = get_collision(self, 'can')
    destroy(newFloor)
    play_sound(self.yes)

if get_collision(self, 'apple'):
    newFloor = get_collision(self, 'apple')
    destroy(newFloor)
    play_sound(self.no)

if get_collision(self, 'newspaper'):
    newFloor = get_collision(self, 'newspaper')
    destroy(newFloor)
    play_sound(self.no)
    
# trash start
import random 
self.number = int(random.uniform(0,3))

if self.number == 1:
    c = can()
    c.y = 200

if self.number == 0:
    a = apple()
    a.y = 200

if self.number == 2:
    n = newspaper()
    n.y =200

# spawner start

import random

self.timer = 60

# spawner loop
self.timer -=1

if self.timer <=0:
    t = trash()
    t.x = 700
    t.y = 100
    self.timer =180

# paperbin start
self.sprite = sprite('paper.png')

self.yes = new_sound('correct.wav')
self.no = new_sound('wrong.mp3')

# paperbin loop
if get_collision(self, 'trash'):
    newFloor = get_collision(self, 'trash')
    destroy(newFloor)
    play_sound(self.yes)

if get_collision(self, 'can'):
    newFloor = get_collision(self, 'can')
    destroy(newFloor)
    play_sound(self.no)

if get_collision(self, 'apple'):
    newFloor = get_collision(self, 'apple')
    destroy(newFloor)
    play_sound(self.no)

if get_collision(self, 'newspaper'):
    newFloor = get_collision(self, 'newspaper')
    destroy(newFloor)
    play_sound(self.yes)
    
# compostbin start
self.sprite = sprite('compost.png')

self.yes = new_sound('correct.wav')
self.no = new_sound('wrong.mp3')

# compostbin loop

if get_collision(self, 'trash'):
    newFloor = get_collision(self, 'trash')
    destroy(newFloor)
    play_sound(self.yes)

if get_collision(self, 'can'):
    newFloor = get_collision(self, 'can')
    destroy(newFloor)
    play_sound(self.no)

if get_collision(self, 'apple'):
    newFloor = get_collision(self, 'apple')
    destroy(newFloor)
    play_sound(self.yes)

if get_collision(self, 'newspaper'):
    newFloor = get_collision(self, 'newspaper')
    destroy(newFloor)
    play_sound(self.no)

# apple start
import random 
self.number = int(random.uniform(0,4))

if self.number ==0:
    self.sprite = sprite('apple.png')
    self.scaleX = 0.2
    self.scaleY=0.2

if self.number ==1:
    self.sprite = sprite('banana.png')
    self.scaleX = 0.1
    self.scaleY=0.1

if self.number ==2:
    self.sprite = sprite('pizza.png')
    self.scaleX = 0.2
    self.scaleY=0.2

if self.number ==3:
    self.sprite = sprite('sushi.png')
    
# newspaper start
import random 
self.number = int(random.uniform(0,3))

if self.number == 0:
    self.sprite = sprite('newspaper.png')
    self.scaleX = 0.3
    self.scaleY=0.3

if self.number == 1:
    self.sprite = sprite('box.png')
    self.scaleX = 2
    self.scaleY=2

if self.number == 2:
    self.sprite = sprite('bag.png')
    self.scaleX = 2
    self.scaleY=2
   
# can start
import random
self.number = int(random.uniform(0,5))

if self.number == 0:
    self.sprite = sprite('can.png')
    self.scaleX = 0.2
    self.scaleY=0.2

if self.number == 1:
    self.sprite = sprite('milkjug.png')
    self.scaleX = 2
    self.scaleY=2

if self.number == 2:
    self.sprite = sprite('bottle.png')
    self.scaleX = 2.5
    self.scaleY=2.5

if self.number == 3:
    self.sprite = sprite('jar.png')
    self.scaleX = .3
    self.scaleY=.3

if self.number == 4:
    self.sprite = sprite('juice.png')
    self.scaleX = .1
    self.scaleY=.1
    
# pointer start
self.sprite = sprite('point.png')
self.scaleX = 0.1
self.scaleY = 0.1

# pointer loop
self.x = mouse_x()
self.y = mouse_y()

# light start
self.sprite= sprite('light.png')

# switch start
self.sprite= sprite('on.png')

# ROOMS 
# Home start

self.menu = new_sound('menu.mp3')

self.music = new_sound('game.mp3')

loop_sound(self.menu)

bg = Background ()
bg.sprite = sprite('bg.png')
bg.scaleX = 3
bg.scaleY = 3

b = button()
b.scaleX = 2
b.scaleY = 2
b.y = -200

self.mouse = pointer()
self.beep = new_sound('beep.wav')

# Home loop
if mouse_was_pressed('left'):
    if get_collision(self.mouse, 'button'):
        set_room('secondmenu')
        play_sound(self.beep)

if key_was_pressed(" "):
    stop_sound(self.music)
    
# secondmenu start
self.menu = new_sound('menu.mp3')
self.music = new_sound('game.mp3')

bg = Background ()
bg.sprite = sprite('bg.png')
bg.scaleX = 3
bg.scaleY = 3

b = bbin()
b.sprite = sprite('bbin.png')
b.scaleX = 2
b.scaleY = 2
b.y = -200
b.x = -400

a = button()
a.sprite = sprite('light.png')
a.scaleX = .5
a.scaleY = .5
a.y = -200
a.x = 400

self.mouse = pointer()
self.beep = new_sound('beep.wav')

# secondmenu loop
if mouse_was_pressed('left'):
    if get_collision(self.mouse, 'bbin'):
        set_room('Recycle')
        play_sound(self.beep)

if mouse_was_pressed('left'):
    if get_collision(self.mouse, 'button'):
        set_room('Energy')
        play_sound(self.beep)
    
if key_was_pressed('escape'): 
    set_room('Home')

if key_was_pressed(" "):
    stop_sound(self.music)
    
# Energy start
stop_sound(get_room('Home').menu)
self.music = new_sound('game.mp3')

loop_sound(self.music)

bg = Background()
bg.sprite = sprite('grass.png')
bg.scaleX = 2
bg.scaleY = 2


self.mouse = pointer()

self.bulb = light()

self.s = stick()
self.s.scaleX = 4
self.s.scaleY = 4
self.s.x = -400

# Energy loop
if get_collision(self.mouse, "stick"):
   self.s.sprite = sprite("off.png")
   self.bulb.sprite = sprite('offlight.png')
   
else:
    self.s.sprite = sprite("on.png")
    self.bulb.sprite = sprite('light.png')        

if key_was_pressed('escape'): 
    set_room('secondmenu')

# Recycle start
stop_sound(get_room('Home').menu)

self.music = new_sound('game.mp3')

loop_sound(self.music)

bg = Background ()
bg.sprite = sprite('grass.png')
bg.scaleX=1.5
bg.scaleY=1.5

self.p = Player()
self.p.y = 200
self.p.x = -200

self.b = bins()
self.b.x=-500
self.b.y=-100
self.b.scaleY = 2
self.b.scaleX = 2

self.paper = paperbin()
self.paper.scaleX=2
self.paper.scaleY = 2
self.paper.x= 0
self.paper.y = -100

self.c = compostbin()
self.c.scaleX =2
self.c.scaleY=2
self.c.x = 500
self.c.y=-100

s = spawner()
s.x=700

self.yes = new_sound('correct.wav')

# Recycle loop
if get_collision(self.b, 'trash'):
    play_sound(self.yes)

if self.p.x < -640 :
    self.p.x = -200
    self.p.y= 200
if self.p.x >640 :
    self.p.x = -200
    self.p.y= 200

if self.p.y< -400:
    self.p.x = -200
    self.p.y= 200
if self.p.y >400 :
    self.p.x = -200
    self.p.y= 200

if key_was_pressed('escape'): 
    set_room('secondmenu')
