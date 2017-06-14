# numpy_introduction

# coding: utf-8

# In[44]:

import numpy as np


# In[45]:

print help(np.genfromtxt)


# In[46]:

#define vector
vertor=np.array([5,10,15,20])
print vertor
#define the matrix
matrix=np.array([[5,10,15],[20,25,30]])
#output the shape
print matrix.shape
#output the type of data
print matrix.dtype


# In[47]:

print vertor[0:3]


# In[48]:

print matrix[:,[0,2]]
print matrix[:,0:2]


# In[49]:

vertor==10 #using this bool value as index


# In[50]:

matrix==25 #using this bool value as index


# In[51]:

print (vertor==10)&(vertor==5)


# In[52]:

print (vertor==10) | (vertor==5)


# In[53]:

np.where(matrix==25)


# In[54]:

vector1=np.array(['1','2','3'])
print vector1.dtype
print vector1
vector1=vector1.astype(float)
print vector1
print vector1.dtype


# In[55]:

vertor.min()


# In[56]:

print matrix.sum(axis=1)
print matrix.sum(axis=0)


# In[57]:

print np.arange(15)
a=np.arange(15).reshape(3,5)
print a


# In[58]:

a.ndim #dimension 


# In[59]:

a.size


# In[60]:

a.dtype.name


# In[61]:

np.zeros((3,4))


# In[62]:

np.zeros([3,4])


# In[63]:

np.ones((2,3,4),dtype=np.int32)


# In[64]:

np.arange(10,30,5)


# In[65]:

np.random.random((2,3))


# In[66]:

np.linspace(0,2*np.pi,100)


# In[67]:

a=np.array([20,30,40,50])
b=np.arange(4)
print a-b


# In[68]:

print a-1


# In[69]:

print b**2


# In[70]:

print a<35


# In[71]:

A=np.array([[1,1],
          [1,0]])
B=np.array([[2,3],
           [3,2]])
print A*B
print np.dot(A,B)


# In[72]:

print np.exp(B)
print np.sqrt(B)


# In[73]:

a=np.floor(10*np.random.random((3,4)))
print a


# In[74]:

a.ravel()


# In[75]:

a.reshape((2,6))


# In[76]:

print a.T


# In[77]:

a.reshape(3,-1)


# In[78]:

a=np.floor(10*np.random.random((2,2)))
b=np.floor(10*np.random.random((2,2)))
print a
print b
print np.hstack((a,b))
print np.vstack((a,b))


# In[79]:

a=np.floor(10*np.random.random([2,12]))
print a
print np.hsplit(a,3)
print np.hsplit(a,(3,5))


# In[80]:

a=np.arange(12)
b=a
print (b is a)
b.shape=3,4
print a.shape
print(id(a))
print (id(b))


# In[81]:

c=a.view()
print (c is a)
c.shape=2,6
print a.shape
c[0,4]=1234
print a
print(id(c))


# In[82]:

d=a.copy()
d is a
d[0,0]=999
print d
print a


# In[83]:

data=np.sin(np.arange(20).reshape(5,-1))
print (data)
ind=data.argmax(axis=0)
print ind
data_max=data[ind,range(data.shape[1])]
print data_max


# In[84]:

a=np.arange(0,40,10)
print a
b=np.tile(a,(2,2))
print b


# In[86]:

a=np.array([4,3,1,2])
j=np.argsort(a)
print a[j]
