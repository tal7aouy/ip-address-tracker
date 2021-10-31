<template>
  <div class="flex flex-col h-screen max-h-screen">
    <div
      class="
        flex
        justify-center
        relative
        px-4
        pt-8
        pb-32
        bg-gray-900
        text-white
      "
    >
      <div class="w-full max-w-screen-sm">
        <h1 class="text-white text-center text-3xl pb-4">IP Address Tracker</h1>
        <div class="flex relative">
          <span class="absolute top-2 left-2">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6"
              viewBox="0 0 20 20"
              fill="gray"
            >
              <path
                fill-rule="evenodd"
                d="M8 4a4 4 0 100 8 4 4 0 000-8zM2 8a6 6 0 1110.89 3.476l4.817 4.817a1 1 0 01-1.414 1.414l-4.816-4.816A6 6 0 012 8z"
                clip-rule="evenodd"
              />
            </svg>
          </span>
          <input
            type="text"
            class="
              flex-1
              py-2
              px-6
              text-center
              rounded-md
              focus:outline-none
              text-gray-600
              font-medium
              shadow-lg
            "
            placeholder="IP Address"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style></style>
