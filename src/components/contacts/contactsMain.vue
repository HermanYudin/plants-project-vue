<template>
  <div class="contacts-main-container">
    <ContactsImg />
    <ContactsTitle />
    <div class="select-wrapper">
      <ContactsCitySelect :cities="cities" @city-change="handleCityChange" />
      <ContactsCitySelectResult
        :index="selectedCity"
        :cities="cities"
        :phones="phones"
        :addresses="adresses"
        :isCardOpened="isCardOpened"
      />
    </div>
  </div>
</template>

<script>
import ContactsImg from "./ContactsImg";
import ContactsTitle from "./ContactsTitle";
import ContactsCitySelect from "./ContactsCitySelect";
import ContactsCitySelectResult from "./ContactsCitySelectResult";

export default {
  name: "contactsMain",
  components: {
    ContactsImg,
    ContactsTitle,
    ContactsCitySelect,
    ContactsCitySelectResult,
  },
  data() {
    return {
      cities: [
        "Canandaigua, NY",
        "New York City",
        "Yonkers, NY",
        "Sherrill, NY",
      ],
      phones: [
        "+1 585 393 0001",
        "+1 212 456 0002",
        "+1 914 678 0003",
        "+1 315 908 0004",
      ],
      adresses: [
        "151 Charlotte Street",
        "9 East 91st Street",
        "511 Warburton Ave",
        "14 WEST Noyes BLVD",
      ],
      selectedCity: 0,
      isOpened: false,
      isCardOpened: false,
    };
  },
  methods: {
    handleCityChange(index) {
      this.selectedCity = index;
      this.isCardOpened = true;
    },
  },
};
</script>

<style scoped>
.contacts-main-container {
  min-width: 1440px;
  width: 100%;
  background-color: #edf2ec;
  display: flex;
  justify-content: space-between;
}
.select-wrapper {
  align-items: center;
  display: flex;
  justify-content: flex-start;
  flex-direction: column;
  max-width: 450px;
  margin-right: 111px;
}
</style>
