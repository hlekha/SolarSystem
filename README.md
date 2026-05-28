# Solar System
A simple visualization of the solar system. Using physics concepts and calculatations I derived on my own, several Python libraries, a Verlet Algorithm, and data from NASA.gov, I was able to accurately demonstrate Newton's law of universal gravitation, and display the orbits of all celestial bodies in our solar system.

## A Catchup on History

If you've had the luxury of looking up into the sky at night, the same curiousity will have sparked.
Curiousity about the sparkling dots we call stars, about the circles that luminate our world through
the day and night. This collective thought has been discovered to date back to since the first
civilizations 


## The Verlet Algorithm

In this project, I implemented the Verlet integration, which is a numerical method famously used to integrate Newton's equations of motions. We know the initial conditions of the system - the initial velocity, which equals \dot{x}(t_0), and the initial position, which is attained from setting the position function at t_0. Since we have the second-order differential equation relating position, and acceleration - \ddot{x}(t) = A(x(t)) - we are able to utilze the basic Størmer-Verlet algorithm,  
