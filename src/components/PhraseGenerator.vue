<script setup>
import { onMounted, ref } from 'vue'

const adjectives = [
  "Amazing",
  "Awesome",
  "Adventurous",
  "Ambitious",
  "Adorable",
  "Artistic",
  "Agile",
  "Acrobatic",
  "Astonishing",
  "Authentic",
  "Awkward",
  "Ancient",
  "Brave",
  "Beautiful",
  "Bright",
  "Busy",
  "Big",
  "Bold",
  "Blue",
  "Basic",
  "Blissful",
  "Bouncy",
  "Bashful",
  "Creative",
  "Confident",
  "Cheerful",
  "Calm",
  "Cute",
  "Clever",
  "Curious",
  "Charming",
  "Courageous",
  "Cool",
  "Considerate",
  "Caring",
  "Crazy",
  "Classic",
  "Delightful",
  "Dreamy",
  "Daring",
  "Decent",
  "Defiant",
  "Dedicated",
  "Dramatic",
  "Dizzy",
  "Demanding",
  "Diligent",
  "Dazzling",
  "Elegant",
  "Enthusiastic",
  "Eager",
  "Efficient",
  "Empathetic",
  "Entertaining",
  "Expressive",
  "Elderly",
  "Fantastic",
  "Fabulous",
  "Friendly",
  "Funny",
  "Fearless",
  "Fluffy",
  "Fierce",
  "Frugal",
  "Fast",
  "Famous",
  "Gorgeous",
  "Gentle",
  "Generous",
  "Gracious",
  "Glorious",
  "Graceful",
  "Groovy",
  "Grumpy",
  "Gigantic",
  "Happy",
  "Humble",
  "Honest",
  "Healthy",
  "Heavy",
  "Helpful",
  "Hilarious",
  "Hardworking",
  "Hungry",
  "Interesting",
  "Intelligent",
  "Inspiring",
  "Imaginative",
  "Inquisitive",
  "Industrious",
  "Idealistic",
  "Icy",
  "Joyful",
  "Jolly",
  "Jaunty",
  "Jumpy",
  "Judgmental",
  "Jittery",
  "Jubilant",
  "Kind",
  "Knowledgeable",
  "Keen",
  "Kooky",
  "Loud",
  "Lively",
  "Lazy",
  "Loyal",
  "Lucky",
  "Mysterious",
  "Moody",
  "Mindful",
  "Mischievous",
  "Modest",
  "Magical",
  "Nervous",
  "Noble",
  "Nonchalant",
  "Noisy",
  "Needy",
  "Optimistic",
  "Observant",
  "Obedient",
  "Offensive",
  "Patient",
  "Positive",
  "Powerful",
  "Popular",
  "Polite",
  "Peaceful",
  "Playful",
  "Pleasant",
  "Practical",
  "Proud",
  "Puzzled",
  "Persistent",
  "Passionate",
  "Quaint",
  "Quick",
  "Quiet",
  "Quirky",
  "Reliable",
  "Responsible",
  "Rich",
  "Rude",
  "Respectful",
  "Rational",
  "Rustic",
  "Reckless",
  "Rambunctious",
  "Strong",
  "Smart",
  "Serious",
  "Sad",
  "Simple",
  "Sincere",
  "Sweet",
  "Shy",
  "Successful",
  "Surprised",
  "Tall",
  "Talkative",
  "Thoughtful",
  "Thrifty",
  "Trustworthy",
  "Tenacious",
  "Tiny",
  "Tired",
  "Unique",
  "Unusual",
  "Useless",
  "Witty",
  "Wise",
  "Wicked",
  "Wary",
  "Wholesome",
  "Young",
  "Zealous"
]

