# monte-carlo-simulation

Monte Carlo simulation is a technique used to estimate the probability of certain outcomes by running simulations based on random sampling.

Let's consider a simple example of estimating the value of π (pi) using a Monte Carlo simulation. The idea is to randomly generate points within a square and determine the ratio of points falling within a quarter circle inscribed within that square.

```js
function monteCarloSimulation(numPoints) {
  let pointsInsideCircle = 0;

  for (let i = 0; i < numPoints; i++) {
    const x = Math.random(); // Generate a random x-coordinate between 0 and 1
    const y = Math.random(); // Generate a random y-coordinate between 0 and 1

    // Check if the point is inside the quarter circle
    if (x * x + y * y <= 1) {
      pointsInsideCircle++;
    }
  }

  // Calculate the estimated value of pi
  const estimatedPi = (4 * pointsInsideCircle) / numPoints;

  return estimatedPi;
}

// Run the simulation with a specified number of points
const numPoints = 1000000;
const estimatedPi = monteCarloSimulation(numPoints);
console.log(`Estimated value of pi: ${estimatedPi}`);
```
