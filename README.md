```markdown
# gas-liquid-flow-cnn-prediction

Official repository for the 1D CNN-based Virtual Sensor to predict liquid holdup time series in dense gas slug flow (I2MTC 2026).

## Presentation Abstract

**Title:** Gas-Liquid Flow Time Series Prediction using Convolutional Neural Networks and Distributed Capacitive Sensors

**Abstract—**Gas-liquid two-phase flow, particularly in the intermittent (slug) regime, is predominant in hydrocarbon production and transport. A growing challenge lies in the exploration of ultra-deepwater reservoirs, such as the Brazilian Pre-Salt, where high gas densities are reached due to pressure and composition. In these scenarios, the gas-liquid density ratio is low, drastically altering hydrodynamics and limiting the accuracy of phenomenological models and commercial simulators. The accurate prediction of two-phase flow behavior in pipelines is critical for optimizing industrial processes. This work proposes the development of a Virtual Sensor for the time-series prediction of liquid holdup in dense gas slug flow. Experiments were conducted using mineral oil and Sulfur Hexafluoride (SF6) at 5 bar in a horizontal pipeline, with a measurement system consisting of five distributed capacitive sensors measuring liquid volume fraction over time. The modeling methodology employs a 1D Convolutional Neural Network (CNN), structured with five convolutional layers and two dense layers, trained collectively and individually with data from 16 operational points. A sliding window technique is utilized, synchronized by a delay calculated from the bubble velocity (Vb) obtained via cross-correlation, allowing the network to effectively track the propagation of slug structures. Results demonstrate that this specialized architecture achieves high accuracy in predicting the time series of the fifth sensor based on the four upstream sensors, with consistently low Mean Squared Errors (e.g., MSE = 0.0019), validating the application of CNNs for robust and dynamic monitoring of complex dense gas flows.

---

## Repository Structure and Notebooks

### Data Processing
* **`i2mtc_data_processing.ipynb`**  
  Handles the processing of raw sensor data and the generation of sliding windows using the cross-correlation desynchronization methodology.

### Specialized Training
* **`i2mtc_specialized_training.ipynb`**  
  Handles the training and evaluation stages using separate, individual experimental points for each model.

### Generalized Training
* **`i2mtc_generalized_training.ipynb`**  
  Trains a single unified model using data from all experimental points. It includes two evaluation options:
  * **Option 1:** Evaluates the model using the combined test sets from all experimental points.
  * **Option 2:** Evaluates the model using the test set from a single, selected experimental point.

```
