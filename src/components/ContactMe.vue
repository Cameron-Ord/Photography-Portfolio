<template>
  <span class="contactSpan">
    <h3 class="contactHeaderText">Contact me</h3>
    <div class="subHeading">
      <p class="contactText">For general inquiries:</p>
      <div class="socialLinks">
        <svg
          v-if="screenSize >= 1024"
          @mouseleave="removehighlight(this.$refs.discordIcon)"
          @mouseover="highlighticon(this.$refs.discordIcon)"
          ref="discordIcon"
          class="svgIcon"
          viewBox="0 -28.5 256 256"
          version="1.1"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          preserveAspectRatio="xMidYMid"
        >
          <path
            d="M216.856339,16.5966031 C200.285002,8.84328665 182.566144,3.2084988 164.041564,0 C161.766523,4.11318106 159.108624,9.64549908 157.276099,14.0464379 C137.583995,11.0849896 118.072967,11.0849896 98.7430163,14.0464379 C96.9108417,9.64549908 94.1925838,4.11318106 91.8971895,0 C73.3526068,3.2084988 55.6133949,8.86399117 39.0420583,16.6376612 C5.61752293,67.146514 -3.4433191,116.400813 1.08711069,164.955721 C23.2560196,181.510915 44.7403634,191.567697 65.8621325,198.148576 C71.0772151,190.971126 75.7283628,183.341335 79.7352139,175.300261 C72.104019,172.400575 64.7949724,168.822202 57.8887866,164.667963 C59.7209612,163.310589 61.5131304,161.891452 63.2445898,160.431257 C105.36741,180.133187 151.134928,180.133187 192.754523,160.431257 C194.506336,161.891452 196.298154,163.310589 198.110326,164.667963 C191.183787,168.842556 183.854737,172.420929 176.223542,175.320965 C180.230393,183.341335 184.861538,190.991831 190.096624,198.16893 C211.238746,191.588051 232.743023,181.531619 254.911949,164.955721 C260.227747,108.668201 245.831087,59.8662432 216.856339,16.5966031 Z M85.4738752,135.09489 C72.8290281,135.09489 62.4592217,123.290155 62.4592217,108.914901 C62.4592217,94.5396472 72.607595,82.7145587 85.4738752,82.7145587 C98.3405064,82.7145587 108.709962,94.5189427 108.488529,108.914901 C108.508531,123.290155 98.3405064,135.09489 85.4738752,135.09489 Z M170.525237,135.09489 C157.88039,135.09489 147.510584,123.290155 147.510584,108.914901 C147.510584,94.5396472 157.658606,82.7145587 170.525237,82.7145587 C183.391518,82.7145587 193.761324,94.5189427 193.539891,108.914901 C193.539891,123.290155 183.391518,135.09489 170.525237,135.09489 Z"
            fill="currentcolor"
            fill-rule="nonzero"
          ></path>
        </svg>
        <svg
          v-if="screenSize < 1024"
          @touchend="removehighlight(this.$refs.discordIcon)"
          @touchstart="highlighticon(this.$refs.discordIcon)"
          ref="discordIcon"
          class="svgIcon"
          viewBox="0 -28.5 256 256"
          version="1.1"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          preserveAspectRatio="xMidYMid"
        >
          <path
            d="M216.856339,16.5966031 C200.285002,8.84328665 182.566144,3.2084988 164.041564,0 C161.766523,4.11318106 159.108624,9.64549908 157.276099,14.0464379 C137.583995,11.0849896 118.072967,11.0849896 98.7430163,14.0464379 C96.9108417,9.64549908 94.1925838,4.11318106 91.8971895,0 C73.3526068,3.2084988 55.6133949,8.86399117 39.0420583,16.6376612 C5.61752293,67.146514 -3.4433191,116.400813 1.08711069,164.955721 C23.2560196,181.510915 44.7403634,191.567697 65.8621325,198.148576 C71.0772151,190.971126 75.7283628,183.341335 79.7352139,175.300261 C72.104019,172.400575 64.7949724,168.822202 57.8887866,164.667963 C59.7209612,163.310589 61.5131304,161.891452 63.2445898,160.431257 C105.36741,180.133187 151.134928,180.133187 192.754523,160.431257 C194.506336,161.891452 196.298154,163.310589 198.110326,164.667963 C191.183787,168.842556 183.854737,172.420929 176.223542,175.320965 C180.230393,183.341335 184.861538,190.991831 190.096624,198.16893 C211.238746,191.588051 232.743023,181.531619 254.911949,164.955721 C260.227747,108.668201 245.831087,59.8662432 216.856339,16.5966031 Z M85.4738752,135.09489 C72.8290281,135.09489 62.4592217,123.290155 62.4592217,108.914901 C62.4592217,94.5396472 72.607595,82.7145587 85.4738752,82.7145587 C98.3405064,82.7145587 108.709962,94.5189427 108.488529,108.914901 C108.508531,123.290155 98.3405064,135.09489 85.4738752,135.09489 Z M170.525237,135.09489 C157.88039,135.09489 147.510584,123.290155 147.510584,108.914901 C147.510584,94.5396472 157.658606,82.7145587 170.525237,82.7145587 C183.391518,82.7145587 193.761324,94.5189427 193.539891,108.914901 C193.539891,123.290155 183.391518,135.09489 170.525237,135.09489 Z"
            fill="currentcolor"
            fill-rule="nonzero"
          ></path>
        </svg>
      </div>
    </div>
    <div class="closingText">
      <p class="contactText">For professional inquiries:</p>
      <div class="professionLinks">
        <svg
          v-if="screenSize >= 1024"
          ref="githubicon"
          @mouseleave="removehighlight(this.$refs.githubicon)"
          @mouseover="highlighticon(this.$refs.githubicon)"
          class="svgIcon"
          viewBox="0 0 20 20"
          version="1.1"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
        >
          <g id="Page-1" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
            <g
              id="Dribbble-Light-Preview"
              transform="translate(-140.000000, -7559.000000)"
              fill="#000000"
            >
              <g id="icons" transform="translate(56.000000, 160.000000)">
                <path
                  fill="currentcolor"
                  d="M94,7399 C99.523,7399 104,7403.59 104,7409.253 C104,7413.782 101.138,7417.624 97.167,7418.981 C96.66,7419.082 96.48,7418.762 96.48,7418.489 C96.48,7418.151 96.492,7417.047 96.492,7415.675 C96.492,7414.719 96.172,7414.095 95.813,7413.777 C98.04,7413.523 100.38,7412.656 100.38,7408.718 C100.38,7407.598 99.992,7406.684 99.35,7405.966 C99.454,7405.707 99.797,7404.664 99.252,7403.252 C99.252,7403.252 98.414,7402.977 96.505,7404.303 C95.706,7404.076 94.85,7403.962 94,7403.958 C93.15,7403.962 92.295,7404.076 91.497,7404.303 C89.586,7402.977 88.746,7403.252 88.746,7403.252 C88.203,7404.664 88.546,7405.707 88.649,7405.966 C88.01,7406.684 87.619,7407.598 87.619,7408.718 C87.619,7412.646 89.954,7413.526 92.175,7413.785 C91.889,7414.041 91.63,7414.493 91.54,7415.156 C90.97,7415.418 89.522,7415.871 88.63,7414.304 C88.63,7414.304 88.101,7413.319 87.097,7413.247 C87.097,7413.247 86.122,7413.234 87.029,7413.87 C87.029,7413.87 87.684,7414.185 88.139,7415.37 C88.139,7415.37 88.726,7417.2 91.508,7416.58 C91.513,7417.437 91.522,7418.245 91.522,7418.489 C91.522,7418.76 91.338,7419.077 90.839,7418.982 C86.865,7417.627 84,7413.783 84,7409.253 C84,7403.59 88.478,7399 94,7399"
                  id="github-[#142]"
                ></path>
              </g>
            </g>
          </g>
        </svg>
        <svg
          v-if="screenSize >= 1024"
          ref="linkedinicon"
          @mouseleave="removehighlight(this.$refs.linkedinicon)"
          @mouseover="highlighticon(this.$refs.linkedinicon)"
          class="svgIcon"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
        >
          <path
            fill="currentcolor"
            d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"
          />
        </svg>
        <svg
          v-if="screenSize < 1024"
          ref="githubicon"
          @touchend="removehighlight(this.$refs.githubicon)"
          @touchstart="highlighticon(this.$refs.githubicon)"
          class="svgIcon"
          viewBox="0 0 20 20"
          version="1.1"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
        >
          <g id="Page-1" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
            <g
              id="Dribbble-Light-Preview"
              transform="translate(-140.000000, -7559.000000)"
              fill="#000000"
            >
              <g id="icons" transform="translate(56.000000, 160.000000)">
                <path
                  fill="currentcolor"
                  d="M94,7399 C99.523,7399 104,7403.59 104,7409.253 C104,7413.782 101.138,7417.624 97.167,7418.981 C96.66,7419.082 96.48,7418.762 96.48,7418.489 C96.48,7418.151 96.492,7417.047 96.492,7415.675 C96.492,7414.719 96.172,7414.095 95.813,7413.777 C98.04,7413.523 100.38,7412.656 100.38,7408.718 C100.38,7407.598 99.992,7406.684 99.35,7405.966 C99.454,7405.707 99.797,7404.664 99.252,7403.252 C99.252,7403.252 98.414,7402.977 96.505,7404.303 C95.706,7404.076 94.85,7403.962 94,7403.958 C93.15,7403.962 92.295,7404.076 91.497,7404.303 C89.586,7402.977 88.746,7403.252 88.746,7403.252 C88.203,7404.664 88.546,7405.707 88.649,7405.966 C88.01,7406.684 87.619,7407.598 87.619,7408.718 C87.619,7412.646 89.954,7413.526 92.175,7413.785 C91.889,7414.041 91.63,7414.493 91.54,7415.156 C90.97,7415.418 89.522,7415.871 88.63,7414.304 C88.63,7414.304 88.101,7413.319 87.097,7413.247 C87.097,7413.247 86.122,7413.234 87.029,7413.87 C87.029,7413.87 87.684,7414.185 88.139,7415.37 C88.139,7415.37 88.726,7417.2 91.508,7416.58 C91.513,7417.437 91.522,7418.245 91.522,7418.489 C91.522,7418.76 91.338,7419.077 90.839,7418.982 C86.865,7417.627 84,7413.783 84,7409.253 C84,7403.59 88.478,7399 94,7399"
                  id="github-[#142]"
                ></path>
              </g>
            </g>
          </g>
        </svg>
        <svg
          v-if="screenSize < 1024"
          ref="linkedinicon"
          @touchend="removehighlight(this.$refs.linkedinicon)"
          @touchstart="highlighticon(this.$refs.linkedinicon)"
          class="svgIcon"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
        >
          <path
            fill="currentcolor"
            d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"
          />
        </svg>
      </div>
    </div>
  </span>
