```markdown
# Happy Birthday App

This is a simple Android application built using [Jetpack Compose](https://developer.android.com/jetpack/compose), Google's modern toolkit for building native UI. The app displays a birthday greeting message with a background image, showcasing how easy it is to create UI elements in a declarative manner with Compose.

## Features

- **Jetpack Compose**: The app leverages Jetpack Compose to create a clean and simple UI with a background image and two text elements.
- **Material Design 3**: The UI follows Material Design 3 principles, ensuring a modern and cohesive look.
- **Edge-to-Edge Support**: The app uses the `enableEdgeToEdge` feature to extend content behind the navigation bars for a full-screen experience.

## Preview

Here's a preview of the app's main screen:

![Birthday Card Preview](./assets/birthday_card_preview.png)

## Code Structure

The main components of the app are:

- `MainActivity.kt`: The main entry point of the app, which sets up the content and theme.
- `GreetingImage`: A composable function that displays a background image and overlays the greeting text.
- `GreetingText`: A composable function that displays the birthday message and signature.

### MainActivity

```kotlin
class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContent {
            HappyBirthdayTheme {
                Surface(
                    modifier = Modifier.fillMaxSize(),
                    color = MaterialTheme.colorScheme.background
                ) {
                    GreetingImage(
                        message = stringResource(R.string.happy_birthday_text),
                        from = stringResource(R.string.signature_text)
                    )
                }
            }
        }
    }
}
```

### GreetingImage

```kotlin
@Composable
fun GreetingImage(message: String, from: String, modifier: Modifier = Modifier) {
    val image = painterResource(id = R.drawable.androidparty)
    Box(modifier) {
        Image(
            painter = image,
            contentDescription = null,
            contentScale = ContentScale.Crop,
            alpha = 0.5F
        )
        GreetingText(
            message = message,
            from = from,
            modifier = Modifier
                .fillMaxSize()
                .padding(8.dp)
        )
    }
}
```

### GreetingText

```kotlin
@Composable
fun GreetingText(message: String, from: String, modifier: Modifier = Modifier) {
    Column(
        verticalArrangement = Arrangement.Center,
        modifier = modifier
    ) {
        Text(
            text = message,
            fontSize = 100.sp,
            lineHeight = 116.sp,
            textAlign = TextAlign.Center
        )
        Text(
            text = from,
            fontSize = 36.sp,
            modifier = Modifier
                .padding(16.dp)
                .align(alignment = Alignment.CenterHorizontally)
        )
    }
}
```

## Getting Started

To run this project, you need:

- Android Studio Dolphin or newer
- Android SDK 21 or higher
- Kotlin 1.7.0 or higher

### Steps to Run:

1. Clone this repository.
2. Open the project in Android Studio.
3. Build and run the project on an emulator or physical device.



## Acknowledgments

- [Jetpack Compose](https://developer.android.com/jetpack/compose) for making Android UI development more intuitive.
- [Material Design 3](https://m3.material.io/) for providing a modern and adaptive UI framework.
```

This README file gives an overview of your project, the code structure, and instructions on how to get started. You can customize it further if needed!
