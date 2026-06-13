# Solar System
A simple visualization of the solar system. Using physics concepts and calculatations I derived on my own, several Python libraries, a Verlet Algorithm, and data from NASA.gov, I was able to accurately demonstrate Newton's law of universal gravitation, and display the orbits of all celestial bodies in our solar system.

## A Catchup on History

If you've had the luxury of looking up into the sky at night, the same curiousity will have sparked. Curiousity about the sparkling dots we call stars, about the circles that luminate our world through the day and night. This collective thought has been discovered to date back to since the first civilizations.

Although the notion that Earth remained stationary at the center of the universe dominated worldviews for almost 2,000 years, the Mesopotomians tracked planetary motions of Mars and Venus with shocking precision. Observers used ziggurats (temple towers) to record the dates and locations of the planetary appearances in systematic "Astronomical Diaries". Specifically, they created the Venus Tablet of Ammisaduga which tracked exact heliacal risings and settings of Venus, allowing observers to track its eight-year cycle. They were even able to mathematically model the motions by using abstract geometry to plot planetary velocity and movement by calculating the area of trapezoids under a curve !

By the second century, the Ptolemaic System, created by Claudius Ptolemy, had been adopted. They weren't qutite ready to abondon the geocentric status of Earth yet but Ptolemy introduced deferents and epicycles. He beleived planets moved in a small circular path, the epicycle, where the center of that epicycle had a trajectory path resesembling a larger circle around the Earth. the deferent. This odd system explained retrograde motion which was the illusion that planets appeared to slow down, stop, and reverse direction; it was also used to find that a planet's speed varies depending on its position in orbit.<img width="741" height="392" alt="0zoOursjv8-i2siKfZWSS3SKG2bwa4s3s6mXmSfx2yQDty2qIVO7dYvLlekxCzY1Oek1w5Q0wh6GG5Cra-oNJ1gX8n_M4KqxUxRULdVlooxr1K-Uv_N-IaXkEklB_tMHRgCHclYVL8TnRnznLT0E2kup4jzCG2iSQQywX5s21NsNtO1AD2KMxI2MqPSPNfmQ" src="https://github.com/user-attachments/assets/59584286-f3b4-481b-bd80-0457e0ac7f7a" />

Finally, in the 1500s Nicolaus Copernicus radicalized astronomy by poposiing the heliocentric model of our solar system where the planets revolved the Sun, not Earth, explaining that the retrodgrade motion is Earth itself moving, and the backward motion is just an observational effect as a result. <img width="800" height="829" alt="u8mq0TN0C35s-ebkR_BZUb0Rj8AnOqK62FTrPZUZyaQ8BwJrAA4lQfJjEw70JUGTXSsnUXpBdgZrtUufBgTNxgDS9fJgNznWYdYVooT9s9UdAp6S041qpNlLbjcCKfT0-c_8yc8veTvYC1bl6BlYmdtPzeDBy30pEIEP8modkP0" src="https://github.com/user-attachments/assets/c4565b7b-f123-4a08-9b1c-afda50c07bbf" />

One flaw in this model is that it was still under the assumption that orbits were perfect circles. It was Kepler who found that planets actually move in ellipses through his analyzation of Tycho Brahe's decades worth of data on Mars. 

From this we were gifted Kepler's Laws:
1. Planets have an elliptical trajectory and have the form $ \frac {x^2}{a^2} + \frac{y^2}{b^2} = 1th 


## Newton's Law of Universal Gravitation


## The Verlet Algorithm

In this project, I implemented the Verlet integration, which is a numerical method famously used to integrate Newton's equations of motions. We know the initial conditions of the system - the initial velocity, which equals $\dot{x}(t_0)$, and the initial position, which is attained from setting the position function at $t_0$. Since we have the second-order differential equation relating position, and acceleration - $\ddot{x}(t) = A(x(t))$ - we are able to utilze the basic Størmer-Verlet algorithm. This algorithm allows us to find a numerical solution for $x_n$ by setting the function of x at $t_n$ for $t_n = t_0 + n \Delta t$ with a discrete time step. 

Since we know that $\dot{x} = v$, and $\ddot{x} = a$, we can obtain the function for x by conducting a second order Taylor-Series expansion which leads to: 
                                                            $$x = x_0 + v_0 \Delta t + \frac{1}2 A(x_0)t^2$$

With a change of variables more appropraite for our problem (changing position to radius from the given celestial body to the center, the Sun) and a step function that looks like: 
$$r_{t+\Delta} = r_t + v_t \Delta t + \frac{1}2 a_t \Delta t^2$$

We derive this to obtain the velocity function:
$v_{t+\Delta t} = v_t + \frac{1}2 (a_t + a_{t+\Delta t})\Delta t$

## Kepler's Third Law and The Timescale 

## Dependencies
