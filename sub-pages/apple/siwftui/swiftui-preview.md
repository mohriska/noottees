# SwiftUI  Preview Functionality

```
import SwiftUI

struct ContentView: View {
    var body: some View {
        //Apple decided that it is better for a view not to be too complex on its own and limited the number of views that you can include inside VStack, HStack, or ZStack to 10
        
        //If you need to add, for example, 12 views inside VStack, you could add two stacks, each containing a subset of your views, inside a third stack.
            ZStack {
                Color.pink
                Text("Hello, world!")
                    .foregroundColor(.white)
                    .border(Color.black, width: 3)
                    .padding()
               
            }.edgesIgnoringSafeArea(.all)
            
        
            
    }
}

struct ContentView2: View {
    var body: some View {
        Text("Hello, world!")
            .foregroundColor(.red)
            .padding()
            .border(Color.blue, width: 3)
    }
}



struct ContentView_Previews: PreviewProvider{
    static var previews : some View{
        ContentView()
            .previewDisplayName("ContentView")
        ContentView2()
            .previewDisplayName("ContentView2")
    }
}

//#Preview {
//    ContentView()
//}
```