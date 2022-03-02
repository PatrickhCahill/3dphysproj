# 3dphysproj
The idea of this project is to create a simple physics engine and visualise it using python.

1. Physics object: An object will be defined by position, velocity and acceleration coordinates.
2. Physics force: class of functions which strictly receive objects as an input and return acceleration vectors.
3. Computation: The system will then evolve in time using numerical integration
4. This will then be animated

## Short term goals:
- Create point-like object and force classes
- Create simple computation mechanism
- Create simple animation

## Longer Term goals:
1. Allow for the creation of arbitrary fields without needing specific force equations.
2. Implement torque and rotational physics
3. Allow for solid-state objects to have dimensions
4. Allow for computation mechanisms other than forces, i.e Lagrangian/Hamiltonian dynamics
5. Allow for different coordinate systems. i.e Spherical coordinates
6. Allow for different geometries and boundaries.

## Physics object
class:
- tag (to keep track of the object)
- Initial position
- Inital velocity
- Initial acceleration
- Initial mass
- optional other quantities such as charge
* In future want to define orientation using angles.
* Also want to have functions like tag.position which will provide the current position of a particle etc and other relevant functions

## Physics forces
class
-Forces must be written to operate on any object and can call as many arbitrary objects as needed.
-Forces are functions that pass objects and output an acceleration vector
-As written above forces can therefore be added. F(objects) = f(objects) + g(objects). This boils down to vector addition and forces need to reflect this

## Computation
Initial simple idea is to use very simple step integration.

i.e for object in all objects:
position += velocity * delta_t
velocity += acceleration * delta_t
acceleration = F_total/mass

Then we can compute for t_init=0 to t_final=t, with some tolerance = 1/num_steps where delta_t = (t_final-t_init)/num_steps.

Better ways might be to implement runge-katte integration.

## Animation
No clue what to do right now.



