<template>
  <div id="app" class="flex justify-center items-center w-full text-sm min-h-screen bg-grey-50 p-4 md:p-8">
    <div class="container justify-center max-w-screen-xl p-4 rounded bg-neutral-200 flex gap-6">
      <div class="flex flex-col w-full xl:w-1/2 bg-white p-4 rounded">
        <div class="flex justify-center gap-x-6 items-center mb-6">
          <BaseButton @click="restart">restart</BaseButton>
          <BaseButton>random</BaseButton>
        </div>
        <div class="flex items-center gap-x-4 mb-2">
          <span class="w-5 shrink-0">AX</span>
          <BaseInput />
          <BaseInput />
        </div>
        <div class="flex items-center gap-x-4 mb-2">
          <span class="w-5 shrink-0">BX</span>
          <BaseInput />
          <BaseInput />
        </div>
        <div class="flex items-center gap-x-4 mb-2">
          <span class="w-5 shrink-0">CX</span>
          <BaseInput />
          <BaseInput />
        </div>
        <div class="flex items-center gap-x-4 mb-6">
          <span class="w-5 shrink-0">DX</span>
          <BaseInput />
          <BaseInput />
        </div>
        <div class="grid grid-cols-2 md:grid-cols-3 gap-2 mb-6">
          <BaseButton :smaller="true">MOV AX, BX</BaseButton>
          <BaseButton :smaller="true">MOV AX, CX</BaseButton>
          <BaseButton :smaller="true">MOV AX, DX</BaseButton>
          <BaseButton :smaller="true">MOV BX, AX</BaseButton>
          <BaseButton :smaller="true">MOV BX, CX</BaseButton>
          <BaseButton :smaller="true">MOV BX, DX</BaseButton>
          <BaseButton :smaller="true">MOV CX, AX</BaseButton>
          <BaseButton :smaller="true">MOV CX, BX</BaseButton>
          <BaseButton :smaller="true">MOV CX, DX</BaseButton>
          <BaseButton :smaller="true">MOV DX, AX</BaseButton>
          <BaseButton :smaller="true">MOV DX, BX</BaseButton>
          <BaseButton :smaller="true">MOV DX, CX</BaseButton>
        </div>
        <div class="grid grid-cols-2 md:grid-cols-3 gap-2">
          <BaseButton :smaller="true">XCHG AX, BX</BaseButton>
          <BaseButton :smaller="true">XCHG AX, CX</BaseButton>
          <BaseButton :smaller="true">XCHG AX, DX</BaseButton>
          <BaseButton :smaller="true">XCHG BX, AX</BaseButton>
          <BaseButton :smaller="true">XCHG BX, CX</BaseButton>
          <BaseButton :smaller="true">XCHG BX, DX</BaseButton>
          <BaseButton :smaller="true">XCHG CX, AX</BaseButton>
          <BaseButton :smaller="true">XCHG CX, BX</BaseButton>
          <BaseButton :smaller="true">XCHG CX, DX</BaseButton>
          <BaseButton :smaller="true">XCHG DX, AX</BaseButton>
          <BaseButton :smaller="true">XCHG DX, BX</BaseButton>
          <BaseButton :smaller="true">XCHG DX, CX</BaseButton>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import BaseButton from "./components/BaseButton.vue";
import BaseInput from "./components/BaseInput.vue";

function restart() {
  console.log("restart");
}
</script>
