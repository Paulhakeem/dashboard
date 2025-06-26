<script setup>
import { Button } from "@/components/ui/button";
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";
import { Tabs, TabsContent, TabsList, TabsTrigger } from "@/components/ui/tabs";

const year = ref([
  { month: "January", value: "january", path: "/jan" },
  { month: "February", value: "february", path: "/feb" },
  { month: "March", value: "march", path: "/mar" },
  { month: "April", value: "april", path: "/apr" },
  { month: "May", value: "may", path: "/may" },
  { month: "June", value: "june", path: "/jun" },
  { month: "July", value: "july", path: "/jul" },
  { month: "August", value: "august", path: "/aug" },
  { month: "September", value: "september", path: "/sep" },
  { month: "October", value: "october", path: "/oct" },
  { month: "November", value: "november", path: "/nov" },
  { month: "December", value: "december", path: "/dec" },
]);
</script>

<template>
  <Tabs class="w-full" default-value="january">
    <TabsList class="grid grid-cols-12 w-full">
      <TabsTrigger
        v-for="(month, index) in year"
        :key="index"
        :value="month.value"
        class="col-span-1 text-xs p-2 rounded hover:bg-blue-500 dark:hover:bg-gray-700"
      >
        {{ month.month }}
      </TabsTrigger>
    </TabsList>
    <!-- content -->
    <div v-for="(month, index) in year" :key="'content-' + index">
      <TabsContent :value="month.value" class="col-span-12 p-4">
          <Card class="w-full">
            <CardHeader>
              <CardTitle>{{ month.month }} Report</CardTitle>
              <CardDescription>
                Manage your records for {{ month.month }}.
              </CardDescription>
            </CardHeader>
            <CardContent class="space-y-2">
              <div class="space-y-1">
                <Label for="name">Name</Label>
                <Input id="name" type="text" placeholder="John Doe" />
              </div>
              <div class="space-y-1">
                <Label for="email">Email</Label>
                <Input id="email" type="email" placeholder="you@example.com" />
              </div>
            </CardContent>
            <CardFooter>
              <Button>Save changes</Button>
            </CardFooter>
          </Card>
      </TabsContent>
    </div>
  </Tabs>
</template>
