#!/usr/bin/python2.7
# encoding: utf-8

import seaborn as sns
import pandas
import matplotlib.pyplot as plt
import numpy as np

ss = pandas.read_csv('stats/avg-block-size.csv', header=None)
df = pandas.DataFrame({'Taille (MB)': ss[1], 'Date': pandas.to_datetime(ss[0])})

# On retire les cadres du graphique
fig, ax = plt.subplots()
ax.spines["top"].set_visible(False)
ax.spines["bottom"].set_visible(False)
ax.spines["right"].set_visible(False)
ax.spines["left"].set_visible(False)


# On réduit la taille des seuils en abs/ord
plt.yticks(np.arange(0.1, 1.1, 0.1), fontsize=8)
plt.xticks(fontsize=8)

# Pour supprimer les marques en abs/ord
plt.tick_params(axis="both", which="both", bottom="off", top="off",
                labelbottom="on", left="off", right="off", labelleft="on")

plt.plot('Date', 'Taille (MB)',linewidth=0.8, data=df)


#  Bar pour indiquer le seuil des 1MB
plt.axhline(y=1, color='r', linestyle='--', linewidth=0.8, alpha=0.3)


plt.title("Evolution de la taille d\'un bloc (BTC)", loc='left',
          fontsize=13, family='sans-serif', fontweight='black')
plt.xlabel("Date", fontsize=11, weight='light')
plt.ylabel("Taille (MB)", fontsize=11, weight='light')


plt.show()
