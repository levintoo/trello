<script setup lang="ts">
import type { Column } from '~/types';
import { nanoid } from "nanoid"
import draggable from 'vuedraggable';
const columns = ref<Column[]>([
    {
        id: nanoid(),
        title: "Backlog",
        tasks: [
            {
                id: nanoid(),
                title: "Create marketing landing page",
                created: new Date()
            },
            {
                id: nanoid(),
                title: "Develop cool new feature",
                created: new Date()
            },
            {
                id: nanoid(),
                title: "Fix page nav bug",
                created: new Date()
            },
        ]
    },
    {
        id: nanoid(),
        title: "Selected for Dev",
        tasks: []
    },
    {
        id: nanoid(),
        title: "In Progress",
        tasks: []
    },
    {
        id: nanoid(),
        title: "QA",
        tasks: []
    },
    {
        id: nanoid(),
        title: "Complete",
        tasks: []
    }
])
</script>

<template>
    <div>
        <draggable v-model="columns" group="columns" item-key="id" class="flex gap-4 overflow-x-auto items-start">
            <template #item="{ element: column }: { element: Column }">
                <div class="p-5 bg-gray-200 rounded min-w-[250px]">
                    <header class="font-medium mb-4">
                        {{ column.title }}
                    </header>
                    <TrelloBoardTask v-for="task in column.tasks" :key="task.id" :task />
                    <footer class="text-gray-500">+ add a card</footer>
                </div>
            </template>
        </draggable>
    </div>
</template>