const animals = [
  "Alligator",
  "Alpaca",
  "Antelope",
  "Ape",
  "Armadillo",
  "Badger",
  "Bear",
  "Beaver",
  "Bee",
  "Bird",
  "Bison",
  "Buffalo",
  "Boar",
  "Butterfly",
  "Camel",
  "Cat",
  "Cheetah",
  "Chicken",
  "Clam",
  "Coyote",
  "Crane",
  "Crow",
  "Deer",
  "Dinosaur",
  "Dog",
  "Dolphin",
  "Donkey",
  "Dove",
  "Duck",
  "Eagle",
  "Echidna",
  "Elephant",
  "Elk",
  "Falcon",
  "Ferret",
  "Fish",
  "Finch",
  "Fox",
  "Frog",
  "Gerbil",
  "Giraffe",
  "Goat",
  "Goose",
  "Gorilla",
  "Grasshopper",
  "Gull",
  "Hamster",
  "Hare",
  "Hawk",
  "Hedgehog",
  "Heron",
  "Hippopotamus",
  "Hornet",
  "Horse",
  "Hummingbird",
  "Hyena",
  "Jellyfish",
  "Kangaroo",
  "Koala",
  "Lark",
  "Leopard",
  "Lion",
  "Llama",
  "Mallard",
  "Mole",
  "Monkey",
  "Moose",
  "Mule",
  "Opossum",
  "Orca",
  "Ostrich",
  "Otter",
  "Owl",
  "Ox",
  "Oyster",
  "Panda",
  "Parrot",
  "Penguin",
  "Pheasant",
  "Pig",
  "Pigeon",
  "Platypus",
  "Porpoise",
  "Quail",
  "Rabbit",
  "Raccoon",
  "Raven",
  "Rhino",
  "Seal",
  "Shark",
  "Sheep",
  "Skunk",
  "Squirrel",
  "Swallow",
  "Swan",
  "Tiger",
  "Toad",
  "Turkey",
  "Turtle",
  "Walrus",
  "Wasp",
  "Weasel",
  "Whale",
  "Wolf",
  "Wombat",
  "Woodpecker",
  "Yak",
  "Zebra"
]

const chosenAdjective = ref('adjective')
const chosenAnimal = ref('animal')
const chosenSeparator = ref('')

onMounted(() => getPhrase())

function getPhrase() {
  chosenAdjective.value = adjectives[getRandomIndex(adjectives.length)].toLowerCase()
  chosenAnimal.value = animals[getRandomIndex(animals.length)].toLowerCase()

}
function getRandomIndex(listLength) {
  return Math.floor(Math.random() * (listLength - 1))
}

</script>

<template>
  <div class="phraseGenerator__container">
    <div class="phraseGenerator__content">
      <div class="phraseGenerator__phrase">
        {{ chosenAdjective }}{{ chosenSeparator }}{{ chosenAnimal }}
      </div>
      <div class="phraseGenerator__separatorOptions">
        <span>
          <input type="radio" id="radioButton__space" name="separator" value=" " v-model="chosenSeparator" />
          <label for="radioButton__space">Space</label>
        </span>
        <span>

          <input type="radio" id="radioButton__period" name="separator" value="." v-model="chosenSeparator" />
          <label for="radioButton__period">Period</label>
        </span>
        <span>
          <input type="radio" id="radioButton__hyphen" name="separator" value="-" v-model="chosenSeparator" />
          <label for="radioButton__hyphen">Hyphen</label>
        </span>
        <span>
          <input type="radio" id="radioButton__none" name="separator" value="" v-model="chosenSeparator" />
          <label for="radioButton__none">None</label>
        </span>
      </div>
    </div>
    <button @click="getPhrase">Generate phrase</button>
  </div>
</template>

<style scoped>
.phraseGenerator__container {
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 20px;
  align-items: center;
  justify-content: center;
}

.phraseGenerator__content {
  width: 100%;

  .phraseGenerator__phrase {
    width: 100%;
    font-size: 3rem;

    color: rgb(219, 219, 219);
    border-bottom: 8px solid rgb(219, 219, 219);

    word-wrap: break-word;
  }

  .phraseGenerator__separatorOptions {
    display: flex;
    gap: 24px;

    label {
      color: white;
    }

    input {
      margin-right: 8px;
    }
  }
}

button {
  width: 200px;
  aspect-ratio: 1 / 1;
  padding: 8px;

  font-size: 2rem;

  background-color: yellow;
  border: none;

  border-radius: 50%;
  cursor: pointer;
}

@media only screen and (min-width: 768px) {
  .phraseGenerator__container {
    width: 50%;
  }
}
</style>
