<script>
    export let movie;
    const {image, title, link, year, rating} = movie;
    </script>


<div class="card">
    <div class="bannerBox"><img src="{image}" alt="shougan" class="banner"></div>
    <div class="infoBox">
        <a href="{link}" class="title"><strong>{title}</strong> ({year})</a>
        <br><span class='badge text-bg-warning'>IMDb {rating}</span>
    </div>
</div>

<style>
    .card {
        width: 12rem;
        height: 23rem;
        
    }
    .bannerBox {
        width: 100%;
        height: 20rem;
        overflow: hidden;
    }

    .banner {
        width: 100%;
        height: 100%;
        object-fit: cover;
        transition: transform 0.3s ease;
    }

    .banner:hover {
        transform: scale(1.1);
    }
    
    a {
        text-decoration: none;
        color: black;
        font-family: arial;
    }

    .infoBox {
        padding: 10px;
    }

    div.card {
        overflow: hidden;
    }
</style>