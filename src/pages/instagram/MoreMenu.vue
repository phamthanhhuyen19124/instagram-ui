<template>
  <div>
    <a @click="CreateModal" class="item-menu">
      <svg aria-label="New post" class="_ab6- icon-menu" color="rgb(0, 0, 0)"
           fill="rgb(0, 0, 0)" height="24" role="img" viewBox="0 0 24 24"
           width="24">
        <path
            d="M2 12v3.45c0 2.849.698 4.005 1.606 4.944.94.909 2.098 1.608 4.946 1.608h6.896c2.848 0 4.006-.7 4.946-1.608C21.302 19.455 22 18.3 22 15.45V8.552c0-2.849-.698-4.006-1.606-4.945C19.454 2.7 18.296 2 15.448 2H8.552c-2.848 0-4.006.699-4.946 1.607C2.698 4.547 2 5.703 2 8.552Z"
            fill="none" stroke="currentColor"
            stroke-linecap="round" stroke-linejoin="round" stroke-width="2"></path>
        <line fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round"
              stroke-width="2" x1="6.545" x2="17.455" y1="12.001" y2="12.001"></line>
        <line fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
              x1="12.003" x2="12.003" y1="6.545" y2="17.455"></line>
      </svg>
      <svg aria-label="New post" class="_ab6- icon-active" color="rgb(0, 0, 0)" fill="rgb(0, 0, 0)" height="24" role="img"
           viewBox="0 0 24 24" width="24">
        <path
            d="m12.003 5.545-.117.006-.112.02a1 1 0 0 0-.764.857l-.007.117V11H6.544l-.116.007a1 1 0 0 0-.877.876L5.545 12l.007.117a1 1 0 0 0 .877.876l.116.007h4.457l.001 4.454.007.116a1 1 0 0 0 .876.877l.117.007.117-.007a1 1 0 0 0 .876-.877l.007-.116V13h4.452l.116-.007a1 1 0 0 0 .877-.876l.007-.117-.007-.117a1 1 0 0 0-.877-.876L17.455 11h-4.453l.001-4.455-.007-.117a1 1 0 0 0-.876-.877ZM8.552.999h6.896c2.754 0 4.285.579 5.664 1.912 1.255 1.297 1.838 2.758 1.885 5.302L23 8.55v6.898c0 2.755-.578 4.286-1.912 5.664-1.298 1.255-2.759 1.838-5.302 1.885l-.338.003H8.552c-2.754 0-4.285-.579-5.664-1.912-1.255-1.297-1.839-2.758-1.885-5.302L1 15.45V8.551c0-2.754.579-4.286 1.912-5.664C4.21 1.633 5.67 1.05 8.214 1.002L8.552 1Z"></path>
      </svg>
      <div class="name-menu">Create</div>
    </a>
    <el-dialog custom-class="modal-moremenu"
               :visible.sync="isOpenModal"
    style="width: 1000px;margin: 0 auto;height: 800px">
      <div>
        <div class="title-modal"> Create new post</div>
        <div class="body-modal">
          <svg aria-label="Icon to represent media such as images or videos" class="x1lliihq x1n2onr6"
               color="rgb(0, 0, 0)" fill="rgb(0, 0, 0)" height="77" role="img" viewBox="0 0 97.6 77.3" width="96">
            <title>Icon to represent media such as images or videos</title>
            <path
                d="M16.3 24h.3c2.8-.2 4.9-2.6 4.8-5.4-.2-2.8-2.6-4.9-5.4-4.8s-4.9 2.6-4.8 5.4c.1 2.7 2.4 4.8 5.1 4.8zm-2.4-7.2c.5-.6 1.3-1 2.1-1h.2c1.7 0 3.1 1.4 3.1 3.1 0 1.7-1.4 3.1-3.1 3.1-1.7 0-3.1-1.4-3.1-3.1 0-.8.3-1.5.8-2.1z"
                fill="currentColor"></path>
            <path
                d="M84.7 18.4 58 16.9l-.2-3c-.3-5.7-5.2-10.1-11-9.8L12.9 6c-5.7.3-10.1 5.3-9.8 11L5 51v.8c.7 5.2 5.1 9.1 10.3 9.1h.6l21.7-1.2v.6c-.3 5.7 4 10.7 9.8 11l34 2h.6c5.5 0 10.1-4.3 10.4-9.8l2-34c.4-5.8-4-10.7-9.7-11.1zM7.2 10.8C8.7 9.1 10.8 8.1 13 8l34-1.9c4.6-.3 8.6 3.3 8.9 7.9l.2 2.8-5.3-.3c-5.7-.3-10.7 4-11 9.8l-.6 9.5-9.5 10.7c-.2.3-.6.4-1 .5-.4 0-.7-.1-1-.4l-7.8-7c-1.4-1.3-3.5-1.1-4.8.3L7 49 5.2 17c-.2-2.3.6-4.5 2-6.2zm8.7 48c-4.3.2-8.1-2.8-8.8-7.1l9.4-10.5c.2-.3.6-.4 1-.5.4 0 .7.1 1 .4l7.8 7c.7.6 1.6.9 2.5.9.9 0 1.7-.5 2.3-1.1l7.8-8.8-1.1 18.6-21.9 1.1zm76.5-29.5-2 34c-.3 4.6-4.3 8.2-8.9 7.9l-34-2c-4.6-.3-8.2-4.3-7.9-8.9l2-34c.3-4.4 3.9-7.9 8.4-7.9h.5l34 2c4.7.3 8.2 4.3 7.9 8.9z"
                fill="currentColor"></path>
            <path
                d="M78.2 41.6 61.3 30.5c-2.1-1.4-4.9-.8-6.2 1.3-.4.7-.7 1.4-.7 2.2l-1.2 20.1c-.1 2.5 1.7 4.6 4.2 4.8h.3c.7 0 1.4-.2 2-.5l18-9c2.2-1.1 3.1-3.8 2-6-.4-.7-.9-1.3-1.5-1.8zm-1.4 6-18 9c-.4.2-.8.3-1.3.3-.4 0-.9-.2-1.2-.4-.7-.5-1.2-1.3-1.1-2.2l1.2-20.1c.1-.9.6-1.7 1.4-2.1.8-.4 1.7-.3 2.5.1L77 43.3c1.2.8 1.5 2.3.7 3.4-.2.4-.5.7-.9.9z"
                fill="currentColor"></path>
          </svg>
          <div>
            Drag photos and videos here
          </div>
