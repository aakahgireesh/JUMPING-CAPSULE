# 11/10/2018

I had a problem with drawing Gizmos in the editor. The functions Gizmos.Draw... all take a position. I assumed this position needed to be the position of the object. This worked, but didn't take the rotation of the object. Then I found the Gizmos.matrix variable, which I set to the object's localToWorldMatrix. But that didn't work either because now it was applying the object offset twice. The counter intuitive and undocumented thing here is that the Gizmos.Draw... calls should take coordinates in the object's local space. For most objects, this means that the position should be (0, 0, 0).

# 15/10/2018

I forgot that you need to add a Rigidbody to an object if you want it to detect collisions using the OnTrigger... or OnCollision... functions.
