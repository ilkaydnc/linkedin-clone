<script>
import SearchIcon from './icons/SearchIcon.vue'
export default {
  components: { SearchIcon },
  name: 'Search',
  data() {
    return {
      value: '',
      toggleDropdown: false,
    }
  },
  methods: {
    focusInput() {
      this.$refs.search.focus()
    },
    onInputFocus() {
      this.toggleDropdown = true
    },
    onInputBlur() {
      this.toggleDropdown = false
    },
  },
}
</script>

<template>
  <div class="search">
    <div class="search-container" @click="focusInput">
      <search-icon class="search-icon" />
      <input
        ref="search"
        v-model="value"
        class="search-input"
        type="text"
        @focus="onInputFocus"
        @blur="onInputBlur"
      />
    </div>
    <div :class="['search-dropdown', toggleDropdown && 'open']">
      <ul>
        <li>asdas</li>
        <li>asdas</li>
        <li>asdas</li>
        <li>asdas</li>
        <li>asdas</li>
        <li>asdas</li>
      </ul>
    </div>
  </div>
</template>

<style>
.search {
  position: relative;
  flex-grow: 1;
}

.search-icon {
  font-size: 24px;
  margin-right: 12px;
}

.search-container {
  display: flex;
  align-items: center;
  flex-grow: 1;
  padding: 8px;
  background: rgba(255, 255, 255, 0.2);
  color: #ffffff;
  border-radius: 4px;
  transition: 0.2s;
}

.search-container:hover {
  background: rgba(255, 255, 255, 0.3);
}

.search-container:focus-within {
  background: rgba(255, 255, 255, 0.1);
  box-shadow: inset 0 0 0 1px rgba(255, 255, 255, 0.6);
}

.search-input {
  outline: 0;
  border: 0;
  padding: 0;
  width: 100%;
  background-color: transparent;
  font-size: 14px;
  line-height: 20px;
  color: inherit;
}

.search-dropdown {
  position: absolute;
  opacity: 0;
  pointer-events: none;
  top: 48px;
  left: 0;
  right: 0;
  background-color: rgb(255, 255, 255);
  border-radius: 4px;
  box-shadow: 0 2px 10px 3px rgba(0, 0, 0, 0.2);
  transform: translateY(20px);
  overflow: hidden;
  transition: 0.2s ease-out;
}

.search-dropdown.open {
  opacity: 1;
  pointer-events: all;
  transform: translateY(0);
}

.search-dropdown > ul {
  list-style: none;
  padding: 0;
}

.search-dropdown > ul > li {
  padding: 16px;
  cursor: pointer;
  transition: 0.2s;
}

.search-dropdown > ul > li:hover {
  background-color: rgba(0, 0, 0, 0.05);
}

.search-dropdown > ul > li:active {
  background-color: rgba(0, 0, 0, 0.1);
}

.search-dropdown > ul > li + li {
  margin-top: 4px;
}
</style>