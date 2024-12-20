# Everest
Peaks identification using CNN

## Usage

To install `everest`, download the release and run the following pip command:
```bash
pip install everest-0.0.1-py3-none-any.whl
```

Import the library into your python project to use `everest`:
```python
from everest import find_peaks

peaks_loc, peaks_mag, probs = find_peaks(X, threshold=0.5)
```

### Parameters
- `X` (_array-like_): Input array representing the signal.
- `threshold` (_float_): Probability threshold for identifying peaks (_default_=`0.5`).
- `return_probs` (_bool_): Set this to `True` to return `probs` (_default_=`True`).

### Returns
- `peaks_loc` (_numpy.array_): Locations of the peaks.
- `peaks_mag` (_numpy.array_): Values of the peaks.
- `probs` (_numpy.array_): Probabilities associated with each peak.

## Model 

```mermaid

graph TB;
    Conv1D1[<b>Conv</b> \n<span style="font-size: smaller;">20 channels</span>] --> MaxPool[MaxPool];
    MaxPool --> Conv1D2[Conv1D\n<span style="font-size: smaller;">40 channels</span>];
    Conv1D2 --> Flatten[Flatten];
    Flatten --> Dense1[FC \n<span style="font-size: smaller;">20 units</span>];
    Dense1 --> Dense2[FC \n<span style="font-size: smaller;">4 units</span>];
    Dense2 --> Output[$$\sigma$$];

    class Conv1D1,MaxPool,Conv1D2,Flatten,Dense1,Dense2,Output non-interactive;
```

## Results

<p align="center"><img src="res/find_peaks.png" width="400"></p>

## Contributing
Contributions to Everest are welcome! If you'd like to contribute, follow these steps:
1. **Fork the Repository:** Start by forking the [Everest](https://github.com/enter-opy/everest).
2. **Make Changes:** Create a new branch , make your changes, and commit them to your branch.
3. **Create a Pull Request:** Push your changes to your fork and submit a pull request to the original repository.
## License
This project is licensed under the GNU General Public License. See the [LICENSE](https://github.com/enter-opy/everest/blob/main/LICENSE) for details.

### References

- Anne Bech Risum, Rasmus Bro, [Using deep learning to evaluate peaks in chromatographic data](https://www.researchgate.net/publication/333266782_Using_deep_learning_to_evaluate_peaks_in_chromatographic_data), 2019
- Arsenty D. Melnikov, Yuri P. Tsentalovich, Vadim V. Yanshole, [Deep Learning for the Precise Peak Detection in High-Resolution LC-MS Data](https://pubs.acs.org/doi/10.1021/acs.analchem.9b04811), 2019