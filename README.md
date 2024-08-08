# Segmented Buttons UI in Jetpack Compose

This project showcases a segmented button UI using Jetpack Compose's `SingleChoiceSegmentedButtonRow`. It allows for easy navigation between different options with a visually appealing design.

## Features

- Dynamic segmented buttons with selectable options.
- Smooth transitions between different segments.
- Customizable button shapes and styles.

## Screenshots
<div style="display: flex; justify-content: center; align-items: center;">
    <img src="https://github.com/user-attachments/assets/30380980-666a-4c54-90e6-9f609496ca4f" alt="First Screenshot" style="width: 200px; height: auto; margin-right: 10px;">
    <img src="https://github.com/user-attachments/assets/37d30c91-4459-4ea8-8265-2a1481d01e1c" alt="Second Screenshot" style="width: 200px; height: auto;">
</div>

## Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/Bhavyansh03-tech/Segmented_Buttons.git
    ```

2. Open the project in Android Studio.

3. Sync the project with Gradle files.

## Usage

To use the segmented button UI in your project, integrate the `SingleChoiceSegmentedButtonRow` and `SegmentedButton` composables as shown below:

```kotlin
@OptIn(ExperimentalMaterial3Api::class)
class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContent {
            SegmentedButtonsTheme {

                var selectedIndex by remember {
                    mutableIntStateOf(0)
                }

                val options = remember {
                    mutableStateListOf("Music", "Movies", "Podcasts")
                }

                Box(
                    modifier = Modifier.fillMaxWidth(),
                    contentAlignment = Alignment.Center
                ) {
                    SingleChoiceSegmentedButtonRow {
                        options.forEachIndexed { index, option ->
                            SegmentedButton(
                                selected = selectedIndex == index,
                                onClick = { selectedIndex = index },
                                shape = SegmentedButtonDefaults.itemShape(
                                    index = index,
                                    count = options.size
                                )
                            ) {
                                Text(text = option)
                            }
                        }
                    }
                }
            }
        }
    }
}
```

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request for any improvements or bug fixes.

1. Fork the repository.
2. Create your feature branch (`git checkout -b feature/your-feature`).
3. Commit your changes (`git commit -am 'Add some feature'`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Create a new Pull Request.

## Contact

For questions or feedback, please contact [@Bhavyansh03-tech](https://github.com/Bhavyansh03-tech).

---
