# Bash Scripting

#### Slicing a String
```bash
char=${text:$i:1}
```

#### Only letters in String
```bash
text="${@//[^a-zA-Z]/}"
```

#### Uppercase String
```bash
phrase=${text,,}
```

#### Downcase String
```bash
phrase=${text,}
```

#### Substring is inside the String
```bash
"$PHRASE" == *"$letter"*
```

#### String is empty
```bash
if [[ -z "$string" ]]; then
	echo "Is empty"
fi
```

#### String is not empty
```bash
if [[ -n "$string" ]]; then
	echo "Not empty"
fi
```

#### String is not empty
```bash
if [[ -n "$string" ]]; then
	echo "Not empty"
fi
```

#### Count the number of arguments
```bash
num_arguments="$#"
```

#### Range
```bash
for letter in {a..z}; do echo $letter; done
for value in {0..5}; do echo $value; done 
```


