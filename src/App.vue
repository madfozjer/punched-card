<script setup>
import TableRows from './components/TableRows.vue';
import { onBeforeUnmount, onMounted, ref } from 'vue';

const data = ref({
  1: Array(30).fill(0),
  2: Array(30).fill(0),
  3: Array(30).fill(0),
  4: Array(30).fill(0),
  5: Array(30).fill(0),
  6: Array(30).fill(0),
  7: Array(30).fill(0),
  8: Array(30).fill(0),
  9: Array(30).fill(0),
  10: Array(30).fill(0),
  11: Array(30).fill(0),
  12: Array(30).fill(0),
});
const translator = {
  0: [1, null],
  1: [2, null],
  2: [3, null],
  3: [4, null],
  4: [5, null],
  5: [6, null],
  6: [7, null],
  7: [8, null],
  8: [9, null],
  9: [10, null],
  A: [12, 1],
  B: [12, 2],
  C: [12, 3],
  D: [12, 4],
  E: [12, 5],
  F: [12, 6],
  G: [12, 7],
  H: [12, 8],
  I: [12, 9],
  J: [11, 1],
  K: [11, 2],
  L: [11, 3],
  M: [11, 4],
  N: [11, 5],
  O: [11, 6],
  P: [11, 7],
  Q: [11, 8],
  R: [11, 9],
  S: [null, 2],
  T: [null, 3],
  U: [null, 4],
  V: [null, 5],
  W: [null, 6],
  X: [null, 7],
  Y: [null, 8],
  Z: [null, 9],
  ' ': [12, 11],
};
var text = ref('');
var index = 1;
var indx = 0;

function addText(input) {
  if (index < 30) {
    if (translator[input][0] != null)
      data.value[translator[input][0]][index] = 1;
    if (translator[input][1] != null)
      data.value[translator[input][1]][index] = 1;
    text.value += input;
    index++;
  }
}

function handleKeyDown(event) {
  if (event.key === 'a' || event.key === 'A') {
    addText('A');
  } else if (event.key === 'b' || event.key === 'B') {
    addText('B');
  } else if (event.key === 'c' || event.key === 'C') {
    addText('C');
  } else if (event.key === 'd' || event.key === 'D') {
    addText('D');
  } else if (event.key === 'e' || event.key === 'E') {
    addText('E');
  } else if (event.key === 'f' || event.key === 'F') {
    addText('F');
  } else if (event.key === 'g' || event.key === 'G') {
    addText('G');
  } else if (event.key === 'h' || event.key === 'H') {
    addText('H');
  } else if (event.key === 'i' || event.key === 'I') {
    addText('I');
  } else if (event.key === 'j' || event.key === 'J') {
    addText('J');
  } else if (event.key === 'k' || event.key === 'K') {
    addText('K');
  } else if (event.key === 'l' || event.key === 'L') {
    addText('L');
  } else if (event.key === 'm' || event.key === 'M') {
    addText('M');
  } else if (event.key === 'n' || event.key === 'N') {
    addText('N');
  } else if (event.key === 'o' || event.key === 'O') {
    addText('O');
  } else if (event.key === 'p' || event.key === 'P') {
    addText('P');
  } else if (event.key === 'q' || event.key === 'Q') {
    addText('Q');
  } else if (event.key === 'r' || event.key === 'R') {
    addText('R');
  } else if (event.key === 's' || event.key === 'S') {
    addText('S');
  } else if (event.key === 't' || event.key === 'T') {
    addText('T');
  } else if (event.key === 'u' || event.key === 'U') {
    addText('U');
  } else if (event.key === 'v' || event.key === 'V') {
    addText('V');
  } else if (event.key === 'w' || event.key === 'W') {
    addText('W');
  } else if (event.key === 'x' || event.key === 'X') {
    addText('X');
  } else if (event.key === 'y' || event.key === 'Y') {
    addText('Y');
  } else if (event.key === 'z' || event.key === 'Z') {
    addText('Z');
  } else if (event.key === ' ') {
    addText(' ');
  } else if (event.key === '0') {
    addText('0');
  } else if (event.key === '1') {
    addText('1');
  } else if (event.key === '2') {
    addText('2');
  } else if (event.key === '3') {
    addText('3');
  } else if (event.key === '4') {
    addText('4');
  } else if (event.key === '5') {
    addText('5');
  } else if (event.key === '6') {
    addText('6');
  } else if (event.key === '7') {
    addText('7');
  } else if (event.key === '8') {
    addText('8');
  } else if (event.key === '9') {
    addText('9');
  } else if (event.key === 'Backspace') {
    clearText();
  }
}

function clearText() {
  text.value = '';

  data.value = {
    1: Array(30).fill(0),
    2: Array(30).fill(0),
    3: Array(30).fill(0),
    4: Array(30).fill(0),
    5: Array(30).fill(0),
    6: Array(30).fill(0),
    7: Array(30).fill(0),
    8: Array(30).fill(0),
    9: Array(30).fill(0),
    10: Array(30).fill(0),
    11: Array(30).fill(0),
    12: Array(30).fill(0),
  };

  index = 1;
}

