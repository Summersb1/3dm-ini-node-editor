<template>
  <div style="width: 100vw; height: 100vh; display: flex; justify-content: center; align-items: center;">
    <BaklavaEditor :view-model="baklava">
    </BaklavaEditor>
  </div>
</template>

<script setup lang="ts">
import { BaklavaEditor, useBaklava, DependencyEngine } from "baklavajs";
import "@baklavajs/themes/dist/syrup-dark.css";

// Initialize Baklava editor and dependency engine
const baklava = useBaklava();
const MyEditor = baklava.editor;
const engine = new DependencyEngine(MyEditor);
engine.start(); // Start the dependency engine

// Configuration settings for the Baklava editor
baklava.settings.nodes.resizable = true;
baklava.settings.enableMinimap = true;
baklava.settings.nodes.maxWidth = 800;
baklava.displayedGraph.scaling *= 0.85;
//baklava.settings.palette.enabled = false;
baklava.settings.toolbar.enabled = false;
</script>
