<!--suppress ALL -->
<template>
  <button type="button"><slot/></button>
</template>

<style lang="scss" scoped>
button {
  font-family: $ff-mono;
  padding: 1rem 2rem;
  border: 1px solid $primary-color;
  border-radius: 5px;
  cursor: pointer;
  background: none;
  color: $primary-color;
  &:hover {
    box-shadow: 3px 3px 0 $primary-color;
    transition: all 0.5s ease-in-out;
  }
  &:focus {
    outline: none;
    box-shadow: 3px 3px 0 $primary-color;
    transition: all 0.5s ease-in-out;
  }
  
  &:active {
    box-shadow: none;
    transform: translateY(3px);
    background: $primary-color;
    color: white;
    border: 1px solid $primary-color;
    transition: all 0.5s ease-in-out;
    cursor: pointer;
    outline: none;
  }
  &:disabled {
    cursor: not-allowed;
    transition:none;
    transform: none;
    box-shadow: none;
    background: $button-disabled-color;
    color: $primary-color;
  }
  a {
    text-decoration: none;
  }
}
</style>
