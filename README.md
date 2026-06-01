# Scene View Rotation Skill

## English

`scene-view-rotation` is a Codex skill for generating alternate camera directions from an uploaded indoor or outdoor scene image. It treats the uploaded image as the 0-degree baseline view, then asks the image generation/editing capability to infer and create 90-degree, 180-degree, and 270-degree views of the same place or environment.

The skill is designed for scene-consistent viewpoint reconstruction. It preserves the original spatial structure, materials, colors, lighting direction, atmosphere, period feel, cleanliness level, aspect ratio, and realistic photography style. When multiple views are generated, the outputs should share the same inferred spatial layout, horizon or ground plane, light source direction, material palette, object identity, and placement logic.

It works for indoor rooms and for outdoor scenes such as streets, courtyards, building exteriors, gardens, landscapes, and natural environments. For outdoor images, it preserves terrain, ground surfaces, sky, horizon line, vegetation, roads or paths, building exteriors, fences, signs, vehicles, street furniture, weather, time of day, and season when those cues are present in the source image.

Typical triggers include:

- Generate 90/180/270 degree views from this uploaded image.
- Create a reverse angle or left/right view of the same room, street, courtyard, building exterior, or landscape.
- Use the image as the 0-degree baseline and rotate the camera horizontally.
- Keep the same space, lighting, materials, and photographic style.

## 中文

`scene-view-rotation` 是一个用于 Codex 的图片视角推理生成 skill。它会把用户上传的室内或户外场景图片作为 `0度基准视角`，然后调用图片生成或图片编辑能力，推理并生成同一地点或环境的 `90度`、`180度`、`270度` 方向视角。

这个 skill 的重点是保持场景一致性，而不是重新设计一个新场景。它要求保留原图的空间结构、主要元素、材质、颜色、光线方向、氛围、年代感、清洁程度、画面比例和真实摄影风格。生成多个视角时，三张图应共享同一个推理出的空间布局、地平线或地面平面、光源方向、材质体系、物体身份和摆放逻辑。

它既适用于室内房间，也适用于街景、庭院、建筑外部、花园、自然景观等户外场景。对于户外图片，它会要求延续原图中的地形、地面材质、天空、地平线、植被、道路或路径、建筑外立面、围栏、标识、车辆、街道设施、天气、时间和季节等线索。

典型触发方式包括：

- 以我上传的图片作为 0 度基准视角，生成 90/180/270 度视角。
- 生成同一房间、街景、庭院、建筑外部或自然景观的背面视角、左侧视角或右侧视角。
- 换个角度看这个房间或这个户外场景。
- 保持同一空间、同一光线、同一材质和真实摄影感。

## Files

- `SKILL.md`: The skill definition and operational instructions.
- `agents/openai.yaml`: UI metadata for the skill.
