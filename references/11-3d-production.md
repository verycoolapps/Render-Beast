# RENDER BEAST — 3D Production Methodology
# DIMENSION BEAST Complete Reference

---

## OVERVIEW

DIMENSION BEAST covers the complete 3D production pipeline — from initial geometry specification through material definition, lighting design, rendering, and implementation. It produces both artistic concept specifications and technical implementation code.

**Critical distinction** — DIMENSION BEAST always clearly labels:
1. **Concept Specification** — Text description of what to create
2. **Procedural Generation Code** — Runnable scripts (Blender Python, Three.js, R3F)
3. **Actual Generated Asset** — Requires a 3D tool to exist (DIMENSION BEAST alone cannot produce files)
4. **Final Rendered Visualization** — Requires a render engine

---

## SUPPORTED 3D CATEGORIES

**Products & Objects**
- Consumer product visualization
- Industrial product design
- Jewelry and accessories
- Electronics and tech products
- Food and beverage packaging
- Automotive components
- Furniture and home goods
- Medical devices

**Characters**
- Game-ready characters (hero, NPC)
- Film/animation characters
- Stylized/cartoon characters
- Realistic characters
- Creature and monster design

**Environment & Architecture**
- Architectural exterior visualization
- Interior design visualization
- Environment design (game, film)
- Landscape visualization
- Urban scenes

**Game Assets**
- Hard-surface props
- Modular environment pieces
- Vehicles and transportation
- Weapons and equipment
- Collectibles and pickups

**Abstract & Geometric**
- Parametric forms
- Data visualization in 3D
- Abstract sculptures
- Logo 3D interpretation

---

## PART 1 — GEOMETRY SPECIFICATION

### Overall Dimensions
Define size in real-world units:
- Width × Height × Depth in meters (or appropriate units)
- Reference object for scale comparison when helpful

### Proportions
Describe the visual weight distribution:
- Tall and thin vs. wide and squat
- Heavy base vs. tapered form
- Balanced vs. asymmetric
- Dominant vs. subordinate volumes

### Silhouette
The silhouette is the most important element of a 3D design — it communicates identity at a distance and must be recognizable.
- Describe the silhouette from primary viewing angle
- Describe from secondary angles if important
- Identify the distinctive silhouette element (what makes it recognizable)
- Test against category conventions (does it read as what it is?)

### Form Hierarchy

**Primary Forms** — The major volumes that define the basic shape
Example: "A tall cylindrical main body with a flat disc base and a smaller cylindrical top section"

**Secondary Forms** — Details that articulate the primary forms
Example: "Horizontal groove lines dividing the main cylinder into thirds; a slight taper from base to top"

**Tertiary Details** — Fine surface detailing
Example: "Subtle knurling on the grip section; chamfered edges on the disc base; small logo emboss on the top face"

### Topology Requirements

**Low-Poly / Stylized**: Minimal geometry. Forms implied rather than detailed. Used for mobile games, stylized aesthetics.
- Target: 500-5,000 triangles for small objects

**Game-Ready**: Optimized geometry with normal map baking from high-poly source.
- Low-poly target: 1,000-50,000 triangles depending on scale
- High-poly (for baking): 10x-100x the low-poly count

**High-Poly / Cinematic**: Maximum geometric detail. Used for film VFX and high-end visualization.
- Polygon count unlimited; quality is the constraint

**Subdivision Surface Workflow**: Model in low-poly with subdivision modifiers. Clean topology with even edge loops.

**CAD-to-Mesh**: Import from engineering files (STEP, IGES). May require topology cleanup for rendering.

---

## PART 2 — MATERIALS SPECIFICATION (PBR WORKFLOW)

Physically-Based Rendering (PBR) is the standard material system for real-time and offline rendering. All DIMENSION BEAST material specs use PBR values.

### PBR Channel Reference

**Base Color (Albedo)**
- RGB or hex value for the surface color
- No baked-in lighting (true albedo — the color as if in pure white diffuse light)
- For metals: dark values (pure metals absorb diffuse light); for non-metals: the actual visible color

**Metallic**
- 0 = non-metal (dielectric)
- 1 = pure metal
- Values between 0-1 are for edge cases (corroded metal, metallic paint — use sparingly)

**Roughness**
- 0 = mirror-perfect smooth (like a polished mirror or glass)
- 0.1 = polished metal or coated surface
- 0.3 = brushed metal or matte plastic
- 0.5 = satin finish
- 0.7 = rough matte surface
- 1 = completely diffuse (chalk, unfinished wood)

