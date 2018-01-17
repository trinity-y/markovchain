import random
foundwords = []
wordsDict = {}

with open("text", "r") as file:
	words = file.read().replace('\n',' ').split(' ')

def findwords(word):
	for i in range(len(words) - 1):
		if words[i] == word:
			foundwords.append(words[i + 1])
	return foundwords

def nextword(word):
	poswords = findwords(word)[:]
	del foundwords[:]
	wordsDict.setdefault(word, poswords)
	wordList = wordsDict[word]
	if not wordList:
		new = random.choice(words)
	else:
		new = random.choice(wordList)
	return new
    
def assemble():
	final = [random.choice(words).capitalize()]
	finalword = final[-1]
	while not finalword[-1] == '!' and not finalword[-1] == '.' and not finalword[-1] == '?':
		final.append(nextword(final[-1]))
		finalword = final[-1]
	if len(final) > 1:
		print(' '.join(final))
	del final[:]
	
for i in range(7):
	assemble()
