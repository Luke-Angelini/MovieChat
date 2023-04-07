 <h1 style="text-align: center;"> Posts </h1>

<h3 style="text-align: center;"> On this page you'll be able to: </h3>

* View the best movies according to our users

* Like and dislike posts in order to help determine which movies are best

* View the reasons behind different movie opinions

<body>
<style>
.custom-field input {
  border: none;
  -webkit-appearance: none;
  -ms-appearance: none;
  -moz-appearance: none;
  appearance: none;
  background: #f2f2f2;
  padding: 12px;
  border-radius: 3px;
  width: 250px;
  font-size: 14px;
}
</style>
    <form>
        <custom-field class="formBox">
            <label for="ftitle">Movie</label>
            <input type="text" id="ftitle" placeholder="Film-Title"/>
        </custom-field>
        <custom-field class="formBox">
            <label for="reason">Reason</label>
            <input type="text" id="reason" placeholder="Reason"/>
        </custom-field>
        <custom-field class="formBox">
           <button ondblclick = "addElement()" > Click Me </button>
        </custom-field>
        <custom-field id="msg">
            <pre></pre>
        </custom-field>
    </form>
    <script>
     function addElement() {
        // create a new div element
        const newDiv = document.createElement("div");
        // and give it some content
        const newContent = document.createTextNode("Hi there and greetings!");   
        // add the text node to the newly created div
        newDiv.appendChild(newContent);
        // add the newly created element and its content into the DOM
        const currentDiv = document.getElementById("div1");
        document.body.insertBefore(newDiv, currentDiv);
        }
    </script>
</body>