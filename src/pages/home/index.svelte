<script lang="ts">
import { basePath } from '@/env';
import { ChevronDown } from 'svelte-ionicons';
import { Link } from 'svelte-navigator';

function scrollDown() {
  const element = document.getElementById('about');
  element.scrollIntoView({ behavior: 'smooth' });
}
</script>

<main>
  <section id="missions">
    <h1>Voyager's Journey</h1>

    <ol class="missions">
      <li>
        <Link to="/voyager/1">
          <picture>
            <img src="{basePath}/images/posters/voyager1.jpg" alt="Voyager 1" />
            <legend>Voyager 1</legend>
          </picture>
        </Link>
      </li>

      <li>
        <Link to="/voyager/2">
          <picture>
            <img src="{basePath}/images/posters/voyager2.jpg" alt="Voyager 2" />
            <legend>Voyager 2</legend>
          </picture>
        </Link>
      </li>
    </ol>

    <button class="scroll-down" on:click={() => scrollDown()}>
      <ChevronDown size="2rem" color="#bd9526" />
    </button>
  </section>

  <section id="about">
    <div>
      <h2>Authors</h2>

      <ul class="authors">
        <li>
          <img src="{basePath}/images/people/adame.jpg" alt="Eduardo Adame" />
          <div class="text">
            <p class="author-name">Eduardo Adame</p>
            <p class="author-email">eduardo.salles@fgv.br</p>
            <p class="author-school">
              <a href="https://emap.fgv.br/en" target="_blank">FGV/EMAp</a>
            </p>
          </div>
        </li>
        <li>
          <img src="{basePath}/images/people/juan.jpg" alt="Juan Belieni" />
          <div class="text">
            <p class="author-name">Juan Belieni</p>
            <p class="author-email">juan.araujo@fgv.edu.br</p>
            <p class="author-school">
              <a href="https://emap.fgv.br/en" target="_blank">FGV/EMAp</a>
            </p>
          </div>
        </li>
        <li>
          <img
            src="{basePath}/images/people/marcelo.jpeg"
            alt="Marcelo Amaral"
          />
          <div class="text">
            <p class="author-name">Marcelo Amaral</p>
            <p class="author-email">marcelo.filho@fgv.br</p>
            <p class="author-school">
              <a href="https://emap.fgv.br/en" target="_blank">FGV/EMAp</a>
            </p>
          </div>
        </li>
      </ul>

      <div class="sources">
        <h3>Sources</h3>

        <ul>
          <li>
            <a
              href="https://data.nasa.gov/Earth-Science/VOYAGER-1-DAILY-POSITION-V1-0/cg9t-y7w6"
              target="_blank"
            >
              Daily Position of Voyager 1
            </a>
          </li>

          <li>
            <a
              href="https://data.nasa.gov/Earth-Science/VOYAGER-2-DAILY-POSITION-V1-0/4hef-z9y3"
              target="_blank"
            >
              Daily Position of Voyager 2
            </a>
          </li>

          <li>
            <a
              href="https://pds-rings.seti.org/galleries/voyager.html"
              target="_blank"
            >
              Published images of Voyager 1 and 2
            </a>
          </li>

          <li>
            <a
              href="https://pds-ppi.igpp.ucla.edu/mission/Voyager"
              target="_blank"
            >
              Voyager Mission Phases
            </a>
          </li>

          <li>
            Special thanks to Tulio Koneçny (<a
              href="https://instagram.com/bald.comics"
              target="_blank">@bald.comics</a
            >) for the beautiful drawings of our Solar System.
          </li>
        </ul>
      </div>
    </div>

    <div class="mission-info">
      <h2>About Voyager</h2>

      <p>
        The Voyager program is an American scientific program that employs two
        robotic interstellar probes, Voyager 1 and Voyager 2. They were launched
        in 1977 to take advantage of a favorable alignment of the two gas giants
        Jupiter and Saturn and the ice giants, Uranus and Neptune, to fly near
        them while collecting data for transmission back to Earth. After launch
        the decision was taken to send Voyager 2 near Uranus and Neptune to
        collect data for transmission back to Earth.
      </p>

      <img
        src="https://www.jpl.nasa.gov/edu/images/news/voyager_trajectories.png"
        alt="Voyager Trajectories"
      />

      <p>
        <span>
          More info about the Voyager program and ou visualization can be found
          in our
        </span>
        <a
          href="https://github.com/fgv-vis-2023/final-project-voyagers-journey/blob/main/docs/article.pdf"
          target="_blank"
        >
          article.
        </a>
      </p>
    </div>
  </section>
