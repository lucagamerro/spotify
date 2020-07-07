<template>
<div id="app">
  <title>Spotify</title>
  <h4 class="buon"><bold>Buon {{ dateBuilder() }}, Luca</bold></h4>
<div class="grid-container">
  <div class="box" @click="cambia('Il podcast di Alessandro Barbero')">
    <div class="immagine">
      <img src="https://d1bm3dmew779uf.cloudfront.net/rss/show/4255213/57d97b8a56f8cf781c7b9ebdc3ed3d7b.png" width="125" height="125">
    
    </div>
      <h6> <a href=""> Alessandro Barbero </a></h6>
  </div>
  <div class="box-2" @click="cambia('Freez tag - Terrace Martin')">
    <div class="immagine">
      <img src="https://www.testietraduzioni.it/wp-content/uploads/2020/03/freeze-tag-feat-kamasi-washington-e-phoelix.jpg" width="125" height="125">
    </div>
      <h6> <a href=""> Freez tag <br> Terrace Martin</a></h6>
  </div>
  <div class="box" @click="cambia('Ottima scusa - Willie Peyote', 'https://images.genius.com/ed682b7570104b345adc2f4af1fbdd1b.960x960x1.jpg')">
    <div class="immagine">
      <img src="https://images.genius.com/ed682b7570104b345adc2f4af1fbdd1b.960x960x1.jpg" width="125" height="125">
    </div>
      <h6> <a href=""> Sindrome di Tourette </a></h6>
  </div>

  <br>

  <div class="box" @click="cambia('Due ali - Frah Quintale')">
    <div class="immagine">
      <img src="https://m.media-amazon.com/images/I/71uc-IWYUFL._SS500_.jpg" width="125" height="125">
    </div>
      <h6> <a href=""> Banzai (lato blu) Frah Quintale </a></h6>
  </div>
  <div class="box" @click="cambia('Il podcast di Pagella Politica')">
    <div class="immagine">
      <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAOEAAADhCAMAAAAJbSJIAAAAolBMVEX////8/v1MUFNHoL5namxJTVA8QUROUlX09fRxdHZGSk6Eh4j3+/o5mrpCnr0wmLlIpsVQo7/h7fDu9fV8tsttrsZElbG21N6Gu85ap8F/gYOaxdXH3uVCRUg9PkC92OGmzNksZ3saGRteYWQ6ZncvKCc6YG44WWcxLi42UVs1SlM2NjcyQEYxNzzU5epDkaxBhp8+epAoISBzlKCHrLpaWFju+4n9AAAEgElEQVR4nO3d61baUBQE4JNEwFpyEBCFCmpbqSjire37v1oD9ZLbmSTWJHuvzvwOMR+EMPska2kMwzAMwzAMwzAMwzAMwzAMwzCM6HgaQyGF8kMhhfJDIYXyQyGF8kMhhU0dZh9lfxvnS1UIzcUgdObw67fNovvddXQqhOZ0EDhzeLns9PzOnmahmYYA+GMVAXULzRECXu2AuoUTBLxe+bvoFZr+zALgzdpXLjTjIQAGN+uecqEZBwh4+wrUKjQj8BUMgs3ZK1Cp0NwNwCd4HAfqFJo5+p0/XsWBKoXmBAHvV904UKMwqqIIuFwkgAqFuIo+pIH6hLiKPiwPUkB1QlxFH7NAdcIJamqPy04GqEtYUEUvnxadA9VCXEXDn3tfomgWmhFqooP53yNR/D2MqqhbaAd3f49BsdDclQEqFppz8Dtvw9HLEQgQGm/0jvcDVtHAvu2ydaHpXwSvZ1QFIKqiNhi/7bBdoTGjaRh9m8KqnyKsona4H9tdm0Jj5pPnudWOKxFhU7PDfnxn7Qm3p+frxdAG/SpCtGgYzlJ/px1hdHqeDuIXezvDL4gHNrVwkv5TbQhjp+cbcVLyPDV92NSO0rtpQWi8k2HOb3VYjogXDbPA5oW70zP/6KYliHjRcJCzi6aF5pd71S88LSRGTQ0B83bQuPD3w6H7CC+KLlBo0dDx8saFe0+IeIKvUKiKul7cuPBTd3kPiHN0iUJNLRic57+0eWFnAYnuigqbmvu9aUHYW6zuwZG6KqqZQqDznWlB6EfEY+eh2jC/osIqGoTgo29BiImOFo6qqEWzSSvCiLgGn+Iw08KNh6qohZNJO8KIuAFrLOkWjhcNE/OuGKHfO9uAY05WVDO2CJgcB8UIMTFRoHEVtTMMbE8YEW8B8a1Cw0XDzLwrSVhAfCnRuIpm5l1Rwi2xsIXjRcOccVCUMCLeuI9+1zNxFS03UbYp3BJhCy+oomWALQsLiCN0/zp/3hUn9HvrazcRXUSLx2Uhwoh4hRxuIB6WBQl9/wz+HriAjnlXpLCDf/LygWgtQKAQr79kY6vcrBIhLFhiygDBvCtVWFBdUql2L06IsAqx6p04IcKCfhbz4XlXsLAkMXl/V5ewYD30GVg074oWRkT4MHpQahwULcRPir4TKEtYQCwz70oXwpXtUvOueCEglhwHxQs941i+fy9QntBBLDvvahDmPrldet7VIczehik/7yoRpokV5l0twsRzXZXmXS1CL/ZkF7z9qVcYI9p/A4oVmvHLZ1hxHFQjfCZWnncVCXd3fovu7+oWRsRwVunJYXVCz4w+ACha+DGhMLEthRR6FNYRChPbUkihR2EdoTCxLYUUehTWEQoT21JIoUdhHaEwsS2FFHoU1hEKE9tSSKFHYR2hMLEthRR6FNYRChPbUvheYb0RIPxcb9J/r3mhf1BvBAibDoUUUkghhRRSSCGFFFJIIYUChHvd9lPv/wPelxDXwX2IUHQopFB+KKRQfiikUH4opFB+KPzPhAzDMAzDMAzDMAzDMAzDMAzDMI3nD5mb478J9v6iAAAAAElFTkSuQmCC" width="125" height="125">
    </div>
      <h6> <a href=""> Il podcast di Pagella Politica </a></h6>
  </div>
  <div class="box" @click="cambia('Sorriso - Calcutta')">
    <div class="immagine">
      <img src="https://images-eu.ssl-images-amazon.com/images/I/8172TTwldgL._AC_UL600_SR600,600_.jpg" width="125" height="125">
    </div>
      <h6> <a href=""> Sorriso <br> Milano dateo </a></h6>
  </div><br>
  <div class="canzone">
    <h4 class="freccia"><a href="#canzone" @click="random()">{{ canzone }}</a></h4>
  </div>
