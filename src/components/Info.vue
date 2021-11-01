<script>
export default {
  name: 'Info',
  props: {
    ipData: {
      type: Object,
      required: true,
    },
  },
}
</script>
<template>
  <div
    class="
      absolute
      -bottom-64
      lg:-bottom-20
      flex flex-col
      lg:flex-row
      bg-gray-100
      gap-y-4 gap-x-12
      px-8
      pt-8
      pb-12
      rounded-md
      text-gray-800
    "
  >
    <!-- item -->
    <div class="flex flex-col">
      <h3 class="text-xs mb-2 uppercase">Ip Address</h3>
      <span class="text-2xl">{{ ipData.ip }}</span>
    </div>
    <!-- end item -->
    <!-- item2 -->
    <div class="flex flex-col">
      <h3 class="text-xs mb-2 uppercase">Location</h3>
      <span class="text-2xl">{{ ipData.state }}</span>
    </div>
    <!-- end item2 -->
    <!-- item3 -->
    <div class="flex flex-col">
      <h3 class="text-xs mb-2 uppercase">Timezone</h3>
      <span class="text-2xl">{{ ipData.timezone }}</span>
    </div>
    <!-- end item3 -->
    <!-- item4 -->
    <div class="flex flex-col">
      <h3 class="text-xs mb-2 uppercase">Isp</h3>
      <span class="text-2xl">{{ ipData.isp }}</span>
    </div>
    <!-- end item4 -->
  </div>
</template>
