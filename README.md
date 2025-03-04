## React Native Commands  

```bash
   npx create-expo-app@latest
```  
```bash
   npx expo start 
```

- The latest version of the Expo SDK is SDK 52  
```bash
   npx create-expo-app@latest CoreComponents --template 
blank@sdk-52
```  
- --template blank@sdk-52: This flag tells the command to use the blank template from the SDK 52 version. The blank template is a minimal starting point for your project, containing just the basic setup and structure without any additional libraries or components.

## React Native Core Components  

![React Native Core Components](<./images/ui_compo.png>)

### View Component

- Basic Usage: View is a core component for building UI, similar to div in HTML.  

   ```jsx
   import { View } from 'react-native';
   
   const MyComponent = () => (
   <View style={styles.container}>
      {/* Other components */}
   </View>
   );
   ```
- Styling: Use the style prop to add styles.

   ```jsx
   const styles = StyleSheet.create({
   container: {
      flex: 1,
      justifyContent: 'center',
      alignItems: 'center',
   },
   });
   ```
- Flexbox Layout: View supports flexbox layout for positioning child components.

   ```jsx
   <View style={{ flexDirection: 'row', justifyContent: 'space-between' }}>
   <View style={{ flex: 1 }} />
   <View style={{ flex: 2 }} />
   </View>
   ```

- Accessibility: Add accessibility props for better usability.
   ```jsx
   <View accessible={true} accessibilityLabel="Timesheet Entry Container">
   {/* Child components */}
   </View>
   ```

- Event Handling: Can handle touch events using props like onTouchStart, onTouchMove, etc.

   ```jsx
   <View onTouchStart={() => console.log('Touch started!')}>
   {/* Child components */}
   </View>
   ```

### Text Component

### Image Component

- The Image component enables us to display various types of images, including
   · Static images
   · Network images
   . Images from the local disk, such as the camera roll

- React Native seamlessly translates the Image component to platform-specific counterparts:
   · UllmageView for iOS
   · ImageView for Android
   . 'img' for the Web

### ScrollView
- ScrollView component wraps the platform-specific scrolling functionality
- ScrollViews require a bounded height to function properly

### Button
- button component allows users to trigger actions
- button component has platform-specific rendering for iOS and Android
- onClick in react = onPress in react-native
- *Button component in React Native does not directly support a style prop. To achieve the desired styling, you can use a View wrapper around the Button and apply the style to the View component.*

- **Pressable**
   - Pressable is a wrapper component that detects various stages of press interactions on its defined children

### Pressable Component
- Flexible: Pressable is highly customizable and can wrap around any element, such as View, Text, Image. Also can create custom button using Pressable. 

- Event Handling: It provides a broader range of event handlers such as onPressIn, onPressOut, onLongPress, onPress, and onHoverIn.

- Use Case: Ideal for creating custom buttons and interactive elements with more complex styles and behaviors.
   ```jsx
      <Pressable 
         style={({ pressed }) => [{ backgroundColor: pressed ? 'lightgray' : 'blue' }, styles.button]}
         onPress={() => console.log('Pressed!')}>
         <Text style={styles.text}>Press Me</Text>
      </Pressable>
   ```

![onpress events](<./images/onPress events.png>)

### Modal

- Model is a screeen that overlays the app content to provide important information or prompt the user for a decision
- Since they are purposefully interruptive make sure to use them only when necessary. 
- Basic Usage: Modal is used to create overlay dialogs or pop-ups.
- Properties:
   - visible: Controls whether the modal is visible.
   - animationType: Can be "none", "slide" or "fade".
   - transparent: If true, makes the modal's background see-through.
   - onRequestClose: Callback called when the user taps the hardware back button on Android.
   - Styling: Style the modal content using a separate View inside the Modal.
   - Dismiss Modal: Use the onRequestClose prop to handle closing the modal on Android back press.
   - Overlay: For an overlay effect, use transparent={true} and style the background of the inner View.

### StatusBar
- The StatusBar component allows you to control the application's status bar
- The status bar is the zone, typically at the top of the screen, that displays the current time, Wi-Fi and network information, battery level other status icons