**Specular (non-metal only)**
- Controls how much light reflects off non-metal surfaces
- 0.5 is physically correct for most plastics and organic materials
- Adjust: Water (0.255), Glass (0.5-0.55), Skin (0.35), Plastic (0.5)

**Normal Map**
- Surface detail without geometry
- Strength: 0-1 (1 = normal map fully visible)
- Used for: surface texture, engraving, fine bumps, fabric weave

**Height/Displacement**
- Actual geometric displacement from a grayscale map
- More expensive than normal maps; use for significant surface variation

**Ambient Occlusion**
- Baked contact shadows for realism
- Always multiply (never replace) with other maps

**Emissive**
- Self-illumination. Screen elements, neon, LEDs, lava
- HDR values for bloom effect in supported renderers

**Transparency / Transmission**
- For glass, liquid, translucent plastic
- Roughness still applies (frosted glass has high roughness + high transmission)
- IOR (Index of Refraction): Glass 1.52, Water 1.33, Diamond 2.42

**Subsurface Scattering (SSS)**
- For organic materials: skin, wax, marble, jade, leaves
- Light penetrates the surface and scatters within the material
- Key parameters: scatter radius, scatter color, weight

### Material Specification Template

```
MATERIAL: [Name]
Type: [Metal / Dielectric / Transparent / SSS / Emissive]
Base Color: #[HEX] or RGB([R], [G], [B])
Metallic: [0.0 - 1.0]
Roughness: [0.0 - 1.0]
Specular: [0.0 - 1.0] (dielectrics only)
Normal Strength: [0.0 - 2.0]
Surface Description: [Plain / Textured / Procedural pattern]
Surface Detail: [Scratches, wear, fingerprints, etc.]
Aging Level: [New / Slightly used / Worn / Heavily aged]
Special Properties: [SSS radius / Transmission IOR / Emissive strength]
```

---

## PART 3 — LIGHTING DESIGN

### Standard Three-Point Setup
**Key Light**: Main light source, 45° horizontal, 30-45° vertical from subject
**Fill Light**: 0.3-0.5 strength of key, opposite side, removes harsh shadows
**Rim Light**: Behind subject, creates separation from background

### Studio/Product Lighting
**Softbox Setup**: Large area lights (emulate studio softboxes)
**Light Tent Simulation**: Fully enveloping soft light for product photography
**HDRI Environment**: Image-based lighting using high-dynamic-range panoramas

### Cinematic Lighting
**Motivated Lighting**: All lights have an in-world source (window, lamp, fire)
**Practical Lights**: Visible light sources within the frame
**Mood Lighting**: Dominant color temperature (warm/cool) with strategic contrast

### Lighting Specification Template

```
LIGHTING SETUP: [Name/Type]
Environment: [HDRI file description / Studio / Practical]
Key Light:
  - Type: [Area / Spot / Sun / Point]
  - Position: [angle from subject]
  - Color Temperature: [K value]
  - Intensity: [value with unit]
  - Size: [determines hardness — small = hard, large = soft]
Fill Light:
  - Intensity ratio: [1:X relative to key]
  - Side: [opposite to key]
Rim Light:
  - Present: [Y/N]
  - Strength: [relative to key]
Shadow Behavior: [Sharp / Soft / Mixed]
Background: [Color / Gradient / Environment / Transparent]
```

---

## PART 4 — TECHNICAL SPECIFICATION

### Software Targets
- Blender 4.x (primary open-source pipeline)
- Autodesk Maya (film/VFX)
- Cinema 4D (motion graphics)
- 3ds Max (architecture/product)
- Houdini (procedural/VFX)
- Three.js / React Three Fiber (web)
- Unity / Unreal Engine (real-time/game)

### File Formats
- **GLTF/GLB**: Universal web standard. Supports PBR, animations, scenes.
- **FBX**: Industry standard. Good animation support. Proprietary.
- **OBJ**: Universal geometry. No animation. No materials embedded.
- **USDZ**: Apple AR. Required for ARKit experiences.
- **ABC (Alembic)**: Complex animations, particles, simulations.
- **STL**: 3D printing. Geometry only. No materials.

### Technical Parameters

