<script lang="ts">
  import {
    BufferGeometry,
    Float32BufferAttribute,
    PerspectiveCamera,
    Points,
    PointsMaterial,
    Scene,
    WebGLRenderer,
  } from "three"
  import {onMount} from "svelte"
  import {OrbitControls} from "three/examples/jsm/controls/OrbitControls.js"

  let scene: Scene
  let input: HTMLInputElement

  async function fileChange() {
    const view = new DataView(await input.files[0].arrayBuffer())

    let vertices = []
    // read xyz values (float32) until the end of the file
    for (let i = 0xb; i < view.byteLength - 4; i += 4) {
      vertices.push(view.getInt32(i, true) / 100_000)
    }
    console.log(vertices)
    console.log(vertices.length, vertices.length / 3)

    const geometry = new BufferGeometry()
    geometry.setAttribute("position", new Float32BufferAttribute(vertices, 3))
    const material = new PointsMaterial({color: 0x88_88_88})
    const points = new Points(geometry, material)
    scene.add(points)
  }

  onMount(async () => {
    scene = new Scene()
    const camera = new PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000)
    const renderer = new WebGLRenderer()
    document.body.append(renderer.domElement)
    const controls = new OrbitControls(camera, renderer.domElement)
    renderer.setClearColor(0xff_ff_ff)
    renderer.setSize(window.innerWidth, window.innerHeight)
    camera.position.set(0, 20, 100)
    controls.update()
    function animate() {
      requestAnimationFrame(animate)
      controls.update()
      renderer.render(scene, camera)
    }
    animate()
  })
</script>

<input bind:this={input} on:change={fileChange} accept=".mdl" type="file" name="filename" />
<p>Path files are just a straight list of little endian float32 3d points, no metadata.</p>
<p>
  Each of the paths in a folder connect, so you can load multiple files at once by selecting them on after
  another
</p>
<p>To clear old results, reload the page</p>
