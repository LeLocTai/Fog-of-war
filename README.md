# Fog-of-war
Youtube video:

[![Video](http://img.youtube.com/vi/SEU8TBxqss8/0.jpg)](https://youtu.be/SEU8TBxqss8)

>I don't have time to comment the code, so I will briefly describe how it work here:
>
>- Draw the field of view as a mesh (thanks /u/SebastianLague for the great tutorial), make sure it cover obstacle as well.
>
>- Use a camera that only sees those mesh to draw to a small RenderTexture. Use a replacement shader to make sure the fields of view are alway opaque, even though they're transparent in the Scene view
>
>- Upscale that Render Texture with anti-aliasing and bilinear filtering, blur it slightly, then project it to the scene by a projector placed at exactly the same place as the camera.
>
>- The projector use a custom shader to ignore any color from the RT, only use its alpha channel (there a dedicated field for color). It also blends the RT from the previous frame in to smooth out the transition.
