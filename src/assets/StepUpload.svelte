<script lang="ts">
    import Dropzone from "dropzone";
    import "dropzone/dist/dropzone.css";

    import { onMount } from "svelte";

    onMount(() => {
        const dropzone = new Dropzone("#dropForm", {
            uploadMultiple: false,
            acceptedFiles: ".jpg,.png,.webp",
            maxFiles: 1,
        });
        dropzone.on("sending", (file, xhr, formData) => {
            formData.append("upload_preset", "wm_default_ml");
            formData.append("timestamp", Date.now() / 100);
            formData.append("api_key", 489514863252836);
        });

        dropzone.on("success", (file, response) => {
            console.log("HA IDO BIEN !!!");
            console.log(response);
        });

        dropzone.on("error", (File, response) => {
            console.log("HA IDO MAL !!!");
            console.log(response);
        });

        dropzone.options.myGreatDropzone();
        {
            autoProcessQueue: false;
            paramName: "file";
            maxFilessizes: 2;
            clickable: "#dropButton";
        }
    });
</script>

<form
    id="dropForm"
    class="py-24 px-24 shadow-2xl border-dotted border-2 border-gray-300 
            rounded-lg  w-full flex items-center 
            justify-center flex-col"
    action=" https://api.cloudinary.com/v1_1/dgcowrkx9/image/upload"
>
    <button
        id="dropButton"
        class="hover:bg-sky-400 hover:text-black bg-blue-800 border-2 border-gray-300
        rounded-full text-bold text-gray-300 text-lg px-3 py-3"
    >
        Upload Files
    </button>
    <p class="mt-3 text-bold text-gray-200 text-sm">or drop a file</p>
</form>
