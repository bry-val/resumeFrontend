<script>
  import card from '../../resources/card';
  import Links from '../components/pages/Card/Links.svelte';
  import Footer from '../components/pages/Card/Footer.svelte';
  import Counter from '../components/Counter.svelte';
</script>

<div class="grid-item-profile">
    <div class="profile-content">
        <div class="banner-container">
            <img class="banner" src={card.coverImage} alt="banner">
        </div>
        <div class="profile-pic-container">
            <img src={card.profileImage} alt="profile pic" class="profile-pic">
        </div>

        <div class="full-name">
            <h1 id="full-name">{card.fullName}</h1>
        </div>

        <div class="subtitle">
            <span class="block primary-color" id="profession">{card.profession}</span>
        </div>

        <Links links={card.links}/>
        <br>  
        <Counter />
        <Footer cv={card.cv} email={card.email}/>
    </div>
</div>

<style>
    .grid-item-profile {
        grid-area: profile;
        height: 72vh;
        min-height: 450px;
        box-shadow: 0 -5px 10px var(--shadow-color);
        border-radius: var(--radius);
        position: relative;
        background: var(--card-background);
        width: 100%
    }

    .banner-container {
        width: 100%;
        height: 35vh;
    }

    .banner {
        object-fit: cover;
        width: 100%;
        height: 100%;
        border-radius: var(--radius);
    }

    .profile-pic-container {
        width: 140px;
        height: 140px;
        margin: -85px auto 20px
    }

    .profile-pic {
        object-fit: cover;
        width: 100%;
        height: 100%;
        border-radius: 100px;
        border: solid 3px var(--card-background);
    }

    .subtitle {
        text-align: center;
        font-size: 0.95em;
    }

    h1 {
        margin: 0;
        font-size: 30px;
        text-align: center;
        font-weight: normal;
    }

    @media only screen and (max-width: 480px) {
        .grid-item-profile {
            height: 85vh;
        }
    }
</style>
