## Add Your Favorite Film
> Here you can add the name of one of your favorite movies as well as a reason why you think it stands out and should be rated so highly.

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
  border-radius: 20px;
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
    </script>
</body>