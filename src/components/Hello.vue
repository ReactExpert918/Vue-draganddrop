<template>
  <div class='main'>
    <div class='container'>
      <div class='treeSelf'>
        <vue-drag-tree class="category" :data='data' :allowDrag='allowDrag' :allowDrop='allowDrop' :defaultText='"New Node"' @current-clicked='curNodeClicked' @drag="dragHandler" @drag-enter="dragEnterHandler" @drag-leave="dragLeaveHandler" @drag-over="dragOverHandler" @drag-end="dragEndHandler" @drop="dropHandler" :disableDBClick='false' expand-all>
        </vue-drag-tree>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Hello",
  data() {
    return {
      en: false,
      data: [
        {
          name: "Node 0-0",
          id: 0,
          children: [
            {
              name: "Node 1-1",
              id: 3,
              children: [
                {
                  name: "Node 2-1",
                  id: 4,
                  children: []
                },
                {
                  name: "Node 2-2",
                  id: 10,
                  children: []
                }
              ]
            },
            {
              name: "Node 1-2",
              id: 13,
              children: []
            }
          ]
        },
        {
          name: "Node 0-1",
          id: 14,
          children: []
        }
      ]
    };
  },
  computed: {
    formatData() {
      return JSON.stringify(this.data, null, 2);
    }
  },
  methods: {
    allowDrag(model, component) {
      return true;
    },
    allowDrop(model, component) {
      return true;
    },
    curNodeClicked(model, component) {
    },
    dragHandler(model, component, e) {
    },
    dragEnterHandler(model, component, e) {
    },
    dragLeaveHandler(model, component, e) {
    },
    dragOverHandler(model, component, e) {
    },
    dragEndHandler(model, component, e) {
    },
    dropHandler(model, component, e) {
    }
  }
};
</script>

<style scoped>
@font-face {
  font-family: "Tangerine";
  src: url("/static/Tangerine-Regular.ttf");
}

.main {
  display: flex;
  flex-direction: column;
  font-size: 35px;
  align-items: center;
}
.container {
  width: 80%;
  display: flex;
  margin-top: 2rem;
  justify-content: space-between;
  padding: 0 5rem;
}
.treeSelf {
  border: 3px solid #e5e9f2;
  color: white;
  width: 100%;
  text-align: left;
  padding: 1rem;
}
</style>
