# Solar System
A simple visualization of the solar system on the 2D plane. Using physics concepts and calculatations I derived on my own, a few Python libraries, a Verlet Algorithm, and data from NASA.gov, I was able to accurately demonstrate Newton's law of universal gravitation, and display the orbits of all celestial bodies in our solar system.

## A Catchup on History

If you've had the luxury of looking up into the sky at night, the same curiousity will have sparked. Curiousity about the sparkling dots we call stars, about the circles that luminate our world through the day and night. This collective thought has been discovered to date back to since the first civilizations.

Although the notion that Earth remained stationary at the center of the universe dominated worldviews for almost 2,000 years, the Mesopotomians tracked planetary motions of Mars and Venus with shocking precision. Observers used ziggurats (temple towers) to record the dates and locations of the planetary appearances in systematic "Astronomical Diaries". Specifically, they created the Venus Tablet of Ammisaduga which tracked exact heliacal risings and settings of Venus, allowing observers to track its eight-year cycle. They were even able to mathematically model the motions by using abstract geometry to plot planetary velocity and movement by calculating the area of trapezoids under a curve !

By the second century, the Ptolemaic System, created by Claudius Ptolemy, had been adopted. They weren't qutite ready to abondon the geocentric status of Earth yet, but Ptolemy introduced deferents and epicycles. He beleived planets moved in a small circular path, the epicycle, where the center of that epicycle had a trajectory path resesembling a larger circle around the Earth. the deferent. This odd system explained retrograde motion which was the illusion that planets appeared to slow down, stop, and reverse direction; it was also used to find that a planet's speed varies depending on its position in orbit.

<p align="center">
  <img width="741" height="392" alt="0zoOursjv8-i2siKfZWSS3SKG2bwa4s3s6mXmSfx2yQDty2qIVO7dYvLlekxCzY1Oek1w5Q0wh6GG5Cra-oNJ1gX8n_M4KqxUxRULdVlooxr1K-Uv_N-IaXkEklB_tMHRgCHclYVL8TnRnznLT0E2kup4jzCG2iSQQywX5s21NsNtO1AD2KMxI2MqPSPNfmQ" src="https://github.com/user-attachments/assets/59584286-f3b4-481b-bd80-0457e0ac7f7a" />
</p>

Finally, in the 1500s Nicolaus Copernicus radicalized astronomy by proposiing the heliocentric model of our solar system where the planets revolved around the Sun, not Earth, explaining that the retrograde motion is Earth itself moving, and the backward motion is just an observational effect as a result.

<p align="center">
  <img width="50%" height="50%" alt="u8mq0TN0C35s-ebkR_BZUb0Rj8AnOqK62FTrPZUZyaQ8BwJrAA4lQfJjEw70JUGTXSsnUXpBdgZrtUufBgTNxgDS9fJgNznWYdYVooT9s9UdAp6S041qpNlLbjcCKfT0-c_8yc8veTvYC1bl6BlYmdtPzeDBy30pEIEP8modkP0" src="https://github.com/user-attachments/assets/c4565b7b-f123-4a08-9b1c-afda50c07bbf" />
</p>

One flaw in this model is that it was still under the assumption that orbits were perfect circles. It was Kepler who found that planets actually move in ellipses through his analyzation of Tycho Brahe's decades worth of data on Mars. 

From this we were gifted Kepler's Laws:
1. Planets have an elliptical trajectory and have the form $\frac {x^2}{a^2} + \frac{y^2}{b^2} = 1$
2. Planets mover faster the closer they are to the sun and slow the further away they are leading to the planets covering equal areas in equal times.
3. This leads to an orbital period relationship of $T^2 \propto a^3$

Finally, after the world accepted this truth, Newton quickly followed with his major breakthrough of astronomy, unifying the gravitation constant of Earth, the Moon's motion, and planetary orbits with the theory of gravity.


## Newton's Law of Universal Gravitation

