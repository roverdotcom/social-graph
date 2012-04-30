Please submit solutions to
<a href="mailto:tech-jobs@rover.com">tech-jobs@rover.com</a> with a
brief introduction. (Please don't post your solutions online / on GitHub!)

## "The Rover.com Social Graph"

### Outline

Rover.com aims to match sitters with dog owners - the more quickly
we can find a suitable match the better!

For this problem, we'll assume the only suitable sitters are:

1. Your friends
2. Friends of your friends
3. Your past sitters to whom you've given at least a 4 star review
4. Sitters to whom your friends have given at least a 4 star review

Your task is to create a program in Python, Ruby, Javascript or Java
that will print a list of suitable sitters for an individual dog owner.
(If you'd like to use a different language, please shoot us an e-mail first.)

### Program Arguments

Your goal is to create a program that will take 2 positional arguments:

1. The filename of our input data
2. The ID of the user seeking a sitter

In other words, we should be able to run your program like this (after compilation if needed):

```bash
$ ./solution input.csv 1234
```

### Input

The input file will consist of 4 sections:

1. The number of users (0 indexed)
2. A list of sitter IDs (not all users are sitters)
3. A list of friend relationships (2 IDs separated by a comma. Friendship is bi-directional)
4. A list of past stays (the dog owner's ID, the sitter's ID and a number from 1 to 5 representing
    the rating in stars given by the dog owner, each separated by a comma)

Sections 2 to 4 will begin with a number on a separate line indictating how many lines
follow for that section. Below is a small sample input.

The actual input will not include the comments indicated by a # or the whitespace preceding the #.
This file is available as ```sample-input.csv``` in this repository.

Please note entries in real inputs are not necessarily ordered like this
sample input.

```csv
5 # total users, indexed from 0 to 4
3 # 3 sitters
1 #
2 # Users 1, 2 and 4 are sitters
4 #
3 # 3 friend relationships
0,1 # 0 & 1 are friends
1,2 # 1 & 2 are friends
2,3 # 2 & 3 are friends
2 # 2 past stays
1,4,4 # 4 sat 1's dog and received a 4 star rating
3,2,5 # 2 sat 3's dog and received a 5 star rating
```

### Output

For a given user as input, please print the IDs of suitable sitters (newline separated) in order of:

1. Friends
2. Friends of friends
3. Your past sitters who you've given a greater than 4 star review
4. Sitters of friends who received a greater than 4 star review

For the above sample input, if we searched for user 0:

```bash
$ ./solution input.csv 0
```

We'd expect (available as ```sample-output.csv```)

```
1
2
4
```

For other sample inputs:

```bash
$ ./solution input.csv 1
```

```
2
```

```bash
$ ./solution input.csv 2
```

```
1
4
```

```bash
$ ./solution input.csv 3
```

```
2
1
```

```bash
$ ./solution input.csv 4
```

```
```
