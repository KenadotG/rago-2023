<template>
  <div class="bg-white py-24 sm:py-32">
    <div class="mx-auto max-w-8xl px-6 lg:px-8">
      <div class="mx-auto max-w-2xl lg:text-center">
        <h2 class="text-base font-semibold leading-7 text-indigo-600">
          Our Process
        </h2>
        <p
          class="mt-2 text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl"
        >
          Everything you need to deploy your app
        </p>
        <p class="mt-6 text-lg leading-8 text-gray-600">
          Quis tellus eget adipiscing convallis sit sit eget aliquet quis.
          Suspendisse eget egestas a elementum pulvinar et feugiat blandit at.
          In mi viverra elit nunc.
        </p>
      </div>
      <div class="mx-auto mt-16 max-w-3xl sm:mt-20 lg:mt-24 lg:max-w-6xl">
        <dl
          class="grid max-w-6xl grid-cols-1 gap-x-8 gap-y-10 lg:max-w-none lg:grid-cols-3 lg:gap-y-16"
        >
          <div
            v-for="feature in features"
            :key="feature.name"
            class="relative pl-16"
          >
            <dt class="text-base font-semibold leading-7 text-gray-900">
              <div
                class="absolute left-0 top-0 flex h-10 w-10 items-center justify-center rounded-lg bg-indigo-600"
              >
                <component
                  :is="feature.icon"
                  class="h-6 w-6 text-white"
                  aria-hidden="true"
                />
              </div>
              {{ feature.name }}
            </dt>
            <dd class="mt-2 text-base leading-7 text-gray-600">
              {{ feature.description }}
            </dd>
          </div>
        </dl>
      </div>
    </div>
  </div>
</template>

<script setup>
import {
  ArrowPathIcon,
  CloudArrowUpIcon,
  FingerPrintIcon,
  LockClosedIcon,
} from "@heroicons/vue/24/outline";

const features = [
  {
    name: "Discovery",
    description:
      "We start by understanding your needs and requirements. We will ask you questions about your business, your goals, and your target audience. We will also review your current systems and processes.",
    icon: CloudArrowUpIcon,
  },
  {
    name: "Design",
    description:
      "Once we have a good understanding of your needs, we will begin to design a solution that meets your specific requirements. We will create wireframes, mockups, and prototypes to help you visualize your solution.",
    icon: LockClosedIcon,
  },
  {
    name: "Development",
    description:
      "Once the design is complete, we will begin development of your solution. We will use the latest technologies and best practices to ensure that your solution is scalable, reliable, and secure.",
    icon: ArrowPathIcon,
  },
  {
    name: "Testing",
    description:
      "Once the development is complete, we will test your solution to ensure that it meets your requirements. We will perform functional, performance, and security testing.",
    icon: FingerPrintIcon,
  },
  {
    name: "Deployment",
    description:
      "Once the testing is complete, we will deploy your solution to production. We will also provide training and support to help you get started.",
    icon: FingerPrintIcon,
  },
];
</script>
