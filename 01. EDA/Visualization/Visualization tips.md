### Menggabungkan 2 plot sekaligus
```python
f = plt.figure(figsize=(12,4))
f.add_subplot(1,2,1)
df['HP'].plot(kind='kde')
f.add_subplot(1,2,2)
plt.boxplot(df['HP'])
plt.show()
```