<br><br>
</div>
  <div class="riproduzione" id="canzone"> <br><br>
    <p class="immagine">
    <img  class="immagine" src="https://www.nuovecanzoni.com/wp-content/uploads/2020/04/Buio-di-giorno-Frah-Quintale.jpg" width="300" height="300" v-if="canzone == 'Buio di giorno - Frah Quintale'">
    <img  class="immagine" src="https://d1bm3dmew779uf.cloudfront.net/rss/show/4255213/57d97b8a56f8cf781c7b9ebdc3ed3d7b.png" width="300" height="300" v-if="canzone == 'Il podcast di Alessandro Barbero'">
    <img  class="immagine" src="https://www.testietraduzioni.it/wp-content/uploads/2020/03/freeze-tag-feat-kamasi-washington-e-phoelix.jpg" width="300" height="300" v-if="canzone == 'Freez tag - Terrace Martin'">
    <img  class="immagine" src="https://images.genius.com/ed682b7570104b345adc2f4af1fbdd1b.960x960x1.jpg" width="300" height="300" v-if="canzone == 'Ottima scusa - Willie Peyote'">
    <img  class="immagine" src="https://m.media-amazon.com/images/I/71uc-IWYUFL._SS500_.jpg" width="300" height="300" v-if="canzone == 'Due ali - Frah Quintale'">
    <img  class="immagine" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAOEAAADhCAMAAAAJbSJIAAAAolBMVEX////8/v1MUFNHoL5namxJTVA8QUROUlX09fRxdHZGSk6Eh4j3+/o5mrpCnr0wmLlIpsVQo7/h7fDu9fV8tsttrsZElbG21N6Gu85ap8F/gYOaxdXH3uVCRUg9PkC92OGmzNksZ3saGRteYWQ6ZncvKCc6YG44WWcxLi42UVs1SlM2NjcyQEYxNzzU5epDkaxBhp8+epAoISBzlKCHrLpaWFju+4n9AAAEgElEQVR4nO3d61baUBQE4JNEwFpyEBCFCmpbqSjire37v1oD9ZLbmSTWJHuvzvwOMR+EMPska2kMwzAMwzAMwzAMwzAMwzAMwzCM6HgaQyGF8kMhhfJDIYXyQyGF8kMhhU0dZh9lfxvnS1UIzcUgdObw67fNovvddXQqhOZ0EDhzeLns9PzOnmahmYYA+GMVAXULzRECXu2AuoUTBLxe+bvoFZr+zALgzdpXLjTjIQAGN+uecqEZBwh4+wrUKjQj8BUMgs3ZK1Cp0NwNwCd4HAfqFJo5+p0/XsWBKoXmBAHvV904UKMwqqIIuFwkgAqFuIo+pIH6hLiKPiwPUkB1QlxFH7NAdcIJamqPy04GqEtYUEUvnxadA9VCXEXDn3tfomgWmhFqooP53yNR/D2MqqhbaAd3f49BsdDclQEqFppz8Dtvw9HLEQgQGm/0jvcDVtHAvu2ydaHpXwSvZ1QFIKqiNhi/7bBdoTGjaRh9m8KqnyKsona4H9tdm0Jj5pPnudWOKxFhU7PDfnxn7Qm3p+frxdAG/SpCtGgYzlJ/px1hdHqeDuIXezvDL4gHNrVwkv5TbQhjp+cbcVLyPDV92NSO0rtpQWi8k2HOb3VYjogXDbPA5oW70zP/6KYliHjRcJCzi6aF5pd71S88LSRGTQ0B83bQuPD3w6H7CC+KLlBo0dDx8saFe0+IeIKvUKiKul7cuPBTd3kPiHN0iUJNLRic57+0eWFnAYnuigqbmvu9aUHYW6zuwZG6KqqZQqDznWlB6EfEY+eh2jC/osIqGoTgo29BiImOFo6qqEWzSSvCiLgGn+Iw08KNh6qohZNJO8KIuAFrLOkWjhcNE/OuGKHfO9uAY05WVDO2CJgcB8UIMTFRoHEVtTMMbE8YEW8B8a1Cw0XDzLwrSVhAfCnRuIpm5l1Rwi2xsIXjRcOccVCUMCLeuI9+1zNxFS03UbYp3BJhCy+oomWALQsLiCN0/zp/3hUn9HvrazcRXUSLx2Uhwoh4hRxuIB6WBQl9/wz+HriAjnlXpLCDf/LygWgtQKAQr79kY6vcrBIhLFhiygDBvCtVWFBdUql2L06IsAqx6p04IcKCfhbz4XlXsLAkMXl/V5ewYD30GVg074oWRkT4MHpQahwULcRPir4TKEtYQCwz70oXwpXtUvOueCEglhwHxQs941i+fy9QntBBLDvvahDmPrldet7VIczehik/7yoRpokV5l0twsRzXZXmXS1CL/ZkF7z9qVcYI9p/A4oVmvHLZ1hxHFQjfCZWnncVCXd3fovu7+oWRsRwVunJYXVCz4w+ACha+DGhMLEthRR6FNYRChPbUkihR2EdoTCxLYUUehTWEQoT21JIoUdhHaEwsS2FFHoU1hEKE9tSSKFHYR2hMLEthRR6FNYRChPbUvheYb0RIPxcb9J/r3mhf1BvBAibDoUUUkghhRRSSCGFFFJIIYUChHvd9lPv/wPelxDXwX2IUHQopFB+KKRQfiikUH4opFB+KPzPhAzDMAzDMAzDMAzDMAzDMAzDMI3nD5mb478J9v6iAAAAAElFTkSuQmCC" width="300" height="300" v-if="canzone == 'Il podcast di Pagella Politica'">
    <img  class="immagine" src="https://images-eu.ssl-images-amazon.com/images/I/8172TTwldgL._AC_UL600_SR600,600_.jpg" width="300" height="300" v-if="canzone == 'Sorriso - Calcutta'">
    </p>
    <h4 class="freccia">{{ canzone }} <a class="button" href="#top">su</a>  </h4>
    <br>
    <div class="playpause" >
      <input type="checkbox" value="None" id="playpause" name="check" disabled="disabled" />
      <label for="playpause" tabindex=1></label>
    </div>
    <i class="sin">0:00</i><i class="des">3:20</i>
    <div class="bar">
      <div v-if="ran == 1" class="zero"></div>
      <div v-if="ran == 2" class="quindici"></div>
      <div v-if="ran == 3" class="trenta"></div>
      <div v-if="ran == 4" class="quarantacinque"></div>
      <div v-if="ran == 5" class="sesanta"></div>
      <div v-if="ran == 6" class="settantacinque"></div>
      <div v-if="ran == 7" class="novanta"></div>
      <div v-if="ran == 8" class="cento"></div>
    </div>
  </div>
