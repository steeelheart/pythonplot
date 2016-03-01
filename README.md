# pythonplot
x=[0.6,1.2]
y1=[0.090,0.087]
y2=[0.073,0.109]
%matplotlib inline
fig=plt.figure()
axes=fig.add_subplot(111)
axes.plot(x,y1, linestyle='--',color='black', marker='^', markersize=8,linewidth=3.0, label='High Number of Restaurants Nearby')
axes.plot(x,y2, marker='o',color='black',markersize=8,linewidth=3.0,label='Low Number of Restaurants Nearby')
plt.ylim([0,0.18])
plt.xlim([0.3,1.5])
ticks=axes.set_xticks([0.3,0.6,1.2,1.5])
labels=axes.set_xticklabels(['','Low','High',''])
stepsize=15
#yticks=axes.set_yticks(np.arange(0, 0.15, stepsize))
ylabels=axes.set_yticklabels([''])
for tick in axes.xaxis.get_major_ticks():
    tick.label.set_fontsize(12)
    tick.label.set_fontname("Times New Roman")
    tick.label.set_fontweight("bold")     
    
plt.xlabel('Average Yelp Ratings', fontname="Times New Roman" ,fontsize=15)
plt.ylabel('Proportion of Groupon Restaurants', fontsize=12)
#axes.get_yaxis().set_visible(False)
for i in range(2):
    axes.annotate(y1[i],(x[i],y1[i]), xytext=(-5, 5),ha='right',textcoords='offset points')

for i in range(2):
    axes.annotate(y2[i],(x[i],y2[i]),xytext=(-5, 5),ha='right',textcoords='offset points')
plt.legend( loc='upper left', numpoints = 1 )
