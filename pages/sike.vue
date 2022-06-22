<template>
  <div class="py-12 bg-white">
    <div
      class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex-col items-center justifiy-center"
    >
      <div class="lg:text-center">
        <h2
          class="text-base text-indigo-600 font-semibold tracking-wide uppercase"
        >
          3TPT Digital Defense Activity
        </h2>
        <p
          class="mt-2 text-3xl leading-8 font-extrabold tracking-tight text-gray-900 sm:text-4xl"
        >
          Uh oh, you fell for a phishing link!
        </p>
        <p class="mt-4 max-w-2xl text-xl text-gray-500 lg:mx-auto">
          This is a phishing link. It's not meant to be clicked.
        </p>
        <p class="mt-4 max-w-2xl text-xl text-gray-500 lg:mx-auto">
          You are the {{ count }}{{ nth(count) }} person to click on this link
        </p>
        <p class="mt-16 text-xl text-block text-gray-500">
          Do await our Battalion Digital Defense Activity, which us coming on
          27th June, A real Dissemination message will come out then! The
          activity will cover various cyber safety guidelines, including, how to
          avoid phishing scams, how to select a good password ect. <br />
          See you there!
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>
let count = ref(0);

function nth(n) {
  return ["st", "nd", "rd"][((((n + 90) % 100) - 10) % 10) - 1] || "th";
}

onMounted(async () => {
  console.log("created");
  const data = await $fetch(
    "https://api.countapi.xyz/get/chuahziyang.com/bbcd8715-1d64-400b-9f25-f4380a2ea5d8",
    {
      method: "GET",
    }
  );

  console.log("data", data);
  //assign count to convert(data)
  count.value = data.value;
});
</script>
