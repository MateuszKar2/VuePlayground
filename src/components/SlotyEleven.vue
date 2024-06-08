<!--sloty-->
<!--przekazywania np. logo-->
<template>
    <div class="container">
      <AwsomeButton :text="'hello'">
            <div class="square"></div>
      </AwsomeButton>
      <!-- <AwsomeButton :text="'hello'">
        <template #text>
            <h1>
                huraaaa
            </h1>
        </template>
        <template #image>
            <img src="../assets/logo.png" alt="logo" class="image"/>
        </template>
      </AwsomeButton> -->
    </div>
  </template>
  
  <script>
import AwsomeButton from './AuxiliaryComponents/AwsomeButton';

  export default {
    name: 'SlotyEleven',
    components: {
        AwsomeButton
    }
  }
  </script>

    <style lang="scss">
        .container {
            width: 100vw;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .image {
            width: 20px;
            height: 20px;
        }
        .square {
            width: 40px;
            height: 40px;
            background-color: red;
        }

    </style>