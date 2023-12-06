<template>
    <div id="map"></div>
    <div></div>
</template>

<script setup>
import * as Cesium from 'cesium'
import { app } from '../../main'
let viewer = null
Cesium.Ion.defaultAccessToken = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJqdGkiOiI0NzJjNmMwZS03YTdiLTRlNGQtODA3Yi1kOTNmYjc3NDM5MzMiLCJpZCI6MTc4MzQ4LCJpYXQiOjE3MDAwMTEzNzV9.oj1U-LjTrpXyXIBCN28aEdUQloA3-HUOt0xBnQKRw6M'
onMounted(() => {
    viewer = new Cesium.Viewer('map', {
        infoBox: false,
        baseLayerPicker: false, //是否显示图层选择控件
        animation: false, //是否显示动画控件
        timeline: false, //是否显示时间轴控件
        fullscreenButton: false, //是否显示全屏按钮
        geocoder: false, //是否显示搜索按钮
        homeButton: false, //是否显示主⻚按钮
        navigationHelpButton: false,//是否显示帮助提示按钮
        sceneModePicker: false//是否显示投影⽅式按钮
    })
})
app.provide('$viewer', viewer)
</script>

<style lang="scss">
.cesium-viewer-bottom {
    display: none;
}
</style>

<style lang="scss" scope>
#map {
    width: 100vw;
    height: 100vh;
    overflow: hidden;
}
</style>