var level = 1;
const quests = {
  1: 'LEVEL 1: C-O-M-P-[22]-E-R',
  2: 'LEVEL 2: C-[7-11]-U',
  3: 'LEVEL 3: [1-12]-D-[1-12]',
  4: 'LEVEL 4: [2-12]-[22]-[7-12]',
  5: 'LEVEL 5: [15-]-[6-11]-[4-12]-[5-12]',
  6: 'Congratulations! YOU WON!',
};

function quest() {
  if (level == 1 && text.value == 'COMPUTER') {
    level++;
  }

  if (level == 2 && text.value == 'CPU') {
    level++;
  }

  if (level == 3 && text.value == 'ADA') {
    level++;
  }

  if (level == 4 && text.value == 'BUG') {
    level++;
  }

  if (level == 5 && text.value == 'CODE') {
    level++;
  }

  clearText();
}

onMounted(() => {
  window.addEventListener('keydown', handleKeyDown);
});

onBeforeUnmount(() => {
  window.removeEventListener('keydown', handleKeyDown);
});
</script>

<template>
  <div class="flex justify-center text-3xl font-bold mt-4">
    VIRTUAL PUNCHED CARD
  </div>
  <div class="flex justify-center">
    <div class="flex flex-col mt-4">
      <TableRows
        :data="value"
        :indx="index + 1"
        v-for="(value, key, index) in data"
      ></TableRows>
    </div>
  </div>
  <div class="ml-48 mr-48">{{ text }}</div>
  <div class="mt-6 px-12 flex justify-center flex-wrap">
    <!-- Letters A-Z -->
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('A')"
      @keydown.a="addText('A')"
    >
      A
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('B')"
      @keydown.b="addText('B')"
    >
      B
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('C')"
      @keydown.c="addText('C')"
    >
      C
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('D')"
      @keydown.d="addText('D')"
    >
      D
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('E')"
      @keydown.e="addText('E')"
    >
      E
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('F')"
      @keydown.f="addText('F')"
    >
      F
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('G')"
      @keydown.g="addText('G')"
    >
      G
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('H')"
      @keydown.h="addText('H')"
    >
      H
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('I')"
      @keydown.i="addText('I')"
    >
      I
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('J')"
      @keydown.j="addText('J')"
    >
      J
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('K')"
      @keydown.k="addText('K')"
    >
      K
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('L')"
      @keydown.l="addText('L')"
    >
      L
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('M')"
      @keydown.m="addText('M')"
    >
      M
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('N')"
      @keydown.n="addText('N')"
    >
      N
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('O')"
      @keydown.o="addText('O')"
    >
      O
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('P')"
      @keydown.p="addText('P')"
    >
      P
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('Q')"
      @keydown.q="addText('Q')"
    >
      Q
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('R')"
      @keydown.r="addText('R')"
    >
      R
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('S')"
      @keydown.s="addText('S')"
    >
      S
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('T')"
      @keydown.t="addText('T')"
    >
      T
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('U')"
      @keydown.u="addText('U')"
    >
      U
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('V')"
      @keydown.v="addText('V')"
    >
      V
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('W')"
      @keydown.w="addText('W')"
    >
      W
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('X')"
      @keydown.x="addText('X')"
    >
      X
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('Y')"
      @keydown.y="addText('Y')"
    >
      Y
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('Z')"
      @keydown.z="addText('Z')"
    >
      Z
    </button>

    <!-- Numbers 0-9 -->
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('0')"
      @keydown.0="addText('0')"
    >
      0
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('1')"
      @keydown.1="addText('1')"
    >
      1
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('2')"
      @keydown.2="addText('2')"
    >
      2
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('3')"
      @keydown.3="addText('3')"
    >
      3
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('4')"
      @keydown.4="addText('4')"
    >
      4
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('5')"
      @keydown.5="addText('5')"
    >
      5
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('6')"
      @keydown.6="addText('6')"
    >
      6
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('7')"
      @keydown.7="addText('7')"
    >
      7
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('8')"
      @keydown.8="addText('8')"
    >
      8
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText('9')"
      @keydown.9="addText('9')"
    >
      9
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="addText(' ')"
      @keydown.space="addText(' ')"
    >
      space
    </button>
    <button
      class="m-1 border-2 border-gray-700 p-1 shadow-2xl hover:bg-gray-200 hover:cursor-pointer"
      @click="clearText()"
    >
      clear
    </button>
  </div>
  <div class="flex justify-center mt-8 text-2xl">
    <div>
      {{ quests[level] }}
      <input
        type="submit"
        value="submit"
        class="rounded-sm border-2 border-gray-500 p-0.5 hover:cursor-pointer hover:bg-gray-100 shadow-sm text-base"
        @click.prevent="quest()"
      />
    </div>
  </div>
</template>
