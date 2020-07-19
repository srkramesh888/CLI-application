# CLI-application
import requests
wiki_link="https://parivahan.gov.in/rcdlstatus/?pur_cd=101"
link=requests.get(wiki_link).text


# In[4]:


print(link)


# In[12]:


from bs4 import BeautifulSoup
soup=BeautifulSoup(link,'lxml')
print(soup)
print(soup.prettify())


# In[15]:


soup.title.string


# In[17]:


soup.a


# In[19]:


soup.find_all("a")


# In[22]:


all_link=soup.find_all("a")
for link in all_link:
    print(link.get("href"))
