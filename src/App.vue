<template>
    <World skybox="stage.hdr">
        <Model
            src="girl.fbx"
            :scale="4"
            toon
            :animations="{
                idle: 'Idle.fbx',
                running: 'Running.fbx',
                Hiphop: 'Hiphop.fbx',
                Moonwalk: 'Moonwalk.fbx',
                Breakdance: 'Breakdance.fbx',
            }"
            :animation="ani"
        />
        <OrbitCamera active enable-zoom enable-damping/>
    </World>
    <div style="position:absolute;left:0;top:0;background:#666;color:white;padding: 10px">
        <button style="margin-left:20px;boder:1px solid" @click="onClick('idle')">保持原地</button>
        <button style="margin-left:20px;boder:1px solid" @click="onClick('Hiphop')">印第安舞蹈</button>
        <button style="margin-left:20px;boder:1px solid" @click="onClick('Moonwalk')">太空步</button>
        <button style="margin-left:20px;boder:1px solid" @click="onClick('Breakdance')">Breakdance</button>
        <button style="margin-left:20px;boder:1px solid;margin-right:20px;" @click="onClick('running')">running</button>
    </div>
</template>
<script setup lang="ts">
import { World, Model,OrbitCamera } from "lingo3d-vue";
import { ref } from "vue";
const ani = ref("idle");

const onClick = str => {
    ani.value = str;
};
</script>