</div>
</template>


<script src="canzoni.js"></script>
<script>
export default {
  name: 'App',
  data() {
    return {
      canzone: 'Buio di giorno - Frah Quintale',
      ran: 0
    };
  },
  methods: {
    cambia (p) {
      this.canzone = p;
    },
    dateBuilder () {
      let d = new Date();
      let days = ["Domenica", "Lunedì", "Martedì", "Mercoledì", "Giovedì", "Venerdì", "Sabato"];
      let day = days[d.getDay()];
      return `${day}`;
    },
    random() {
      this.ran = Math.floor(Math.random()*(7-1+1)+1);
    }
  }
}
</script>

<style>

html {
  scroll-behavior: smooth;
	/** background-color: #373737; **/
  background: #000;
	color: #F1F1F1;
}

#app {
  font-family: Helvetica, Arial, sans-serif;
  color: #F1F1F1;
}

.buon {
  margin-top: 30px;
  margin-right: 10px;
}

.box {
  margin-left: 15px; 
}
.box img:hover {
  opacity: 0.3;
}

.bar {
  background: #F1F1F1;
  margin-left: 10px;

  height: 10px;
  width: 455px;
  border: 10px;
}

.canzone {
  grid-area: canzone; 
  border-radius: 20px 20px 0px 0px;
  margin-top: 50px;
  margin-left: none;
  height: 150px;
  width: 475px;
  border: 10px;
  background: #373737;
}

