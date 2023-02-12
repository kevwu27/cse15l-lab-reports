# Kevin Wu - Lab Report 3
  
## grep Command 
This page shows a few ways of using the grep command in terminal.

### 1. grep -c "pattern" /file/
  This command prints out the number of instances the given pattern appears in each line of the file(s) (-c).
  Command is taken from terminal manual for grep (man grep).
  
**Example 1:**
```
$ grep -c "Lucayans" ./written_2/travel_guides/berlitz2/*.txt
./written_2/travel_guides/berlitz2/Algarve-History.txt:0
./written_2/travel_guides/berlitz2/Algarve-Intro.txt:0
./written_2/travel_guides/berlitz2/Algarve-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/Algarve-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/Amsterdam-History.txt:0
./written_2/travel_guides/berlitz2/Amsterdam-Intro.txt:0
./written_2/travel_guides/berlitz2/Amsterdam-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/Amsterdam-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/Athens-History.txt:0
./written_2/travel_guides/berlitz2/Athens-Intro.txt:0
./written_2/travel_guides/berlitz2/Athens-WhatToDo.txt:0
./written_2/travel_guides/berlitz2/Athens-WhereToGo.txt:0
./written_2/travel_guides/berlitz2/Bahamas-History.txt:2
./written_2/travel_guides/berlitz2/Bahamas-Intro.txt:0
./written_2/travel_guides/berlitz2/Bahamas-WhatToDo.txt:0
## MORE OUTPUT THAT HAS BEEN REDACTED DUE TO LENGTH ##
```

**Example 2:**
```
$ grep -c "femtosecond" ./written_2/non-fiction/OUP/Kauffman/*.txt
./written_2/non-fiction/OUP/Kauffman/ch1.txt:0
./written_2/non-fiction/OUP/Kauffman/ch10.txt:0
./written_2/non-fiction/OUP/Kauffman/ch3.txt:0
./written_2/non-fiction/OUP/Kauffman/ch4.txt:0
./written_2/non-fiction/OUP/Kauffman/ch5.txt:0
./written_2/non-fiction/OUP/Kauffman/ch6.txt:0
./written_2/non-fiction/OUP/Kauffman/ch7.txt:3
./written_2/non-fiction/OUP/Kauffman/ch8.txt:0
./written_2/non-fiction/OUP/Kauffman/ch9.txt:0
```

### 2. grep --colour -n "pattern" /file/
  This command prints out the line and corresponding line numbers in the file that contain the given pattern (-n). It also colors the given pattern
  in the output to make it stand out (--colour).
  Command is taken from terminal manual for grep (man grep).
  
  * Color does not show in code block, but it was red in the terminal

**Example 1:**
```
$ grep --colour -n "Lucayans" ./written_2/travel_guides/berlitz2/Bahamas-History.txt
6:Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
7:The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
```
**Example 2:**
```
$ grep --colour -n "femtosecond" ./written_2/non-fiction/OUP/Kauffman/ch7.txt
29:Now let’s consider the estimated number of particles in the known universe, which is . Thus, the maximum number of pairwise collisions that could occur in any instant, ignoring distances between particles, is that number squared, or . A fast reaction occurs in a femtosecond, or one part in seconds. Then the number of pairwise collisions and reactions that can have occurred since the estimated time of the big bang fourteen billion years ago is times the number of femtoseconds since the big bang, which is about .
30:The total number of reactions on a femtosecond timescale cannot be larger than , a very very big number. But is infinitesimally small compared to the number of possible proteins of length , namely, . In short, the known universe has not had time since the big bang to create all possible proteins of length once. Indeed the time required to create all possible proteins at least once is at least the ratio of possible proteins to the maximum number of reactions that can have occurred in the lifetime of the universe, or times the lifetime of the universe.
33:What about the arbitrary restriction to a femtosecond? The fastest known timescale is the Planck timescale, one in to the rd parts of a second, or seconds. At the Planck timescale, therefore, the universe can have created at most proteins of length compared to such proteins. It would take the known universe, chunking along on the Planck timescale, times its current lifetime to make all proteins of length .

```

### 3. grep -v "pattern" /file/
  This command prints out all lines in the file that do NOT contain the pattern (-v).
  Command is taken from terminal manual for grep (man grep).
  
**Example 1:**
```
$ grep -v "Lucayans" ./written_2/travel_guides/berlitz2/Bahamas-History.txt
A Brief History
English sea captains also came to know the beautiful but deserted Bahamian islands during the 17th century. England’s first formal move was on 30 October 1629, when Charles I granted the Bahamas and a chunk of the American south to his Attorney General, Sir Robert Health. But nothing came of that, nor of a rival French move in 1633 when Cardinal Richelieu, the 17th-century French statesman, tried claiming the islands for France.
Colonization and Piracy
In 1648 a group of English Puritans from Bermuda, led by William Sayle, sailed to Bahamian waters and established the first permanent European settlement on the island they named Eleutheria (now Eleuthera) after the Greek word for freedom. The 70 colonists called themselves the Eleutherian Adventurers, but life was very difficult and the colony never flourished, though Sayle was long honored for the effort. In 1666 a smaller island (called Sayle’s island) with a fine harbor was settled by Bermudians and renamed New Providence. It was later to become known as Nassau, capital of the Bahamas.
## MORE OUTPUT THAT HAS BEEN REDACTED DUE TO LENGTH ##
```

