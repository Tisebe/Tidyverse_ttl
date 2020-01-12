# Tidyverse_ttl
Tutorial on TIdyverse
### load libraries

library(tidyverse)

### load the data to be used
mpg

## compare engine size and fuel consumption

library(ggplot2)


ggplot(data = mpg)+
  geom_jitter(mapping = aes(x=displ, y=hwy))

### add level 'class' to the plot

ggplot(data = mpg)+
  geom_point(mapping = aes(x=displ, y=hwy, color=class))

## or size

ggplot(data = mpg)+
  geom_point(mapping = aes(x=displ, y=hwy, size=class))

## or transparency of the points using 'alpha'

ggplot(data = mpg)+
  geom_point(mapping = aes(x=displ, y=hwy, shape=class))

### add facet to ensure each data is displayed for a given class of vehicles

ggplot(data = mpg)+
  geom_point(mapping = aes(x=displ, y=hwy))+
  facet_wrap(~class, nrow = 5)

## facet plot on a combination of two variables


ggplot(data = mpg)+
  geom_point(mapping = aes(x=displ, y=hwy))+
  facet_grid(drv~cyl)


ggplot(data = mpg) + 
  geom_point(mapping = aes(x = drv, y = cyl))


?facet_wrap
ggplot(mpg, aes(displ,hwy)) + geom_smooth()


ggplot(data = mpg) + 
  geom_smooth(mapping = aes(x = displ, y = hwy, color = drv))
