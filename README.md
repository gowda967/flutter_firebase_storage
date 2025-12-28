# frontend

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://docs.flutter.dev/cookbook)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.

1. add cli
   dart pub global activate flutterfire_cli
  export PATH="$PATH":"$HOME/.pub-cache/bin"

Firestore DataBase

2. add 
   FirebaseFirestore.instance.collection('tasks').add({}); //add new itm to draw
   FirebaseFirestore.instance.collection('tasks').doc(uuid).set({}); set for perticular doc 

3. Get
   FirebaseFirestore.instance
                    .collection('tasks') //.doc() for perticular docs
                    .where('uid', // perticular user
                        isEqualTo: FirebaseAuth.instance.currentUser!.uid)
                    .snapshots() //Stream and .get() for future value
5. update
   FirebaseFirestore.instance.collection('tasks').doc(snapshot.data.doc[index].id).update({"":"","":""}); 
                       
4. delete
   FirebaseFirestore.instance.collection('tasks').doc(snapshot.data.doc[index].id).delete();                    

Firebase Storage
1. for images and files because cloud firestore database docs data size limit to 1MB

2. final ref= FirebaseStorage.instance().ref("images").child('abc').child(id)  //images/abc/id
   
   ref.putBlob().    //binary large objects for web
   ref.putFile(file)
   1. final uploadTask= ref.putFile(file)
   2. final snapshot= uploadtask
   3. final imageUrl=await snapshot.ref.getDownloadUrl()

1. dissmissible() widget for delete item on left swipe                    

