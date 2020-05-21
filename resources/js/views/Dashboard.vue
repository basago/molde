<template>
<div>
  <div id="wrapper">
    <Menu/>
    <div id="content-wrapper" class="d-flex flex-column">
      <div id="content">
        <Cabecera/>
        <Cuerpo/>
      </div>
      <Pie/>
    </div>
  </div>
  <a class="scroll-to-top rounded" href="#page-top">
    <i class="fas fa-angle-up"></i>
  </a>
</div>
</template>

<script>

import Menu from "./menu/Menu";
import Cabecera from "./cabecera/Cabecera";
import Cuerpo from "./cuerpo/Cuerpo";
import Pie from "./pie/Pie";

export default {
  name: 'Dashboard',
  components: {
    Menu, 
    Cabecera, 
    Cuerpo,
    Pie
  }
}

</script>