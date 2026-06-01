# Universal Prompt Template

Use this prompt with any image-generation agent that supports a reference image.

```text
Use the uploaded image as the 0-degree baseline view of the scene. Infer and generate only the same scene from the [TARGET_VIEW] camera direction.

Preserve the current scene's spatial structure, main elements, materials, colors, lighting, atmosphere, period feel, cleanliness level, image proportions, and realistic photographic style.

Rotate around the spatial center point of the original scene. Keep the camera height close to the original image. Only rotate the camera horizontally; do not change the place and do not redesign the scene.

[TARGET_VIEW_INSTRUCTION]

If generating multiple outputs, keep this view consistent with the same inferred spatial layout, horizon/ground plane, light source direction, material palette, object identity, and placement logic used for the other views.

All newly visible content must follow the spatial logic of the original image. For indoor scenes, extend visible walls, floor, ceiling, doors, windows, furniture, lamps, decoration, and object placement relationships plausibly and consistently. For outdoor scenes, extend visible terrain, ground surface, horizon line, sky, vegetation, roads or paths, building exteriors, fences, signs, vehicles, street furniture, natural features, and object placement relationships plausibly and consistently.

Do not turn the scene into a new location. Do not redesign the interior, exterior, landscape, street, or natural environment. Do not change the lighting direction, weather, time of day, season, materials, or color tone. Do not add objects that conflict with the original period, geography, climate, function, or setting.

Keep a realistic photography look, natural camera height, stable perspective, and no wide-angle distortion.

Aspect ratio: [ASPECT_RATIO].

The final image must look like a continuous shot from the same place or environment, not a different scene.
```

Target view instructions:

- `90 degree view`: Rotate the camera horizontally 90 degrees to the right from the original direction. Show the spatial/environmental content on the original image's right side.
- `180 degree view`: Rotate the camera horizontally 180 degrees. Generate the reverse angle and show the space or environment behind the original camera.
- `270 degree view`: Rotate the camera horizontally 90 degrees to the left from the original direction. Show the spatial/environmental content on the original image's left side.
