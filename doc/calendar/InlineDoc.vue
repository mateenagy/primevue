<template>
    <DocSectionText v-bind="$attrs">
        <p>Calendar is used a controlled input component with <i>v-model</i> property.</p>
    </DocSectionText>
    <div class="card flex justify-content-center">
        <Calendar v-model="date" inline showWeek>
            <template #header="{ year, month, onPrevButtonClick, onNextButtonClick }">
                <div class="flex w-full justify-content-between align-items-center">
                    <button @click="onPrevButtonClick">prev</button>
                    <span>{{ year }} {{ month }}</span>
                    <button @click="onNextButtonClick">next</button>
                </div>
            </template>
        </Calendar>
    </div>
    <DocSectionCode :code="code" />
</template>

<script>
export default {
    data() {
        return {
            date: null,
            code: {
                basic: `
<Calendar v-model="date" inline showWeek />
`,
                options: `
<template>
    <div class="card flex justify-content-center">
        <Calendar v-model="date" inline showWeek />
    </div>
</template>

<script>
export default {
    data() {
        return {
            date: null
        };
    }
};
<\/script>
`,
                composition: `
<template>
    <div class="card flex justify-content-center">
        <Calendar v-model="date" inline showWeek />
    </div>
</template>

<script setup>
import { ref } from "vue";

const date = ref();
<\/script>
`
            }
        };
    }
};
</script>
