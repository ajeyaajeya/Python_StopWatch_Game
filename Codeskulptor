# template for "Stopwatch: The Game"

import simplegui


# define global variables
time = 0
success = 0
total = 0

# define helper function format that converts time
# in tenths of seconds into formatted string A:BC.D
def format(t):
    
    temp = t
    sec = t % 10
    t = t / 10
    
    t = t % 60
    min = t   
    #print "min =", min
    if (min < 10):
        min  = '0' + str (min)
        
   
    
    if temp > 599:
        hr = temp / 600
        
        #print "temp =", hr , "\n"
        
    else:
        t = t / 60
        #print "hr= " , t, "\n"
        hr = t
        
   
    
    if (hr < 10):
        hr  = '0' + str (hr)
    elif hr == 24:
        timer.start()

        
    
    return str(hr) + ":" + str(min) + ":" + str ( sec ) 
 
    
# define event handlers for buttons; "Start", "Stop", "Reset"
def reset_handler():
    global total, success
    total, success = 0, 0

def start_handler():
    timer.start()
    global total
    total = total + 1
    

def stop_handler():
    if (time % 2) == 0 :
        global success
        success += 1
    timer.stop()
    
    

def draw_handler(canvas):
    global success, total
    canvas.draw_text(str(format(time)), [150, 150], 12, 'red')
    canvas.draw_text(str('/'), [260, 10], 12, 'white')
    canvas.draw_text(str(total), [270, 10], 12, 'red')
    canvas.draw_text(str(success), [250, 10], 12, 'green')
# define event handler for timer with 0.1 sec interval
def timer_handler():
    global time
    time += 1
    print time
   
    
# create frame
frame = simplegui.create_frame('Stopwatch: The Game', 300,300)
button1 = frame.add_button('Start', start_handler)
button2 = frame.add_button('Stop', stop_handler)
button3 = frame.add_button('Reset', reset_handler)

# define draw handler
frame.set_draw_handler(draw_handler)

# register event handlers
timer = simplegui.create_timer(100, timer_handler)

# start frame
frame.start()
timer.start()

# Please remember to review the grading rubric
