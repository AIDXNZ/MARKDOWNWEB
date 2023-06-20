<iframe 
  width="660"
  height="375"
  src="https://www.youtube.com/embed/D4QoQWboM-U"
  frameborder="0"
  allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
  allowfullscreen>
</iframe>

# Welcome to my personal website! 👽🪐
Hello! Welcome! Here, I strive to showcase my passion for programming and creativity. As an avid programmer, my favorite languages include Rust, Dart, Golang, and Python. Although I like learning new paradigms and langs frequently. 

Linux is my preferred operating system, and I particularly love using PopOs!. When it comes to open-source applications, Blender holds a special place in my heart. Its scripting apabilities and addons i'm able to develop tools to help me create what I want!

During my free time, you'll often find me engrossed in programming projects or indulging in artistic endeavors. I thoroughly enjoy combining my technical skills with my creativity to bring ideas to life. Whether it's crafting intricate animations or designing captivating visuals, I'm always exploring new ways to express my imagination.

My current favorite movie is "Everything Everywhere all at once." Feel free to explore my website to learn more about my programming projects, artistic creations, and the intersections of technology and creativity in my life.

---

# Projects
A short list of projects I've worked on over the years.
## Authenticated Matrix Clocks
The goal is to provide trustless space-time bounds in distributed systems. 

## flutter-libp2p
flutter_libp2p is implemented using rust-libp2p and FFI. Read more about rust-libp2p [here](https://github.com/libp2p/rust-libp2p)

#### How it works 
- Dart FFI
- flutter_rust_bridge
- Cbor/Json RPC using embedded websockets


#### Usage
To spawn a libp2p node in flutter_libp2p use the start method
````Dart
flutter_libp2p.spawnNode();
````
Listen to Swarm events
````Dart
EventBus swarmEvents = await flutter_libp2p.events();
swarmEvents.on<ConnectionEstablished>().listen((event) {
  //Do something
  print(event.peerID);
});
````

To use in your flutter app you can call `flutter_libp2p.spawnNode()` in the initState method in main.dart like so 
````Dart
class _MyAppState extends State<MyApp> {
  ....
  
  @override
  void initState() {
    super.initState();
    flutter_libp2p.spawnNode();
  }
  
  .... //Proceeding Code
}
````

Get the current Local Peer Id
````Dart
String pid = await flutter_libp2p.localPeerId();
````

Dial one or multiple from a list of Multi-Addresses
````Dart
List<String> toDial = [
    "/ip4/172.30.144.1/tcp/42006/p2p/12D3KooWDk4Dez7KeWi5Z6JMVgQdEateaBY26yBpasdUedn29GaA"
  ];
// Note dial will not return result, instead event is sent through event stream  
await flutter_libp2p.dial(toDial);
````

