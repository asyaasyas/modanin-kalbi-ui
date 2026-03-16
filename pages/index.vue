<template>
  <v-app>
    <!-- Top Navigation -->
    <v-app-bar elevation="1" class="px-4 px-md-8">
      <v-container class="d-flex align-center justify-space-between px-0" max-width="1200">
        <div class="d-flex align-center ga-2">
          <v-avatar color="primary" size="32">
            <v-icon icon="mdi-flower" size="22" />
          </v-avatar>
          <span class="text-h6 font-weight-black">MODE</span>
        </div>

        <div class="d-none d-md-flex align-center ga-6">
          <v-btn variant="text" density="compact">New Arrivals</v-btn>
          <v-btn variant="text" density="compact">Collections</v-btn>
          <v-btn variant="text" density="compact">Bestsellers</v-btn>
          <v-btn variant="text" density="compact">Journal</v-btn>
        </div>

        <div class="d-flex align-center ga-3">
          <v-text-field v-model="search" density="comfortable" variant="solo-filled" prepend-inner-icon="mdi-magnify"
            hide-details class="d-none d-sm-flex search-field" placeholder="Search" />
          <v-btn icon>
            <v-icon>mdi-account-outline</v-icon>
          </v-btn>
          <v-badge color="primary" :content="2" offset-x="4" offset-y="4">
            <v-btn icon>
              <v-icon>mdi-shopping-bag-outline</v-icon>
            </v-btn>
          </v-badge>
          <v-btn icon class="d-md-none">
            <v-icon>mdi-menu</v-icon>
          </v-btn>
        </div>
      </v-container>
    </v-app-bar>

    <v-main>
      <!-- Hero -->
      <section class="py-8 py-md-12">
        <v-container max-width="1200">
          <v-sheet rounded="xl" class="pa-6 pa-md-10 hero-sheet">
            <v-row class="align-center" no-gutters>
              <v-col cols="12" lg="6" class="pe-lg-8">
                <div class="mb-4 text-primary text-uppercase text-caption font-weight-bold letter-spacing">
                  Summer 2024
                </div>
                <h1 class="text-h3 text-md-h2 text-lg-h1 font-weight-black mb-4">
                  The New
                  <br />
                  Collection
                </h1>
                <p class="text-body-1 text-medium-emphasis mb-7">
                  Discover the essence of modern minimalism with our curated seasonal pieces,
                  designed for the contemporary woman.
                </p>
                <div class="d-flex flex-wrap ga-3">
                  <v-btn color="primary" size="large" class="px-8">
                    Explore Now
                  </v-btn>
                  <v-btn variant="outlined" size="large" class="px-8">
                    View Lookbook
                  </v-btn>
                </div>
              </v-col>

              <v-col cols="12" lg="6" class="mt-6 mt-lg-0">
                <v-img
                  src="https://lh3.googleusercontent.com/aida-public/AB6AXuBixNpruq-du_wPyHGAZzoA8iN4bzLP-5CwMiZ8cO2yhFTe1epzH5zvDssU09Fr2ymDtsXdPVwMsqsU1N3zN8bwV6yrvKR6ipF_hbwVmSqzVW4bWdlZG8x1kUPHvZ2ejzjz275jBxXxK3WuPV4iKhOv3q3CWSFBtmMKceFmT8WAIQd3V6JZT9vpHXxj--3-gXsv63Ho27bAyOtQ46pa23Nv5enrXB5Rf3vmnLbCK1GgB_uWsdrIyizOUNQ7JBQ5FbMtgaEpQVsb57DT"
                  alt="The New Collection" height="420" cover class="rounded-xl" />
              </v-col>
            </v-row>
          </v-sheet>
        </v-container>
      </section>

      <!-- Categories -->
      <section class="py-10 py-md-14">
        <v-container max-width="1200">
          <div class="d-flex justify-space-between align-end mb-8 flex-column flex-sm-row ga-4">
            <div>
              <h2 class="text-h4 font-weight-bold">Shop by Category</h2>
              <div class="mt-2 primary-bar" />
            </div>
            <v-btn variant="text" color="primary" class="text-subtitle-2 font-weight-bold"
              append-icon="mdi-arrow-right">
              View All Categories
            </v-btn>
          </div>

          <v-row dense>
            <v-col
              v-for="category in categories"
              :key="category.title"
              cols="12"
              sm="6"
              lg="4"
            >
              <v-card class="category-card" flat>
                <v-img
                  :src="category.image"
                  :alt="category.alt"
                  aspect-ratio="4/5"
                  cover
                />
                <div class="category-gradient" />
                <div class="category-text">
                  <div class="text-h5 text-white font-weight-bold">
                    {{ category.title }}
                  </div>
                  <div class="text-caption text-white text-high-emphasis">
                    {{ category.subtitle }}
                  </div>
                </div>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </section>

      <!-- New Arrivals -->
      <section class="py-12 new-arrivals">
        <v-container max-width="1200">
          <div class="text-center mb-10">
            <h2 class="text-h4 text-md-h3 font-weight-black">
              New Arrivals
            </h2>
            <p class="mt-3 text-body-2 text-medium-emphasis font-italic">
              Freshly picked styles just for you
            </p>
          </div>

          <v-row dense>
            <v-col v-for="product in products" :key="product.name" cols="6" md="3" class="mb-6">
              <v-card flat class="product-card">
                <div class="product-image-wrapper">
                  <v-btn icon size="small" class="product-fav-btn">
                    <v-icon>mdi-heart-outline</v-icon>
                  </v-btn>
                  <v-img :src="product.image" :alt="product.alt" aspect-ratio="3/4" cover />
                  <v-btn block class="add-to-bag-btn" color="grey-900" variant="flat">
                    ADD TO BAG
                  </v-btn>
                </div>
                <v-card-text class="pa-0 pt-3">
                  <div class="text-body-2 font-weight-semibold">
                    {{ product.name }}
                  </div>
                  <div class="text-body-2 font-weight-bold text-primary mt-1">
                    {{ product.price }}
                  </div>
                </v-card-text>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </section>

      <!-- Footer -->
      <v-footer class="py-10 border-t">
        <v-container max-width="1200">
          <v-row class="mb-8">
            <v-col cols="12" lg="4">
              <div class="d-flex align-center ga-2 mb-4">
                <v-avatar color="primary" size="32">
                  <v-icon icon="mdi-flower" size="22" />
                </v-avatar>
                <span class="text-h6 font-weight-black">MODE</span>
              </div>
              <p class="text-body-2 text-medium-emphasis">
                Sustainable fashion for the modern woman. Quality materials, ethical production,
                timeless design.
              </p>
              <div class="d-flex ga-3 mt-4">
                <v-btn icon variant="text">
                  <v-icon>mdi-web</v-icon>
                </v-btn>
                <v-btn icon variant="text">
                  <v-icon>mdi-camera-outline</v-icon>
                </v-btn>
                <v-btn icon variant="text">
                  <v-icon>mdi-at</v-icon>
                </v-btn>
              </div>
            </v-col>

            <v-col cols="6" sm="4" lg="2">
              <h4 class="text-caption text-uppercase font-weight-bold mb-4">
                Shop
              </h4>
              <v-list density="compact" class="pa-0">
                <v-list-item v-for="item in shopLinks" :key="item">
                  <v-list-item-title class="text-body-2">
                    {{ item }}
                  </v-list-item-title>
                </v-list-item>
              </v-list>
            </v-col>

            <v-col cols="6" sm="4" lg="2">
              <h4 class="text-caption text-uppercase font-weight-bold mb-4">
                Help
              </h4>
              <v-list density="compact" class="pa-0">
                <v-list-item v-for="item in helpLinks" :key="item">
                  <v-list-item-title class="text-body-2">
                    {{ item }}
                  </v-list-item-title>
                </v-list-item>
              </v-list>
            </v-col>

            <v-col cols="12" sm="4" lg="4">
              <h4 class="text-caption text-uppercase font-weight-bold mb-4">
                Newsletter
              </h4>
              <p class="text-body-2 text-medium-emphasis mb-3">
                Join our mailing list for updates and exclusive offers.
              </p>
              <v-row no-gutters>
                <v-col cols="8">
                  <v-text-field v-model="newsletterEmail" placeholder="Your email" variant="solo-filled"
                    density="comfortable" hide-details class="rounded-s-lg" />
                </v-col>
                <v-col cols="4">
                  <v-btn color="primary" block height="40">
                    Join
                  </v-btn>
                </v-col>
              </v-row>
            </v-col>
          </v-row>

          <v-divider />

          <div class="text-center text-caption text-medium-emphasis mt-6">
            © 2024 MODE E-Commerce. All rights reserved.
          </div>
        </v-container>
      </v-footer>
    </v-main>
  </v-app>
