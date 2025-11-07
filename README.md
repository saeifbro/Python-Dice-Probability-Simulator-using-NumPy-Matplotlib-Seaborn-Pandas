# Python-Dice-Probability-Simulator-using-NumPy-Matplotlib-Seaborn-Pandas
This project is made of using Numpy,Pandas,Matplotlib,Seaborn and Pandas.This projects simulates the multiple  dice Rolls using Numpy.Calculating using Numpy and pandas,Seaborn and Matplotlib are use in Visualization the data


Author:Towhidul Islam


import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
import seaborn as sns

size=int(input("Enter the how many time you want to occur:"))






p=np.random.randint(1,7,size=size)
print(p)

unique,counts=np.unique(p,return_counts=True)
print(unique)
print(counts)
unique=list(unique)
count=list(counts)

d=pd.DataFrame({
    "unique":unique,
     "counts":count,
    "probability":((unique/counts)*100)
})
print(f"your d is \n {d}")


plt.bar(unique,counts,align="center")
plt.xlabel("Unique Number",color="red",size=15)
plt.ylabel("Count",color="blue",size=15)
plt.xticks(color="green",size=10)
plt.yticks(color="purple",size=10)
plt.grid(True,color="green",linestyle="--",alpha=0.3)
plt.title("Unique Number Distribution",color="red",size=20)
plt.tight_layout()
plt.savefig("dice_count_distribution.png", dpi=300)

plt.show()

probbability=counts/size

p_array=np.array(probbability)



for i,j,k in zip(unique,counts,p_array):
    print(f'The {i} of the count is {j} and the probability is {k}')








sns.barplot(x="unique",y="counts",hue="probability",data=d,palette="deep")
sns.set_style("darkgrid")
plt.xlabel("Roll_numbers",color="red",size=20)
plt.ylabel("Counts",color="blue",size=20)
plt.xticks(color="green",size=10)
plt.yticks(color="purple",size=10)
plt.title("Counts of the Numbers ",color="blue",size=25)
plt.savefig("dice_count_distribution.png", dpi=300)
plt.tight_layout()

plt.show()

sns.barplot(data=d,x="unique",y="probability",hue="counts",palette="viridis")
sns.set_style("dark")
plt.xlabel("Roll_Numbers",color="red",size=15)
plt.ylabel("Probability",color="blue",size=15)
plt.xticks(color="green",size=10)
plt.yticks(color="red",size=10)
plt.title("Probability Distribution of the Numbers",color="blue",size=20)
plt.savefig("dice_count_distribution.png", dpi=300)
plt.tight_layout()
plt.show()