| Parameter | Value |
|---|---|
| Coordinate System | Y-up (Three.js, Blender export) or Z-up (Blender native) |
| Units | Meters (always specify) |
| Origin | Center of object at world origin (unless rig requires otherwise) |
| Scale | Apply all transforms before export |
| UV Islands | Non-overlapping, within 0-1 space for primary UVs |
| Naming | Descriptive snake_case or camelCase (consistent) |

---

## PART 5 — BLENDER PYTHON SCRIPT TEMPLATES

### Basic Scene Setup

```python
import bpy
import mathutils

# Clear default scene
bpy.ops.object.select_all(action='SELECT')
bpy.ops.object.delete(use_global=False)

# Create collection
collection = bpy.data.collections.new("RenderBeast_Scene")
bpy.context.scene.collection.children.link(collection)

def create_pbr_material(name, base_color, metallic=0.0, roughness=0.5):
    """Create a PBR material with standard BSDF settings."""
    mat = bpy.data.materials.new(name=name)
    mat.use_nodes = True
    nodes = mat.node_tree.nodes
    links = mat.node_tree.links
    
    # Clear defaults
    nodes.clear()
    
    # Create nodes
    output = nodes.new('ShaderNodeOutputMaterial')
    principled = nodes.new('ShaderNodeBsdfPrincipled')
    
    # Set values
    principled.inputs['Base Color'].default_value = (*base_color, 1.0)
    principled.inputs['Metallic'].default_value = metallic
    principled.inputs['Roughness'].default_value = roughness
    
    # Connect
    links.new(principled.outputs['BSDF'], output.inputs['Surface'])
    
    # Position nodes
    output.location = (300, 0)
    principled.location = (0, 0)
    
    return mat

def setup_three_point_lighting():
    """Create standard three-point lighting setup."""
    # Key Light
    bpy.ops.object.light_add(type='AREA', location=(3, -3, 4))
    key = bpy.context.object
    key.name = "Key_Light"
    key.data.energy = 500
    key.data.size = 2
    key.data.color = (1.0, 0.95, 0.9)  # Slightly warm
    key.rotation_euler = mathutils.Euler((0.9, 0, 0.6), 'XYZ')
    
    # Fill Light
    bpy.ops.object.light_add(type='AREA', location=(-4, -2, 3))
    fill = bpy.context.object
    fill.name = "Fill_Light"
    fill.data.energy = 150
    fill.data.size = 3
    fill.data.color = (0.9, 0.95, 1.0)  # Slightly cool
    
    # Rim Light
    bpy.ops.object.light_add(type='AREA', location=(0, 4, 2))
    rim = bpy.context.object
    rim.name = "Rim_Light"
    rim.data.energy = 200
    rim.data.size = 1
    rim.data.color = (1.0, 1.0, 1.0)

def setup_render_settings(resolution_x=2048, resolution_y=2048, samples=256):
    """Configure Cycles render settings for quality output."""
    scene = bpy.context.scene
    scene.render.engine = 'CYCLES'
    scene.render.resolution_x = resolution_x
    scene.render.resolution_y = resolution_y
    scene.render.resolution_percentage = 100
    
    # Cycles settings
    scene.cycles.samples = samples
    scene.cycles.use_denoising = True
    scene.cycles.denoiser = 'OPENIMAGEDENOISE'
    scene.cycles.device = 'GPU'  # Change to 'CPU' if no GPU
    
    # Output settings
    scene.render.image_settings.file_format = 'PNG'
    scene.render.image_settings.color_mode = 'RGBA'
    scene.render.image_settings.color_depth = '16'
    scene.render.filepath = "//render_output/frame_"
```

### Product Visualization Template

```python
def create_product_visualization(mesh_path=None):
    """
    Set up a complete product visualization scene.
    Pass mesh_path to import an existing mesh,
    or leave None to use a placeholder cube.
    """
    
    # Import or create product
    if mesh_path:
        bpy.ops.import_scene.gltf(filepath=mesh_path)
        product = bpy.context.selected_objects[0]
    else:
        bpy.ops.mesh.primitive_cube_add(size=1, location=(0, 0, 0.5))
        product = bpy.context.object
        product.name = "Product_Placeholder"
    
    # Create ground plane
    bpy.ops.mesh.primitive_plane_add(size=20, location=(0, 0, 0))
    ground = bpy.context.object
    ground.name = "Ground_Plane"
    
    # Ground material (gradient shadow catcher alternative)
    ground_mat = create_pbr_material(
        "Ground_Mat",
        base_color=(0.9, 0.9, 0.9),
        metallic=0.0,
        roughness=0.95
    )
    ground.data.materials.append(ground_mat)
    
    # Setup lighting
    setup_three_point_lighting()
    
    # Setup camera
    bpy.ops.object.camera_add(location=(3, -4, 2.5))
    camera = bpy.context.object
    camera.name = "Product_Camera"
    camera.data.lens = 85  # Portrait lens for product
    
    # Point camera at product
    constraint = camera.constraints.new('TRACK_TO')
    constraint.target = product
    constraint.track_axis = 'TRACK_NEGATIVE_Z'
    constraint.up_axis = 'UP_Y'
    
    bpy.context.scene.camera = camera
    
    # Configure render
    setup_render_settings(resolution_x=2048, resolution_y=2048, samples=512)
    
    return product
```

