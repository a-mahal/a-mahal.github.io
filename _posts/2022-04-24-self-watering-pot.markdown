---
layout: post
title:  "Self-Watering Pot"
date:   2020-04-24 10:36:35 -0400
categories: jekyll update
---
If you have an extremely busy scheduele, this project may be useful for you. It's easy to neglect our plants, but by implementing this code with a few sensors and actuators, you can automate plant watering to where you never have to worry about your plants being dehydrated!

Reading the voltage drop of a thermistor to create a temperature sensor on Arduino
{% highlight ruby %}
float V = analogRead(A0);
float Vout = 5*(V/1023);
float R1 = (thermister rating)* (1-(Vin/Vout));
R1 = map(R1, 700, 6700, 500, 73);
int T = R1
{% endhighlight %}


Inputting strings from Arduino to Processing to create responsive images 
{% highlight ruby %}
void setup {
  println(Serial.list());
  myPort = new Serial(this, Serial.list()[4], 115200); 
}

void draw () {
  while (myPort.available () > 0) {
    String inString = myport.readStringUntil('\n');
    
    if (inString !=null) {
      inString = trim(inString);
      String[] myRaw = splitTokens(inString, ",");
    if (myRaw.length == 3){
      int cm = int(myRaw[0]);
      int t = int(myRaw[1]);
      int b = int(myRaw[2]);
    }
    }
  }
}
{% endhighlight %}


The physical components of this project are listed below. (will add specific part numbers) 
- `2 servo motors`                                                                                     
- `thermistor`
- `miniature pump`
- `ultrasonic sensor` 
- `two flower pots`
- `custom design to hold components` 

Link to project files: (coming soon)


