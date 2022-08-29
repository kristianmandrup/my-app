<script language="ts">
  import { goto } from "@roxi/routify";
  import { chevronBack } from "ionicons/icons";
</script>

<ion-header>
  <ion-toolbar color="primary">
    <ion-buttons>
      <ion-button slot="start" on:click={() => $goto("/")} expand="full">
        <ion-icon icon={chevronBack} />
      </ion-button>
    </ion-buttons>
    <ion-title>My Details</ion-title>
  </ion-toolbar>
</ion-header>

<ion-item>details </ion-item>
