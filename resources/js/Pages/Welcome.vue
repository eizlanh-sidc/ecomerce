<script setup>
import { Popover, PopoverButton, PopoverPanel } from "@headlessui/vue";
import { Bars3Icon, XMarkIcon } from "@heroicons/vue/24/outline";
import { ChevronRightIcon } from "@heroicons/vue/20/solid";

const navigation = [
    { name: "Product", href: "#" },
    { name: "Features", href: "#" },
    { name: "Marketplace", href: "#" },
    { name: "Company", href: "#" },
];

const stats = [
    { id: 1, name: "Student", value: "9,450+" },
    { id: 2, name: "Fee for programme", value: "30%" },
    { id: 3, name: "Passed guarantee", value: "99.9%" },
    { id: 4, name: "Allowance", value: "$70M" },
];

import { ref } from "vue";
import { RadioGroup, RadioGroupLabel, RadioGroupOption } from "@headlessui/vue";
import { CheckIcon } from "@heroicons/vue/20/solid";

const frequencies = [
    { value: "Programme", label: "Programme" },
    { value: "Course", label: "Course" },
];
const tiers = [
    {
        name: "Starter",
        id: "tier-starter",
        href: "#",
        featured: false,
        description: "All your essential business finances, taken care of.",
        price: { Programme: "RM1500", Course: "RM2300" },
        mainFeatures: [
            "Basic invoicing",
            "Easy to use accounting",
            "Mutli-accounts",
        ],
    },
    {
        name: "Scale",
        id: "tier-scale",
        href: "#",
        featured: true,
        description: "The best financial services for your thriving business.",
        price: { Programme: "RM1600", Course: "RM2400" },
        mainFeatures: [
            "Advanced invoicing",
            "Easy to use accounting",
            "Mutli-accounts",
            "Tax planning toolkit",
            "VAT & VATMOSS filing",
            "Free bank transfers",
        ],
    },
    {
        name: "Growth",
        id: "tier-growth",
        href: "#",
        featured: false,
        description:
            "Convenient features to take your business to the next level.",
        price: { Programme: "RM1030", Course: "RM2988" },
        mainFeatures: [
            "Basic invoicing",
            "Easy to use accounting",
            "Mutli-accounts",
            "Tax planning toolkit",
        ],
    },
];
const sections = [
    {
        name: "Catered for business",
        features: [
            {
                name: "Tax Savings",
                tiers: { Starter: true, Scale: true, Growth: true },
            },
            {
                name: "Easy to use accounting",
                tiers: { Starter: true, Scale: true, Growth: true },
            },
            {
                name: "Multi-accounts",
                tiers: {
                    Starter: "3 accounts",
                    Scale: "Unlimited accounts",
                    Growth: "7 accounts",
                },
            },
            {
                name: "Invoicing",
                tiers: {
                    Starter: "3 invoices",
                    Scale: "Unlimited invoices",
                    Growth: "10 invoices",
                },
            },
            {
                name: "Exclusive offers",
                tiers: { Starter: false, Scale: true, Growth: true },
            },
            {
                name: "6 months free advisor",
                tiers: { Starter: false, Scale: true, Growth: true },
            },
            {
                name: "Mobile and web access",
                tiers: { Starter: false, Scale: true, Growth: false },
            },
        ],
    },
    {
        name: "Other perks",
        features: [
            {
                name: "24/7 customer support",
                tiers: { Starter: true, Scale: true, Growth: true },
            },
            {
                name: "Instant notifications",
                tiers: { Starter: true, Scale: true, Growth: true },
            },
            {
                name: "Budgeting tools",
                tiers: { Starter: true, Scale: true, Growth: true },
            },
            {
                name: "Digital receipts",
                tiers: { Starter: true, Scale: true, Growth: true },
            },
            {
                name: "Pots to separate money",
                tiers: { Starter: false, Scale: true, Growth: true },
            },
            {
                name: "Free bank transfers",
                tiers: { Starter: false, Scale: true, Growth: false },
            },
            {
                name: "Business debit card",
                tiers: { Starter: false, Scale: true, Growth: false },
            },
        ],
    },
];

const frequency = ref(frequencies[0]);

import { defineComponent, h } from "vue";
import { ChevronDownIcon } from "@heroicons/vue/20/solid";

const navigation1 = {
    solutions: [
        { name: "Marketing", href: "#" },
        { name: "Analytics", href: "#" },
        { name: "Commerce", href: "#" },
        { name: "Insights", href: "#" },
    ],
    support: [
        { name: "Pricing", href: "#" },
        { name: "Documentation", href: "#" },
        { name: "Guides", href: "#" },
        { name: "API Status", href: "#" },
    ],
    company: [
        { name: "About", href: "#" },
        { name: "Blog", href: "#" },
        { name: "Jobs", href: "#" },
        { name: "Press", href: "#" },
        { name: "Partners", href: "#" },
    ],
    legal: [
        { name: "Claim", href: "#" },
        { name: "Privacy", href: "#" },
        { name: "Terms", href: "#" },
    ],
    social: [
        {
            name: "Facebook",
            href: "#",
            icon: defineComponent({
                render: () =>
                    h("svg", { fill: "currentColor", viewBox: "0 0 24 24" }, [
                        h("path", {
                            "fill-rule": "evenodd",
                            d: "M22 12c0-5.523-4.477-10-10-10S2 6.477 2 12c0 4.991 3.657 9.128 8.438 9.878v-6.987h-2.54V12h2.54V9.797c0-2.506 1.492-3.89 3.777-3.89 1.094 0 2.238.195 2.238.195v2.46h-1.26c-1.243 0-1.63.771-1.63 1.562V12h2.773l-.443 2.89h-2.33v6.988C18.343 21.128 22 16.991 22 12z",
                            "clip-rule": "evenodd",
                        }),
                    ]),
            }),
        },
        {
            name: "Instagram",
            href: "#",
            icon: defineComponent({
                render: () =>
                    h("svg", { fill: "currentColor", viewBox: "0 0 24 24" }, [
                        h("path", {
                            "fill-rule": "evenodd",
                            d: "M12.315 2c2.43 0 2.784.013 3.808.06 1.064.049 1.791.218 2.427.465a4.902 4.902 0 011.772 1.153 4.902 4.902 0 011.153 1.772c.247.636.416 1.363.465 2.427.048 1.067.06 1.407.06 4.123v.08c0 2.643-.012 2.987-.06 4.043-.049 1.064-.218 1.791-.465 2.427a4.902 4.902 0 01-1.153 1.772 4.902 4.902 0 01-1.772 1.153c-.636.247-1.363.416-2.427.465-1.067.048-1.407.06-4.123.06h-.08c-2.643 0-2.987-.012-4.043-.06-1.064-.049-1.791-.218-2.427-.465a4.902 4.902 0 01-1.772-1.153 4.902 4.902 0 01-1.153-1.772c-.247-.636-.416-1.363-.465-2.427-.047-1.024-.06-1.379-.06-3.808v-.63c0-2.43.013-2.784.06-3.808.049-1.064.218-1.791.465-2.427a4.902 4.902 0 011.153-1.772A4.902 4.902 0 015.45 2.525c.636-.247 1.363-.416 2.427-.465C8.901 2.013 9.256 2 11.685 2h.63zm-.081 1.802h-.468c-2.456 0-2.784.011-3.807.058-.975.045-1.504.207-1.857.344-.467.182-.8.398-1.15.748-.35.35-.566.683-.748 1.15-.137.353-.3.882-.344 1.857-.047 1.023-.058 1.351-.058 3.807v.468c0 2.456.011 2.784.058 3.807.045.975.207 1.504.344 1.857.182.466.399.8.748 1.15.35.35.683.566 1.15.748.353.137.882.3 1.857.344 1.054.048 1.37.058 4.041.058h.08c2.597 0 2.917-.01 3.96-.058.976-.045 1.505-.207 1.858-.344.466-.182.8-.398 1.15-.748.35-.35.566-.683.748-1.15.137-.353.3-.882.344-1.857.048-1.055.058-1.37.058-4.041v-.08c0-2.597-.01-2.917-.058-3.96-.045-.976-.207-1.505-.344-1.858a3.097 3.097 0 00-.748-1.15 3.098 3.098 0 00-1.15-.748c-.353-.137-.882-.3-1.857-.344-1.023-.047-1.351-.058-3.807-.058zM12 6.865a5.135 5.135 0 110 10.27 5.135 5.135 0 010-10.27zm0 1.802a3.333 3.333 0 100 6.666 3.333 3.333 0 000-6.666zm5.338-3.205a1.2 1.2 0 110 2.4 1.2 1.2 0 010-2.4z",
                            "clip-rule": "evenodd",
                        }),
                    ]),
            }),
        },
        {
            name: "X",
            href: "#",
            icon: defineComponent({
                render: () =>
                    h("svg", { fill: "currentColor", viewBox: "0 0 24 24" }, [
                        h("path", {
                            d: "M13.6823 10.6218L20.2391 3H18.6854L12.9921 9.61788L8.44486 3H3.2002L10.0765 13.0074L3.2002 21H4.75404L10.7663 14.0113L15.5685 21H20.8131L13.6819 10.6218H13.6823ZM11.5541 13.0956L10.8574 12.0991L5.31391 4.16971H7.70053L12.1742 10.5689L12.8709 11.5655L18.6861 19.8835H16.2995L11.5541 13.096V13.0956Z",
                        }),
                    ]),
            }),
        },
        {
            name: "GitHub",
            href: "#",
            icon: defineComponent({
                render: () =>
                    h("svg", { fill: "currentColor", viewBox: "0 0 24 24" }, [
                        h("path", {
                            "fill-rule": "evenodd",
                            d: "M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z",
                            "clip-rule": "evenodd",
                        }),
                    ]),
            }),
        },
        {
            name: "Dribbble",
            href: "#",
            icon: defineComponent({
                render: () =>
                    h("svg", { fill: "currentColor", viewBox: "0 0 24 24" }, [
                        h("path", {
                            "fill-rule": "evenodd",
                            d: "M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10c5.51 0 10-4.48 10-10S17.51 2 12 2zm6.605 4.61a8.502 8.502 0 011.93 5.314c-.281-.054-3.101-.629-5.943-.271-.065-.141-.12-.293-.184-.445a25.416 25.416 0 00-.564-1.236c3.145-1.28 4.577-3.124 4.761-3.362zM12 3.475c2.17 0 4.154.813 5.662 2.148-.152.216-1.443 1.941-4.48 3.08-1.399-2.57-2.95-4.675-3.189-5A8.687 8.687 0 0112 3.475zm-3.633.803a53.896 53.896 0 013.167 4.935c-3.992 1.063-7.517 1.04-7.896 1.04a8.581 8.581 0 014.729-5.975zM3.453 12.01v-.26c.37.01 4.512.065 8.775-1.215.25.477.477.965.694 1.453-.109.033-.228.065-.336.098-4.404 1.42-6.747 5.303-6.942 5.629a8.522 8.522 0 01-2.19-5.705zM12 20.547a8.482 8.482 0 01-5.239-1.8c.152-.315 1.888-3.656 6.703-5.337.022-.01.033-.01.054-.022a35.318 35.318 0 011.823 6.475 8.4 8.4 0 01-3.341.684zm4.761-1.465c-.086-.52-.542-3.015-1.659-6.084 2.679-.423 5.022.271 5.314.369a8.468 8.468 0 01-3.655 5.715z",
                            "clip-rule": "evenodd",
                        }),
                    ]),
            }),
        },
    ],
};

