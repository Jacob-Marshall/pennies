<template>
  <div class="container">
  <template>
    <div class="center">
      <vs-button @click="active=!active">
        Change your budget
      </vs-button>
      <vs-dialog blur v-model="active">
        <template #header>
          <h4 class="not-margin">
            Welcome to <b>Pennies</b>
          </h4>
        </template>


        <div class="con-form">
          <vs-input type="number" v-model="input1" placeholder="Money">
            <template #icon>
              💲
            </template>
          </vs-input>
          <vs-input type="number" v-model="input2" placeholder="Budget">
            <template #icon>
              💳
            </template>
          </vs-input>
        </div>

        <template #footer>
          <div class="footer-dialog">
            <vs-button block @click="active=!active">
              Save
            </vs-button>
            <div class="new">
              There's no need for a <b>£</b> sign
            </div>
          </div>
        </template>
      </vs-dialog>
    </div>
  </template>
    
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      active: true,
        input1: '',
        input2: '',
      budget: [
          {
            "id": 1,
            "name": "Leanne Graham",
            "amount": "7.00"
          }
        ]
    }
  }
}
</script>


  <style lang="stylus">
    getColor(vsColor, alpha = 1)
        unquote("rgba(var(--vs-"+vsColor+"), "+alpha+")")
    getVar(var)
        unquote("var(--vs-"+var+")")
    .not-margin
      margin 0px
      font-weight normal
      padding 10px
    .con-form
      width 100%
      .flex
        display flex
        align-items center
        justify-content space-between
        a
          font-size .8rem
          opacity .7
          &:hover
            opacity 1
      .vs-checkbox-label
        font-size .8rem
      .vs-input-content
        margin 10px 0px
        width calc(100%)
        .vs-input
          width 100%
    .footer-dialog
      display flex
      align-items center
      justify-content center
      flex-direction column
      width calc(100%)
      .new
        margin 0px
        margin-top 20px
        padding: 0px
        font-size .7rem
        a
          color getColor('primary') !important
          margin-left 6px
          &:hover
            text-decoration underline
      .vs-button
        margin 0px
    </style>