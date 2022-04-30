<template>
  <div class="q-pa-md">
    <div class="q-gutter-y-md" style="max-width: 600px">
      <q-card>
        <q-tabs
          v-model="tab"
          dense
          class="text-grey"
          active-color="primary"
          indicator-color="primary"
          align="justify"
          narrow-indicator
        >
          <q-tab name="overview" label="Overview" />
          <q-tab name="timeline" label="Timeline" />
          <q-tab name="documents" label="Documents" />
          <q-btn-dropdown
            active-color="primary"
            auto-close
            stretch
            flat
            label=""
          >
            <q-list>
              <q-item clickable @click="tab = 'movies'">
                <q-item-section>Movies</q-item-section>
              </q-item>

              <q-item clickable @click="tab = 'photos'">
                <q-item-section>Photos</q-item-section>
              </q-item>
            </q-list>
          </q-btn-dropdown>
        </q-tabs>

        <q-separator />
      </q-card>
    </div>
  </div>
  <q-tab-panels v-model="tab" animated>
    <q-tab-panel name="timeline">
      <div class="text-h6">Timeline</div>
      <TimeLine></TimeLine>
    </q-tab-panel>
    <q-tab-panel name="documents">
      <div class="text-h6">Documents</div>
      <q-uploader
        url="http://localhost:4444/upload"
        label="Individual upload"
        multiple
        style="max-width: 300px"
      />
    </q-tab-panel>
  </q-tab-panels>
</template>

<script>
import { defineComponent } from "vue";
import { ref } from "vue";
import TimeLine from "src/components/TimeLine.vue";
export default defineComponent({
  name: "IndexPage",
  components: { TimeLine },
  setup() {
    return {
      tab: ref("mails"),
    };
  },
  data() {
    return {
      timelineVisible: false,
      docsVisible: false,
    };
  },
  methods: {
    showTimeline() {
      this.docsVisible = false;
      this.timelineVisible = true;
    },
    showDocs() {
      this.timelineVisible = false;
      this.docsVisible = true;
    },
  },
});
</script>
