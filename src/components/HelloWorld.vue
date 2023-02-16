<template>
  <head> 
        <link rel="stylesheet" href="https://cdn.datatables.net/1.12.1/css/jquery.dataTables.min.css">
        <link rel="stylesheet" href="https://cdn.datatables.net/buttons/2.1.0/css/buttons.dataTables.min.css">
        <link href="https://fonts.googleapis.com/css2?family=News+Cycle&amp;display=swap" rel="stylesheet">
        <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="">
        <link rel="preconnect" href="https://fonts.googleapis.com">
        <link rel="stylesheet" type="text/css" href="style.css">
        <link rel="icon" href="logo.png">
    </head>
    <body>
        <header>
            <div class="inner">
                <div class="logo">
                    <div>
                        <img src="logo.png" alt="logo">
                    </div>

                </div>
                <nav>
                    <li><span>LEARNER CORPUS OF SLAVIC LANGUAGES (RUSSIAN)</span></li>
                    <li><span><a href="http://lcsl.nccu.edu.tw/"><i class="fas fa-home"></i> Home</a></span></li>
                    <li><span><a href="http://lcsl.nccu.edu.tw:3838/sample-apps/searchCorpus/Russian.Rmd#section-search"><i class="fas fa-search"></i> Search</a></span></li>
                    <li><span><a href="http://lcsl.nccu.edu.tw:3838/sample-apps/searchCorpus/Russian.Rmd#section-advanced-filter"><i class="fas fa-filter"></i> Advanced Filter</a></span></li>
                    <li><span><a href="http://lcsl.nccu.edu.tw:8080/search/"><i class="fab fa-searchengin"></i> Lexical/Grammatical Search</a></span></li>
                    <li><span><a href=""><i class="fab error-anno"></i> Error Annotation</a></span></li>
                </nav>
            </div>
        </header>
        <!-- <br> -->
        <div>
            <div id="toolbar">
            <label class="switch">
                <input type="checkbox">
                <span class="slider round"></span>
            </label>
            <span id="mode">Original</span>
            <button id="saveButton" @click="saveContent()"><img src="../../public/save.png" class="pic"/></button>
            <button @click="transContent()"><img src="../../public/transfer-data.png" class="pic" /></button>
            <button @click="preStep()"><img src="../../public/back-arrow.png"  class="pic" /></button>
            <button @click="nextStep()"><img src="../../public/next.png"  class="pic" /></button>
            </div>
            <hr>
            
            
            <textarea id="textarea_input" v-model="rawContent" v-if="view===0"></textarea>
            <div id="selectArea" @mouseup="getSelection">
                <label v-if="view===1">{{ori_content}}</label>
            </div>
        </div>
        <footer class="bottomBar">
            <b>NCCU LCSL © 2023.</b>
        </footer>
    </body>

</template>

<script>
// import { ref } from 'vue'

// let select_content = ref(''); //選取內容
let selectionObj = window.getSelection();
console.log(selectionObj.toString());

function transContent() {
    this.ori_content = this.rawContent;
    this.view = 1;
    console.log(this.view);

}
function saveContent() {

}
function preStep() {

}
function nextStep() {

}
function getSelection() {
    const selection = window.getSelection();
    const selectedText = selection.toString();
    const words = selectedText.split(/\s+/);
    const range = selection.getRangeAt(0);
    const selectedWords = [];

    for (let i = 0; i < words.length; i++) {
    const word = words[i];
    if (range.toString().indexOf(word) !== -1) {
        selectedWords.push(word);
    }
    }

    console.log(selectedWords); 
}
export default {

  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return {
        rawContent: '',
        ori_content: '',
        view: 0,
    }
  },
    methods: {
        transContent: transContent,
        saveContent: saveContent,
        preStep: preStep,
        nextStep: nextStep,
        getSelection: getSelection,
    }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#saveButton{
    margin-left: 20px;
    /* margin-top:5px; */
}
#mode {
    margin-left: 5px;
    font-family: 'Inter';
    font-size: 14px;
}
#selectArea{
    width: 60%;
    height: 250px;
    margin-top: 10px;
    margin-left: 20px;
}
.pic{
    width: 25px;
    height: 25px;  
}
.bottomBar{
    position:fixed; bottom:0; left: 0px; width:100%; height:22px;
                color: #FFFFFF; padding: 1%; background-color: #A26969; font-family: 'News Cycle'; text-align:center;
}
.switch {
    position: relative;
    display: inline-block;
    margin-left: 20px;
    margin-top: 0px;
    /* margin-bottom: 10px; */
    width: 60px;
    height: 28px;
}
  
  /* Hide default HTML checkbox */
.switch input {
    opacity: 0;
    width: 0;
    height: 0;
}
</style>
