<template>
    <p class="my-8">
        <slot name="first-paragraph" />
    </p>

    <p class="my-8">
        <slot name="second-paragraph" />
    </p>

    <h2 class="text-3xl font-semibold">
        <slot name="sub-header" />
    </h2>

    <p class="my-8">
        <slot name="third-paragraph" />
    </p>

    <p class="my-8">
        <slot name="fourth-paragraph" />
    </p>
</template>