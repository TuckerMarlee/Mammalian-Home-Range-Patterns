Home Range Plotting Code
========================

Begin by loading the HR_dataset.txt file

```
read.table("HR_dataset.txt",header=T)->data
```

### Plotting all home range versus body mass and diet for all species.

```
# Set figure name
pdf("Figure 2.pdf")

# Set axes labels
labelsX='Body Mass (kg)'
labelsY=expression (Home*phantom(x)*range*phantom(x)*(km^'2'))

# Set figure margins
par(mar=c(5,6,4,2)+0.1)

# Set figure colours
palette(c("black","white","snow4"))

# Plot figure
plot(data$Home_range_km2~data$Mass_kg,xlab=labelsX,ylab="",axes=F,col="black",pch=21,bg=data$Diet)
mtext (labelsY,side=2,line=4)
options(scipen=10) #so no sci notation used
axis(side=2,at=-4:6,labels=10^(-4:6),las=1, tck=-0.01,cex=0.6)
axis(side=1,at=-3:5,labels=10^(-3:5),tck=-0.01,cex=0.6)
box(bty='L')

# Add regression lines
abline(-0.29,1.19,col="black",lwd=2)
abline(-0.91,1.19,col="snow4",lwd=2)
abline(-1.47,1.19,col="black",lwd=2,lty=2)

#Add legend
legend("topleft", c("Carnivore","Omnivore","Herbivore"),
        pch=21,  pt.bg=c("black","white","snow4"),bty = "n",cex=0.9,col = "black") 

# Print figure to file
dev.off()


```
### Figure 2
![alt text](c:/Users/user/Documents/UNSW/HR data/Figure 2.jpeg "Figure 2")



