# TransceiVR
#### Asymetrical Communication Tool Within Unity

TransceiVR is a package that enables asymmetric communication within Unity VR projects, turning them into collaborative virtual environments. External users can navigate through the VR scene and place depth corrected annotations in the VR scene. This package uses the Unity Render Streaming package and WebRTC.

![transceivr_img1 (2)](https://user-images.githubusercontent.com/9502341/131243243-2a1be295-65d0-48ed-b7ca-6a49558b6d96.PNG)

### Features
- Two external users
- Depth corrected world based annotations
- Object selection
- Scene navigation
- Place target points
- C# server to handle input from Web Client

### Prerequisites
- Unity Render Streaming Package [https://github.com/Unity-Technologies/UnityRenderStreaming]
- Works with Unity 2019.4 or 2020.3, or any version compatible with Unity RenderStreaming

### Installation
1. Open Unity Project (VR enabled optional) and Unity Package Manager
2. Import `Unity RenderStreaming` from the Unity Package Manager in the editor (You may have to select `Show preview packages` under the `Advanced` tab)

![transceivr_img5](https://user-images.githubusercontent.com/9502341/131243448-799565a8-d048-4679-add6-c0be932fe980.PNG)

4. Download this Github repository (web app and Unity package)
5. Import the TransceiVR unity package (Assets > Import Package > Custom Package)
6. Install the Newtonsoft.JSON package from the package manager by selecting (+ > Add package from git URL) and entering https://github.com/jilleJr/Newtonsoft.Json-for-Unity.git#upm 

![transceivr_5](https://user-images.githubusercontent.com/9502341/132085611-f005a379-607f-4c91-9393-348e15f8fba1.PNG)

7. Install and import the Quick Outline package from the Unity Asset Store: https://assetstore.unity.com/packages/tools/particles-effects/quick-outline-115488
8. Open the TransceiVR folder and navigate to the `Prefabs` folder
9. Drag and drop the `TransceiVR_Utilities` prefab into your scene
10. Position the External User Cameras in proper locations in your scene
11. In the Hierarchy, move the `AnnotationWindow` gameobject under the hand controller (this can be placed anywhere)

![image](https://user-images.githubusercontent.com/9502341/131243486-ea85b241-ec1f-4a83-b1fb-c4a73ec5599a.png)

11. Launch the web server (webserver.exe) and copy one of the urls in the launched windows in the Signalling URL in the 'RenderStreaming' gameObject. (For example: http://127.0.0.1/)

![transceivr_img3](https://user-images.githubusercontent.com/9502341/131243397-ca8b6054-414c-4d41-8e0b-37f28b422b0e.PNG)

12. Navigate to the Signalling URL in a compatible web browser (such as Chrome)
13. Run the scene in Unity and then start the client.

The Client Manager Should look like this

![transceivr_img4 (4)](https://user-images.githubusercontent.com/9502341/131243554-1b59e903-1e58-4ddc-9f77-20cc9e658e36.PNG)

For further details on the Render Streaming package and server refer to the Unity Render Streaming documentation [https://docs.unity3d.com/Packages/com.unity.renderstreaming@2.0/manual/index.html]

### Web Client
Each instance of the web client is assigned an ID with a respective camera.
| Tools | Description |
| ------ | ------ |
| Annotate |  Places a world space annotation drawn by an external user|
| Select | Outlines the selected object (Requires Asset) |
| Place Target | Places a target point where an external users clicks |
| Annotate Window | Places an annotation on the 'annotation window' gameObject view |
| Switch View | Switch between the external camera (only make changes on the client view |

Annotation Window

![image (1)](https://user-images.githubusercontent.com/9502341/131244440-110ff797-cd1f-465a-afc4-b9528442851a.png)

Full Screen Mode
![transceivr_img2](https://user-images.githubusercontent.com/9502341/131243039-8b470266-a6e0-43af-b5b9-42cc44be460f.PNG)

### External Users
Navigate with WASD keys and use Q and E to go up and down. Hold the right mouse button to orbit the camera view. Tools can only be applied with respect to the coreresponding camera and client.

### Editing the Web Client
If you edit the web client files, make sure to re pack the folder to create the new `webserver.exe` file.
```sh
npm run build
npm run pack
```
If you run into issues with the web client refer to the official Unity documentation here: [https://docs.unity3d.com/Packages/com.unity.renderstreaming@2.0/manual/en/webapp.html]
### Contributors:
Cyrus Vachha, Bala Kumaravel
