# PROJECT-SEABORN
# this project shows how seaborn library of python is used to analyze data 
import seaborn as sns 
import pandas as pd
import numpy as np  
%matplotlib inline 
sns.set_style( 'darkgrid')#setting style to 'darkgrid'
penguins= sns.load_dataset('penguins') #loads data set of pemguins  
penguins.head()#loading dataset,head function brings first 5 rows of the dataset
sns.distplot(penguins['body_mass_g'],bins=50,kde=False)#this will show histogram and a k.d.e(kernel density estimation),kde=False removes kde curve,you can use hist=False removes the histogram,rug=True puts the rug feature in the plot.

sns.distplot(penguins['body_mass_g',bins=50,kde=False])#this will show histogram and a k.d.e(kernel density estimation)   

sns.kdeplot(penguins['body_mass_g'])#this will only show the kde 
sns.rugplot(penguins['body_mass_g'])#this will only show the rug plot. 
sns.jointplot(x='bill_length_mm', y='bill_depth_mm', data=penguins,kind='kde')#tthis shows histogram and scatter gragh,kind='hex' wil show hexplot 
sns.pairplot(penguins)#t numericals colums are plotted against each other 
sns.pairplot(penguins,hue='sex')# a four by four numerical chart will produced here numerical plots will be plotted against each other basing on sex 

sns.barplot(x='sex',y='bosnsdy_mass_g',data=penguins,estimator=np.mean,hue='island',)# itwill show barplot, estimator function may also represent standard deviation estimator=np.std
sns.countplot(x='sex',data=penguins,hue='species') 
sns.boxplot(x='species',y='flipper_length_mm',data=penguins)#this creates box plot 
sns.violinplot(x='island',y='flipper_length_mm',data=penguins,hue='sex',split=True)#this creates violin plot,split=True puts both male and female sex on the same violin plot 

sns.stripplot(x='island',y='flipper_length_mm',data=penguins,hue='sex',dodge='True')#this creates strip plot,dodge='True'seperates the dotes of female and male sex 
sns.swarmplot(x='island',y='flipper_length_mm',data=penguins,hue='sex')#this creates swarm plot  
this method below creates 

sns.catplot(x='island',y='flipper_length_mm',data=penguins,kind='bar')#this method creates all the above plots strip ,swarm,count,box you just say kind ='bar' or kind ='strip'
