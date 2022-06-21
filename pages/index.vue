<template></template>

<script setup>
onMounted(async () => {
  console.log("created");
  const data = await $fetch(
    "https://api.countapi.xyz/hit/chuahziyang.com/bbcd8715-1d64-400b-9f25-f4380a2ea5d8?callback=websiteVisits",
    {
      method: "GET",
    }
  );

  //assign count to convert(data)
  navigateTo("/sike");
});
</script>
