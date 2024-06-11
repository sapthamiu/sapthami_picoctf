## Description

## Data Provided

## Hints

## Approach

## Commands

## Flags
----------------------------------------------------------

# Flags

## Description
What do the flags mean?

## Data Provided
<img width="821" alt="flag" src="https://github.com/sapthamiu/sapthami_picoctf/assets/157310822/7f8e4e70-6a49-44ff-9c53-9a4c238da951">

## Hints
The flag is in the format PICOCTF{}  

## Approach
The png file contains a set of flag symbols  
When given to Google Lens, it said that these are the signal flags used in the navy  
Looking up its chart decoded the required flag  

![image](https://github.com/sapthamiu/sapthami_picoctf/assets/157310822/295e0486-95b6-4bbf-bffa-c0a64b040bdd)

## Flag
PICOCTF{f1ag5and5tuff}  

# miniRSA

## Description
Let's decrypt this: ciphertext? Something seems a bit small.  

## Data Provided
N: 29331922499794985782735976045591164936683059380558950386560160105740343201513369939006307531165922708949619162698623675349030430859547825708994708321803705309459438099340427770580064400911431856656901982789948285309956111848686906152664473350940486507451771223435835260168971210087470894448460745593956840586530527915802541450092946574694809584880896601317519794442862977471129319781313161842056501715040555964011899589002863730868679527184420789010551475067862907739054966183120621407246398518098981106431219207697870293412176440482900183550467375190239898455201170831410460483829448603477361305838743852756938687673  
e: 3  

ciphertext (c): 2205316413931134031074603746928247799030155221252519872649649212867614751848436763801274360463406171277838056821437115883619169702963504606017565783537203207707757768473109845162808575425972525116337319108047893250549462147185741761825125  

## Hints
1: RSA <a href="https://en.wikipedia.org/wiki/RSA_(cryptosystem)">tutorial</a>  
2: How could having too small an e affect the security of this 2048 bit key?  
3: Make sure you don't lose precision, the numbers are pretty big (besides the e value)

## Approach
Hint 1 provides a link to the wikipedia page of the RSA cryptosystem  
For an encrypted ciphertext c, the decryption function is  
m(c)=(c^d) mod n  
## Commands

## Flag

# transposition-trial

## Description
Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around!  
The first word seems to be three letters long, maybe you can use that to recover the rest of the message.  
Download the corrupted message here.  

## Data Provided
heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V6E5926A}4  

## Hints
Split the message up into blocks of 3 and see how the first block is scrambled  

## Approach
Taking the given hint into consideration, split the coded text into groups of 3  
heT  fl_  g_a  s_i  icp  CTo  {7F  4NR  P05  1N5  _16  _35  P3X  51N  3_V  6E5  926  A}4  
It is clear that the first word is The, which shows that the rearrangement has taken place in the order: 123 to 312
Applying this for all the blocks,
The  _fl  ag_  is_  pic  oCT  F{7  R4N  5P0  51N  6_1  5_3  XP3  N51  V3_  56E  692  4A}  
We get the required flag by joining these blocks  
The flag is picoCTF{7R4N5P051N6_15_3XP3N51V3_56E6924A} 

## Flags
picoCTF{7R4N5P051N6_15_3XP3N51V3_56E6924A} 

# Substitution1

## Description
A second message has come in the mail, and it seems almost identical to the first one.  
Maybe the same thing will work again.
Download the message here.

## Data Provided
SYTe (eakdy tkd sjbyndr yar thjm) jdr j yobr kt skxbnyrd ersndzyo skxbryzyzkc. Skcyreyjcye jdr bdrercyrq gzya j ery kt sajhhrcmre gazsa yrey yarzd sdrjyzwzyo, yrsaczsjh (jcq mkkmhzcm) evzhhe, jcq bdklhrx-ekhwzcm jlzhzyo. Sajhhrcmre nenjhho skwrd j cnxlrd kt sjyrmkdzre, jcq garc ekhwrq, rjsa ozrhqe j eydzcm (sjhhrq j thjm) gazsa ze enlxzyyrq yk jc kchzcr eskdzcm erdwzsr. SYTe jdr j mdrjy gjo yk hrjdc j gzqr jddjo kt skxbnyrd ersndzyo evzhhe zc j ejtr, hrmjh rcwzdkcxrcy, jcq jdr akeyrq jcq bhjorq lo xjco ersndzyo mdknbe jdkncq yar gkdhq tkd tnc jcq bdjsyzsr. Tkd yaze bdklhrx, yar thjm ze: bzskSYT{TD3UN3CSO_4774SV5_4D3_S001_7JJ384LS}

## Hints
1: Try a frequency attack  
2: Do the punctuation and the individual words help you make any substitutions?

## Approach
j is the letter that is being used individually, which indicates that it represents the letter a.  
We know that the flag is always in the format picoCTF{}, which is at the end of the given text.  
SYT seems to be representing CTF  
Using the context, other letters are substituted as:  
abcdefghijklmnopqrstuvwxyz---> hpnrsjwlqaobguyxdecfqkvmti  

Decoded text:  
CTFs (short for capture the flag) are a type of computer security competition. Contestants are presented with a set of challenges which test their creativity, technical (and googling) skills, and problem-solving ability. Challenges usually cover a number of categories, and when solved, each yields a string (called a flag) which is submitted to an online scoring service. CTFs are a great way to learn a wide array of computer security skills in a safe, legal environment, and are hosted and played by many security groups around the world for fun and practice. For this problem, the flag is: picoCTF{FR3QU3NCY_4774CK5_4R3_C001_7AA384BC}  

## Flags
picoCTF{FR3QU3NCY_4774CK5_4R3_C001_7AA384BC}  




