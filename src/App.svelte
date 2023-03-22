<script lang="ts">
    import CloudinaryLogo from "./assets/CloudinaryLogo.svelte";
    import StepUpload from "./assets/StepUpload.svelte";
</script>

<div
    class="m-auto grid place-content-center w-full h-screen bg-gradient-to-b from-blue-900 via-blue-900 to-black"
>
    <header class="flex justify-center py-10">
        <h1 class="text-3xl font-bold text-cyan-400 tracking-tighter">
            Edit<span class="text-white font-thin">Image</span>
        </h1>
    </header>

    <main>
        <StepUpload />
    </main>

    <footer
        class="flex justify-center items-center gap-x-2 font-semibold pt-10 text-white"
    >
        Hecho con <a href="http://cloudinary" target="_blank" rel="noreferrer">
            <CloudinaryLogo />
        </a>
    </footer>
</div>