</template>

<script setup lang="ts">
const search = ref("");
const newsletterEmail = ref("");

const categories = [
  {
    title: "Dresses",
    subtitle: "Shop the collection",
    image:
      "https://lh3.googleusercontent.com/aida-public/AB6AXuAquC7b_yX6AQnqLtZMQaXOVmK-Se3dXXNaPRS6vx79bmMPb-SC_JsOp1ojaIMMVlrYfj9JBuOyD-uOMP1XJ0v0aitEwQPGssKbzrMDFNtRAS-2tY3PMwCIunZcpOOnnx1xy7WR_MBwgVhMFxhLM_cnWNMz5QGcSG-oFfILobkjx8L7DVxSARCnAoEVfRglFD3lwTR7XoPVofzc3TY8Jq2FH_ye_KXeB-p952B9C1ZOcBGJQIKZNno7ydIjYjxpqB2TYEFwBii2IUMC",
    alt: "Elegant silk dresses hanging in a boutique",
  },
  {
    title: "Shoes",
    subtitle: "Walk with style",
    image:
      "https://lh3.googleusercontent.com/aida-public/AB6AXuD7s1asOzeEEXgsLeH6KwmRuFI7F72eZmdPjG0SPvlcvcUn25oduuMNX7idIH1xQBT9E_Qq7Az015iTKLv_HSmjc7FD426PxU_nA-nMiT_UgAguZykYC0ayxj0aUpdy5uZyK-BWIt_HwMVPdKVlNtREgCFJLhPd2IW3-FQ32KWaLzXQVFSPIkuixYMOcwSkrd5mGqYKQ68T8XCzDhxipdwFAVuuLoTmuiquaIjyPSyAf7Rc10xftdDFmxal78h4vYv6w-iL-j6QAIfn",
    alt: "High-end designer shoes in minimalist setting",
  },
  {
    title: "Bags",
    subtitle: "Everyday essentials",
    image:
      "https://lh3.googleusercontent.com/aida-public/AB6AXuB1lFkA6eLpZ46xgV7JhZcq4J0PmXF33tC7eqtyGmafr5ABdCJ30NACTUs4gartfFjbccLVSmTW8P1PoKh5F0rtwJpFPKWyWEloXg0EG_ig8I0TzpeNFx7ZnMvoBE1r8JD6Lyk6wnsfG7N4_FYVqKOGKuU6Meczzp1F9c5AHcGEQfDWVw41Vt0UPLrDW7A7ANMMVE5ZLlbTm5ozghUcj7CcTtEIDHyQOSh0mpT_1K0GHXQajkGmAuL4H4UwyNr5_EJDaG8zSHKcJ7B2",
    alt: "Luxury leather handbags displayed on pedestals",
    large: true,
  },
];

