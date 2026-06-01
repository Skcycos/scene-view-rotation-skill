# Scene View Rotation Skill

## English

`scene-view-rotation` is a Codex skill for generating alternate camera directions from an uploaded scene image. It treats the uploaded image as the 0-degree baseline view, then asks the image generation/editing capability to infer and create 90-degree, 180-degree, and 270-degree views of the same space.

The skill is designed for scene-consistent viewpoint reconstruction. It preserves the original spatial structure, materials, colors, lighting direction, atmosphere, period feel, cleanliness level, aspect ratio, and realistic photography style. When multiple views are generated, the outputs should share the same inferred floor plan, light source direction, material palette, furniture identity, and object placement logic.

Typical triggers include:

- Generate 90/180/270 degree views from this uploaded image.
- Create a reverse angle or left/right view of the same room.
- Use the image as the 0-degree baseline and rotate the camera horizontally.
- Keep the same space, lighting, materials, and photographic style.

## 中文

`scene-view-rotation` 是一个用于 Codex 的图片视角推理生成 skill。它会把用户上传的场景图片作为 `0度基准视角`，然后调用图片生成或图片编辑能力，推理并生成同一空间的 `90度`、`180度`、`270度` 方向视角。

这个 skill 的重点是保持场景一致性，而不是重新设计一个新场景。它要求保留原图的空间结构、主要元素、材质、颜色、光线方向、氛围、年代感、清洁程度、画面比例和真实摄影风格。生成多个视角时，三张图应共享同一个推理出的平面布局、光源方向、材质体系、家具身份和物品摆放逻辑。

典型触发方式包括：

- 以我上传的图片作为 0 度基准视角，生成 90/180/270 度视角。
- 生成同一房间的背面视角、左侧视角或右侧视角。
- 换个角度看这个房间。
- 保持同一空间、同一光线、同一材质和真实摄影感。

## Files

- `SKILL.md`: The skill definition and operational instructions.
- `agents/openai.yaml`: UI metadata for the skill.