**Example 2:**
```
$ grep -v "femtosecond" ./written_2/non-fiction/OUP/Kauffman/ch7.txt
Chapter 7
The Nonergodic Universe:
The Possibility of New Laws
rom a biosphere and its mysteries, this investigation now steps gingerly toward the cosmos. Caveat lector: I am not a physicist.
Our now familiar liter of gas particles at room temperature comes to equilibrium rapidly, certainly on the order of hours or days. “Equilibrium” means, roughly, that the macroscopic properties of the system, such as temperature and pressure, have stopped changing, except for small “square root N” fluctuations away from equilibrium that soon dissipate back toward equilibrium. As we have noted, thanks to the ergodic hypothesis, the gas system ultimately visits each macrostate at a number of times proportional to the number of microstates in that macrostate. For equilibrium with respect to all macroscopic properties to have been attained, it is not necessary that all microstates have been sampled, of course, but that the statistical distribution of microstates approaches the equilibrium distribution.
## MORE OUTPUT THAT HAS BEEN REDACTED DUE TO LENGTH ##
```

### 4. grep -C# "pattern" /file/
  This command prints out a given number of lines before and after the matched line with the pattern, along with the matching line itself (-C#).
  Command is taken from [here](https://www.geeksforgeeks.org/grep-command-in-unixlinux/).
  
**Example 1:**
* -C3 is three lines before and after
```
$ grep -C3 "Lucayans" ./written_2/travel_guides/berlitz2/Bahamas-History.txt
A Brief History
Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
English sea captains also came to know the beautiful but deserted Bahamian islands during the 17th century. England’s first formal move was on 30 October 1629, when Charles I granted the Bahamas and a chunk of the American south to his Attorney General, Sir Robert Health. But nothing came of that, nor of a rival French move in 1633 when Cardinal Richelieu, the 17th-century French statesman, tried claiming the islands for France.
Colonization and Piracy
In 1648 a group of English Puritans from Bermuda, led by William Sayle, sailed to Bahamian waters and established the first permanent European settlement on the island they named Eleutheria (now Eleuthera) after the Greek word for freedom. The 70 colonists called themselves the Eleutherian Adventurers, but life was very difficult and the colony never flourished, though Sayle was long honored for the effort. In 1666 a smaller island (called Sayle’s island) with a fine harbor was settled by Bermudians and renamed New Providence. It was later to become known as Nassau, capital of the Bahamas.

```

**Example 2:**
* -C1 is one line before and after
```
$ grep -C1 "femtosecond" ./written_2/non-fiction/OUP/Kauffman/ch7.txt
Consider the number of possible proteins of length . That is, we consider proteins made of the familiar kinds of standard encoded amino acids and, thus, linear chains of such amino acids. Since there are choices at each of positions, the number of possible proteins of length is raised to the th power, or approximately raised to the th power, . Now let’s consider the estimated number of particles in the known universe, which is . Thus, the maximum number of pairwise collisions that could occur in any instant, ignoring distances between particles, is that number squared, or . A fast reaction occurs in a femtosecond, or one part in seconds. Then the number of pairwise collisions and reactions that can have occurred since the estimated time of the big bang fourteen billion years ago is times the number of femtoseconds since the big bang, which is about .
The total number of reactions on a femtosecond timescale cannot be larger than , a very very big number. But is infinitesimally small compared to the number of possible proteins of length , namely, . In short, the known universe has not had time since the big bang to create all possible proteins of length once. Indeed the time required to create all possible proteins at least once is at least the ratio of possible proteins to the maximum number of reactions that can have occurred in the lifetime of the universe, or times the lifetime of the universe.
Let that sink in. It would take at least to the th times the current lifetime of the universe for the universe to manage to make all possible proteins of length at least once. Obviously, with respect to proteins of length the universe is vastly nonergodic. It cannot have equilibrated over all these possible dierent molecules. At a level of complexity above atomic nuclei, once into the realm of complex molecules, the universe will not, cannot, come to equilibrium, on vastly long timescales compared to its historical age. Indeed, the giant cold molecular clouds in galaxies, about degrees absolute in temperature, are highly complex mixtures of molecular species, many carbonaceous, as well as the birthplace of stars. We will return in a moment to wonder about whether a galaxy, considered as a closed thermodynamic system, reaches equilibrium chemically. What about the arbitrary restriction to a femtosecond? The fastest known timescale is the Planck timescale, one in to the rd parts of a second, or seconds. At the Planck timescale, therefore, the universe can have created at most proteins of length compared to such proteins. It would take the known universe, chunking along on the Planck timescale, times its current lifetime to make all proteins of length . Now many biological proteins are of length , or even amino acids. Hence the number of possible proteins of length does its now familiar hyperastronomical combinatorial explosion to or . The universe can have managed to make to the of these at the Planck timescale.
```

---
## END 


