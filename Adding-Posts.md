## Add Your Favorite Film
> Here you can add the name of one of your favorite movies as well as a reason why you think it stands out and should be rated so highly.

<body>
<style>
custom-field input {
  border: 2px solid darkgrey;
  -webkit-appearance: none;
  -ms-appearance: none;
  -moz-appearance: none;
  appearance: none;
  background: #f2f2f2;
  padding: 12px;
  border-radius: 10px;
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
            <button id="btn">Click to Add</button>
        </custom-field>
        <custom-field id="msg">
            <pre></pre>
        </custom-field>
    </form>
    <div class="col-4">
                    <h2 class="card-title">Movies</h2>
                    <p id="demo" onclick="myFunction()">Click me to see movies.</p>
    </div>
    <script>
        let movies = [];
        // example {id:1592304983049, title: 'Avengers: Endgame', reason: 'good action scenes.'}
        const addMovie = (ev)=>{
            ev.preventDefault();  //to stop the form submitting automatically
            let movie = {
                id: Date.now(),
                ftitle: document.getElementById('ftitle').value,
                reason: document.getElementById('reason').value
            }
           movies.push(movie);
            document.forms[0].reset(); // to clear the form for the next entries
            //to display the text of movies
            console.warn('added' , {movies} );
            let pre = document.querySelector('#msg pre');
            pre.textContent = '\n' + JSON.stringify(movies, '\t', 2);
            //saving to localStorage
            localStorage.setItem('MyMovieList', JSON.stringify(movies) );
        }
        document.addEventListener('DOMContentLoaded', ()=>{
            document.getElementById('btn').addEventListener('click', addMovie);
        });
        function myFunction() {
         for (var i=0;i<movies.length;i+=1) {
            console.log(movies[i].ftitle);
            const newDiv = document.createElement("div");
            const newContent = document.createTextNode("Movie: " + movies[i].ftitle + ", Comments: " + movies[i].reason);
            newDiv.appendChild(newContent);
            const currentDiv = document.getElementById("div1");
            document.body.insertBefore(newDiv, currentDiv);
            }
        }
    </script>
</body>