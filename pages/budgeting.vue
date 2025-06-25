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
  { month: "January", value: "january" },
  { month: "February", value: "february" },
  { month: "March", value: "march" },
  { month: "April", value: "april" },
  { month: "May", value: "may" },
  { month: "June", value: "june" },
  { month: "July", value: "july" },
  { month: "August", value: "august" },
  { month: "September", value: "september" },
  { month: "October", value: "october" },
  { month: "November", value: "november" },
  { month: "December", value: "december" },
]);
</script>

<template>
  <Tabs default-value="account" class="w-full">
    <TabsList class="grid w-full grid-cols-12">
      <div v-for="(month, index) in year" :key="index">
        <TabsTrigger value="account"> {{ month.month }} </TabsTrigger>
      </div>
    </TabsList>
    <TabsContent value="account">
      <Card>
        <CardHeader>
          <CardTitle>Account</CardTitle>
          <CardDescription>
            Make changes to your account here. Click save when you're done.
          </CardDescription>
        </CardHeader>
        <CardContent class="space-y-2">
          <div class="space-y-1">
            <Label for="name">Name</Label>
            <Input id="name" type="text" placeholder="John Doe" />
          </div>
          <div class="space-y-1">
            <Label for="email">Email</Label>
            <Input id="email" type="email" placeholder="" />
          </div>
        </CardContent>
        <CardFooter>
          <Button>Save changes</Button>
        </CardFooter>
      </Card>
    </TabsContent>
    <TabsContent value="password">
      <Card>
        <CardHeader>
          <CardTitle>Password</CardTitle>
          <CardDescription>
            Change your password here. After saving, you'll be logged out.
          </CardDescription>
        </CardHeader>
        <CardContent class="space-y-2">
          <div class="space-y-1">
            <Label for="current">Current password</Label>
            <Input id="current" type="password" />
          </div>
          <div class="space-y-1">
            <Label for="new">New password</Label>
            <Input id="new" type="password" />
          </div>
        </CardContent>
        <CardFooter>
          <Button>Save password</Button>
        </CardFooter>
      </Card>
    </TabsContent>
  </Tabs>
</template>
