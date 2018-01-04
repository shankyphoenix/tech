import random
from time import clock

randomint = random.randint(1, 100)
print randomint
print("Hello, World!")
print "3" + "-"
print 3 * "-"
print("This %(verb)s a %(noun)s." % {"noun": "test", "verb": "is"})
print("a ad asdf %s- asdfasd"%"xxxxx")
#print (dir("asdf"))
print ("Am fine".startswith("Ams"))
print("a ad asdf {0} asdfasd").format("shanky")
print("a ad asdf {0} asdfasd").format("shanky")

age = {}
age['shanky'] = 31;
age['ryan'] = 3;

print(age.get('ryand','not found'));

#[***]
print([x for x in [2,3] for y in [5,7]])
print([x for x in [2,3,8,9,34,2] if  x != 3])



animal = ["cat","dog","bird"]
for index in animal:
	print index

for index,value in enumerate(animal):
	print index,value

mydict = {"name":"shanky","age":31}

for key in mydict.keys():
	print key

for key in mydict.values():
	print key

for key,value in mydict.items():
	print key,value


#old style
fin = open("helloworld.py")
for line in fin:
	print("=====>",line)
fin.close()

#new style
with open("testing.code") as fin:
	print("=====>",line)

fout = open("testing.code","w")
fout.write("helloworld")
fout.close();


class Shanky:
	def __init__(self,name):
		self.name = name
	def talk(self):
		print self.name


a = Shanky("asdfasdf")
a.talk()




