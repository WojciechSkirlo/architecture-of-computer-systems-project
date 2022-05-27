<template>
  <div id="app" class="flex items-start justify-center w-full min-h-screen p-4 px-2 text-sm md:items-center bg-grey-50 md:p-8">
    <div class="container flex justify-center max-w-screen-xl gap-6 p-4 rounded bg-neutral-200">
      <div class="flex flex-col w-full p-4 bg-white rounded xl:w-1/2">
        <div class="flex items-center justify-center mb-6 gap-x-6">
          <BaseButton :bigger="true" @click="restart">restart</BaseButton>
          <BaseButton :bigger="true" @click="random">random</BaseButton>
        </div>
        <div class="flex items-center mb-2 gap-x-4">
          <span class="w-5 shrink-0">AX</span>
          <BaseInput v-model="ax.h" />
          <BaseInput v-model="ax.l" />
        </div>
        <div class="flex items-center mb-2 gap-x-4">
          <span class="w-5 shrink-0">BX</span>
          <BaseInput v-model="bx.h" />
          <BaseInput v-model="bx.l" />
        </div>
        <div class="flex items-center mb-2 gap-x-4">
          <span class="w-5 shrink-0">CX</span>
          <BaseInput v-model="cx.h" />
          <BaseInput v-model="cx.l" />
        </div>
        <div class="flex items-center mb-6 gap-x-4">
          <span class="w-5 shrink-0">DX</span>
          <BaseInput v-model="dx.h" />
          <BaseInput v-model="dx.l" />
        </div>
        <div class="grid grid-cols-2 gap-2 mb-6 md:grid-cols-3">
          <BaseButton @click="mov(ax, bx)">MOV AX, BX</BaseButton>
          <BaseButton @click="mov(ax, cx)">MOV AX, CX</BaseButton>
          <BaseButton @click="mov(ax, dx)">MOV AX, DX</BaseButton>
          <BaseButton @click="mov(bx, ax)">MOV BX, AX</BaseButton>
          <BaseButton @click="mov(bx, cx)">MOV BX, CX</BaseButton>
          <BaseButton @click="mov(bx, dx)">MOV BX, DX</BaseButton>
          <BaseButton @click="mov(cx, ax)">MOV CX, AX</BaseButton>
          <BaseButton @click="mov(cx, bx)">MOV CX, BX</BaseButton>
          <BaseButton @click="mov(cx, dx)">MOV CX, DX</BaseButton>
          <BaseButton @click="mov(dx, ax)">MOV DX, AX</BaseButton>
          <BaseButton @click="mov(dx, bx)">MOV DX, BX</BaseButton>
          <BaseButton @click="mov(dx, cx)">MOV DX, CX</BaseButton>
        </div>
        <div class="grid grid-cols-2 gap-2 md:grid-cols-3">
          <BaseButton @click="xchg(ax, bx)">XCHG AX, BX</BaseButton>
          <BaseButton @click="xchg(ax, cx)">XCHG AX, CX</BaseButton>
          <BaseButton @click="xchg(ax, dx)">XCHG AX, DX</BaseButton>
          <BaseButton @click="xchg(bx, ax)">XCHG BX, AX</BaseButton>
          <BaseButton @click="xchg(bx, cx)">XCHG BX, CX</BaseButton>
          <BaseButton @click="xchg(bx, dx)">XCHG BX, DX</BaseButton>
          <BaseButton @click="xchg(cx, ax)">XCHG CX, AX</BaseButton>
          <BaseButton @click="xchg(cx, bx)">XCHG CX, BX</BaseButton>
          <BaseButton @click="xchg(cx, dx)">XCHG CX, DX</BaseButton>
          <BaseButton @click="xchg(dx, ax)">XCHG DX, AX</BaseButton>
          <BaseButton @click="xchg(dx, bx)">XCHG DX, BX</BaseButton>
          <BaseButton @click="xchg(dx, cx)">XCHG DX, CX</BaseButton>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import BaseButton from "./components/BaseButton.vue";
import BaseInput from "./components/BaseInput.vue";
import { reactive, ref } from "vue";

const ax = reactive({ h: "00", l: "00" }),
  bx = reactive({ h: "00", l: "00" }),
  cx = reactive({ h: "00", l: "00" }),
  dx = reactive({ h: "00", l: "00" });

function restart() {
  [ax.h, ax.l, bx.h, bx.l, cx.h, cx.l, dx.h, dx.l] = ["00", "00", "00", "00", "00", "00", "00", "00"];
}

function random() {
  [ax.h, ax.l, bx.h, bx.l, cx.h, cx.l, dx.h, dx.l] = [
    generateString(),
    generateString(),
    generateString(),
    generateString(),
    generateString(),
    generateString(),
    generateString(),
    generateString(),
  ];
}

function mov(to, from) {
  [to.h, to.l] = [from.h, from.l];
}

function xchg(to, from) {
  [to.h, to.l, from.h, from.l] = [from.h, from.l, to.h, to.l];
}

function generateString(min = 48, max = 122) {
  const firstRandomNumber = Math.floor(Math.random() * (max - min + 1)) + min;
  const secondRandomNumber = Math.floor(Math.random() * (max - min + 1)) + min;

  if ((firstRandomNumber >= 58 && firstRandomNumber <= 64) || (firstRandomNumber >= 91 && firstRandomNumber <= 96)) {
    return generateString();
  }

  return String.fromCharCode(firstRandomNumber) + String.fromCharCode(secondRandomNumber);
}
</script>
