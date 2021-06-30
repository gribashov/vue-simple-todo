<template>
  <body class="bg-gray-200">
    <div class="container flex items-center h-screen justify-center">
      <div
        class="
          bg-white
          px-40
          py-20
          rounded-xl
          shadow-xl
          overflow-y-scroll
          md:no-scrollbar
        "
        style="max-height: 570px"
      >
        <!-- input field -->
        <div class="flex items-center justify-center h-full mb-16 relative">
          <input
            v-model="note"
            type="text"
            class="outline-none border-2 rounded-xl pl-8 pr-16 text-xl"
            style="width: 700px; height: 80px"
          />
          <div
            class="
              absolute
              right-0
              top-0
              flex
              items-center
              justify-center
              h-full
              pr-8
              cursor-pointer
            "
          >
            <svg
              v-on:click="add"
              width="36"
              height="36"
              viewBox="0 0 36 36"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M28.5 4.5H7.5C5.835 4.5 4.5 5.85 4.5 7.5V28.5C4.5 30.15 5.835 31.5 7.5 31.5H28.5C30.15 31.5 31.5 30.15 31.5 28.5V7.5C31.5 5.85 30.15 4.5 28.5 4.5ZM25.5 19.5H19.5V25.5H16.5V19.5H10.5V16.5H16.5V10.5H19.5V16.5H25.5V19.5Z"
                fill="#6E48AA"
              />
            </svg>
          </div>
        </div>
        <!-- task field -->
        <div
          v-for="n in notes"
          v-bind:key="n"
          class="flex items-center justify-center mb-16 relative"
        >
          <div class="absolute left-0 pl-8 text-xl text-white select-none">
            {{ n.text }}
          </div>
          <div
            class="rounded-xl"
            style="
              width: 700px;
              height: 80px;
              background: linear-gradient(45deg, #6e48aa, #9d50bb);
            "
          ></div>
          <div
            class="
              absolute
              right-0
              top-0
              flex
              items-center
              justify-center
              h-full
              pr-8
              cursor-pointer
            "
          >
            <svg
              width="36"
              height="36"
              viewBox="0 0 36 36"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M9 28.5C9 30.15 10.35 31.5 12 31.5H24C25.65 31.5 27 30.15 27 28.5V10.5H9V28.5ZM28.5 6H23.25L21.75 4.5H14.25L12.75 6H7.5V9H28.5V6Z"
                fill="white"
              />
            </svg>
          </div>
        </div>
      </div>
    </div>
  </body>
</template>

<script>
export default {
  name: "App",

  data() {
    return {
      note: "",
      notes: [
        { text: "Tailwind VK make header" },
        { text: "Алгоритм быстрой сортировки" }
      ]
    };
  },

  methods: {
    add() {
      const newNote = {
        text: this.note
      };
      this.notes.push(newNote);
      this.note;
    }
  }
};
</script>

<style src="./app.css"></style>