.canzone h4 {
  text-align: center;
  margin-top: 25px;
}

.box-2 h6 {
  margin-left: 13px;
}
.box-2 img:hover {
  opacity: 0.3;
}


.grid-container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  grid-template-rows: 1fr 1fr 1fr;
  gap: 1px 1px;
  grid-template-areas: ". box-2 box-3 ." ". . . ." "canzone canzone canzone canzone";
}
.box-2 { grid-area: box-2; }

.riproduzione {
  grid-area: canzone; 
  border-radius: 30px;
  margin-top: 500px;
  margin-left: none;
  height: 600px;
  width: 475px;
  background: rgb(28,212,100);
  background: linear-gradient(0deg, rgba(28,212,100,1) 0%, rgba(0,0,0,0.9444152661064426) 80%);
}

.riproduzione .immagine {
  text-align: center;
}

nav .link.nome {
  font-size: 30px;
}

nav .link.destra {
  text-align: right;
  margin-left: 740px;
}

nav hr {
  margin-top: 2.5rem;
  margin-bottom: 3.5rem;
  border-width: 0;
  border-top: 1px solid #F1F1F1; 
}

nav .link {
    display: inline-block;
    height: 38px;
    padding: 0 30px;
    color: #F1F1F1;
    text-align: center;
    font-size: 11px;
    font-weight: 600;
    line-height: 38px;
    letter-spacing: .1rem;
    text-transform: uppercase;
    text-decoration: none;
    white-space: nowrap;
    background-color: transparent;
    border: none;
    cursor: pointer;
    box-sizing: border-box; 
    text-align: center;
}


