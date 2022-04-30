<template>
  <div class="q-px-lg q-pb-md">
    <q-timeline :layout="layout" color="secondary">
      <h1>Transaction Progress</h1>
      <q-timeline-entry heading>
        Preliminary Steps
        <br />
        <!--({{$q.screen.lt.sm ? 'Dense' : ($q.screen.lt.md ? 'Comfortable' : 'Loose')}} layout)-->
      </q-timeline-entry>

      <q-timeline-entry
        title="Listing Agreement Signed"
        subtitle=""
        side="left"
        color="blue"
      >
        <div></div>
      </q-timeline-entry>

      <q-timeline-entry
        title="Listing Live"
        subtitle=""
        side="right"
        color="blue"
      >
        <div>
          <q-btn
            onclick="window.location.href='https://www.diamocycle.com/';"
            color="primary"
            label="View Docs"
          />
        </div>
      </q-timeline-entry>

      <q-timeline-entry heading>Under Contract</q-timeline-entry>

      <q-timeline-entry
        title="Offer Accepted"
        subtitle=""
        side="left"
        color="orange"
      >
        <div></div>
      </q-timeline-entry>

      <q-timeline-entry
        title="Inspection"
        subtitle=""
        side="right"
        color="orange"
      >
        <div></div>
      </q-timeline-entry>

      <q-timeline-entry
        title="Appraisal"
        subtitle=""
        side="left"
        color="orange"
      >
        <div></div>
      </q-timeline-entry>

      <q-timeline-entry heading>Contingencies Removed</q-timeline-entry>

      <q-timeline-entry title="Pending" subtitle="" side="right" color="red">
        <div></div>
      </q-timeline-entry>

      <q-timeline-entry
        title="Sold"
        subtitle=""
        side="left"
        color="red"
        icon="done_all"
      >
        <div></div>
      </q-timeline-entry>
    </q-timeline>
  </div>
</template>

<script>
import { useTimeline } from "../stores/timeline";
import { useQuasar } from "quasar";
import { computed } from "vue";

export default {
  name: "TimeLine",
  setup() {
    const $tl = useTimeline();

    const $q = useQuasar();
    return {
      $tl,
      layout: computed(() => {
        return $q.screen.lt.sm
          ? "dense"
          : $q.screen.lt.md
          ? "comfortable"
          : "loose";
      }),
    };
  },
};
</script>