### ActivityIndicator
- The ActivityIndicator component displays a circular loading indicator
- It is used to inform users about the status of ongoing processes, such as loading an app, submitting a form, or saving updates

### Alert
- Alert launches an alert dialog with specified title and message
- You can also specify a list of buttons

### Custom Components

### Styling 
- Doesn't use CSS, uses JS. Names written in camel case.
   **StyleSheet API**
   - 

   **Multiple Styles**
   - 

   **Box Model**
   - 
   ![box model](<./images/box_model.png>)

   **Shadow and Elevation**
   - *box-shadow: h-offset v-offset blur spread color*
   
   **Style Inheritance**
   - The components in View cannot be inherited in Text. For that, we have to create sepearte container in StyleSheet.
   - It can be inherited from parent Text Component to child Text Component.

   **Layout with Flexbox**
   - At the core of layout design in React Native is Flexbox.  

      **Flexbox:**
      - It consists of main entities: 
         - flex containers
         - flex items

      ![flex box](<./images/flexbox.png>)

      ![flex box contd](<./images/flexbox contd.png>)

      **Flex**  
      ![flex](<./images/flex.png>)

      **flexDirection**
      - for main axis (top to bottom)
      ![flexDirection](<./images/flexDirection.png>)

      **alignItems**
      - for cross axis (left to right)
      ![alignItems](<./images/alignItems.png>)

      **alignSelf**
      ![alignSelf](<./images/alignSelf.png>)

      **Flex Wrap**
      - It allows us to control how flex items behave when there's limited space wthin the container. 

      **alignContent**
      - The property aligns the lines of content along the cross axis. 

      **gap**
      - gap related properties allows us to manage spacing between rows and cols. 
      - rowGap, columnGap, gap

      **flexBasis**
      - The property determines the initial size of a flex item before any extra space in the container is distributed

   **Relative and Absolute Layout**
   - Relative layout
      - The element is positioned according to the normal flow of the layout
      - It remains in its original position and can be offset from that position using the top, right, bottom, and left values
      - Importantly, this offset does not affect the positioning of any sibling or parent
elements.

   **Dynamic User Interface**
   - 

   **Dimensions API and it's drawback**
   - 

   **useWindowDimensions**
   - 

   **SafeAreaView**
   - 

   **Platform Specific Code**
   - 

- for testing all the knowledge, I tried Pokemon Cards project. 
 
 ### Lists in React Native
 - Rendering List with ScrollView and map method is not recommended in RN. Rendering List is usually done with FlatList.  
   
   **FlatList**
      - FlatList component renders only the items currently in view, making it highly performant for long lists. 
      - SectionList is used as performant component designed for rendering sectioned lists
      
   **SectionList**
      - 

### Inputs and Forms 
- Inputs
   ![input and forms](<./images/inputs.png>)

- Forms
   ![forms](<./images/forms.png>)

   **TextInput**
   - 

   **TextInputProps**
   - placeholder
   - secureTextEntry
   - keyboardType="numeric" 
   - Two of the props are pre-enabled, to disable, use:
      - autoCapitalize='none'
      - autoCorrect={false}
   
   - Multiline TextInput

### Networking  
- Fetching and submitting data to an API. 
- Loading states, error handling and FlatList component to display our data. 
 
- GET Requests
- Loading State, pull to refresh, error handling
- POST Request

### Navigation

   ![navigation](<./images/navigation.png>)

   - Overall
      ![react navigation](<./images/react nav.png>)

- Stack Navigation
   - Navigation between screens can also be done with useNavigation hook. useNavigation hook can be used for any component, not only for screen component. Basically useNavigation is flexible to use when we have nested components or working with utility compenents that need to initiate navigation.

   - It is better to use `{ navigation }` component for screens and useNavigation hook when necessary.  

   ![stack navigation](<./images/stack nav.png>)  

   ![stack navigation types](<./images/stack nav types.png>) 

- Drawer Navigation

   ![Drawer Navigation](<./images/drawer nav.png>)

- Tab Navigator
   
   ![Tab Navigator](<./images/tab nav.png>)

- Nesting Navigators  

   ![Nesting Navigator](<./images/nesting nav.png>)