const products = [
  {
    name: "Linen Blend Blazer",
    price: "$189.00",
    image:
      "https://lh3.googleusercontent.com/aida-public/AB6AXuBvBhdlPsckZAksrzXf7MvoEwmEUQKr2da67uYqmek3YBq9n-LTG_2uCUHMIFNoYc2TmLITunfB6zLxALgKqGKvDTsYb9O0SRAYXrG9vFewypmLT-JW-RAobq7llD_jFVLmJ7G1kYPD2TOWyTHH6uYb2JkLIeB-LPHOsYiugBJfy2F0-eLfd4eC0hlAbBbMlm0SiVqHCwWufJGLgZJIeSjLv9MfilExGDOEbrQWmvK_FDmya2FPebTxoNXixchjD1coiQNF_rtgomZV",
    alt: "Linen blend blazer in sand color",
  },
  {
    name: "Satin Midi Skirt",
    price: "$120.00",
    image:
      "https://lh3.googleusercontent.com/aida-public/AB6AXuCRNvApEY2JYSMA1C4vCmWN05HcviG8K35gKVhKLXk3TNUJx4N1C4_UXmhEyFcE0G7KbNfbXtIJqZ7tzEQtcb6_i1ULmnRZDufYWNAWrcIhsF0OtmRTPAOOVEuuthkKUoG96rzKIXZ_bmlycUq4xzKWQy8452mkF52Kn-pW7zCGnnLqjHwk9YT4MV23NtK6O7oqgooJaBSFS-Gu8lZKSOCuZhbtK4kgxlXcb_eqAlvn-GzAGcviY5l_od36E0m-FSBr2rOnrAyLbzY1",
    alt: "Satin midi skirt in emerald green",
  },
  {
    name: "Puff Sleeve Knit",
    price: "$75.00",
    image:
      "https://lh3.googleusercontent.com/aida-public/AB6AXuAUVPoZRqrDzbmvpNgiS9945GyB6vD3kliVKKtCXSqoOr2MLcGbtM8zteKPEPNzmLwHme0cNFB7Kvp5NeqtxcMJzeOjK4b2Dusrkty0cIARB0j-aABJAA2WjFXzcXOLq9LInf0QROUw71bV-mWwzrjt760pbS_QlpGDmcW-UGe3F0HII3s3SiA2izS-uWuM1uqXbYJnZH606bqc2ZdxcopF8RhcjkNWw-ANW10ap7N76cco2hSWJUe9psdUkbT8qKfQsdGYiWVLXK5P",
    alt: "White knit top with puff sleeves",
  },
  {
    name: "Layered Gold Set",
    price: "$45.00",
    image:
      "https://lh3.googleusercontent.com/aida-public/AB6AXuAGf07SANiOQ0dfVhCOAB-P7QF_Ch4LCLJS7UFfRiSbm3NWaHXyh0z2lxEc8rhOakwDNmowtp_YrxCrdZjg5BKNuVPE395bEQEJuTM1BBfuxwKH41OKveagm28HpnT3BhADNafZanpEhC_yM1PzitG2IloDkxlqly19RQoFZggwd81-Hvr72Vh5pfwF0d3rploT1N9N0D7l5uKGNJaDHAP_WXhFTwvWcmz9pJkBxUogOtDPT2666hJeVpT5ELvFEClf9GlvvOI2ROEy",
    alt: "Gold layered necklaces set",
  },
];

