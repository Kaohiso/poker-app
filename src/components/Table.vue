<template>
  <div class="table">
    <div class="pot">145 500</div>
  </div>
</template>

<script>
export default {
  name: "Table",
};
</script>

<style>
/* Style pour la table */
.table {
  width: 800px; /* Largeur de la table */
  height: 400px; /* Hauteur de la table */
  background-color: #0a6847; /* Fond vert */
  border: 20px solid #8b4513; /* Bordure marron */
  border-radius: 300px; /* Table ovale */
  position: relative; /* Pour positionner les éléments */
  margin: auto; /* Centrer la table */
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5); /* Effet d'ombre */
}

/* Style pour le pot central */
.pot {
  position: absolute;
  top: 10%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: #0f5132;
  color: white;
  padding: 10px 20px;
  border-radius: 20px;
  font-weight: bold;
  font-size: 20px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
}
</style>
