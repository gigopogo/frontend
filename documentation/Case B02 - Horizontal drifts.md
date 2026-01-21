

# Horizontal Drift in Loops 


### The Issue
When iterating through a loop that creates frames, the layout engine shifts each subsequent frame further to the right. 

* **The Drift:** As seen between **Stepper 81 and 82**, the new frame is pushed horizontally instead staying aligned.

* **Visual Disconnect:** The frame block containing the function contents drifts further and further away from its parameter frame (context). This spatial separation makes it impossible to visually determine which child frame belongs to which parent context.

### Link: **[Run "Horizontal Drift" Test Case](https://share.sourceacademy.nus.edu.sg/we42a)**

### 📝 The Code
```javascript
const make_frame = (x) => {
    const filler = "I am frame number " + stringify(x); 
    return () => filler;
};

// Create an array of functions
const frames = [];
for (let i = 0; i < 2; i = i + 1) {
    frames[i] = make_frame(i);
}