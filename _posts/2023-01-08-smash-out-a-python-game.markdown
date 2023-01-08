---
layout: post
title:  "Smash Out a Python Game"
date:   2023-01-08 17:40:25 +1300
categories: game python
---
This will be a quick post as I need to get back to cleaning Windows.

Strange but true.

Yesterday I spent 16 hours using ChatGPT, Twitter and Python; which was interesting itself. However sometime at about 11 PM, I thought 'I should see if I can make a Python Game using only ChatGPT, no references to any existing Python module or searching any open WWW source.

... just a quick play before bed.

I recalled that I dabbled 2 years ago making a command-line Game which I dropped however I will revisit that soon ... but I might as well use a similar concept; throwing something fast to cause mayhem.

Many years ago I had a Barnett Hunting Crossbow only for target practice, but had also watched a documentary on a large Crossbow that the Ancient Romans used as a siege weapon.

Opened a new ChatGPT Chat, and scoped out my initial query, although I knew what it was that I was looking for, I wanted to see if ChatGPT 'knew' it, so to speak.

Many ChatGPT Text Prompt examples use the 'Act As' method, where the Human is one thing and the AI is tasked to 'act as' something else, normally an expert in some subject matter or field.

**Query_01:**

> Let's play a role-playing game. I am an Ancient History student, and you will act as a highly regarded expert in Ancient Roman warfare and martial practices. I want you to summarize the dimensions, man-power requirements, maximum battle range, normal rate of fire, energy delivered and initial velocity of the largest siege crossbow in the Roman arsenal.

Well, colour me Pink, here's the result:

**Result_01:**

> Certainly! In Ancient Rome, one of the largest siege crossbows used was known as the scorpio. It was a type of bolt-throwing artillery that was used to defend fortifications or attack enemy fortifications. The scorpio was a relatively small weapon, with dimensions of approximately 2.5 meters in length and a weight of around 50 kilograms. It required a crew of two to operate, one to load and aim the weapon and another to turn the winch that span the torsion springs that powered the shot. The maximum range of a scorpio was around 300 meters, although its effective range was much shorter, around 100-150 meters. The rate of fire for a scorpio was slow, with a skilled crew able to launch around 3-4 bolts per minute. Each bolt was made of iron and weighed around 0.5 kilograms, and when fired from a scorpio, had an initial velocity of around 50 meters per second. This gave the bolt an energy delivery of around 400 joules, which was sufficient to penetrate the wooden gates of a fortification or cause serious injury to a soldier on the battlefield.

I do not recall the specifics, but I am pretty confident that this is spot on.

Let's scope this out further.

**Query_02:**

> Referring to the above result, I want you to create a command line Game using Python. This game will simulate the use of the Scorpio siege crossbow and will allow a player of the Game, hereby called a 'User' to calculate the 'time of flight', 'distance travelled' and 'energy delivered' based on the known values of the 'maximum range', 'rate of fire', 'Crossbow Bolt Mass' and the 'Angle of Elevation' above the ground. This game is to be mathematically accurate, easy to use and follows Python's code naming conventions. Ensure that the game is completely commented for future human maintainers.

**Result_02:**

> Sure! Here is a Python program that simulates the use of the Scorpio siege crossbow. The program allows the user to input the maximum range, rate of fire, crossbow bolt mass, and angle of elevation above the ground. Based on these inputs, the program calculates the time of flight, distance traveled, and energy delivered. I have also added comments to the code to explain what each part of the program is doing.

**Result_02_Code:**

{% highlight ruby %}
import math

# function to calculate time of flight
def time_of_flight(range, velocity):
  # time of flight = range / velocity
  return range / velocity

# function to calculate distance traveled
def distance_traveled(time, velocity):
  # distance traveled = time * velocity
  return time * velocity

# function to calculate energy delivered
def energy_delivered(mass, velocity):
  # energy delivered = 1/2 * mass * velocity^2
  return 0.5 * mass * velocity**2

# function to calculate initial velocity
def initial_velocity(angle, range):
  # initial velocity = range * 9.81 * sin(angle) / time_of_flight
  return range * 9.81 * math.sin(angle) / time_of_flight

