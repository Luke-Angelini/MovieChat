## Add Your Favorite Film
> Here you can add the name of one of your favorite movies as well as a reason why you think it stands out and should be rated so highly.

<form action="/action_page.php">
  <div class ="formBox">
    <label for="fname">Film Name:</label><br>
    <input type="text" id="filmName" name="filmName" style="width: 200px" maxlength="200"><br>
  </div>
  <div class="formBox">
    <label for="lname">Your Reasoning:</label> <br>
    <input type="text" id="reason" name="reason" maxlength="1000"><br><br>
  </div>
  <div class="formBox">
    <button id="btn">Click to Add </button>
  </div>
  <div id="msg">
    <pre></pre>
  </div>
</form>

<script>
        let movies = [];
        const addMovie = (ev)=>{
            ev.preventDefault();  //to stop the form submitting
            let movie = {
                id: Date.now(),
                title: document.getElementById('fname').value,
                year: document.getElementById('lname').value
            }
            if (value === "") {
             clearTimeout(movies)
            }
            movies.push(movie);
            document.forms[0].reset(); // to clear the form for the next entries
            //document.querySelector('form').reset();

            //for display purposes only
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