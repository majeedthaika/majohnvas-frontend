<template>
  <div class="post">
    <md-layout md-gutter md-align="center" style="margin-top:150px;">
      <md-card md-align="center" style="width:600px;">
        <md-card-area>
          <md-card-header>
            <div class="md-title">Title of post</div>
          </md-card-header>

          <md-card-content>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Optio itaque ea, nostrum odio. Dolores, sed accusantium quasi non, voluptas eius illo quas, saepe voluptate pariatur in deleniti minus sint. Excepturi.
          </md-card-content>
        </md-card-area>

        <md-card-actions>
          <md-dialog md-open-from="#fab" md-close-to="#fab" ref="dialog2">
            <md-dialog-title>Edit comment</md-dialog-title>

            <md-dialog-content>
              <form>
                <md-input-container>
                  <label>Comment</label>
                  <md-textarea maxlength="100"></md-textarea>
                </md-input-container>
              </form>
            </md-dialog-content>

            <md-dialog-actions>
              <md-button class="md-primary" @click.native="closeDialog('dialog2')">Cancel</md-button>
              <md-button class="md-primary" @click.native="closeDialog('dialog2')">Confirm</md-button>
            </md-dialog-actions>
          </md-dialog>

          <router-link to="/comment">
            <md-button class="md-accent">Back</md-button>
          </router-link>
          <md-button class="md-accent md-raised" id="fab" @click.native="openDialog('dialog2')" disabled>Edit</md-button>
        </md-card-actions>
      </md-card>
    </md-layout>
  </div>
</template>

<script>
export default {
  methods: {
    openDialog (ref) {
      this.$refs[ref].open()
    },
    closeDialog (ref) {
      this.$refs[ref].close()
    },
    onOpen () {
      console.log('Opened')
    },
    onClose (type) {
      console.log('Closed', type)
    },
    viewComment () {
      console.log('view comment')
    }
  }
}
</script>

<style>

</style>
