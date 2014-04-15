Home Range Plotting Code
========================

Begin by loading the HR_dataset.txt file

```
read.table("HR_dataset.txt",header=T)->data
```

### Plotting all home range versus body mass and diet for all species.

```
# Make up x and y labels
labelsX='Body Mass (kg)'
labelsY=expression ('Home range' (km^'2'))

# Create colours for diet categories
col.diet<-c(Carnivore="Black",
            Omnivore="snow4",
            Herbivore="White")

# Plot data and axes
plot(data$Home_range_km2~data$Mass_kg,xlab=labelsX,ylab=labelsY,axes=F,col="black",pch=21,bg=col.diet)

axis(side=2,at=-4:6,labels=10^(-4:6),las=1, tck=0.01)
axis(side=1,at=-3:5,labels=10^(-3:5),tck=0.01)
box(bty='L')

# Add regression lines


```



