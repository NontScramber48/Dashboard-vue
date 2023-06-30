<!-- eslint-disable prettier/prettier -->
<template>
  <div class="row">
    <div class="col-12">
      <card :title="table1.title" :subTitle="table1.subTitle">
        <div slot="raw-content" class="table-responsive">
          <paper-table :data="table1.data" :columns="table1.columns">
          </paper-table>
        </div>
      </card>
    </div>

    <!-- <div class="col-12">
      <card class="card-plain">
        <div class="table-full-width table-responsive">
          <paper-table
            type="hover"
            :title="table2.title"
            :sub-title="table2.subTitle"
            :data="table2.data"
            :columns="table2.columns"
          >
          </paper-table>
        </div>
      </card>
    </div> -->
  </div>
</template>
<!-- eslint-disable prettier/prettier -->
<script setup>
import { PaperTable } from "@/components";
import { ref } from "vue";
const table1 = ref({
  title: "สรุปยอดประจำสัปดาห์",
  subTitle: "",
  columns: ["day", "income", "expenses", "profit", "loss"],
  data: [
    {
      day: "Sun",
      income: "$36.738",
      expenses: "$36.738",
      profit: "$36.738",
      loss: "$36.738",
    },
    {
      day: "Mon",
      income: "$63,542",
      expenses: "$23,789",
      profit: "$36.738",
      loss: "$36.738",
    },
    {
      day: "Tue",
      income: "$63,542",
      expenses: "$56,142",
      profit: "$56,142",
      loss: "$36.738",
    },
    {
      day: "Wed",
      income: "$63,542",
      expenses: "$38,735",
      profit: "$36.738",
      loss: "$36.738",
    },
    {
      day: "Thu",
      income: "$63,542",
      expenses: "$63,542",
      profit: "$36.738",
      loss: "$63,542",
    },
    {
      day: "Fri",
      income: "$63,542",
      expenses: "$63,542",
      profit: "$36.738",
      loss: "$36.738",
    },
    {
      day: "Sat",
      income: "$63,542",
      expenses: "$63,542",
      profit: "$36.738",
      loss: "$36.738",
    },
  ],
});
</script>
// table2: { // title: "Table on Plain Background", // subTitle: "Here is a
subtitle for this table", // columns: [...tableColumns], // data:
[...tableData],

<style></style>