---

## PART 6 — THREE.JS IMPLEMENTATION PATTERNS

### Basic Three.js Scene

```javascript
import * as THREE from 'three';
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls';
import { GLTFLoader } from 'three/examples/jsm/loaders/GLTFLoader';
import { RGBELoader } from 'three/examples/jsm/loaders/RGBELoader';

class RenderBeastScene {
  constructor(container) {
    this.container = container;
    this.width = container.clientWidth;
    this.height = container.clientHeight;
    
    this.init();
    this.setupLighting();
    this.setupControls();
    this.animate();
  }
  
  init() {
    // Renderer
    this.renderer = new THREE.WebGLRenderer({ antialias: true, alpha: true });
    this.renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
    this.renderer.setSize(this.width, this.height);
    this.renderer.outputColorSpace = THREE.SRGBColorSpace;
    this.renderer.toneMapping = THREE.ACESFilmicToneMapping;
    this.renderer.toneMappingExposure = 1.2;
    this.renderer.shadowMap.enabled = true;
    this.renderer.shadowMap.type = THREE.PCFSoftShadowMap;
    this.container.appendChild(this.renderer.domElement);
    
    // Scene
    this.scene = new THREE.Scene();
    
    // Camera
    this.camera = new THREE.PerspectiveCamera(45, this.width / this.height, 0.1, 100);
    this.camera.position.set(3, 2, 5);
    this.camera.lookAt(0, 0, 0);
    
    // Resize handler
    window.addEventListener('resize', () => this.onResize());
  }
  
  setupLighting() {
    // Ambient — base fill
    const ambient = new THREE.AmbientLight(0xffffff, 0.3);
    this.scene.add(ambient);
    
    // Key light — main directional
    const keyLight = new THREE.DirectionalLight(0xfff5e0, 2.5);
    keyLight.position.set(5, 8, 5);
    keyLight.castShadow = true;
    keyLight.shadow.mapSize.width = 2048;
    keyLight.shadow.mapSize.height = 2048;
    keyLight.shadow.camera.near = 0.1;
    keyLight.shadow.camera.far = 50;
    keyLight.shadow.bias = -0.001;
    this.scene.add(keyLight);
    
    // Fill light — cool opposite side
    const fillLight = new THREE.DirectionalLight(0xe0f0ff, 0.8);
    fillLight.position.set(-5, 3, -5);
    this.scene.add(fillLight);
    
    // Rim light — back separation
    const rimLight = new THREE.DirectionalLight(0xffffff, 1.5);
    rimLight.position.set(0, 5, -8);
    this.scene.add(rimLight);
  }
  
  async loadHDRI(path) {
    const rgbeLoader = new RGBELoader();
    const texture = await rgbeLoader.loadAsync(path);
    texture.mapping = THREE.EquirectangularReflectionMapping;
    this.scene.environment = texture;
    this.scene.background = texture;
    return texture;
  }
  
  async loadModel(path) {
    const loader = new GLTFLoader();
    const gltf = await loader.loadAsync(path);
    const model = gltf.scene;
    
    // Center model
    const box = new THREE.Box3().setFromObject(model);
    const center = box.getCenter(new THREE.Vector3());
    model.position.sub(center);
    
    // Enable shadows on all meshes
    model.traverse((child) => {
      if (child.isMesh) {
        child.castShadow = true;
        child.receiveShadow = true;
      }
    });
    
    this.scene.add(model);
    return model;
  }
  
  createPBRMaterial({ color = 0xffffff, metalness = 0, roughness = 0.5, envMapIntensity = 1 }) {
    return new THREE.MeshStandardMaterial({
      color: new THREE.Color(color),
      metalness,
      roughness,
      envMapIntensity
    });
  }
  
  setupControls() {
    this.controls = new OrbitControls(this.camera, this.renderer.domElement);
    this.controls.enableDamping = true;
    this.controls.dampingFactor = 0.05;
    this.controls.enableZoom = true;
    this.controls.minDistance = 1;
    this.controls.maxDistance = 20;
    this.controls.maxPolarAngle = Math.PI / 2;
  }
  
  onResize() {
    this.width = this.container.clientWidth;
    this.height = this.container.clientHeight;
    this.camera.aspect = this.width / this.height;
    this.camera.updateProjectionMatrix();
    this.renderer.setSize(this.width, this.height);
  }
  
  animate() {
    requestAnimationFrame(() => this.animate());
    this.controls.update();
    this.renderer.render(this.scene, this.camera);
  }
  
  dispose() {
    this.renderer.dispose();
    this.controls.dispose();
    window.removeEventListener('resize', () => this.onResize());
  }
}

export default RenderBeastScene;
```

