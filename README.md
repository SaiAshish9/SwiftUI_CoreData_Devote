```
Select core data while creating the app.
```

```
import Foundation
import AVFoundation

var audioPlayer: AVAudioPlayer?

func playSound(sound: String, type: String) {
  if let path = Bundle.main.path(forResource: sound, ofType: type) {
    do {
      audioPlayer = try AVAudioPlayer(contentsOf: URL(fileURLWithPath: path))
      audioPlayer?.play()
    } catch {
      print("Could not find and play the sound file.")
    }
  }
}
```

```
static let shared = PersistenceController()
```

```
let container: NSPersistentContainer
```

```
 @AppStorage("isDarkMode") private var isDarkMode: Bool = false
 @Environment(\.managedObjectContext) private var viewContext
 @State private var task: String = ""
 @Binding var isShowing: Bool
 
```

```
  @AppStorage("isDarkMode") private var isDarkMode: Bool = false
  @State var task: String = ""
  @State private var showNewTaskItem: Bool = false
  @Environment(\.managedObjectContext) private var viewContext
  @FetchRequest(
    sortDescriptors: [NSSortDescriptor(keyPath: \Item.timestamp, ascending: true)],
    animation: .default)
```

```
SwiftUI gives us a dedicated property wrapper for working with Core Data fetch requests, and it allows us to embed data directly into SwiftUI views without having to write extra logic. You must provide @FetchRequest with at least two values: the entity you want to read, and any sort descriptors to arrange the data.
```

```
With @Binding, you can pass the @State variable value from parent view to child view and if child view alters, mutates, or changes the value of @State, the parent will automatically get the updated value and re-render the view. This means you can update the parent view from the child view just by changing the value of the parent view’s @State variable in the child view using @Binding.
BindingView(valueFromParent: $currentValue)
https://betterprogramming.pub/what-is-binding-in-swiftui-how-to-use-it-206d22affd9a
```

```
  @Environment(\.managedObjectContext) var viewContext
  @ObservedObject var item: Item
```

```
isDarkMode.toggle()
```
