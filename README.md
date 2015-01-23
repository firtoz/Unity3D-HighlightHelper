# Unity3D-HighlightHelper
This little snippet allows you to see which objects you are hovering over in the Unity3D hierarchy pane. It also shows which objects are being dragged. 

How it works:

When the Unity3D editor loads, it calls the static constructor of this script. Then, the HighlighHelper hooks on to the scene view’s GUI callbacks, editor update callbacks, as well as the editor’s Hierarchy Pane’s item callbacks. 

Whenever the Unity3D editor updates, the script checks whether the user is hovering over the hierarchy pane or not. If so, then it allows the window to get MouseMove callbacks. It's hacky, but it works! Then, during the MouseMove events, the script checks if the mouse is inside the rectangle of the name label for any gameobject in the hierarchy, and if so, it notes down which object’s name is hovered over.

The scene view gui method then looks up if any gameobjects match that ‘instance ID’, and draws some circles around them. It does the same for dragged objects. I hope it helps! If you have any questions, please write it in the comments of the article linked below.

For more info, see: http://wp.me/p1tYzm-2V
