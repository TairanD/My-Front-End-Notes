# Virtual DOM

## 1 - What is DOM?
The DOM is an object-oriented representation of the web page, which can be modified with a scripting language like JavaScript.
When you change an element on a web page, the browser updates the DOM to reflect those changes. However, manipulating
the DOM directly can be slow, especially when there are many changes, as the browser needs to re-render part or all of
the page each time a change is made.

## 2 - What is Virtual DOM?
The Virtual DOM is an abstraction of the actual DOM, a lightweight **copy** that React keeps in memory. 
When a component's state or props change, React creates a new VDOM tree. This virtual tree is then compared with the
previous VDOM tree (a process known as reconciliation). React identifies the differences (or "diffs") between the two 
VDOM trees and calculates the most efficient way to update the actual DOM to reflect these changes.