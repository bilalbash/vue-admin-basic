<template>
  <nav>
    <ul class="pagination">
      <li class="page-item" v-bind:class="{ disabled: isPrev }">
        <a class="page-link" href="javascript:void(0)" @click="prev">Prev</a>
      </li>
      <li class="page-item" v-bind:class="{ disabled: isNext }">
        <a class="page-link" href="javascript:void(0)" @click="next">Next</a>
      </li>
    </ul>
  </nav>
</template>

<script>
import { ref, onMounted } from "vue";

export default {
  name: "Paginator",
  emits: ["page-changed"],
  props: {
    lastPage: Number,
  },
  setup(props, { emit }) {
    const page = ref(1);
    const isPrev = ref(false);
    const isNext = ref(false);

    const load = () => {
      isPrev.value = page.value === 1 ? true : false;
      isNext.value = page.value === props.lastPage ? true : false;
    };

    onMounted(load);

    const next = async () => {
      if (page.value === props.lastPage) return;
      page.value++;
      emit("page-changed", page.value);
      load();
    };

    const prev = async () => {
      if (page.value === 1) return;
      page.value--;
      emit("page-changed", page.value);
      load();
    };

    return {
      next,
      prev,
      isPrev,
      isNext,
    };
  },
};
</script>

<style scoped></style>
