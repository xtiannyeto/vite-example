<template>
  <select v-model="currentCard">
    <option disabled value="">Please select theme</option>
    <option v-for="option in themes" :key="option.name" :value="option">
      {{ option.name }}
    </option>
  </select>
  <figure :class="currentCard.otkCard">
    <img
      :class="currentCard.otkcardImg"
      src="/user.jpg"
      alt=""
      width="384"
      height="512"
    />
    <div :class="currentCard.otokCardContent">
      <blockquote>
        <p :class="currentCard.otkBlockquotP">
          “Tailwind CSS is the only framework that I've seen scale on large
          teams. It’s easy to customize, adapts to any design, and the build
          size is tiny.”
        </p>
      </blockquote>
      <figcaption :class="currentCard.otkFigureCaption">
        <div :class="currentCard.otkFigureCaptionFirst">Sarah Dayan</div>
        <div :class="currentCard.otkFigureCaptionSecond">
          Staff Engineer, Algolia
        </div>
      </figcaption>
    </div>
  </figure>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
type CardProps = {
  name: string;
  otkCard: string;
  otkcardImg: string;
  otokCardContent: string;
  otkBlockquote: string;
  otkBlockquotP: string;
  otkFigureCaption: string;
  otkFigureCaptionFirst: string;
  otkFigureCaptionSecond: string;
};

export default defineComponent({
  name: 'Card',
  setup(props) {
    const themes = ref([
      {
        name: 'no theme'
      } as CardProps,
      {
        name: 'theme1',
        otkCard:
          'w-1/3 mx-4 my-4 bg-yellow-200 rounded-xl p-8 dark:bg-gray-800',
        otkcardImg: 'w-24 h-24 rounded-full mx-auto',
        otokCardContent: 'pt-6 text-center space-y-4',
        otkBlockquote: '',
        otkBlockquotP: 'text-lg font-medium',
        otkFigureCaption: 'font-medium',
        otkFigureCaptionFirst: 'text-red-500 dark:text-red-400',
        otkFigureCaptionSecond: 'text-gray-700 dark:text-gray-500'
      } as CardProps,
      {
        name: 'theme2',
        otkCard:
          'w-1/3 mx-4 my-4 md:flex bg-green-100 rounded-xl p-8 md:p-0 dark:bg-gray-800',
        otkcardImg:
          'w-24 h-24 md:w-48 md:h-auto md:rounded-none rounded-full mx-auto',
        otokCardContent: 'pt-6 md:p-8 text-center md:text-left space-y-4',
        otkBlockquotP: 'text-xl font-medium',
        otkFigureCaption: 'font-medium',
        otkFigureCaptionFirst: 'text-sky-500 dark:text-sky-400',
        otkFigureCaptionSecond: 'text-indigo-700 dark:text-indigo-500'
      } as CardProps
    ]);
    const currentCard = ref(themes.value[0]);

    return { themes, currentCard };
  }
});
</script>
