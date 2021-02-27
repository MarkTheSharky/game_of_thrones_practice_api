<!-- Rewatch video on contect -->

getGameOfThronesCharacters() {
    fetch('https://anapioficeandfire.com/api/characters')
    .then((res) => res.json())                                  <!-- What is res meaning here? -->
    .then((data) => this.characters = data)                     <!-- What is data relationship here? -->

mounted() {
    this.getBeers();                                            <!-- Double check what this is for -->
  }

AllBooks.vue
    Want to input a link "http://covers.openlibrary.org/b/isbn/{{978-0345537263}}-M.jpg" so the moustached part is dynamic and changes.
    alt name of image needs to change to be for each book