Famously centralized around the equation, $F = G \frac{m_1 m_2 }{r^2}$, Newton realized that there exists a universal attractive force from one mass onto another. He knew that this force was proportional to both masses of the system, and inversley proportional to the square of the distance between their centers of mass. He also knew that there was a proportionality constant but was unable to find its numerical value.

111 years later in 1797-1798, Henry Cavendish was able to measure the magnitude of gravitational attraction between two masses by using a torsion wire and calculating how much the wire twisted against its resistance. This data lead to the gravitational constant, G, the proportionality constant Newton was missing.

In the context of our problem, since force is a vector with both magnitude and direction, and because the force experienced on planets is attractive, the force is negative, as well as multiplied by the unit vector of radius. This leads us to:
<p align="center">
  $$\vec{F} = \frac {GMm}{r^2} \hat {r}$$
</p>
We then relate this to Newton's secoond law to solve for acceleration:
<p align="center">
  $$a = \frac{-GM}{r^2} \hat {r}$$
</p>
Note that the smaller mass cancels out, indicating that the resulting gravitational acceleration is independent of its mass. This is consistent with the underlying concept that the accerleration experienced by the smaller mass is exerted from the larger mass of the system. 

Tailoring this to our project, with our assumptions made (the only forces acting upon a given planet is the force of the Sun), the acceleration of each planet is given by this equation.

## The Verlet Algorithm

In this project, I implemented the Verlet integration, which is a numerical method famously used to integrate Newton's equations of motions. It begins with initial conditions, and a pair of differential equations which updates along set time steps. For our problem, we set the initial position to the perihelion distance, and the initial velocity to the perihelion velocity - perihelion means the point at which any given planet in our solar system is closest to the Sun. which equals $\dot{x}(t_0)$, and the initial position, which is attained from setting the position function at $t_0$. Since we have the second-order differential equation relating position, and acceleration - $\ddot{x}(t) = A(x(t))$ - we are able to utilze the basic Størmer-Verlet algorithm. This algorithm allows us to find a numerical solution for $x_n$ by setting the function of x at $t_n$ for $t_n = t_0 + n \Delta t$ with a discrete time step. 

Since we know that $\dot{x} = v$, and $\ddot{x} = a$, we can obtain the function for x by conducting a second order Taylor-Series expansion which leads to: 
<p align="center">
  $$x = x_0 + v_0 \Delta t + \frac{1}2 A(x_0)t^2$$
</p>
With a change of variables more appropraite for our problem (changing position to radius from the given celestial body to the center, the Sun) and a step function that looks like: 
<p align="center">
  $$r_{t+\Delta} = r_t + v_t \Delta t + \frac{1}2 a_t \Delta t^2$$
</p>
We derive this to obtain the velocity function:
<p align="center">
  $v_{t+\Delta t} = v_t + \frac{1}2 (a_t + a_{t+\Delta t})\Delta t$
</p>

## Kepler's Third Law and The Timescale 
Kepler's Third Law states that the period 

## Dependencies and Assumptions Made

In this project I used 

## Closing Remarks

In the early 1900s, Einstein theorized general relativity. He stated that gravity actually wasn't a force like Newton stated, but a curvature of spacetime represented by the equation: $G_{\mu v} = \frac {8\pi G}{c^4}T_{\mu v}$. This explained unusual activity with Mercury's orbit, gravitational lensing, and - most fascinatingly - black holes. 

I plan to elevate this project with a new project in C++ demonstrating some of the orbital mechanics shown in the solar system utilizing this equation.
<p align="center">
  <img width="50%" height="50%" alt="obT8k3ZMXNjZJyvrk-JdhOB6oPZtj_SR7GHwhjdcRG6ZNMK6YgNNk8qVhaYiYwSUfU2wyjTePZ7Vhb4JQoPED11QeDFbXCx5jNFEw5aWAEqe7aW1p0PFWCt6RhWCfSxlsj6OBjKo2q5dCwfRnkCQEpuJBxht8HRhW54QlggTdjqQ8gYbRE9wCWj7FNlx2kGu" src="https://github.com/user-attachments/assets/bdfed4b4-7b61-4b37-8011-6e7a7438ce23" />
</p>