<!--          <button>Select from computer</button>-->
          <input type="file" placeholder="Select from computer" accept="image/png, image/jpeg"/>
        </div>
      </div>
    </el-dialog>
  </div>
</template>
<script>
export default {
  data() {
    return {
      isOpenModal: false,
    }
  },
  methods: {
    CreateModal() {
      this.isOpenModal = true
    }
  }
}
</script>

<style scoped>
.title-modal{
  text-align: center;
  padding-bottom: 10px;
  border-bottom: 1px solid grey;
  color: black;
  font-weight: 500;
  font-size: 16px;
}
.body-modal{
  margin-top: 60px;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  margin-bottom: 40px;
}
.item-menu {
  display: flex;
  gap: 16px;
  padding: 12px;
  margin: 2px 0;
  width: 220px;
  align-items: center;
  text-decoration: none;
}
.body-modal svg{
  margin-bottom: 10px;
}
.body-modal div{
  margin-bottom: 15px;
  font-size: 20px;
}
.body-modal button{
  border-radius: 12px;
  padding: 10px 20px;
  font-size: 12px;
  font-weight: 500;
  color: #FFFFFF;
  background: rgb(0, 149, 246);
  border: 0;
}
.item-menu:hover {
  background: rgba(0, 0, 0, .05);
  border-radius: 8px;
  cursor: pointer;
}

.name-menu {
  font-size: 16px;
  line-height: 24px;
  color: rgb(0, 0, 0);
  font-weight: 400;
}
.icon-active{
  display: none;
}
@media (max-width: 415px) {
.name-menu{
  display: none;
}
  .item-menu{
    display: block;
    padding: 0;
    margin: 0;
    width: auto;
  }
  .icon-active{
    display: none;
  }
}
</style>