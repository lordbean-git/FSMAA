# FSMAA
Fast Subpixel Morphological Anti-Aliasing, a ReShade 4 shader
This is an edit to Enhanced Subpixel Morphological Anti-Aliasing to strip it down to its bare minimum execution level in order to improve the performance of the shader.
Significant improvements are realized by performing only horizontal edge detection instead of horizontal+diagonal, and by removing all depth buffer info from the shader.
It is intended for use in scenarios matching any one of the following bullets:
- There is already no depth buffer access
- The host software has a very low average frame-rate, making every additional source of overhead hurt
- High-resolution usage (such as 2560x1440 or 3840x2160) where aggressive anti-aliasing is not required due to high pixel count
