<script>
    import CategorySection from './WorldList.svelte';
    const worldArticles = [
      {
        image: '/worldImg.jpg',
        title: 'Japan sees record 3.14 million visitors in June as weak yen fuels tourism boom',
        description: '',
        link: '#'
      },
      {
        title: 'ArcelorMittal\'s 55-day Mexico work stoppage ends, firm agrees pay hike',
        description: '',
        link: '#'
      },
      {
        title: 'Microsoft outage causes Frontier airlines to briefly ground all flights',
        description: '',
        link: '#'
      }
    ];
  
    const companiesArticles = [
      {
        image: '/comapny.jpg',
        title: 'Q1 Results 2024 LIVE: Paytm\'s consolidated net loss widens to Rs 839 crore',
        description: '',
        link: '#'
      },
      {
        title: 'SpiceJet board to consider raising fresh capital via QIP on July 23',
        description: '',
        link: '#'
      },
      {
        title: 'Vedanta Resources pays $246 million dues to help revive operations .',
        description: '',
        link: '#'
      }
    ];
  
    const economyArticles = [
      {
        image: '/economy.jpg',
        title: 'Federal Reserve’s critics on inflation should now champion July cut',
        description: '',
        link: '#'
      },
      {
        title: 'Moneycontrol Pro Panorama | Karnataka’s risky experiment on job reservation',
        description: '',
        link: '#'
      },
      {
        title: 'India targets $110 billion FDI a year to help boost economy',
        description: '',
        link: '#'
      }
    ];
  
    const politicsArticles = [
      {
        image: '/politics.jpg',
        title: 'AAP to contest all 90 assembly seats in Haryana: Sanjay Singh',
        description: '',
        link: '#'
      },
      {
        title: 'US: Robert Menendez conviction is a rare win against public corruption',
        description: '',
        link: '#'
      },
      {
        title: 'We will contest 2026 assembly polls as part of united opposition: Assam Cong chief',
        description: '',
        link: '#'
      }
    ];
  </script>
  
  <div style="max-width: 1200px; margin: 2rem auto;">
    <div style="display: flex; flex-wrap: wrap;">
      <CategorySection title="WORLD" articles={worldArticles} seeMoreLink="#"/>
      <CategorySection title="COMPANIES" articles={companiesArticles} seeMoreLink="#"/>
      <CategorySection title="ECONOMY" articles={economyArticles} seeMoreLink="#"/>
      <CategorySection title="POLITICS" articles={politicsArticles} seeMoreLink="#"/>
    </div>
    <div class="bg-gray-500 w-full h-1 mt-5"></div>
  </div>
  