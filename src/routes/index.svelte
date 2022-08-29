<script language="ts">
  import { goto } from "@roxi/routify";
  import { Camera, CameraSource, CameraResultType } from "@capacitor/camera";
  let myImage = "";

  const takePicture = async () => {
    const image = await Camera.getPhoto({
      quality: 90,
      allowEditing: true,
      source: CameraSource.Prompt,
      resultType: CameraResultType.Base64,
    });
    myImage = `data:image/jpeg;base64,${image.base64String}`;
  };
</script>

<ion-header>
  <ion-toolbar color="primary">
    <ion-title>My Svelte App</ion-title>
  </ion-toolbar>
</ion-header>

<ion-card>
  {#if myImage}
    <!-- svelte-ignore a11y-missing-attribute -->
    <img src={myImage} />
  {/if}
  <ion-card-content>
    My card
    <ion-button expand="block" fill="outline" on:click={takePicture}
      >Capture image</ion-button
    >
  </ion-card-content>
</ion-card>

<ion-button on:click={() => $goto("/details")} expand="full"
  >Go to details</ion-button
>
