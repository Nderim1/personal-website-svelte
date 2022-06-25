<script>
  import "./app.css";
  import videoSrc from "./assets/bg-video.mp4";
  // @ts-ignore
  import IoMdRocket from "svelte-icons/io/IoMdRocket.svelte";
  import { spring } from "svelte/motion";
  import { draggable } from "svelte-drag";

  const particlesJson = "./src/assets/particles.json";

  /* particlesJS.load(@dom-id, @path-json, @callback (optional)); */
  // @ts-ignore
  particlesJS.load("particles-js", particlesJson, function () {
    console.log("callback - particles.js config loaded");
  });

  let mainContent;
  const scrollRocketYCoord = spring(1);
  scrollRocketYCoord.stiffness = 0.09;
</script>

<main>
  <div class="absolute top-0 left-0 h-full w-full overflow-hidden -z-10">
    <!-- background video -->
    <video
      class="object-cover h-full w-full"
      autoplay
      muted
      playsinline
      loop
      id="myVideo"
    >
      <source src={videoSrc} type="video/mp4" />
    </video>
  </div>
  <div class="z-0 absolute h-screen w-full">
    <!-- particles js -->
    <div id="particles-js" class="h-screen w-full" />
  </div>
  <div
    id="mainContent"
    bind:this={mainContent}
    on:scroll={(e) => {
      e.preventDefault();
      // @ts-ignore
      $scrollRocketYCoord = e.target.scrollTop;
    }}
    class="relative h-screen w-screen flex flex-col z-10 text-red-50 w-screen overflow-auto scroll-smooth"
  >
    <div
      class="text-red-100 h-12 fixed right-0 w-fit hover: cursor-grab"
      use:draggable={{
        axis: "y",
        position: { y: $scrollRocketYCoord, x: 0 },
      }}
      on:svelte-drag={(e) => {
        mainContent.scrollTop = e.detail.offsetY;
      }}
    >
      <IoMdRocket />
    </div>
    <!-- content -->
    <h2>hello main content</h2>
    <p>
      this is some content Lorem ipsum dolor sit amet consectetur adipisicing
      elit. Facere qui cupiditate natus amet dicta magni doloremque ut harum
      quaerat, veniam magnam aut accusantium minus quis ratione laborum
      quisquam! Mollitia, quia!
    </p>
    <div>
      Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quibusdam rerum
      porro, consequuntur inventore odit a suscipit ab, odio quos, provident
      aliquam veritatis dolor excepturi omnis assumenda. Quasi expedita officia
      hic. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vel
      repellendus, labore atque velit repudiandae harum commodi sunt soluta
      odio! Id, illo similique! Ut doloremque voluptas reprehenderit impedit.
      Ratione, possimus impedit. Lorem ipsum dolor sit amet consectetur
      adipisicing elit. Deleniti, repellat quidem modi magni dolores, ipsam
      animi, omnis atque odit sed aliquid vel esse. Perspiciatis ducimus amet
      eius deleniti tenetur? Ducimus.
      <br />
      <br />
      <br />
      <br />
      <br />
      Lorem ipsum, dolor sit amet consectetur adipisicing elit. Nam fugiat repellendus
      consectetur id eaque. Eum laborum repellendus ipsam iusto, labore impedit optio
      animi commodi ipsa expedita quis soluta quo? Molestiae!
      <br />
      <br />
      <br />
      <br />
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Error debitis totam
      fugiat alias. Temporibus adipisci a labore possimus excepturi voluptatibus
      explicabo, impedit, ratione maiores autem repellat, obcaecati ex omnis error?
      <br />
      <br />
      <br />
      <br />
      <br />
      Lorem ipsum dolor sit amet consectetur, adipisicing elit. Ullam aliquam rerum
      tempora et aspernatur nisi, ipsa sint inventore impedit dicta distinctio similique
      omnis illo non. Voluptatibus repellat nostrum enim officiis!

      <br />
      <br />
      <br />
      <br />
      Lorem ipsum dolor sit amet consectetur, adipisicing elit. Officia reiciendis
      ratione ad necessitatibus numquam? Saepe velit corrupti rem quos vitae nisi,
      molestiae ea voluptates atque nemo totam suscipit soluta unde! Lorem ipsum
      dolor sit amet consectetur adipisicing elit. Iure aliquam vero nisi illum qui
      vel officiis magni laborum nam quam odio cum, perspiciatis natus impedit dolore
      voluptas, reprehenderit excepturi inventore.
      <br />
      <br />
      <br />
      <br />
      <br />
      Lorem, ipsum dolor sit amet consectetur adipisicing elit. Possimus, magni accusantium
      enim quo quia quasi excepturi totam aut consequuntur. Sint iusto fugit debitis
      velit repudiandae aliquid beatae quibusdam minus? Officia.
      <br />
      <br />
      <br />
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Explicabo esse debitis
      illum voluptatum consequuntur magni ad qui dignissimos repellendus, nihil atque
      cum corporis animi sit quis repudiandae ipsa impedit molestias.
    </div>
  </div>
  <p>
    this is some content Lorem ipsum dolor sit amet consectetur adipisicing
    elit. Facere qui cupiditate natus amet dicta magni doloremque ut harum
    quaerat, veniam magnam aut accusantium minus quis ratione laborum quisquam!
    Mollitia, quia!
  </p>
  <br />
  <p>
    this is some content Lorem ipsum dolor sit amet consectetur adipisicing
    elit. Facere qui cupiditate natus amet dicta magni doloremque ut harum
    quaerat, veniam magnam aut accusantium minus quis ratione laborum quisquam!
    Mollitia, quia!
  </p>
  <p>
    this is some content Lorem ipsum dolor sit amet consectetur adipisicing
    elit. Facere qui cupiditate natus amet dicta magni doloremque ut harum
    quaerat, veniam magnam aut accusantium minus quis ratione laborum quisquam!
    Mollitia, quia!
  </p>
  <p>
    this is some content Lorem ipsum dolor sit amet consectetur adipisicing
    elit. Facere qui cupiditate natus amet dicta magni doloremque ut harum
    quaerat, veniam magnam aut accusantium minus quis ratione laborum quisquam!
    Mollitia, quia!
  </p>

  <p>
    this is some content Lorem ipsum dolor sit amet consectetur adipisicing
    elit. Facere qui cupiditate natus amet dicta magni doloremque ut harum
    quaerat, veniam magnam aut accusantium minus quis ratione laborum quisquam!
    Mollitia, quia!
  </p>
  <p>
    this is some content Lorem ipsum dolor sit amet consectetur adipisicing
    elit. Facere qui cupiditate natus amet dicta magni doloremque ut harum
    quaerat, veniam magnam aut accusantium minus quis ratione laborum quisquam!
    Mollitia, quia!
  </p>
  <p>
    this is some content Lorem ipsum dolor sit amet consectetur adipisicing
    elit. Facere qui cupiditate natus amet dicta magni doloremque ut harum
    quaerat, veniam magnam aut accusantium minus quis ratione laborum quisquam!
    Mollitia, quia!
  </p>
</main>

<style>
  #mainContent::-webkit-scrollbar {
    background-color: transparent;
  }
  #mainContent::-webkit-scrollbar-track {
    background-color: transparent;
  }
</style>