.download {
  text-align: center;
  align-items: center;
}

a {
  color: #F1F1F1;
  text-decoration: none;
}
a:hover {
  text-decoration: underline;
}

.sin {
  margin-top: none;
  margin-left: 10px;
}
.des {
  margin-top: none;
  margin-left: 395px;
}

.zero {
  background: #000;
  margin-left: 1%;
  height: 10px;
  width: 454px;
}
.quindici {
  background: #000;
  margin-left: 15%;
  height: 10px;
  width: 388px;
}
.trenta {
  background: #000;
  margin-left: 30%;
  height: 10px;
  width: 318px;
}
.quarantacinque {
  background: #000;
  margin-left: 45%;
  height: 10px;
  width: 250px;
}
.sesanta {
  background: #000;
  margin-left: 60%;
  height: 10px;
  width: 182px;
}
.settantacinque {
  background: #000;
  margin-left: 75%;
  height: 10px;
  width: 114px;
}
.cento {
  background: #000;
  margin-left: 100%;
  height: 10px;
  width: 0px;
}

.freccia .button {
  margin-left: 56px;
}

.playpause label {
  display: block;
  box-sizing: border-box;
  width: 0;
  height: 65px;
  border-color: transparent transparent transparent #FFF;
  transition: 100ms all ease;
  cursor:inherit;
  border-style: double;
  border-width: 0px 0 0px 60px;
  margin-left: 210px;
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
.playpause input[type="checkbox"] {
  position: absolute;
  left: -9999px;
}
.playpause input[type="checkbox"]:hover + label {
  border-style: solid;
  border-width: 37px 0 37px 60px;
}


/*
* Skeleton V2.0.4
* Copyright 2014, Dave Gamache
* www.getskeleton.com
* Free to use under the MIT license.
* http://www.opensource.org/licenses/mit-license.php
* 12/29/2014
*/


/* Table of contents
––––––––––––––––––––––––––––––––––––––––––––––––––
- Grid
- Base Styles
- Typography
- Links
- Buttons
- Forms
- Lists
- Code
- Tables
- Spacing
- Utilities
- Clearing
- Media Queries
*/


/* Grid
–––––––––––––––––––––––––––––––––––––––––––––––––– */
.container {
  position: relative;
  width: 100%;
  max-width: 960px;
  margin: 0 auto;
  padding: 0 20px;
  box-sizing: border-box; }
.column,
.columns {
  width: 100%;
  float: left;
  box-sizing: border-box; }

/* For devices larger than 400px */
@media (min-width: 400px) {
  .container {
    width: 85%;
    padding: 0; }
}

/* For devices larger than 550px */
@media (min-width: 550px) {
  .container {
    width: 80%; }
  .column,
  .columns {
    margin-left: 4%; }
  .column:first-child,
  .columns:first-child {
    margin-left: 0; }

  .one.column,
  .one.columns                    { width: 4.66666666667%; }
  .two.columns                    { width: 13.3333333333%; }
  .three.columns                  { width: 22%;            }
  .four.columns                   { width: 30.6666666667%; }
  .five.columns                   { width: 39.3333333333%; }
  .six.columns                    { width: 48%;            }
  .seven.columns                  { width: 56.6666666667%; }
  .eight.columns                  { width: 65.3333333333%; }
  .nine.columns                   { width: 74.0%;          }
  .ten.columns                    { width: 82.6666666667%; }
  .eleven.columns                 { width: 91.3333333333%; }
  .twelve.columns                 { width: 100%; margin-left: 0; }

  .one-third.column               { width: 30.6666666667%; }
  .two-thirds.column              { width: 65.3333333333%; }

  .one-half.column                { width: 48%; }

  /* Offsets */
  .offset-by-one.column,
  .offset-by-one.columns          { margin-left: 8.66666666667%; }
  .offset-by-two.column,
  .offset-by-two.columns          { margin-left: 17.3333333333%; }
  .offset-by-three.column,
  .offset-by-three.columns        { margin-left: 26%;            }
  .offset-by-four.column,
  .offset-by-four.columns         { margin-left: 34.6666666667%; }
  .offset-by-five.column,
  .offset-by-five.columns         { margin-left: 43.3333333333%; }
  .offset-by-six.column,
  .offset-by-six.columns          { margin-left: 52%;            }
  .offset-by-seven.column,
  .offset-by-seven.columns        { margin-left: 60.6666666667%; }
  .offset-by-eight.column,
  .offset-by-eight.columns        { margin-left: 69.3333333333%; }
  .offset-by-nine.column,
  .offset-by-nine.columns         { margin-left: 78.0%;          }
  .offset-by-ten.column,
  .offset-by-ten.columns          { margin-left: 86.6666666667%; }
  .offset-by-eleven.column,
  .offset-by-eleven.columns       { margin-left: 95.3333333333%; }

  .offset-by-one-third.column,
  .offset-by-one-third.columns    { margin-left: 34.6666666667%; }
  .offset-by-two-thirds.column,
  .offset-by-two-thirds.columns   { margin-left: 69.3333333333%; }

  .offset-by-one-half.column,
  .offset-by-one-half.columns     { margin-left: 52%; }

}


/* Base Styles
–––––––––––––––––––––––––––––––––––––––––––––––––– */
/* NOTE
html is set to 62.5% so that all the REM measurements throughout Skeleton
are based on 10px sizing. So basically 1.5rem = 15px :) */
html {
  font-size: 62.5%; }
body {
  font-size: 1.5em; /* currently ems cause chrome bug misinterpreting rems on body element */
  line-height: 1.6;
  font-weight: 400;
  font-family: "Raleway", "HelveticaNeue", "Helvetica Neue", Helvetica, Arial, sans-serif;
  color: #222; }


/* Typography
–––––––––––––––––––––––––––––––––––––––––––––––––– */
h1, h2, h3, h4, h5, h6 {
  margin-top: 0;
  margin-bottom: 2rem;
  font-weight: 300; }
h1 { font-size: 4.0rem; line-height: 1.2;  letter-spacing: -.1rem; text-align: center;}
h2 { font-size: 3.6rem; line-height: 1.25; letter-spacing: -.1rem; margin-left: 10px;}
h3 { font-size: 3.0rem; line-height: 1.3;  letter-spacing: -.1rem; margin-left: 10px;}
h4 { font-size: 2.4rem; line-height: 1.35; letter-spacing: -.08rem; margin-left: 10px;}
h5 { font-size: 1.8rem; line-height: 1.5;  letter-spacing: -.05rem; margin-left: 10px;}
h6 { font-size: 1.5rem; line-height: 1.6;  letter-spacing: 0; }

/* Larger than phablet */
@media (min-width: 550px) {
  h1 { font-size: 5.0rem; }
  h2 { font-size: 4.2rem; }
  h3 { font-size: 3.6rem; }
  h4 { font-size: 3.0rem; }
  h5 { font-size: 2.4rem; }
  h6 { font-size: 1.5rem; }
}

p {
  margin-top: 0; }


/* Links
–––––––––––––––––––––––––––––––––––––––––––––––––– */


/* Buttons
–––––––––––––––––––––––––––––––––––––––––––––––––– */
.button,
button,
input[type="submit"],
input[type="reset"],
input[type="button"] {
  display: inline-block;
  height: 38px;
  padding: 0 30px;
  color: #F1F1F1;
  text-align: center;
  font-size: 11px;
  font-weight: 600;
  line-height: 38px;
  letter-spacing: .1rem;
  text-transform: uppercase;
  text-decoration: none;
  white-space: nowrap;
  background-color: transparent;
  border-radius: 4px;
  border: 1px solid #bbb;
  cursor: pointer;
  box-sizing: border-box; }


/* Forms
–––––––––––––––––––––––––––––––––––––––––––––––––– */
input[type="email"],
input[type="number"],
input[type="search"],
input[type="text"],
input[type="tel"],
input[type="url"],
input[type="password"],
textarea,
select {
  height: 38px;
  padding: 6px 10px; /* The 6px vertically centers text on FF, ignored by Webkit */
  background-color: #fff;
  border: 1px solid #D1D1D1;
  border-radius: 4px;
  box-shadow: none;
  box-sizing: border-box; }
/* Removes awkward default styles on some inputs for iOS */
input[type="email"],
input[type="number"],
input[type="search"],
input[type="text"],
input[type="tel"],
input[type="url"],
input[type="password"],
textarea {
  -webkit-appearance: none;
     -moz-appearance: none;
          appearance: none; }
textarea {
  min-height: 65px;
  padding-top: 6px;
  padding-bottom: 6px; }
input[type="email"]:focus,
input[type="number"]:focus,
input[type="search"]:focus,
input[type="text"]:focus,
input[type="tel"]:focus,
input[type="url"]:focus,
input[type="password"]:focus,
textarea:focus,
select:focus {
  border: 1px solid #33C3F0;
  outline: 0; }
label,
legend {
  display: block;
  margin-bottom: .5rem;
  font-weight: 600; }
fieldset {
  padding: 0;
  border-width: 0; }
input[type="radio"] {
  display: inline; }
label > .label-body {
  display: inline-block;
  margin-left: .5rem;
  font-weight: normal; }


/* Lists
–––––––––––––––––––––––––––––––––––––––––––––––––– */
ul {
  list-style: circle inside; }
ol {
  list-style: decimal inside; }
ol, ul {
  padding-left: 0;
  margin-top: 0; }
ul ul,
ul ol,
ol ol,
ol ul {
  margin: 1.5rem 0 1.5rem 3rem;
  font-size: 90%; }
li {
  margin-bottom: 1rem; }


/* Code
–––––––––––––––––––––––––––––––––––––––––––––––––– */
code {
  padding: .2rem .5rem;
  margin: 0 .2rem;
  font-size: 90%;
  white-space: nowrap;
  background: #F1F1F1;
  border: 1px solid #E1E1E1;
  border-radius: 4px; }
pre > code {
  background: rgb(255,255,255);
  background: linear-gradient(90deg, rgba(255,255,255,1) 0%, rgba(255,255,255,1) 24%, rgba(1,193,171,1) 100%);
  display: block;
  padding: 1rem 1.5rem;
  white-space: pre;
  text-align: left;
  color: #222;
}


/* Tables
–––––––––––––––––––––––––––––––––––––––––––––––––– */
th,
td {
  padding: 12px 15px;
  text-align: left;
  border-bottom: 1px solid #E1E1E1; }
th:first-child,
td:first-child {
  padding-left: 0; }
th:last-child,
td:last-child {
  padding-right: 0; }


/* Spacing
–––––––––––––––––––––––––––––––––––––––––––––––––– */
button,
.button {
  margin-bottom: 1rem; }
input,
textarea,
select,
fieldset {
  margin-bottom: 1.5rem; }
pre,
blockquote,
dl,
figure,
table,
p,
ul,
ol,
form {
  margin-bottom: 2.5rem; }


/* Utilities
–––––––––––––––––––––––––––––––––––––––––––––––––– */
.u-full-width {
  width: 100%;
  box-sizing: border-box; }
.u-max-full-width {
  max-width: 100%;
  box-sizing: border-box; }
.u-pull-right {
  float: right; }
.u-pull-left {
  float: left; }


/* Misc
–––––––––––––––––––––––––––––––––––––––––––––––––– */
hr {
  color: black;
  margin-top: 3rem;
  margin-bottom: 3.5rem;
  border-width: 0;
  border-top: 1px solid #E1E1E1; }


/* Clearing
–––––––––––––––––––––––––––––––––––––––––––––––––– */

/* Self Clearing Goodness */
.container:after,
.row:after,
.u-cf {
  content: "";
  display: table;
  clear: both; }


/* Media Queries
–––––––––––––––––––––––––––––––––––––––––––––––––– */
/*
Note: The best way to structure the use of media queries is to create the queries
near the relevant code. For example, if you wanted to change the styles for buttons
on small devices, paste the mobile query code up in the buttons section and style it
there.
*/


/* Larger than mobile */
@media (min-width: 400px) {}

/* Larger than phablet (also point when grid becomes active) */
@media (min-width: 550px) {}

/* Larger than tablet */
@media (min-width: 750px) {}

/* Larger than desktop */
@media (min-width: 1000px) {}

/* Larger than Desktop HD */
@media (min-width: 1200px) {}
</style>