import {
    ChevronLeftIcon,
    ClockIcon,
    EllipsisHorizontalIcon,
} from "@heroicons/vue/20/solid";
import { Menu, MenuButton, MenuItem, MenuItems } from "@headlessui/vue";

const days = [
    { date: "2021-12-27", events: [] },
    { date: "2021-12-28", events: [] },
    { date: "2021-12-29", events: [] },
    { date: "2021-12-30", events: [] },
    { date: "2021-12-31", events: [] },
    { date: "2022-01-01", isCurrentMonth: true, events: [] },
    { date: "2022-01-02", isCurrentMonth: true, events: [] },
    {
        date: "2022-01-03",
        isCurrentMonth: true,
        events: [
            {
                id: 1,
                name: "CMDP: Module 1 Directors as Gatekeepers of Market Participants",
                time: "10AM",
                datetime: "2022-01-03T10:00",
                href: "#",
            },
            {
                id: 2,
                name: "CMDP: Module 2",
                time: "2PM",
                datetime: "2022-01-03T14:00",
                href: "#",
            },
        ],
    },
    { date: "2022-01-04", isCurrentMonth: true, events: [] },
    { date: "2022-01-05", isCurrentMonth: true, events: [] },
    { date: "2022-01-06", isCurrentMonth: true, events: [] },
    {
        date: "2022-01-07",
        isCurrentMonth: true,
        events: [
            {
                id: 3,
                name: "Dela",
                time: "6PM",
                datetime: "2022-01-08T18:00",
                href: "#",
            },
        ],
    },
    { date: "2022-01-08", isCurrentMonth: true, events: [] },
    { date: "2022-01-09", isCurrentMonth: true, events: [] },
    { date: "2022-01-10", isCurrentMonth: true, events: [] },
    { date: "2022-01-11", isCurrentMonth: true, events: [] },
    {
        date: "2022-01-12",
        isCurrentMonth: true,
        isToday: true,
        events: [
            {
                id: 6,
                name: "Del",
                time: "2PM",
                datetime: "2022-01-25T14:00",
                href: "#",
            },
        ],
    },
    { date: "2022-01-13", isCurrentMonth: true, events: [] },
    { date: "2022-01-14", isCurrentMonth: true, events: [] },
    { date: "2022-01-15", isCurrentMonth: true, events: [] },
    { date: "2022-01-16", isCurrentMonth: true, events: [] },
    { date: "2022-01-17", isCurrentMonth: true, events: [] },
    { date: "2022-01-18", isCurrentMonth: true, events: [] },
    { date: "2022-01-19", isCurrentMonth: true, events: [] },
    { date: "2022-01-20", isCurrentMonth: true, events: [] },
    { date: "2022-01-21", isCurrentMonth: true, events: [] },
    {
        date: "2022-01-22",
        isCurrentMonth: true,
        isSelected: true,
        events: [
            {
                id: 4,
                name: "eFPMR 1",
                time: "3PM",
                datetime: "2022-01-22T15:00",
                href: "#",
            },
            {
                id: 5,
                name: "eFPMR 2",
                time: "7PM",
                datetime: "2022-01-22T19:00",
                href: "#",
            },
        ],
    },
    { date: "2022-01-23", isCurrentMonth: true, events: [] },
    { date: "2022-01-24", isCurrentMonth: true, events: [] },
    { date: "2022-01-25", isCurrentMonth: true, events: [] },
    { date: "2022-01-26", isCurrentMonth: true, events: [] },
    { date: "2022-01-27", isCurrentMonth: true, events: [] },
    { date: "2022-01-28", isCurrentMonth: true, events: [] },
    { date: "2022-01-29", isCurrentMonth: true, events: [] },
    { date: "2022-01-30", isCurrentMonth: true, events: [] },
    { date: "2022-01-31", isCurrentMonth: true, events: [] },
    { date: "2022-02-01", events: [] },
    { date: "2022-02-02", events: [] },
    { date: "2022-02-03", events: [] },
    {
        date: "2022-02-04",
        events: [
            {
                id: 7,
                name: "AML",
                time: "9PM",
                datetime: "2022-02-04T21:00",
                href: "#",
            },
        ],
    },
    { date: "2022-02-05", events: [] },
    { date: "2022-02-06", events: [] },
];
const selectedDay = days.find((day) => day.isSelected);
</script>

