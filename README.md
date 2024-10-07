# java--3

const obj1 = { a: undefined, b: 1 };
const jsonString1 = JSON.stringify(obj1);
console.log(jsonString1); 

const arr = [1, undefined, 3];
const jsonString2 = JSON.stringify(arr);
console.log(jsonString2); 

const date = new Date();
const jsonString3 = JSON.stringify({ date });
console.log(jsonString3); 

const parsedDate = JSON.parse(JSON.stringify(date));
console.log(parsedDate);
const obj2 = { a: undefined, b: Symbol('sym'), c: function() {} };
const jsonString4 = JSON.stringify(obj2);
console.log(jsonString4); 

const original1 = { a: 1, b: { c: 2 } };
const shallowCopy = Object.assign({}, original1);
shallowCopy.b.c = 3;
console.log(original1.b.c); 

const deepCopy1 = JSON.parse(JSON.stringify(original1));
deepCopy1.b.c = 4;
console.log(original1.b.c); 

const obj3 = { a: undefined, b: Symbol('sym'), c: function() {}, d: { e: 1 } };
const deepCopy2 = JSON.parse(JSON.stringify(obj3));
console.log(deepCopy2); 

const obj4 = { a: 1, b: 2 };
const shallowCopy1 = Object.assign({}, obj4);

const shallowCopy2 = { ...obj4 };

const arr2 = [1, 2, 3];
const shallowCopy3 = arr2.slice();

const original2 = { a: 1, b: { c: 2 } };
const shallowCopy4 = Object.assign({}, original2);
shallowCopy4.b.c = 3;
console.log(original2.b.c); 

const deepCopy3 = JSON.parse(JSON.stringify(original2));


function deepClone(obj) {
  if (obj === null || typeof obj !== 'object') return obj;
  const clone = Array.isArray(obj) ? [] : {};
  for (let key in obj) {
    clone[key] = deepClone(obj[key]);
  }
  return clone;
}
const deepCopiedObject = deepClone(original2);
deepCopiedObject.b.c = 3;
console.log(original2.b.c);

const original3 = { a: 1, b: { c: 2 } };
const copy1 = Object.assign({}, original3);
copy1.b.c = 3;
console.log(original3.b.c); 

const originalArray = [1, 2, { a: 3 }];
const copiedArray = [...originalArray];
copiedArray[2].a = 4;
console.log(originalArray[2].a); 

const original4 = { a: 1, b: { c: 2 } };
const deepCopiedObject2 = deepClone(original4);
deepCopiedObject2.b.c = 3;
console.log(original4.b.c); 

const obj5 = { a: 1, b: function() {} };
const jsonString5 = JSON.stringify(obj5);
console.log(jsonString5); 

const original5 = { a: 1, b: { c: 2 } };
const deepCopy4 = JSON.parse(JSON.stringify(original5));
deepCopy4.b.c = 3;
console.log(original5.b.c); 

const originalArray2 = [[1], [2], [3]];
const copiedArray2 = originalArray2.slice();
copiedArray2[0][0] = 4;
console.log(originalArray2[0][0]); 

const jsonString6 = '{"a":1, "b":true, "c":"hello"}';
const parsedObj = JSON.parse(jsonString6);
console.log(parsedObj); 

const original6 = { a: 1, b: { c: 2 } };
const deepCopy5 = JSON.parse(JSON.stringify(original6));
deepCopy5.b.c = 3;
console.log(original6.b.c); 

const obj6 = { a: Symbol('sym') };
const jsonString7 = JSON.stringify(obj6);
console.log(jsonString7); 

const obj7 = {};
obj7.self = obj7;
try {
  const jsonString8 = JSON.stringify(obj7);
} catch (error) {
  console.error(error); 
}
