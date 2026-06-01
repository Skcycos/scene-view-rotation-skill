---
name: scene-view-rotation
description: Generate alternate camera directions for the same photographed scene from an uploaded reference image. Use when the user asks to treat an uploaded image as the 0-degree baseline and infer/generate 90-degree, 180-degree, and/or 270-degree views, right/left/reverse/back views, continuous shots of the same space, scene rotation, orbit/turnaround views, spatial viewpoint reconstruction, or Chinese requests such as "以我上传的图片作为0度基准视角", "生成同一场景其他方向视角", "90度/180度/270度视角", "正反打视角", "向右/向左水平旋转90度", "换个角度看这个房间", "生成背面视角", "左侧视角", "右侧视角", "环绕视角". This skill must call image generation/editing capability to produce images, not merely write a prompt, unless the user explicitly asks only for the prompt.
---

# Scene View Rotation

## Workflow

Use the uploaded image as the 0-degree baseline scene. Prefer image editing or reference-image generation that can directly use the uploaded image as input. Do not use pure text-to-image generation when a reference-image workflow is available, because the task depends on preserving the original scene's spatial identity. If no reference image is available, ask the user to upload one before generating.

Generate three outputs by default unless the user requests fewer:

- `90 degree view`: rotate the camera horizontally 90 degrees to the right from the original direction; show the space on the original image's right side.
- `180 degree view`: rotate the camera horizontally 180 degrees; show the reverse angle behind the original camera direction.
- `270 degree view`: rotate the camera horizontally 90 degrees to the left from the original direction; show the space on the original image's left side.

Keep the camera near the original height. Rotate around the spatial center of the original scene. Do not redesign, relocate, renovate, restage, or relight the scene.

When generating multiple views, keep one shared inferred floor plan, light source direction, material palette, furniture identity, and object placement logic across all outputs. Avoid treating each direction as an unrelated scene.

## Generation Prompt

Use this prompt as the core instruction for image generation/editing, filling in the target view, target-view instruction, and aspect ratio. For each generation call, include only the instruction for the current target view; do not include instructions for unrequested directions.

```text
Use the uploaded image as the 0-degree baseline view of the scene. Infer and generate only the same scene from the [TARGET_VIEW] camera direction.

Preserve the current scene's spatial structure, main elements, materials, colors, lighting, atmosphere, period feel, cleanliness level, image proportions, and realistic photographic style.

Rotate around the spatial center point of the original scene. Keep the camera height close to the original image. Only rotate the camera horizontally; do not change the space and do not redesign the scene.

[TARGET_VIEW_INSTRUCTION]

If generating multiple outputs, keep this view consistent with the same inferred floor plan, light source direction, material palette, furniture identity, and object placement logic used for the other views.

All newly visible content must follow the spatial logic of the original image. Extend visible walls, floor, ceiling, doors, windows, furniture, lamps, decoration, and object placement relationships plausibly and consistently.

Do not turn the scene into a new location. Do not redesign the interior or exterior. Do not change the lighting direction. Do not change materials or color tone. Do not add objects that conflict with the original period, function, or setting.

Keep a realistic photography look, natural camera height, stable perspective, and no wide-angle distortion.

Aspect ratio: [ASPECT_RATIO].

The final image must look like a continuous shot from the same space, not a different scene.
```

## Aspect Ratio

Use the source image aspect ratio when the user does not specify one. If the user leaves a placeholder such as `【填写比例】`, preserve the uploaded image's aspect ratio instead of asking a follow-up question, unless exact dimensions are essential to the requested deliverable.

## Target View Instructions

Use exactly one of these target-view instructions per generation call:

- `90 degree view`: Rotate the camera horizontally 90 degrees to the right from the original direction. Show the spatial content on the original image's right side.
- `180 degree view`: Rotate the camera horizontally 180 degrees. Generate the reverse angle and show the space behind the original camera.
- `270 degree view`: Rotate the camera horizontally 90 degrees to the left from the original direction. Show the spatial content on the original image's left side.

## Output Handling

Label each generated image clearly as `90 degree view`, `180 degree view`, and `270 degree view`. If the image generation tool supports only one image per call, make separate calls with the same reference image and the same preservation constraints, changing only `[TARGET_VIEW]`.

If generation fails or a tool cannot access the uploaded image, explain the limitation briefly and ask the user to re-upload or provide the image path.
