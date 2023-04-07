# Задачи по JavaScript

## Является ли слово палиндромом

```jsx
// Base
function isPalindrome(string) {
	let arr = string.split('');
	let reversArr = arr.reverse();
	let resString = reversArr.join('');
	let res = string === resString;
	return res;
}
```

```jsx
/ Advanced
function isPalindrome(str) {
	return str === str.split('').reverse().join ('');
}
```

```jsx
// ES6 const isPalindrome = str =>
	str === str.split('').reverse().join('');
```

## Поиск самого короткого слова в предложении

```jsx
// Base
function findShort(string) {
	let wordsArr = string.split(' ');
	let sortedWordsArr = wordsArr.sort(function(a, b) {
		return a.length - b.length;
	});
return sortedWordsArr[0];
```

```jsx

// Advanced
function findShort(string) {
	return string
		.split(' ')
		.sort(function(a, b) {
			return a.length - b.length;
		})[0];
}
```

```jsx
// ES6
const findShort = string =>
	string
		.split(' ')
		.sort((a, b) => a.length - b.length)[0];
```

## Создание инициалов

```jsx
// Base
function tolnitials(name) {
	var nameArr = name.split(' ');
	var firstLettersArr = nameArr.map(function(el) {
			return el.slice(0,1).toUpperCase() + '.';
	});
	var initials = firstLettersArr.join('');
	return initials;
}
```

```jsx
// Advanced function
tolnitials(name) {
	return name
		.split (' ')
		.map(function(el) {
			return el.slice(0,1).toUpperCase() + '.';
		})
		.join('’);
}
```

```jsx
// ES6
const tolnitials = name =>
	name
		.split('')
		.map(el => `${el.slice(0,1).toUpperCase()}.`)
		.join('');
```

## Суммирование всех цифр числа

```jsx
// Base
function sumDigits(number) {
	var moduleNumber = Math.abs(number);
	var str = moduleNumber.toString();
	var arr = str.split('');
	var res = arr.reduce (function(sum, cur) {
		return Number(sum) + Number(cur);
	}, 0);
	return res;
}
```

```jsx
// Advanced
function sumDigits(number) {
	return Math.abs(number)
		.toString()
		.split('')
		.reduce(function(sum, cur) {
			return +sum + +cur
		}, 0)
}
```

```jsx
// ES6
const sumDigits = number =>
	Math.abs(number)
		.toStringO
		.split('')
		.reduce((sum, eur) => +sum + +cur, 0);
```

## Поиск min и max значений в массиве

```jsx
// Base
function minMax(arr){
	var res = [];
	var minValue = Math.min.apply(null, arr);
	var maxValue = Math.max.apply(null, arr);
	return res.push(minValue, maxValue);
}
```

```jsx
// Advanced
function minMax(arr){
	return [Math.min.apply(null, arr), Math.max.apply(null, arr)];
}
```

```jsx
// ES6
const minMax = (arr) =>
	[Math.min(...arr), Math.max(...arr)];
```

## Создание набора дубликатов символов строки

```jsx
// Base
function accum(string) {
	var arr = string.toUpperCase().split('');
	var repeatArr = arr.map(function(el,i) {
		return el += el.repeat(i).toLowerCase();
	});
	var resString = repeatArr.join('-');
	return resString;
}
```

```jsx
// Advanced
function accum(string) {
	return string.toUpperCase().split('').map(
		function(el,i) {
			return el += el.repeat(i).toLowerCase(); 
		}
	).join('-');
}
```

```jsx
// ES6
const accum = (string) 
	=> string
		.toUpperCase()
		.split('')
		.map((el,i) -> `${el}${el.repeat(i).toLowerCase()}`)
		.join('-');
```

## Возврат индексов заглавных букв строки

```jsx
// Base
function capitals(word) {
	var bigLetters = word.toUpperCase().split('');
	var smallLetters = word.split('');
	var res = [];
	for(var i = 0; i < word.length; i++) {
		if (smallLetters[i] === bigLetters[i]) {
			res.push(i); }
		}
	return res;
};
```

```jsx
// Advanced
function capitals(word) {
	var res = [];
	word.split('').forEach(function(letter, index) {
		if (letter === letter.toUpperCase()) {
			res.push(index);
		} 
	});
	return res;
};
```

```jsx
// ES6
const capitals = (word) =>
	word
		.split('')
		.reduce((result, letter, index) => {
			if (letter === letter.toUpperCase()) {
				result.push(index);
			}
	return result;
},[]};
```

## Вывод чисел от 1 до n. ‘foo’ вместо чисел % 3, ‘bar’ вместо чисел % 5, ‘foobar’ вместо чисел % 3 и 5

```jsx
// Base
const fooBar = num => {
	for(let i = 1; i <= num; i++) {
		if (i % 3 === 0 && i % 5 === 0) { // multiple of 3 and 5
				console.log('foobar ');
		} else if (i % 3 === 0) { // multiple of 3
				console.log('foo');
		} else if (i % 5 === 0) { // multiple 5
				console.log('bar');
		} else { // other numbers
				console.log(i);
		}
	}
};
```

## Возврат уникальных значений из нескольких массивов

```jsx
// Base
function uniteUnique () {
	const arr = [...arguments];
	let newArr = [] ;
	for(var i = 0; i < arr.length; i++){
		newArr.push(...arr[i]);
	}
	newArr = new Set(newArr);
	return [...newArr];
}
```

```jsx
// Advanced
function uniteUnique() {
	return [...new Set([...arguments].flat())];
}
```

## Форматирование цифр в телефонный номер

```jsx
// Base
function createPhoneNumber(number) {
	let numArr = number.toString().split('');
	numArr.splice(0,0,'(');
	numArr.splice(4,0,')');
	numArr.splice(5,0,' ');
	numArr.splice(9,0,'-');
	return numArr.join(' ');
}
```

```jsx
// Advanced
const createPhoneNumber = (number) => {
	const strNum = number.toString(); // template pattern: (xxx) xxx-xxx
	return `(${strNum.slice(0, 3)}) ${strNum.slice(3, 6)}-${strNum.slice(6, 9)}`;
}

```

## Количество гласных букв в строке

```jsx
// Base
const findVowels = (str) => {
	const vowels = ['a', 'e', 'i', 'o', 'u'];
	let count = 0;
	for(let char of str.toLowerCase()) {
		if(vowels.includes(char)) {
			count++;
		}
	}
	return count;
}
```

```jsx
// Advanced
const findVowelsl = (str) => {
	const matches = str.match(/[aeiou]/gi);
	return matches ? matches.length : 0;
}
```

## Трансформация букв в заглавный регистр

```jsx
// Base
function toCapitalCasel(str) {
	const arr = str.split(' ');
	const resArr = [];
	for (let i = 0; i < arr.length; i++) {
		resArr.push(arr[i][0].tolIpperCase() + arr[i].slice(1));
	}
	return resArr.join (' ');
}
```

```jsx
// Advanced
const toCapitalCase = (str) =>
	str
		.split(' ')
		.map((word) => `${word[0].toUpperCase()}${word.slice(1)}`)
		.join(' ');
```
