
# Horizontal Stack with Multiple Frame Calls

### The Issue
When a single parent frame spawns many child frames (e.g., declaring 10 variables that each hold a function), the layout engine places all children in a single horizontal row.

* **Infinite Width:** The canvas expands indefinitely to the right, requiring excessive scrolling.
* **Line Occlusion (Critical):** The arrows connecting the Global Frame to the distant child frames (e.g., `a10`) become almost perfectly horizontal. They overlap and merge into a single "messy highway" of lines, making it impossible to trace which variable points to which frame.

### Link:  **[Run Test Case](https://share.sourceacademy.nus.edu.sg/acbee)**

### 📝 The Code
```javascript
const make_adder = x => y => x + y;

// Create 10 adders to force horizontal expansion
const a1 = make_adder(1);
const a2 = make_adder(2);
const a3 = make_adder(3);
const a4 = make_adder(4);
const a5 = make_adder(5);
const a6 = make_adder(6);
const a7 = make_adder(7);
const a8 = make_adder(8);
const a9 = make_adder(9);
const a10 = make_adder(10);
