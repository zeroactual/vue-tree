
<template>
  <div class="container">
    <vue-tree
      style="width: 1000px; height: 600px; border: 1px solid gray"
      :dataset="richMediaData"
      :config="treeConfig"
      linkStyle="straight"
    >
      <template v-slot:node="{ node, collapsed }">
        <div
          class="rich-media-node"
          :style="{ border: collapsed ? '2px solid grey' : '' }"
        >
          <!-- <img
            :src="node.avatar"
            style="width: 48px; height: 48px; border-raduis: 4px"
          /> -->
          <span style="padding: 4px 0; font-weight: bold">{{ node.name }}</span>
          <!-- <span style="padding: 4px 0; font-weight: bold">{{
            node.value
          }}</span> -->
        </div>
      </template>
    </vue-tree>
  </div>
</template>
<script>
import VueTree from "@ssthouse/vue3-tree-chart";
import "@ssthouse/vue3-tree-chart/dist/vue3-tree-chart.css";

export default {
  components: { VueTree },
  data() {
    return {
      richMediaData: {
        name: "James",
        value: 800,
        children: [
          {
            name: "Bob",
            value: 400,
            children: [
              {
                name: "C1",
                value: 100,
              },
              {
                name: "C2",
                value: 300,
              },
              {
                name: "C3",
                value: 200,
              },
            ],
          },
          {
            name: "Smith",
            value: 200,
            children: [
              {
                name: "S1",
                value: 230,
              },
            ],
          },
          {
            name: "Jackson",
            value: 300,
          },
        ],
      },
      treeConfig: {
        nodeWidth: 120,
        nodeHeight: 80,
        levelHeight: 100,
        linkStyle: "straight",
      },
    };
  },
};

// let sampleData =  {
//   value: "1",
//   children: [
//     { value: "2", children: [{ value: "4" }, { value: "5" }] },
//     { value: "3" },
//   ],
// };
// let treeConfig = { nodeWidth: 120, nodeHeight: 80, levelHeight: 200 };
</script>


<style>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.rich-media-node {
  width: 80px;
  padding: 8px;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  color: white;
  background-color: #f7c616;
  border-radius: 4px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
