Here's the full README file content with the `MainActivity` section rewritten to match the style of the `GreetingImage` section:

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

### MainActivity

```kotlin
class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        
        // Enables edge-to-edge content display
        enableEdgeToEdge()
        
        // Sets the content view using Jetpack Compose
        setContent {
            HappyBirthdayTheme {
                
                // Defines the surface for the UI
                Surface(
                    modifier = Modifier.fillMaxSize(), // Fills the entire screen
                    color = MaterialTheme.colorScheme.background // Applies the background color from the theme
                ) {
                    
                    // Calls the GreetingImage composable with the message and signature
                    GreetingImage(
                        message = stringResource(R.string.happy_birthday_text), // Fetches the birthday message string
                        from = stringResource(R.string.signature_text) // Fetches the signature string
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
        
        // Displays the background image with a semi-transparent overlay
        Image(
            painter = image,
            contentDescription = null, // No description needed as the image is decorative
            contentScale = ContentScale.Crop, // Crops the image to fill the space
            alpha = 0.5F // Sets the image transparency
        )
        
        // Overlays the greeting text on top of the image
        GreetingText(
            message = message,
            from = from,
            modifier = Modifier
                .fillMaxSize() // Fills the available space
                .padding(8.dp) // Adds padding around the text
        )
    }
}
```

### GreetingText

```kotlin
@Composable
fun GreetingText(message: String, from: String, modifier: Modifier = Modifier) {
    
    // Arranges the text elements in a vertical column
    Column(
        verticalArrangement = Arrangement.Center, // Centers the text vertically
        modifier = modifier
    ) {
        
        // Displays the main birthday message
        Text(
            text = message,
            fontSize = 100.sp, // Sets the font size
            lineHeight = 116.sp, // Sets the line height
            textAlign = TextAlign.Center // Centers the text horizontally
        )
        
        // Displays the signature below the main message
        Text(
            text = from,
            fontSize = 36.sp, // Sets the font size for the signature
            modifier = Modifier
                .padding(16.dp) // Adds padding around the signature
                .align(alignment = Alignment.CenterHorizontally) // Centers the signature horizontally
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

This README file is formatted consistently, with detailed comments explaining the key parts of the code. It provides an overview of the project, its features, and instructions for getting started.
