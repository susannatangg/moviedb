<script context="module">
    export async function load({fetch}){
        const res = await fetch(`https://api.themoviedb.org/3/movie/popular?api_key=23b9412f8d7be86d07facf9e5002ac01&language=en-US&page=1`);
        const data = await res.json();
        console.log(data);
        if(res.ok){
            return{
                props: {popular: data.results}
            };
        }
    }
</script>

<script>
    import SearchMovies from '../components/SearchMovies.svelte'
    import PopularMovies from '../components/PopularMovies.svelte'
    export let popular;
    import global from '../global.css';
</script>

<section>
    <SearchMovies/>
    <PopularMovies {popular}/>
</section>