# main function
def main():
  # prompt user for input
  max_range = float(input("Enter the maximum range of the Scorpio (in meters): "))
  rate_of_fire = float(input("Enter the rate of fire of the Scorpio (in bolts per minute): "))
  bolt_mass = float(input("Enter the mass of the crossbow bolt (in kilograms): "))
  angle = float(input("Enter the angle of elevation above the ground (in degrees): "))

  # convert angle from degrees to radians
  angle = math.radians(angle)

  # calculate initial velocity
  velocity = initial_velocity(angle, max_range)

  # calculate time of flight
  time = time_of_flight(max_range, velocity)

  # calculate distance traveled
  distance = distance_traveled(time, velocity)

  # calculate energy delivered
  energy = energy_delivered(bolt_mass, velocity)

  # print results
  print("Time of flight: %.2f seconds" % time)
  print("Distance traveled: %.2f meters" % distance)
  print("Energy delivered: %.2f joules" % energy)

# call main function
main()
{% endhighlight %}

Looks pretty good, although there is no Python Shebang by default. Next, create a file called `crossbow_game_v02.py`, make it an executable and see what happens.

`$ python3 crossbow_game_v02.py`

Ah it failed, but the error was clearly identified by the Python interpreter.

Well, I might as well inform ChatGPT about it and see what it says.

**Query_03:**

> Referring to the above result, the line 'return range * 9.81 * math.sin(angle) / time_of_flight' causes the game to fail. Can you describe why?

**Result_03:**

> Yes, the line return range * 9.81 * math.sin(angle) / time_of_flight causes a problem because time_of_flight is a function, but it is being used as a variable. This causes a NameError, because Python is unable to find a variable with the name time_of_flight.

> To fix this error, you can either remove the time_of_flight function and use the formula for time of flight directly in the initial_velocity function, or you can call the time_of_flight function and pass the necessary arguments to it. Here is an example of how you could modify the code to fix the error:

**Result_03_Code_01:**

{% highlight ruby %}
# function to calculate time of flight
def time_of_flight(range, velocity):
  # time of flight = range / velocity
  return range / velocity

# function to calculate initial velocity
def initial_velocity(angle, range):
  # calculate time of flight
  time = time_of_flight(range, 9.81 * math.sin(angle))

  # initial velocity = range / time
  return range / time
{% endhighlight %}

**Result_03_Code_02:**

{% highlight ruby %}
# function to calculate initial velocity
def initial_velocity(angle, range):
  # initial velocity = range * 9.81 * sin(angle) / (range / (range * 9.81 * sin(angle)))
  return range * 9.81 * math.sin(angle) / (range / (range * 9.81 * math.sin(angle)))
{% endhighlight %}

> Either of these modifications should fix the error and allow the program to run correctly. I hope this helps! Let me know if you have any further questions.

How's that? I told it the issue, and it provided two fixes on it's own accord.

That was unexpected, but let's get it to fix the issue itself.

**Query_04:**

> Referring to the above result, modify the game using the first code fix to make the game run correctly.

**Result_04:**

> Certainly! Here is the modified version of the program that uses the first code fix to calculate the initial velocity:

**Result_04_Code:**

{% highlight ruby %}
import math

# function to calculate time of flight
def time_of_flight(range, velocity):
  # time of flight = range / velocity
  return range / velocity

# function to calculate distance traveled
def distance_traveled(time, velocity):
  # distance traveled = time * velocity
  return time * velocity

# function to calculate energy delivered
def energy_delivered(mass, velocity):
  # energy delivered = 1/2 * mass * velocity^2
  return 0.5 * mass * velocity**2

# function to calculate initial velocity
def initial_velocity(angle, range):
  # calculate time of flight
  time = time_of_flight(range, 9.81 * math.sin(angle))

  # initial velocity = range / time
  return range / time