</template>

<script>
export default {
  data() {
    return {
      screenSize: undefined
    }
  },
  created() {
    this.screenSize = window.innerWidth
  },

  methods: {
    handleResize() {
      console.log('handling resize...')
      this.screenSize = window.innerWidth
    },

    removehighlight(ref) {
      ref.style.width = ''
    },

    highlighticon(ref) {
      ref.style.width = '35px'
    }
  }
}
</script>

<style lang="scss" scoped>
.contactSpan {
  display: grid;
  align-items: center;
  justify-items: center;
  width: 100%;

  grid-auto-flow: row;
  row-gap: 50px;
  > .closingText {
    display: grid;
    justify-items: center;
    align-items: center;
    width: 100%;
    height: 100%;
    grid-auto-flow: row;
    row-gap: 25px;

    > .professionLinks {
      display: grid;
      justify-items: center;
      align-items: center;
      grid-template-columns: repeat(auto-fit, minmax(75px, 1fr));
      width: 75%;
      max-width: 325px;
      padding-top: 5px;
      padding-bottom: 5px;
    }
    > .contactText {
      text-align: center;
      width: clamp(100px, 60%, 300px);
      padding: 10px;
    }
  }
  > .subHeading {
    display: grid;
    justify-items: center;
    align-items: center;
    width: 100%;
    height: 100%;

    grid-auto-flow: row;
    row-gap: 25px;

    > .socialLinks {
      display: grid;
      justify-items: center;
      align-items: center;
    }
    > .contactText {
      text-align: center;
      width: clamp(100px, 50%, 250px);
      padding: 10px;
    }
  }
}
@media only screen and (min-width: 770px) {
  .contactSpan {
    height: 500px;
    grid-template-rows: 100px 200px 200px;
    grid-auto-flow: row;
    row-gap: 0px;

    > .closingText {
      grid-auto-flow: row;
      row-gap: 35px;

      > .professionLinks {
      }
      > .contactText {
        width: clamp(305px, 25%, 350px);
      }
    }
    > .subHeading {
      grid-auto-flow: row;
      row-gap: 35px;

      > .socialLinks {
      }
      > .contactText {
        text-align: center;
        width: clamp(250px, 25%, 275px);
        max-width: 450px;
        padding: 10px;
      }
    }
  }
}

@media only screen and (min-width: 1024px) {
  .contactSpan {
    width: clamp(500px, 100%, 800px);
    height: 500px;
    grid-template-rows: 100px 200px 200px;
    > .closingText {
      grid-template-rows: 1fr;
      grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
      grid-auto-flow: row;
      row-gap: 0px;
      height: 100%;

      > .professionLinks {
        width: 80%;
      }
      > .contactText {
        width: 80%;
      }
    }
    > .subHeading {
      grid-template-rows: 1fr;
      grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
      grid-auto-flow: row;
      row-gap: 0px;
      height: 100%;

      > .socialLinks {
      }
      > .contactText {
        width: 70%;
      }
    }
  }
}
</style>
