# **islamic_app(الموعظه)**
It's an app for listening to the Holy Koran and reading talk and watching some of the famous speeches and words of Muslim scholars.

## **Description & motivation:**
create a full website with html css and js  wthout any framework or library.


[**Demos website** ](https://mohamedsaberabdelhakim.github.io/islamic_app/)


# Version 1.0.0

# Installation instructions

## 1-Fonts
```
<!-- Fonts Links Are in Description -->
    <!-- thuluth decorated Font-->
    <link
      rel="stylesheet"
      type="text/css"
      href="https://www.fontstatic.com/f=thuluth-decorated"
    />
    <!-- Cairo Font-->
    <link
      rel="stylesheet"
      type="text/css"
      href="https://www.fontstatic.com/f=cairo-bold"
    />
    <!-- Font AWesome -->
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.2/css/all.min.css"
    />
```
## HadithChanger
```
function HadithChanger() {
  fetch("https://api.hadith.sutanlab.id/books/muslim?range=1-300")
    .then((response) => response.json())
    .then((data) => {
      let Hadiths = data.data.hadiths;
      changeHadith();
      next.addEventListener("click", () => {
        hadithIndex == 299 ? (hadithIndex = 0) : hadithIndex++;
        changeHadith();
      });
      prev.addEventListener("click", () => {
        hadithIndex == 0 ? (hadithIndex = 299) : hadithIndex--;
        changeHadith();
      });
      function changeHadith() {
        hadithContainer.innerText = Hadiths[hadithIndex].arab;
        number.innerText = `300  -  ${hadithIndex + 1}`;
      }
    });
}
```
## getSurahs
```
function getSurahs() {
  //fetch Surahs meta data {Name of SuraHS}
  fetch("http://api.alquran.cloud/v1/meta")
    .then((response) => response.json())
    .then((data) => {
      let surahs = data.data.surahs.references;
      let numberOfSurahs = 114;
      SurahsContainer.innerHTML = "";
      for (let i = 0; i < numberOfSurahs; i++) {
        SurahsContainer.innerHTML += `
                    <div class="surah">
                        <p>${surahs[i].name}</p>
                        <p>${surahs[i].englishName}</p>
                    </div>
                `;
      }


```
