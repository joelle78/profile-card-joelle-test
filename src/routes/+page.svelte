<script>
    import {SliceZone} from '@prismicio/svelte'
    import {components} from '$lib/slices'
    import {PrismicImage} from "@prismicio/svelte"


    export let data
</script>

<!-- HTML CODE -->
<html lang="en">
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta http-equiv="X-UA-Compatible" content="ie=edge">

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap"
      rel="stylesheet">

<body class="animated-gradient">
<main>


    <section class="container-profile">
        <div class="profile-card">

            <!--   PROFILE IMG   -->
            <div class="profile-img">
                <PrismicImage field={data.profilepicture}
                              imgixParams={{ sat: -100, mask: 'ellipse' }}
                />
            </div>

            <!--  BIO    -->
            <div class="biography">
                <h1> {data.firstname} {data.surname} </h1>
                <h2>{data.study}</h2>
            </div>

            <!--  SKILLS   -->
            <div class="container-skills">

                <div class="html-rating">
                    <p>HTML</p>
                    <PrismicImage field={data.rating}/>
                    <PrismicImage field={data.rating}/>
                    <PrismicImage field={data.rating}/>
                </div>

                <div class="css-rating">
                    <p>CSS</p>
                    <PrismicImage field={data.rating}/>
                    <PrismicImage field={data.rating}/>
                </div>

                <div class="js-rating">
                    <p>JS</p>
                    <PrismicImage field={data.rating}/>
                </div>

            </div>


            <!--  GITHUB ICON   -->
            <div class="github-profile">
                <a href="https://github.com/joelle78">
                    <PrismicImage field={data.githubicon}
                    />
                </a>
            </div>

        </div>
    </section>

</main>
</body>
</html>

<!-- CSS CODE -->
<style>

    body {
        padding: 0;
        margin: 0;
        /*box-sizing: border-box;*/
        font-family: 'Roboto', sans-serif;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    h1 {
        margin-bottom: 0;
        font-weight: normal;
        font-size: 30px;
    }

    h2 {
        font-weight: normal;
        font-size: 20px;
    }

    .animated-gradient {
        animation: animateBg 8s linear infinite;
        background-image: linear-gradient(90deg, #bd4faf, #5794db, #bd4faf, #5794db);
        background-size: 300% 100%;
    }

    @keyframes animateBg {
        0% {
            background-position: 0% 0%;
        }
        100% {
            background-position: 100% 0%;
        }
    }


    .profile-card {
        background-color: rgba(255, 255, 255, 0.5);
        border-radius: 5px;
        width: 20rem;

    }

    /* MEDIA QUERY TABLET*/
    @media screen and (min-width: 768px) and (max-width: 1024px) {
        .container-profile {
            padding-top: 8rem;
        }

        .profile-card {
            height: 45rem;
            width: 25rem;
        }
    }

    /* MEDIA QUERY LAPTOP*/
    @media only screen and (min-width: 1024px)  {
        .container-profile {
            margin-top: 8rem;
        }

        .profile-card {
            height: 45rem;
            width: 25rem;
        }
    }

    .profile-img {
        display: flex;
        align-items: center;
        justify-content: center;
        padding-top: 2rem;
    }

    .biography {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        padding-top: 2rem;
    }

    /* SKILLS */
    .container-skills {
        padding-bottom: 1.5rem;
    }

    .html-rating, .css-rating, .js-rating {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        gap: 1rem;
    }

    /* GITHUB ICON */
    .github-profile {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .github-profile a {
        margin-bottom: 1rem;
        cursor: pointer;
    }


</style>


<SliceZone slices={data.slices} {components}/>