</main>

<style lang="scss">
main {
  background-color: #121212;
  overflow-x: hidden;

  scroll-behavior: smooth;
}

@keyframes scroll-down {
  0% {
    transform: translateY(0);
  }

  50% {
    transform: translateY(0.5rem);
  }

  100% {
    transform: translateY(0);
  }
}

section {
  height: 100vh;
  width: 100vw;
  margin: 0;

  display: flex;
  flex-direction: column;
  align-items: center;

  .scroll-down {
    position: absolute;
    bottom: 2rem;

    background-color: transparent;
    border: none;
    width: min-content;

    cursor: pointer;
    animation: scroll-down 2s infinite;
  }

  &#missions {
    display: flex;
    flex-direction: column;
    align-items: center;

    h1 {
      font-size: 4rem;
      color: #bd9526;

      text-align: center;
      margin-top: 2rem;
    }

    ol.missions {
      max-width: 100vw;

      display: flex;
      flex-direction: row;
      align-items: center;
      gap: 2rem;

      justify-content: center;
      list-style: none;
      padding: 0;
      margin: 0 2rem;

      li {
        opacity: 0.75;
        margin: 0;
        transition: all 200ms;

        :global(a) {
          color: white;
          text-decoration: none;
        }

        picture {
          img {
            width: 100%;
            max-width: 30rem;
          }

          legend {
            margin-top: -3.5rem;
            margin-left: 1rem;

            font-size: 2rem;
            font-weight: bold;
          }
        }

        &:hover {
          opacity: 1;
          transform: scale(1.05);
          z-index: 2;
        }
      }
    }
  }

  &#about {
    background-color: #141e28;

    display: grid;
    grid-template-columns: repeat(2, 1fr);

    padding: 2rem 4rem;

    & > div {
      margin: auto;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: start;
      height: 100%;
      max-width: 40rem;

      h2 {
        font-size: 4rem;
        color: #bd9526;

        text-align: center;
        margin-bottom: 4rem;
      }
    }

    .authors {
      display: flex;
      flex-direction: column;
      align-items: start;
      justify-content: center;
      gap: 2rem;
      list-style: none;
      padding: 0;
      margin: 0 2rem;

      li {
        display: flex;
        flex-direction: row;
        gap: 1rem;

        img {
          width: 8rem;
          height: 8rem;
          object-fit: cover;
        }

        .text {
          display: flex;
          flex-direction: column;
          justify-content: start;
          height: 8rem;

          p {
            color: white;

            &.author-name {
              font-size: 2rem;
              font-weight: bold;
              line-height: 1;

              margin-bottom: 0.5rem;
            }

            &.author-email {
              color: #bbb;
              font-size: 1.24rem;
            }

            &.author-school {
              margin-bottom: 0;
              margin-top: auto;
            }
          }
        }
      }
    }

    .sources {
      margin-top: 4rem;

      display: flex;
      flex-direction: column;
      align-items: center;

      h3 {
        margin-bottom: 0.5rem;
      }

      ul {
        display: flex;
        flex-direction: column;
        align-items: center;

        li {
          margin: 0;
          list-style: none;
          text-align: center;
        }
      }
    }

    .mission-info {
      text-align: justify;

      img {
        max-width: 30rem;
        margin-bottom: 1rem;
      }
    }
  }
}
</style>
