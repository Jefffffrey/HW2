<h1>HW2</h1>


```swift


import SwiftUI

struct ContentView: View {
    @State private var playerChoice = ""
    @State private var computerChoice = ""
    @State private var result = ""
    var body: some View {
        VStack {
            Text("剪刀石頭布")
                .font(.largeTitle)
                .padding()
            Text("選擇：\(playerChoice)")
                .font(.title)
            Spacer()
            HStack {
                Button("剪刀"){
                    playerChoice = "剪刀"
                    playGame()
                }
                .padding(.all,3)
                .font(.system(size: 50))
                .foregroundColor(.white)
                .tint(.green)
                .controlSize(.small) 
                .buttonStyle(.borderedProminent)
                .padding()

                Button("石頭") {
                    playerChoice = "石頭"
                    playGame()
                }
                .padding(.all,3)
                .font(.system(size: 50))
                .foregroundColor(.white)
                .tint(.yellow)
                .controlSize(.small) 
                .buttonStyle(.borderedProminent)
                .padding()
                
                Button("布") {
                    playerChoice = "布"
                    playGame()
                }
                .padding(.all,3)
                .font(.system(size: 50))
                .foregroundColor(.white)
                .tint(.red)
                .controlSize(.small) 
                .buttonStyle(.borderedProminent)
                .padding()
            }
            Text("結果：\(result)")
                .font(.system(size: 70))
            Spacer()
            Text("電腦選擇：\(computerChoice)")
                .font(.title)
        }
    }
    
    func playGame() {
        let choices = ["剪刀", "石頭", "布"]
        computerChoice = choices.randomElement()!
        
        if playerChoice == computerChoice {
            result = "平局"
        } else if (playerChoice == "剪刀" && computerChoice == "布") ||
                    (playerChoice == "石頭" && computerChoice == "剪刀") ||
                    (playerChoice == "布" && computerChoice == "石頭") {
            result = "你贏了！"
        } else {
            result = "電腦贏了！"
        }
    }
}

```
https://github.com/Jefffffrey/HW2/assets/125536328/9d258062-a29c-4c0f-b161-96454f017e42