# main function
def main():
  # prompt user for input
  max_range = float(input("Enter the maximum range of the Scorpio (in meters): "))
  rate_of_fire = float(input("Enter the rate of fire of the Scorpio (in bolts per minute): "))
  bolt_mass = float(input("Enter the mass of the crossbow bolt (in kilograms): "))
  angle = float(input("Enter the angle of elevation above the ground (in degrees): "))

  # convert angle from degrees to radians
  angle = math.radians(angle)

  # calculate initial velocity
  velocity = initial_velocity(angle, max_range)

  # calculate time of flight
  time = time_of_flight(max_range, velocity)

  # calculate distance traveled
  distance = distance_traveled(time, velocity)

  # calculate energy delivered
  energy = energy_delivered(bolt_mass, velocity)

  # print results
  print("Time of flight: %.2f seconds" % time)
  print("Distance traveled: %.2f meters" % distance)
  print("Energy delivered: %.2f joules" % energy)

# call main function
main()
{% endhighlight %}

Created a new version of the game, titled `crossbow_game_v03.py`, ran it and it works.

It is very limited in function, not very exciting (OK, not exciting at all) but conceptually, it is a command-line game made using Python solely with ChatGPT.

If I had committed to this task, with no blogging of the process and did not stop once I had started, this would have taken 10 minutes, no more.

For the sake of brevity, you can see the final prompt by myself and the resulting code.

**Query_End:**

> Referring to the above result, insert a Python Shebang at the top of the file. Then insert a commented section after the import statements that describes what this game is about and refers to the original briefing statement 'Let's play a role-playing game. I am an Ancient History student, and you will act as a highly regrded expert in Ancient Roman warfare and martial practices. I want you to summarize the dimensions, man-power requirements, maximum battle range, normal rate of fire, energy delivered and initial velocity of the largest siege crossbow in the Roman arsenal.' Ensure that you Capitalize any proper noun or name.

**Result_End:**

> Certainly! Here is the modified version of the program that includes a Python shebang at the top of the file and a commented section that describes what the game is about and refers to the original briefing statement:

**Result_End_Code:**

{% highlight ruby %}
#!/usr/bin/env python3

import math
import random

# This game simulates the use of the Scorpio siege crossbow, a type of 
# bolt-throwing artillery used in Ancient Rome to defend fortifications
# or attack enemy fortifications. The Scorpio was a relatively small 
# weapon, with dimensions of approximately 2.5 meters in length and a
# weight of around 50 kilograms. It required a crew of two to operate,
# one to load and aim the weapon and another to turn the winch that 
# span the torsion springs that powered the shot.

# function to calculate time of flight
def time_of_flight(range, velocity):
  # time of flight = range / velocity
  return range / velocity

# function to calculate distance traveled
def distance_traveled(time, velocity):
  # distance traveled = time * velocity
  return time * velocity

# main function
def main():
  # set initial velocity to 150 meters per second
  velocity = 150

  # prompt user for input
  max_range = float(input("\nEnter the maximum range of the Scorpio (in meters): "))
  angle = float(input("\nEnter the angle of elevation above the ground (in degrees): "))
  bolt_mass = float(input("\nEnter the mass of the crossbow bolt (in kilograms): "))

  # convert angle from degrees to radians
  angle = math.radians(angle)

  # calculate time of flight
  time = time_of_flight(max_range, velocity)

  # calculate distance traveled
  distance = distance_traveled(time, velocity)

  # calculate energy delivered
  energy = 0.5 * bolt_mass * velocity**2

  # generate random crosswind speed
  crosswind_speed = random.uniform(1, 6)

  # print results
  print("\nTime of flight: %.2f seconds" % time)
  print("Distance traveled: %.2f meters" % distance)
  print("Energy delivered: %.2f joules" % energy)
  print("Crosswind speed: %.2f meters per second" % crosswind_speed)

# call main function
main()
{% endhighlight %}

Verdict?

Again, I am impressed at not only the knowledge that can be presented based on simple English-text, but the fact that it seems to understand some of the nuances, and oblique references that as Humans, we use. It also showed simple adaptability and was able to implement 1 of it's 2 solutions to an identified issue, with minimal guidance.

Now, that is impressive.

I think that I will continue with this game, focusing on:

  - Extending the functionality
  - Adding some sort of scoring system
  - Adding in Targetting instability from outside vectors
  - Consider a simple GUI framework, perhaps `tkinter`
  - Add Historical documentation
  - Add Gameplay documentation
  - Push to my GitHub repository

This combination of Human imagination and machine capability is a potent one.

No doubt in my mind at all.
