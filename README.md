#### Question #1: Turning Strings to URLs
URLs cannot have spaces. Instead, all spaces in a string are replaced with %20. Write an algorithm that replaces all spaces in a string with %20.

You may not use the replace() method or regular expressions to solve this problem. Solve the problem with and without recursion.

Example
Input: "Jasmine Ann Jones"

Output: "Jasmine%20Ann%20Jones"

```
function stringToUrl(input)
{
  let url = "";
  let value = "";
  if ("string" !== typeof(input))
  {
    input = input.toString();
  }
  for(i = 0; i < input.length; i++)
  {
    if(input[i] === " ")
    {
      value = "%20"
    }
    else
    {
      value = input[i]
    }
    url += value;
  }
  return url
}
```
```
function stringToUrl(input)
{
  let value = "";
  let count = input.length;
  if ("string" !== typeof(input))
  {
    input = input.toString();
  }
  if (count === 1)
  {
    if (input === " ")
    {
      value = "%20";
    }
    else
    {
      value = input;
    }
    return value;
  }
  else
  {
    let midpoint = input.length / 2;
    let part1 = input.substring(0, midpoint);
    let part2 = input.substring(midpoint);
    return stringToUrl(part1) + stringToUrl(part2);
  }
}
```