const shopLinks = ["All Products", "New Arrivals", "Bestsellers", "Sales"];
const helpLinks = ["Track Order", "Shipping Info", "Returns & Exchanges", "Contact Us"];
</script>

<style scoped>
.search-field :deep(.v-field) {
  border-radius: 999px;
}

.hero-sheet {
  background: linear-gradient(120deg, #e2e8f0, #f1f5f9);
}

.primary-bar {
  width: 48px;
  height: 4px;
  border-radius: 999px;
  background: rgb(var(--v-theme-primary));
}

.letter-spacing {
  letter-spacing: 0.18em;
}

.category-card {
  cursor: pointer;
  overflow: hidden;
  border-radius: 20px;
}

.category-gradient {
  position: absolute;
  inset: 0;
  background: linear-gradient(to top, rgba(0, 0, 0, 0.75), rgba(0, 0, 0, 0.15), transparent);
}

.category-text {
  position: absolute;
  left: 20px;
  bottom: 20px;
}

.new-arrivals {
  background: color-mix(in srgb, rgb(var(--v-theme-primary)) 5%, transparent);
}

.product-card {
  cursor: pointer;
}

.product-image-wrapper {
  position: relative;
  border-radius: 16px;
  overflow: hidden;
  background-color: #e5e7eb;
}

.product-fav-btn {
  position: absolute;
  top: 10px;
  right: 10px;
  background-color: rgba(255, 255, 255, 0.9);
  z-index: 2;
}

.add-to-bag-btn {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  transform: translateY(100%);
  transition: transform 0.25s ease;
  font-size: 11px;
  font-weight: 700;
}

.product-image-wrapper:hover .add-to-bag-btn {
  transform: translateY(0);
}
</style>