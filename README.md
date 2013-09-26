vapor
=====

A DHT-based replacement for the World Wide Web

Here's how vapor will work:

1.  User A creates a document using the vapor editor application
2.  When the document is published, a hash of each component (html file, images, media assets, etc.) is generated and a pointer for each object is inserted into the DHT along with pointers to where the actual assets are avaliable (more on this later)
3.  User B finds and selects the new document in the DHT via direct link (from another document, search result, etc.)
4.  Once selected, the components of the document are downloaded from peers (more later), minimally from User A's node
5.  Downloaded assets are then validated against the original hash from the DHT
6.  If validation is sucessful, the document components are stored on User B's node and the DHT is updated to reflect their avaliability on node B to other users
7.  Finally, the document is displayed on user B's editor

From this point on, anytime User B accesses the document it is loaded (quickly) from the local copy.

When User A updates the document, a simular series of events occur:

1.  User A saves a change to the document
2.  The modified files are again hashed and the hash is updated in the DHT
3.  When User B next accesses the document, their local copy is validated against the hash stored in the DHT
4.  In this case the hash is different, so User B's node fetches a fresh copy