<template>
    <div class="relative overflow-hidden">
        <Popover as="header" class="relative">
            <div class="pt-6 bg-gray-900">
                <nav
                    class="relative flex items-center justify-between px-6 mx-auto max-w-7xl"
                    aria-label="Global"
                >
                    <div class="flex items-center flex-1">
                        <div
                            class="flex items-center justify-between w-full md:w-auto"
                        >
                            <a href="#">
                                <span class="sr-only">Your Company</span>
                                <img src="/images/logoci.png" class="h-16" />
                            </a>
                            <div class="flex items-center -mr-2 md:hidden">
                                <PopoverButton
                                    class="relative inline-flex items-center justify-center p-2 text-gray-400 bg-gray-900 rounded-md focus-ring-inset hover:bg-gray-800 focus:outline-none focus:ring-2 focus:ring-white"
                                >
                                    <span class="absolute -inset-0.5" />
                                    <span class="sr-only">Open main menu</span>
                                    <Bars3Icon
                                        class="w-6 h-6"
                                        aria-hidden="true"
                                    />
                                </PopoverButton>
                            </div>
                        </div>
                        <div class="hidden space-x-8 md:ml-10 md:flex">
                            <a
                                v-for="item in navigation"
                                :key="item.name"
                                :href="item.href"
                                class="text-base font-medium text-white hover:text-gray-300"
                                >{{ item.name }}</a
                            >
                        </div>
                    </div>
                    <div class="hidden md:flex md:items-center md:space-x-6">
                        <a
                            :href="route('register')"
                            class="text-base font-medium text-white hover:text-gray-300"
                            >Register</a
                        >
                        <a
                            :href="route('login')"
                            class="hover:scale-110 text-white bg-gradient-to-r from-blue-500 via-blue-600 to-blue-700 hover:bg-gradient-to-br focus:ring-4 focus:outline-none focus:ring-blue-300 dark:focus:ring-blue-800 font-medium rounded-lg text-sm px-5 py-2.5 text-center mr-2 mb-1"
                            >Log in</a
                        >
                    </div>
                </nav>
            </div>

            <transition
                enter-active-class="duration-150 ease-out"
                enter-from-class="scale-95 opacity-0"
                enter-to-class="scale-100 opacity-100"
                leave-active-class="duration-100 ease-in"
                leave-from-class="scale-100 opacity-100"
                leave-to-class="scale-95 opacity-0"
            >
                <PopoverPanel
                    focus
                    class="absolute inset-x-0 top-0 z-10 p-2 transition origin-top transform md:hidden"
                >
                    <div
                        class="overflow-hidden bg-white rounded-lg shadow-md ring-1 ring-black ring-opacity-5"
                    >
                        <div
                            class="flex items-center justify-between px-5 pt-4"
                        >
                            <div>
                                <img
                                    class="w-auto h-8"
                                    src="https://tailwindui.com/img/logos/mark.svg?color=indigo&shade=600"
                                    alt=""
                                />
                            </div>
                            <div class="-mr-2">
                                <PopoverButton
                                    class="relative inline-flex items-center justify-center p-2 text-gray-400 bg-white rounded-md hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-600"
                                >
                                    <span class="absolute -inset-0.5" />
                                    <span class="sr-only">Close menu</span>
                                    <XMarkIcon
                                        class="w-6 h-6"
                                        aria-hidden="true"
                                    />
                                </PopoverButton>
                            </div>
                        </div>
                        <div class="pt-5 pb-6">
                            <div class="px-2 space-y-1">
                                <a
                                    v-for="item in navigation"
                                    :key="item.name"
                                    :href="item.href"
                                    class="block px-3 py-2 text-base font-medium text-gray-900 rounded-md hover:bg-gray-50"
                                    >{{ item.name }}</a
                                >
                            </div>
                            <div class="px-5 mt-6">
                                <a
                                    href="#"
                                    class="block w-full px-4 py-3 font-medium text-center text-white bg-indigo-600 rounded-md shadow hover:bg-indigo-700"
                                    >Start free trial</a
                                >
                            </div>
                            <div class="px-5 mt-6">
                                <p
                                    class="text-base font-medium text-center text-gray-500"
                                >
                                    Existing customer?
                                    <a
                                        href="#"
                                        class="text-gray-900 hover:underline"
                                        >Login</a
                                    >
                                </p>
                            </div>
                        </div>
                    </div>
                </PopoverPanel>
            </transition>
        </Popover>

        <main>
            <div
                class="pt-10 bg-gray-900 sm:pt-16 lg:overflow-hidden lg:pb-14 lg:pt-8"
            >
                <div class="mx-auto max-w-7xl lg:px-8">
                    <div class="lg:grid lg:grid-cols-2 lg:gap-8">
                        <div
                            class="max-w-md px-6 mx-auto sm:max-w-2xl sm:text-center lg:flex lg:items-center lg:px-0 lg:text-left"
                        >
                            <div class="lg:py-24">
                                <div
                                    class="hidden sm:mb-5 sm:flex sm:justify-center lg:justify-start"
                                >
                                    <a
                                        href="#"
                                        class="flex items-center p-1 pr-2 text-white bg-black rounded-full hover:text-gray-200 sm:text-base lg:text-sm xl:text-base"
                                    >
                                        <span
                                            class="rounded-full bg-indigo-500 px-3 py-0.5 text-sm font-semibold leading-5 text-white"
                                            >We're hiring</span
                                        >
                                        <span class="ml-4 text-sm"
                                            >Visit our Programme Page</span
                                        >
                                        <ChevronRightIcon
                                            class="w-5 h-5 ml-2 text-gray-500"
                                            aria-hidden="true"
                                        />
                                    </a>
                                </div>
                                <h1
                                    class="text-4xl font-bold tracking-tight text-white sm:text-6xl lg:mt-6 xl:text-6xl"
                                >
                                    <span class="block"
                                        >NEW Certified Capital Market
                                        Professional
                                    </span>
                                    <span class="block text-indigo-400"
                                        >Programme:</span
                                    >
                                </h1>

                                <p
                                    class="mt-3 text-base text-gray-300 sm:mt-5 sm:text-xl lg:text-lg xl:text-xl"
                                >
                                    Dealing in Derivatives for Dealer's
                                    Representatives
                                </p>
                                <div class="mt-10 sm:mt-12">
                                    <form
                                        action="#"
                                        class="sm:mx-auto sm:max-w-xl lg:mx-0"
                                    >
                                        <div class="sm:flex">
                                            <div class="flex-1 min-w-0">
                                                <label
                                                    for="email"
                                                    class="sr-only"
                                                    >Email address</label
                                                >
                                                <input
                                                    id="email"
                                                    type="email"
                                                    placeholder="Enter your email"
                                                    class="block w-full px-4 py-3 text-base text-gray-900 placeholder-gray-500 border-0 rounded-md focus:outline-none focus:ring-2 focus:ring-indigo-300 focus:ring-offset-2 focus:ring-offset-gray-900"
                                                />
                                            </div>
                                            <div class="mt-3 sm:ml-3 sm:mt-0">
                                                <button
                                                    type="submit"
                                                    class="block w-full px-4 py-3 font-medium text-white bg-indigo-500 rounded-md shadow hover:bg-indigo-600 focus:outline-none focus:ring-2 focus:ring-indigo-300 focus:ring-offset-2 focus:ring-offset-gray-900"
                                                >
                                                    I'm interested
                                                </button>
                                            </div>
                                        </div>
                                        <p
                                            class="mt-3 text-sm text-gray-300 sm:mt-4"
                                        >
                                            Our mission is to raise the standard
                                            of capital market participants to
                                            support the rapid growth and
                                            development of the capital market
                                            industry, through
                                            <a
                                                href="#"
                                                class="font-medium text-white"
                                                >strategic and effective</a
                                            >.
                                        </p>
                                    </form>
                                </div>
                            </div>
                        </div>
                        <div class="mt-12 -mb-16 sm:-mb-48 lg:relative lg:m-0">
                            <div
                                class="max-w-md px-6 mx-auto sm:max-w-2xl lg:max-w-none lg:px-0"
                            >
                                <img
                                    class="w-full lg:absolute lg:inset-y-0 lg:left-0 lg:h-full lg:w-auto lg:max-w-none"
                                    src="https://tailwindui.com/img/component-images/cloud-illustration-indigo-400.svg"
                                    alt=""
                                />
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Percentage -->

            <div class="py-24 bg-gray-900 sm:py-32">
                <div class="px-6 mx-auto max-w-7xl lg:px-8">
                    <div class="max-w-2xl mx-auto lg:max-w-none">
                        <div class="text-center">
                            <h2
                                class="text-3xl font-bold tracking-tight text-white sm:text-4xl"
                            >
                                Trusted by creators worldwide, our legacy dates
                                back to 1994
                            </h2>
                            <p class="mt-4 text-lg leading-8 text-gray-300">
                                SECURITIES INDUSTRY DEVELOPMENT CORPORATION
                            </p>
                        </div>
                        <dl
                            class="mt-16 grid grid-cols-1 gap-0.5 overflow-hidden rounded-2xl text-center sm:grid-cols-2 lg:grid-cols-4"
                        >
                            <div
                                v-for="stat in stats"
                                :key="stat.id"
                                class="flex flex-col p-8 bg-white/5"
                            >
                                <dt
                                    class="text-sm font-semibold leading-6 text-gray-300"
                                >
                                    {{ stat.name }}
                                </dt>
                                <dd
                                    class="order-first text-3xl font-semibold tracking-tight text-white"
                                >
                                    {{ stat.value }}
                                </dd>
                            </div>
                        </dl>
                    </div>
                </div>
            </div>

            <!-- Calendar -->

            <div class="mt-4 lg:flex lg:h-full lg:flex-col">
                <header
                    class="flex items-center justify-between px-6 py-4 border-b border-gray-200 dark:bg-gray-800 lg:flex-none"
                >
                    <h1
                        class="text-base font-semibold leading-6 text-gray-900 dark:text-white"
                    >
                        <p>Update on SIDC 2024 Programmes</p>
                        <time datetime="2022-01">January 2022</time>
                    </h1>
                    <div class="flex items-center">
                        <div
                            class="relative flex items-center bg-white rounded-md shadow-sm md:items-stretch"
                        >
                            <button
                                type="button"
                                class="flex items-center justify-center w-12 pr-1 text-gray-400 border-l border-gray-300 h-9 rounded-l-md border-y hover:text-gray-500 focus:relative md:w-9 md:pr-0 md:hover:bg-gray-50"
                            >
                                <span class="sr-only">Previous month</span>
                                <ChevronLeftIcon
                                    class="w-5 h-5"
                                    aria-hidden="true"
                                />
                            </button>
                            <button
                                type="button"
                                class="hidden border-y border-gray-300 px-3.5 text-sm font-semibold text-gray-900 hover:bg-gray-50 focus:relative md:block"
                            >
                                Today
                            </button>
                            <span
                                class="relative w-px h-5 -mx-px bg-gray-300 md:hidden"
                            />
                            <button
                                type="button"
                                class="flex items-center justify-center w-12 pl-1 text-gray-400 border-r border-gray-300 h-9 rounded-r-md border-y hover:text-gray-500 focus:relative md:w-9 md:pl-0 md:hover:bg-gray-50"
                            >
                                <span class="sr-only">Next month</span>
                                <ChevronRightIcon
                                    class="w-5 h-5"
                                    aria-hidden="true"
                                />
                            </button>
                        </div>
                        <div class="hidden md:ml-4 md:flex md:items-center">
                            <Menu as="div" class="relative">
                                <MenuButton
                                    type="button"
                                    class="flex items-center gap-x-1.5 rounded-md bg-white px-3 py-2 text-sm font-semibold text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 hover:bg-gray-50"
                                >
                                    Month view
                                    <ChevronDownIcon
                                        class="w-5 h-5 -mr-1 text-gray-400"
                                        aria-hidden="true"
                                    />
                                </MenuButton>

                                <transition
                                    enter-active-class="transition duration-100 ease-out"
                                    enter-from-class="transform scale-95 opacity-0"
                                    enter-to-class="transform scale-100 opacity-100"
                                    leave-active-class="transition duration-75 ease-in"
                                    leave-from-class="transform scale-100 opacity-100"
                                    leave-to-class="transform scale-95 opacity-0"
                                >
                                    <MenuItems
                                        class="absolute right-0 z-10 mt-3 overflow-hidden origin-top-right bg-white rounded-md shadow-lg w-36 ring-1 ring-black ring-opacity-5 focus:outline-none"
                                    >
                                        <div class="py-1">
                                            <MenuItem v-slot="{ active }">
                                                <a
                                                    href="#"
                                                    :class="[
                                                        active
                                                            ? 'bg-gray-100 text-gray-900'
                                                            : 'text-gray-700',
                                                        'block px-4 py-2 text-sm',
                                                    ]"
                                                    >Day view</a
                                                >
                                            </MenuItem>
                                            <MenuItem v-slot="{ active }">
                                                <a
                                                    href="#"
                                                    :class="[
                                                        active
                                                            ? 'bg-gray-100 text-gray-900'
                                                            : 'text-gray-700',
                                                        'block px-4 py-2 text-sm',
                                                    ]"
                                                    >Week view</a
                                                >
                                            </MenuItem>
                                            <MenuItem v-slot="{ active }">
                                                <a
                                                    href="#"
                                                    :class="[
                                                        active
                                                            ? 'bg-gray-100 text-gray-900'
                                                            : 'text-gray-700',
                                                        'block px-4 py-2 text-sm',
                                                    ]"
                                                    >Month view</a
                                                >
                                            </MenuItem>
                                            <MenuItem v-slot="{ active }">
                                                <a
                                                    href="#"
                                                    :class="[
                                                        active
                                                            ? 'bg-gray-100 text-gray-900'
                                                            : 'text-gray-700',
                                                        'block px-4 py-2 text-sm',
                                                    ]"
                                                    >Year view</a
                                                >
                                            </MenuItem>
                                        </div>
                                    </MenuItems>
                                </transition>
                            </Menu>
                            <div class="w-px h-6 ml-6 bg-gray-300" />
                            <button
                                type="button"
                                class="px-3 py-2 ml-6 text-sm font-semibold text-white bg-indigo-600 rounded-md shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-500"
                            >
                                Add event
                            </button>
                        </div>
                        <Menu as="div" class="relative ml-6 md:hidden">
                            <MenuButton
                                class="flex items-center p-2 -mx-2 text-gray-400 border border-transparent rounded-full hover:text-gray-500"
                            >
                                <span class="sr-only">Open menu</span>
                                <EllipsisHorizontalIcon
                                    class="w-5 h-5"
                                    aria-hidden="true"
                                />
                            </MenuButton>

                            <transition
                                enter-active-class="transition duration-100 ease-out"
                                enter-from-class="transform scale-95 opacity-0"
                                enter-to-class="transform scale-100 opacity-100"
                                leave-active-class="transition duration-75 ease-in"
                                leave-from-class="transform scale-100 opacity-100"
                                leave-to-class="transform scale-95 opacity-0"
                            >
                                <MenuItems
                                    class="absolute right-0 z-10 mt-3 overflow-hidden origin-top-right bg-white divide-y divide-gray-100 rounded-md shadow-lg w-36 ring-1 ring-black ring-opacity-5 focus:outline-none"
                                >
                                    <div class="py-1">
                                        <MenuItem v-slot="{ active }">
                                            <a
                                                href="#"
                                                :class="[
                                                    active
                                                        ? 'bg-gray-100 text-gray-900'
                                                        : 'text-gray-700',
                                                    'block px-4 py-2 text-sm',
                                                ]"
                                                >Create event</a
                                            >
                                        </MenuItem>
                                    </div>
                                    <div class="py-1">
                                        <MenuItem v-slot="{ active }">
                                            <a
                                                href="#"
                                                :class="[
                                                    active
                                                        ? 'bg-gray-100 text-gray-900'
                                                        : 'text-gray-700',
                                                    'block px-4 py-2 text-sm',
                                                ]"
                                                >Go to today</a
                                            >
                                        </MenuItem>
                                    </div>
                                    <div class="py-1">
                                        <MenuItem v-slot="{ active }">
                                            <a
                                                href="#"
                                                :class="[
                                                    active
                                                        ? 'bg-gray-100 text-gray-900'
                                                        : 'text-gray-700',
                                                    'block px-4 py-2 text-sm',
                                                ]"
                                                >Day view</a
                                            >
                                        </MenuItem>
                                        <MenuItem v-slot="{ active }">
                                            <a
                                                href="#"
                                                :class="[
                                                    active
                                                        ? 'bg-gray-100 text-gray-900'
                                                        : 'text-gray-700',
                                                    'block px-4 py-2 text-sm',
                                                ]"
                                                >Week view</a
                                            >
                                        </MenuItem>
                                        <MenuItem v-slot="{ active }">
                                            <a
                                                href="#"
                                                :class="[
                                                    active
                                                        ? 'bg-gray-100 text-gray-900'
                                                        : 'text-gray-700',
                                                    'block px-4 py-2 text-sm',
                                                ]"
                                                >Month view</a
                                            >
                                        </MenuItem>
                                        <MenuItem v-slot="{ active }">
                                            <a
                                                href="#"
                                                :class="[
                                                    active
                                                        ? 'bg-gray-100 text-gray-900'
                                                        : 'text-gray-700',
                                                    'block px-4 py-2 text-sm',
                                                ]"
                                                >Year view</a
                                            >
                                        </MenuItem>
                                    </div>
                                </MenuItems>
                            </transition>
                        </Menu>
                    </div>
                </header>
                <div
                    class="shadow ring-1 ring-black ring-opacity-5 lg:flex lg:flex-auto lg:flex-col"
                >
                    <div
                        class="grid grid-cols-7 gap-px text-xs font-semibold leading-6 text-center text-gray-700 bg-gray-200 border-b border-gray-300 dark:text-white lg:flex-none"
                    >
                        <div class="py-2 bg-white dark:bg-gray-800">
                            M<span class="sr-only sm:not-sr-only">on</span>
                        </div>
                        <div class="py-2 bg-white dark:bg-gray-800">
                            T<span class="sr-only sm:not-sr-only">ue</span>
                        </div>
                        <div class="py-2 bg-white dark:bg-gray-800">
                            W<span class="sr-only sm:not-sr-only">ed</span>
                        </div>
                        <div class="py-2 bg-white dark:bg-gray-800">
                            T<span class="sr-only sm:not-sr-only">hu</span>
                        </div>
                        <div class="py-2 bg-white dark:bg-gray-800">
                            F<span class="sr-only sm:not-sr-only">ri</span>
                        </div>
                        <div class="py-2 bg-white dark:bg-gray-800">
                            S<span class="sr-only sm:not-sr-only">at</span>
                        </div>
                        <div class="py-2 bg-white dark:bg-gray-800">
                            S<span class="sr-only sm:not-sr-only">un</span>
                        </div>
                    </div>
                    <div
                        class="flex mb-4 text-xs leading-6 text-gray-700 bg-gray-200 dark:text-white lg:flex-auto"
                    >
                        <div
                            class="hidden w-full lg:grid lg:grid-cols-7 lg:grid-rows-6 lg:gap-px"
                        >
                            <div
                                v-for="day in days"
                                :key="day.date"
                                :class="[
                                    day.isCurrentMonth
                                        ? 'bg-white dark:bg-gray-800 dark:hover:bg-gray-600 hover:bg-gray-300'
                                        : 'bg-gray-50 text-gray-500 dark:text-white hover:bg-gray-300 dark:hover:bg-gray-600 dark:bg-gray-800',
                                    'relative px-3 py-2',
                                ]"
                            >
                                <time
                                    :datetime="day.date"
                                    :class="
                                        day.isToday
                                            ? 'flex h-6 w-6 items-center justify-center rounded-full bg-indigo-600 font-semibold text-white'
                                            : undefined
                                    "
                                    >{{
                                        day.date
                                            .split("-")
                                            .pop()
                                            .replace(/^0/, "")
                                    }}</time
                                >
                                <ol v-if="day.events.length > 0" class="mt-2">
                                    <li
                                        v-for="event in day.events.slice(0, 2)"
                                        :key="event.id"
                                    >
                                        <a
                                            :href="event.href"
                                            class="flex group"
                                        >
                                            <p
                                                class="flex-auto font-medium text-gray-900 truncate dark:text-white group-hover:text-indigo-600"
                                            >
                                                {{ event.name }}
                                            </p>
                                            <time
                                                :datetime="event.datetime"
                                                class="flex-none hidden ml-3 text-gray-500 dark:text-white group-hover:text-indigo-600 xl:block"
                                                >{{ event.time }}</time
                                            >
                                        </a>
                                    </li>
                                    <li
                                        v-if="day.events.length > 2"
                                        class="text-gray-500"
                                    >
                                        + {{ day.events.length - 2 }} more
                                    </li>
                                </ol>
                            </div>
                        </div>
                        <div
                            class="grid w-full grid-cols-7 grid-rows-6 gap-px isolate lg:hidden"
                        >
                            <button
                                v-for="day in days"
                                :key="day.date"
                                type="button"
                                :class="[
                                    day.isCurrentMonth
                                        ? 'bg-white'
                                        : 'bg-gray-50',
                                    (day.isSelected || day.isToday) &&
                                        'font-semibold',
                                    day.isSelected && 'text-white',
                                    !day.isSelected &&
                                        day.isToday &&
                                        'text-indigo-600',
                                    !day.isSelected &&
                                        day.isCurrentMonth &&
                                        !day.isToday &&
                                        'text-gray-900',
                                    !day.isSelected &&
                                        !day.isCurrentMonth &&
                                        !day.isToday &&
                                        'text-gray-500',
                                    'flex h-14 flex-col px-3 py-2 hover:bg-gray-100 focus:z-10',
                                ]"
                            >
                                <time
                                    :datetime="day.date"
                                    :class="[
                                        day.isSelected &&
                                            'flex h-6 w-6 items-center justify-center rounded-full',
                                        day.isSelected &&
                                            day.isToday &&
                                            'bg-indigo-600',
                                        day.isSelected &&
                                            !day.isToday &&
                                            'bg-gray-900',
                                        'ml-auto',
                                    ]"
                                    >{{
                                        day.date
                                            .split("-")
                                            .pop()
                                            .replace(/^0/, "")
                                    }}</time
                                >
                                <span class="sr-only"
                                    >{{ day.events.length }} events</span
                                >
                                <span
                                    v-if="day.events.length > 0"
                                    class="-mx-0.5 mt-auto flex flex-wrap-reverse"
                                >
                                    <span
                                        v-for="event in day.events"
                                        :key="event.id"
                                        class="mx-0.5 mb-1 h-1.5 w-1.5 rounded-full bg-gray-400"
                                    />
                                </span>
                            </button>
                        </div>
                    </div>
                </div>
                <div
                    v-if="selectedDay?.events.length > 0"
                    class="px-4 py-10 sm:px-6 lg:hidden"
                >
                    <ol
                        class="overflow-hidden text-sm bg-white divide-y divide-gray-100 rounded-lg shadow ring-1 ring-black ring-opacity-5"
                    >
                        <li
                            v-for="event in selectedDay.events"
                            :key="event.id"
                            class="flex p-4 pr-6 group focus-within:bg-gray-50 hover:bg-gray-50"
                        >
                            <div class="flex-auto">
                                <p class="font-semibold text-gray-900">
                                    {{ event.name }}
                                </p>
                                <time
                                    :datetime="event.datetime"
                                    class="flex items-center mt-2 text-gray-700"
                                >
                                    <ClockIcon
                                        class="w-5 h-5 mr-2 text-gray-400"
                                        aria-hidden="true"
                                    />
                                    {{ event.time }}
                                </time>
                            </div>
                            <a
                                :href="event.href"
                                class="self-center flex-none px-3 py-2 ml-6 font-semibold text-gray-900 bg-white rounded-md shadow-sm opacity-0 ring-1 ring-inset ring-gray-300 hover:ring-gray-400 focus:opacity-100 group-hover:opacity-100"
                                >Edit<span class="sr-only"
                                    >, {{ event.name }}</span
                                ></a
                            >
                        </li>
                    </ol>
                </div>
            </div>

            <!-- Price -->

            <div class="overflow-hidden isolate">
                <div class="flow-root pt-24 pb-16 bg-gray-900 sm:pt-32 lg:pb-0">
                    <div class="px-6 mx-auto max-w-7xl lg:px-8">
                        <div class="relative z-10">
                            <h2
                                class="max-w-4xl mx-auto text-5xl font-bold tracking-tight text-center text-white"
                            >
                                Simple pricing, More knowledge
                            </h2>
                            <p
                                class="max-w-2xl mx-auto mt-4 text-lg leading-8 text-center text-white/60"
                            >
                                Whether you need capital market products and
                                services training, technical skills training,
                                behavioural training or digital technology
                                trainings, we can develop a programme to fit
                                your needs.
                            </p>
                            <div class="flex justify-center mt-16">
                                <RadioGroup
                                    v-model="frequency"
                                    class="grid grid-cols-2 p-1 text-xs font-semibold leading-5 text-center text-white rounded-full gap-x-1 bg-white/5"
                                >
                                    <RadioGroupLabel class="sr-only"
                                        >Payment frequency</RadioGroupLabel
                                    >
                                    <RadioGroupOption
                                        as="template"
                                        v-for="option in frequencies"
                                        :key="option.value"
                                        :value="option"
                                        v-slot="{ checked }"
                                    >
                                        <div
                                            :class="[
                                                checked ? 'bg-indigo-500' : '',
                                                'cursor-pointer rounded-full px-2.5 py-1',
                                            ]"
                                        >
                                            <span>{{ option.label }}</span>
                                        </div>
                                    </RadioGroupOption>
                                </RadioGroup>
                            </div>
                        </div>
                        <div
                            class="relative grid max-w-md grid-cols-1 mx-auto mt-10 gap-y-8 lg:mx-0 lg:-mb-14 lg:max-w-none lg:grid-cols-3"
                        >
                            <svg
                                viewBox="0 0 1208 1024"
                                aria-hidden="true"
                                class="absolute -bottom-48 left-1/2 h-[64rem] -translate-x-1/2 translate-y-1/2 [mask-image:radial-gradient(closest-side,white,transparent)] lg:-top-48 lg:bottom-auto lg:translate-y-0"
                            >
                                <ellipse
                                    cx="604"
                                    cy="512"
                                    fill="url(#d25c25d4-6d43-4bf9-b9ac-1842a30a4867)"
                                    rx="604"
                                    ry="512"
                                />
                                <defs>
                                    <radialGradient
                                        id="d25c25d4-6d43-4bf9-b9ac-1842a30a4867"
                                    >
                                        <stop stop-color="#7775D6" />
                                        <stop offset="1" stop-color="#E935C1" />
                                    </radialGradient>
                                </defs>
                            </svg>
                            <div
                                class="hidden lg:absolute lg:inset-x-px lg:bottom-0 lg:top-4 lg:block lg:rounded-t-2xl lg:bg-gray-800/80 lg:ring-1 lg:ring-white/10"
                                aria-hidden="true"
                            />
                            <div
                                v-for="tier in tiers"
                                :key="tier.id"
                                :class="[
                                    tier.featured
                                        ? 'z-10 bg-white shadow-xl ring-1 ring-gray-900/10'
                                        : 'bg-gray-800/80 ring-1 ring-white/10 lg:bg-transparent lg:pb-14 lg:ring-0',
                                    'relative rounded-2xl',
                                ]"
                            >
                                <div class="p-8 lg:pt-12 xl:p-10 xl:pt-14">
                                    <h3
                                        :id="tier.id"
                                        :class="[
                                            tier.featured
                                                ? 'text-gray-900'
                                                : 'text-white',
                                            'text-sm font-semibold leading-6',
                                        ]"
                                    >
                                        {{ tier.name }}
                                    </h3>
                                    <div
                                        class="flex flex-col gap-6 sm:flex-row sm:items-end sm:justify-between lg:flex-col lg:items-stretch"
                                    >
                                        <div
                                            class="flex items-center mt-2 gap-x-4"
                                        >
                                            <p
                                                :class="[
                                                    tier.featured
                                                        ? 'text-gray-900'
                                                        : 'text-white',
                                                    'text-4xl font-bold tracking-tight',
                                                ]"
                                            >
                                                {{
                                                    tier.price[frequency.value]
                                                }}
                                            </p>
                                            <div class="text-sm leading-5">
                                                <p
                                                    :class="
                                                        tier.featured
                                                            ? 'text-gray-900'
                                                            : 'text-white'
                                                    "
                                                >
                                                    RINGGIT MALAYSIA
                                                </p>
                                                <p
                                                    :class="
                                                        tier.featured
                                                            ? 'text-gray-500'
                                                            : 'text-gray-400'
                                                    "
                                                >
                                                    {{
                                                        `Billed ${frequency.value}`
                                                    }}
                                                </p>
                                            </div>
                                        </div>
                                        <a
                                            :href="tier.href"
                                            :aria-describedby="tier.id"
                                            :class="[
                                                tier.featured
                                                    ? 'bg-indigo-600 shadow-sm hover:bg-indigo-500 focus-visible:outline-indigo-600'
                                                    : 'bg-white/10 hover:bg-white/20 focus-visible:outline-white',
                                                'rounded-md py-2 px-3 text-center text-sm font-semibold leading-6 text-white focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2',
                                            ]"
                                            >Buy this module</a
                                        >
                                    </div>
                                    <div class="flow-root mt-8 sm:mt-10">
                                        <ul
                                            role="list"
                                            :class="[
                                                tier.featured
                                                    ? 'divide-gray-900/5 border-gray-900/5 text-gray-600'
                                                    : 'divide-white/5 border-white/5 text-white',
                                                '-my-2 divide-y border-t text-sm leading-6 lg:border-t-0',
                                            ]"
                                        >
                                            <li
                                                v-for="mainFeature in tier.mainFeatures"
                                                :key="mainFeature"
                                                class="flex py-2 gap-x-3"
                                            >
                                                <CheckIcon
                                                    :class="[
                                                        tier.featured
                                                            ? 'text-indigo-600'
                                                            : 'text-gray-500',
                                                        'h-6 w-5 flex-none',
                                                    ]"
                                                    aria-hidden="true"
                                                />
                                                {{ mainFeature }}
                                            </li>
                                        </ul>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="relative bg-gray-50 lg:pt-14">
                    <div class="px-6 py-24 mx-auto max-w-7xl sm:py-32 lg:px-8">
                        <!-- Feature comparison (up to lg) -->
                        <section
                            aria-labelledby="mobile-comparison-heading"
                            class="lg:hidden"
                        >
                            <h2 id="mobile-comparison-heading" class="sr-only">
                                Feature comparison
                            </h2>

                            <div class="max-w-2xl mx-auto space-y-16">
                                <div
                                    v-for="tier in tiers"
                                    :key="tier.id"
                                    class="border-t border-gray-900/10"
                                >
                                    <div
                                        :class="[
                                            tier.featured
                                                ? 'border-indigo-600'
                                                : 'border-transparent',
                                            '-mt-px w-72 border-t-2 pt-10 md:w-80',
                                        ]"
                                    >
                                        <h3
                                            :class="[
                                                tier.featured
                                                    ? 'text-indigo-600'
                                                    : 'text-gray-900',
                                                'text-sm font-semibold leading-6',
                                            ]"
                                        >
                                            {{ tier.name }}
                                        </h3>
                                        <p
                                            class="mt-1 text-sm leading-6 text-gray-600"
                                        >
                                            {{ tier.description }}
                                        </p>
                                    </div>

                                    <div class="mt-10 space-y-10">
                                        <div
                                            v-for="section in sections"
                                            :key="section.name"
                                        >
                                            <h4
                                                class="text-sm font-semibold leading-6 text-gray-900"
                                            >
                                                {{ section.name }}
                                            </h4>
                                            <div class="relative mt-6">
                                                <!-- Fake card background -->
                                                <div
                                                    aria-hidden="true"
                                                    class="absolute inset-y-0 right-0 hidden w-1/2 bg-white rounded-lg shadow-sm sm:block"
                                                />

                                                <div
                                                    :class="[
                                                        tier.featured
                                                            ? 'ring-2 ring-indigo-600'
                                                            : 'ring-1 ring-gray-900/10',
                                                        'relative rounded-lg bg-white shadow-sm sm:rounded-none sm:bg-transparent sm:shadow-none sm:ring-0',
                                                    ]"
                                                >
                                                    <dl
                                                        class="text-sm leading-6 divide-y divide-gray-200"
                                                    >
                                                        <div
                                                            v-for="feature in section.features"
                                                            :key="feature.name"
                                                            class="flex items-center justify-between px-4 py-3 sm:grid sm:grid-cols-2 sm:px-0"
                                                        >
                                                            <dt
                                                                class="pr-4 text-gray-600"
                                                            >
                                                                {{
                                                                    feature.name
                                                                }}
                                                            </dt>
                                                            <dd
                                                                class="flex items-center justify-end sm:justify-center sm:px-4"
                                                            >
                                                                <span
                                                                    v-if="
                                                                        typeof feature
                                                                            .tiers[
                                                                            tier
                                                                                .name
                                                                        ] ===
                                                                        'string'
                                                                    "
                                                                    :class="
                                                                        tier.featured
                                                                            ? 'font-semibold text-indigo-600'
                                                                            : 'text-gray-900'
                                                                    "
                                                                    >{{
                                                                        feature
                                                                            .tiers[
                                                                            tier
                                                                                .name
                                                                        ]
                                                                    }}</span
                                                                >
                                                                <template
                                                                    v-else
                                                                >
                                                                    <CheckIcon
                                                                        v-if="
                                                                            feature
                                                                                .tiers[
                                                                                tier
                                                                                    .name
                                                                            ] ===
                                                                            true
                                                                        "
                                                                        class="w-5 h-5 mx-auto text-indigo-600"
                                                                        aria-hidden="true"
                                                                    />
                                                                    <XMarkIcon
                                                                        v-else
                                                                        class="w-5 h-5 mx-auto text-gray-400"
                                                                        aria-hidden="true"
                                                                    />
                                                                    <span
                                                                        class="sr-only"
                                                                        >{{
                                                                            feature
                                                                                .tiers[
                                                                                tier
                                                                                    .name
                                                                            ] ===
                                                                            true
                                                                                ? "Yes"
                                                                                : "No"
                                                                        }}</span
                                                                    >
                                                                </template>
                                                            </dd>
                                                        </div>
                                                    </dl>
                                                </div>

                                                <!-- Fake card border -->
                                                <div
                                                    aria-hidden="true"
                                                    :class="[
                                                        tier.featured
                                                            ? 'ring-2 ring-indigo-600'
                                                            : 'ring-1 ring-gray-900/10',
                                                        'pointer-events-none absolute inset-y-0 right-0 hidden w-1/2 rounded-lg sm:block',
                                                    ]"
                                                />
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </section>

                        <!-- Feature comparison (lg+) -->
                        <section
                            aria-labelledby="comparison-heading"
                            class="hidden lg:block"
                        >
                            <h2 id="comparison-heading" class="sr-only">
                                Feature comparison
                            </h2>

                            <div
                                class="grid grid-cols-4 border-t gap-x-8 border-gray-900/10 before:block"
                            >
                                <div
                                    v-for="tier in tiers"
                                    :key="tier.id"
                                    aria-hidden="true"
                                    class="-mt-px"
                                >
                                    <div
                                        :class="[
                                            tier.featured
                                                ? 'border-indigo-600'
                                                : 'border-transparent',
                                            'border-t-2 pt-10',
                                        ]"
                                    >
                                        <p
                                            :class="[
                                                tier.featured
                                                    ? 'text-indigo-600'
                                                    : 'text-gray-900',
                                                'text-sm font-semibold leading-6',
                                            ]"
                                        >
                                            {{ tier.name }}
                                        </p>
                                        <p
                                            class="mt-1 text-sm leading-6 text-gray-600"
                                        >
                                            {{ tier.description }}
                                        </p>
                                    </div>
                                </div>
                            </div>

                            <div class="-mt-6 space-y-16">
                                <div
                                    v-for="section in sections"
                                    :key="section.name"
                                >
                                    <h3
                                        class="text-sm font-semibold leading-6 text-gray-900"
                                    >
                                        {{ section.name }}
                                    </h3>
                                    <div class="relative mt-10 -mx-8">
                                        <!-- Fake card backgrounds -->
                                        <div
                                            class="absolute inset-y-0 grid grid-cols-4 inset-x-8 gap-x-8 before:block"
                                            aria-hidden="true"
                                        >
                                            <div
                                                class="w-full h-full bg-white rounded-lg shadow-sm"
                                            />
                                            <div
                                                class="w-full h-full bg-white rounded-lg shadow-sm"
                                            />
                                            <div
                                                class="w-full h-full bg-white rounded-lg shadow-sm"
                                            />
                                        </div>

                                        <table
                                            class="relative w-full border-separate border-spacing-x-8"
                                        >
                                            <thead>
                                                <tr class="text-left">
                                                    <th scope="col">
                                                        <span class="sr-only"
                                                            >Feature</span
                                                        >
                                                    </th>
                                                    <th
                                                        v-for="tier in tiers"
                                                        :key="tier.id"
                                                        scope="col"
                                                    >
                                                        <span class="sr-only"
                                                            >{{
                                                                tier.name
                                                            }}
                                                            tier</span
                                                        >
                                                    </th>
                                                </tr>
                                            </thead>
                                            <tbody>
                                                <tr
                                                    v-for="(
                                                        feature, featureIdx
                                                    ) in section.features"
                                                    :key="feature.name"
                                                >
                                                    <th
                                                        scope="row"
                                                        class="w-1/4 py-3 pr-4 text-sm font-normal leading-6 text-left text-gray-900"
                                                    >
                                                        {{ feature.name }}
                                                        <div
                                                            v-if="
                                                                featureIdx !==
                                                                section.features
                                                                    .length -
                                                                    1
                                                            "
                                                            class="absolute h-px mt-3 bg-gray-200 inset-x-8"
                                                        />
                                                    </th>
                                                    <td
                                                        v-for="tier in tiers"
                                                        :key="tier.id"
                                                        class="relative w-1/4 px-4 py-0 text-center"
                                                    >
                                                        <span
                                                            class="relative w-full h-full py-3"
                                                        >
                                                            <span
                                                                v-if="
                                                                    typeof feature
                                                                        .tiers[
                                                                        tier
                                                                            .name
                                                                    ] ===
                                                                    'string'
                                                                "
                                                                :class="[
                                                                    tier.featured
                                                                        ? 'font-semibold text-indigo-600'
                                                                        : 'text-gray-900',
                                                                    'text-sm leading-6',
                                                                ]"
                                                                >{{
                                                                    feature
                                                                        .tiers[
                                                                        tier
                                                                            .name
                                                                    ]
                                                                }}</span
                                                            >
                                                            <template v-else>
                                                                <CheckIcon
                                                                    v-if="
                                                                        feature
                                                                            .tiers[
                                                                            tier
                                                                                .name
                                                                        ] ===
                                                                        true
                                                                    "
                                                                    class="w-5 h-5 mx-auto text-indigo-600"
                                                                    aria-hidden="true"
                                                                />
                                                                <XMarkIcon
                                                                    v-else
                                                                    class="w-5 h-5 mx-auto text-gray-400"
                                                                    aria-hidden="true"
                                                                />
                                                                <span
                                                                    class="sr-only"
                                                                    >{{
                                                                        feature
                                                                            .tiers[
                                                                            tier
                                                                                .name
                                                                        ] ===
                                                                        true
                                                                            ? "Yes"
                                                                            : "No"
                                                                    }}</span
                                                                >
                                                            </template>
                                                        </span>
                                                    </td>
                                                </tr>
                                            </tbody>
                                        </table>

                                        <!-- Fake card borders -->
                                        <div
                                            class="absolute inset-y-0 grid grid-cols-4 pointer-events-none inset-x-8 gap-x-8 before:block"
                                            aria-hidden="true"
                                        >
                                            <div
                                                v-for="tier in tiers"
                                                :key="tier.id"
                                                :class="[
                                                    tier.featured
                                                        ? 'ring-2 ring-indigo-600'
                                                        : 'ring-1 ring-gray-900/10',
                                                    'rounded-lg',
                                                ]"
                                            />
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </section>
                    </div>
                </div>
            </div>
        </main>
    </div>

    <!-- footer -->

    <footer class="bg-gray-800" aria-labelledby="footer-heading">
        <h2 id="footer-heading" class="sr-only">Footer</h2>
        <div class="px-6 py-12 mx-auto max-w-7xl lg:px-8 lg:py-16">
            <div class="pb-8 xl:grid xl:grid-cols-5 xl:gap-8">
                <div class="grid grid-cols-2 gap-8 xl:col-span-4">
                    <div class="md:grid md:grid-cols-2 md:gap-8">
                        <div>
                            <h3 class="text-base font-medium text-white">
                                Solutions
                            </h3>
                            <ul role="list" class="mt-4 space-y-4">
                                <li
                                    v-for="item in navigation1.solutions"
                                    :key="item.name"
                                >
                                    <a
                                        :href="item.href"
                                        class="text-base text-gray-300 hover:text-white"
                                        >{{ item.name }}</a
                                    >
                                </li>
                            </ul>
                        </div>
                        <div class="mt-12 md:mt-0">
                            <h3 class="text-base font-medium text-white">
                                Support
                            </h3>
                            <ul role="list" class="mt-4 space-y-4">
                                <li
                                    v-for="item in navigation1.support"
                                    :key="item.name"
                                >
                                    <a
                                        :href="item.href"
                                        class="text-base text-gray-300 hover:text-white"
                                        >{{ item.name }}</a
                                    >
                                </li>
                            </ul>
                        </div>
                    </div>
                    <div class="md:grid md:grid-cols-2 md:gap-8">
                        <div>
                            <h3 class="text-base font-medium text-white">
                                Company
                            </h3>
                            <ul role="list" class="mt-4 space-y-4">
                                <li
                                    v-for="item in navigation1.company"
                                    :key="item.name"
                                >
                                    <a
                                        :href="item.href"
                                        class="text-base text-gray-300 hover:text-white"
                                        >{{ item.name }}</a
                                    >
                                </li>
                            </ul>
                        </div>
                        <div class="mt-12 md:mt-0">
                            <h3 class="text-base font-medium text-white">
                                Legal
                            </h3>
                            <ul role="list" class="mt-4 space-y-4">
                                <li
                                    v-for="item in navigation1.legal"
                                    :key="item.name"
                                >
                                    <a
                                        :href="item.href"
                                        class="text-base text-gray-300 hover:text-white"
                                        >{{ item.name }}</a
                                    >
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
                <div class="mt-12 xl:mt-0">
                    <h3 class="text-base font-medium text-white">
                        Language &amp; Currency
                    </h3>
                    <form class="mt-4 sm:max-w-xs">
                        <fieldset class="w-full">
                            <label for="language" class="sr-only"
                                >Language</label
                            >
                            <div class="relative">
                                <select
                                    id="language"
                                    name="language"
                                    class="block w-full py-2 pl-3 pr-10 text-base text-white bg-gray-700 border border-transparent rounded-md appearance-none bg-none focus:border-white focus:outline-none focus:ring-white sm:text-sm"
                                >
                                    <option selected="">English</option>
                                    <option>French</option>
                                    <option>German</option>
                                    <option>Japanese</option>
                                    <option>Spanish</option>
                                </select>
                                <div
                                    class="absolute inset-y-0 right-0 flex items-center px-2 pointer-events-none"
                                >
                                    <ChevronDownIcon
                                        class="w-4 h-4 text-white"
                                        aria-hidden="true"
                                    />
                                </div>
                            </div>
                        </fieldset>
                        <fieldset class="w-full mt-4">
                            <label for="currency" class="sr-only"
                                >Currency</label
                            >
                            <div class="relative mt-1.5">
                                <select
                                    id="currency"
                                    name="currency"
                                    class="block w-full py-2 pl-3 pr-10 text-base text-white bg-gray-700 border border-transparent rounded-md appearance-none bg-none focus:border-white focus:outline-none focus:ring-white sm:text-sm"
                                >
                                    <option>ARS</option>
                                    <option selected="">AUD</option>
                                    <option>CAD</option>
                                    <option>CHF</option>
                                    <option>EUR</option>
                                    <option>GBP</option>
                                    <option>JPY</option>
                                    <option>USD</option>
                                </select>
                                <div
                                    class="absolute inset-y-0 right-0 flex items-center px-2 pointer-events-none"
                                >
                                    <ChevronDownIcon
                                        class="w-4 h-4 text-white"
                                        aria-hidden="true"
                                    />
                                </div>
                            </div>
                        </fieldset>
                    </form>
                </div>
            </div>
            <div
                class="pt-8 border-t border-gray-700 lg:flex lg:items-center lg:justify-between xl:mt-0"
            >
                <div>
                    <h3 class="text-base font-medium text-white">
                        checkout to our newsletter
                    </h3>
                    <p class="mt-2 text-base text-gray-300">
                        The latest news, articles, and resources, sent to your
                        inbox weekly.
                    </p>
                </div>
                <form class="mt-4 sm:flex sm:max-w-md lg:mt-0">
                    <label for="email-address" class="sr-only"
                        >Email address</label
                    >
                    <input
                        type="email"
                        name="email-address"
                        id="email-address"
                        autocomplete="email"
                        required=""
                        class="w-full min-w-0 px-4 py-2 text-base text-gray-900 placeholder-gray-500 bg-white border border-transparent rounded-md appearance-none focus:border-white focus:placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-gray-800 sm:max-w-xs"
                        placeholder="Enter your email"
                    />
                    <div
                        class="mt-3 rounded-md sm:ml-3 sm:mt-0 sm:flex-shrink-0"
                    >
                        <button
                            type="submit"
                            class="flex items-center justify-center w-full px-4 py-2 text-base font-medium text-white bg-indigo-500 border border-transparent rounded-md hover:bg-indigo-600 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 focus:ring-offset-gray-800"
                        >
                            Interested
                        </button>
                    </div>
                </form>
            </div>
            <div
                class="pt-8 mt-8 border-t border-gray-700 md:flex md:items-center md:justify-between"
            >
                <div class="flex space-x-6 md:order-2">
                    <a
                        v-for="item in navigation.social"
                        :key="item.name"
                        :href="item.href"
                        class="text-gray-400 hover:text-gray-300"
                    >
                        <span class="sr-only">{{ item.name }}</span>
                        <component
                            :is="item.icon"
                            class="w-6 h-6"
                            aria-hidden="true"
                        />
                    </a>
                </div>
                <p
                    class="mt-6 leading-3 text-center text-gray-500 text-medium dark:text-white"
                >
                    <span class="block sm:inline"
                        >&copy; Copyright {{ new Date().getFullYear() }} SIDC.
                    </span>
                    <span class="block sm:inline">All rights reserved.</span>
                </p>
            </div>
        </div>
    </footer>
</template>