---

## PART 7 — REACT THREE FIBER PATTERNS

```jsx
import { Canvas, useFrame, useLoader } from '@react-three/fiber'
import { 
  OrbitControls, 
  Environment, 
  ContactShadows,
  useGLTF,
  PresentationControls,
  Float
} from '@react-three/drei'
import { Suspense, useRef } from 'react'
import * as THREE from 'three'

// Product viewer component with RENDER BEAST standards
function ProductModel({ modelPath, autoRotate = false }) {
  const ref = useRef()
  const { scene } = useGLTF(modelPath)
  
  // Auto-rotate if enabled
  useFrame((state, delta) => {
    if (autoRotate && ref.current) {
      ref.current.rotation.y += delta * 0.3
    }
  })
  
  // Enable shadows on all meshes
  scene.traverse((child) => {
    if (child.isMesh) {
      child.castShadow = true
      child.receiveShadow = true
    }
  })
  
  return <primitive ref={ref} object={scene} dispose={null} />
}

// Main product viewer — production-ready component
function ProductViewer({ modelPath, hdriPath = 'studio' }) {
  return (
    <Canvas
      camera={{ position: [3, 2, 5], fov: 45 }}
      gl={{
        antialias: true,
        toneMapping: THREE.ACESFilmicToneMapping,
        toneMappingExposure: 1.2,
        outputColorSpace: THREE.SRGBColorSpace,
      }}
      shadows
      style={{ background: '#1a1a1a' }}
    >
      <Suspense fallback={null}>
        {/* Environment lighting */}
        <Environment preset={hdriPath} />
        
        {/* Three-point supplement lighting */}
        <directionalLight
          position={[5, 8, 5]}
          intensity={2.5}
          color="#fff5e0"
          castShadow
          shadow-mapSize={[2048, 2048]}
          shadow-bias={-0.001}
        />
        <directionalLight position={[-5, 3, -5]} intensity={0.8} color="#e0f0ff" />
        <directionalLight position={[0, 5, -8]} intensity={1.5} color="#ffffff" />
        
        {/* Product with float animation */}
        <Float speed={1.5} rotationIntensity={0.2} floatIntensity={0.5}>
          <ProductModel modelPath={modelPath} />
        </Float>
        
        {/* Ground shadow */}
        <ContactShadows
          position={[0, -1, 0]}
          opacity={0.65}
          scale={10}
          blur={1.5}
          far={4}
        />
        
        {/* Controls */}
        <OrbitControls
          enablePan={false}
          enableZoom={true}
          minDistance={2}
          maxDistance={15}
          maxPolarAngle={Math.PI / 2}
          dampingFactor={0.05}
          enableDamping
        />
      </Suspense>
    </Canvas>
  )
}

export default ProductViewer
```

---

## DIMENSION BEAST QUALITY RULES

Strictly prohibited in DIMENSION BEAST deliverables:

- Geometry with non-manifold edges (breaks 3D printing and many renderers)
- Inverted normals (surfaces facing the wrong direction)
- Overlapping UV islands that cause texture stretching
- Unoptimized mesh (excessive geometry where not needed; insufficient where it is)
- Materials that do not follow PBR values (physically impossible values)
- Lighting with no direction or source
- Objects that do not match their scale in real-world terms without specification
- Rendering without denoising when noise is not intentional
- Claiming a 3D file exists when only a specification was produced
- Providing code that has not been verified for syntax
