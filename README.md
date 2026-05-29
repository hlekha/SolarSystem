# Solar System
A simple visualization of the solar system. Using physics concepts and calculatations I derived on my own, several Python libraries, a Verlet Algorithm, and data from NASA.gov, I was able to accurately demonstrate Newton's law of universal gravitation, and display the orbits of all celestial bodies in our solar system.

## A Catchup on History

If you've had the luxury of looking up into the sky at night, the same curiousity will have sparked.
Curiousity about the sparkling dots we call stars, about the circles that luminate our world through
the day and night. This collective thought has been discovered to date back to since the first
civilizations 

## Newton's Law of Universal Gravitation


## The Verlet Algorithm

In this project, I implemented the Verlet integration, which is a numerical method famously used to integrate Newton's equations of motions. We know the initial conditions of the system - the initial velocity, which equals $\dot{x}(t_0)$, and the initial position, which is attained from setting the position function at $t_0$. Since we have the second-order differential equation relating position, and acceleration - $\ddot{x}(t) = A(x(t))$ - we are able to utilze the basic Størmer-Verlet algorithm. This algorithm allows us to find a numerical solution for $x_n$ by setting the function of x at $t_n$ for $t_n = t_0 + n \Delta t$ with a discrete time step. 

Since we know that $\dot{x} = v$, and $\ddot{x} = a$, we can obtain the function for x by conducting a second order Taylor-Series expansion which leads to: 
$$ x = x_0 + v_0 \Delta t + 1/2 A(x_0)t^2$$
With a change of variables more appropraite for our problem (changing position to radius from the given celestial body to the center, the Sun) and a step function that looks like: 
$$ r_{t+\Delta} = r_t + v_t \Delta t + 1/2 a_t \Delta t^2$$
We derive this to obtain the velocity function:
$$ v_{t+\Delta t} = v_t + 1/2 (a_t + a_{t+\Delta t})\Delta t$$

## Kepler's Third Law and The Timescale 

## Dependencies
