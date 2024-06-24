# Climate Change Weather Station Tutorial Part 1

## Measure and track temperature @unplugged

In this tutorial, you will learn how to measure temperature with your Micro:bit and track changes over time. Let's get coding!

## Step 1 - Add code to display temperature.
Click on the ``||basic:Basic||`` category in the Toolbox. 
Drag the ``||basic:show number||`` block into the ``||basic:forever||`` block. 


```blocks
basic.forever(function() {
    basic.showNumber(0)
})
```

## Step 2

Get a ``||input:temperature||`` block and place it in the value slot of ``||basic:show number||``.

```blocks
basic.forever(function() {
    basic.showNumber(input.temperature())
})
```

## Step 3
Add a pause of one second between displaying temperatures by dragging the ``||basic:pause||`` block below the ``||input:temperature||`` block. Choose '1 second' from the drop down menu.  


```blocks
basic.forever(function() {
    basic.showNumber(input.temperature())
    basic.pause(1000)
})
```

## Step 4 - Record the temperature
Now we need to set up your table to track the temperature. Drag ``||datalogger:set columns||`` into the ``||basic:on start||``
block.

```blocks
datalogger.setColumnTitles(" ")
```

## Step 5
Name your first column by typing "temperature" in the value box of ``||datalogger:set columns||``.
```blocks
datalogger.setColumnTitles("temperature")
```


## Step 6 - Create a time loop
Every minute, we want to track the temperature and record it to our log. Drag the ``||loops:every||`` block into the workspace. Choose '1 minute' from the drop down menu. 

```blocks
loops.everyInterval(60000, function () {
})
```

## Step 7
Now drag the ``||datalogger:log data||`` block into the ``||loops:time loop||``. Select column "temperature" from the drop down menu. 
Get a ``||input:temperature||`` block and place it in the value slot of ``||datalogger:log data||``.

```blocks
loops.everyInterval(60000, function () {
    datalogger.log(datalogger.createCV("temperature", input.temperature()))
})
```

## Congratulations, you did it! @unplugged
What else could you track to improve your Climate Change Weather Station? Learn more about Climate Change here.


    

<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>


```package
datalogger
neopixel=github:microsoft/pxt-neopixel
```

