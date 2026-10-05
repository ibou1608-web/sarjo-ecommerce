const translations = {
  fr: {
    navHome: 'Accueil',
    navProducts: 'Produits',
    navAbout: 'À propos',
    navContact: 'Contact',
    eyebrow: 'Vente en ligne • GAMBIE',
    heroTitle: 'Des produits frais, élégants et utiles pour votre quotidien.',
    heroText:
      'Sarjo.com vous propose des jus savoureux, des articles de décoration intérieure et des produits variés pour embellir votre maison et satisfaire vos besoins quotidiens.',
    ctaShop: 'Commander',
    ctaCall: 'Appeler',
    hoursLabel: 'Horaires :',
    hoursText: 'Lun - Sam : 9h à 16h',
    badgeFresh: 'Jus frais',
    badgeDecor: 'Décoration',
    bestSeller: 'Best seller',
    juiceName: 'Jus du jour',
    juiceDesc: 'Naturel, rafraîchissant et prêt à consommer.',
    featureFresh: 'Jus rafraîchissants',
    featureFreshText: 'Une sélection de boissons naturelles pour votre énergie et votre plaisir.',
    featureDecor: 'Décoration intérieure',
    featureDecorText: 'Des items élégants pour sublimer votre maison et votre espace de vie.',
    featureVaried: 'Divers produits',
    featureVariedText: 'Des articles utiles et variés pour un shopping pratique et agréable.',
    shopTitleLabel: 'Notre catalogue',
    shopTitle: 'Produits populaires',
    tagJuice: 'Jus',
    prodJuice: 'Jus tropical',
    prodJuiceText: 'Un mélange gourmand aux saveurs fruitées et très rafraîchissantes.',
    addCart: 'Acheter',
    tagDecor: 'Décoration',
    prodDecor: 'Accessoires maison',
    prodDecorText: 'Des pièces modernes pour donner une touche chic à votre intérieur.',
    tagMisc: 'Divers',
    prodMisc: 'Articles du quotidien',
    prodMiscText: 'Des produits utiles pour votre maison, votre routine et votre confort.',
    aboutLabel: 'Pourquoi nous choisir ?',
    aboutTitle: 'Un commerce moderne, simple et accessible.',
    aboutText:
      'Chez Sarjo.com, nous mettons l’accent sur la qualité, la fraîcheur et le service. Nous proposons des produits soigneusement sélectionnés pour répondre aux besoins de nos clients au quotidien.',
    statHours: 'Heures d’ouverture',
    statDaily: 'Disponible chaque jour',
    statPhone: 'Contact immédiat',
    footerText: 'Vente de jus, décoration intérieure et divers produits pour votre maison.',
    hoursLabelFooter: 'Horaires :',
    footerHours: 'Lundi au samedi : 9h - 16h'
  },
  en: {
    navHome: 'Home',
    navProducts: 'Products',
    navAbout: 'About',
    navContact: 'Contact',
    eyebrow: 'Online shop • GAMBIA',
    heroTitle: 'Fresh, elegant and useful products for your everyday life.',
    heroText:
      'Sarjo.com offers delicious juices, interior decoration items and a variety of products to beautify your home and meet your daily needs.',
    ctaShop: 'Order now',
    ctaCall: 'Call us',
    hoursLabel: 'Opening hours:',
    hoursText: 'Mon - Sat: 9am to 4pm',
    badgeFresh: 'Fresh juice',
    badgeDecor: 'Decoration',
    bestSeller: 'Best seller',
    juiceName: 'Daily juice',
    juiceDesc: 'Natural, refreshing and ready to drink.',
    featureFresh: 'Refreshing juices',
    featureFreshText: 'A selection of natural drinks to keep you energized and satisfied.',
    featureDecor: 'Interior decoration',
    featureDecorText: 'Elegant items to enhance your home and living space.',
    featureVaried: 'Various products',
    featureVariedText: 'Useful and varied items for a practical and pleasant shopping experience.',
    shopTitleLabel: 'Our catalog',
    shopTitle: 'Popular products',
    tagJuice: 'Juice',
    prodJuice: 'Tropical juice',
    prodJuiceText: 'A delicious blend with fruity, refreshing flavors.',
    addCart: 'Buy',
    tagDecor: 'Decoration',
    prodDecor: 'Home accessories',
    prodDecorText: 'Modern pieces to add a chic touch to your interior.',
    tagMisc: 'Miscellaneous',
    prodMisc: 'Everyday items',
    prodMiscText: 'Useful products for your home, your routine and your comfort.',
    aboutLabel: 'Why choose us?',
    aboutTitle: 'A modern, simple and accessible shop.',
    aboutText:
      'At Sarjo.com, we focus on quality, freshness and service. We offer carefully selected products to meet the needs of our customers every day.',
    statHours: 'Opening hours',
    statDaily: 'Available every day',
    statPhone: 'Immediate contact',
    footerText: 'Sale of juices, interior decoration and various products for your home.',
    hoursLabelFooter: 'Hours:',
    footerHours: 'Monday to Saturday: 9am - 4pm'
  }
};

const langButtons = document.querySelectorAll('.lang-btn');
const i18nNodes = document.querySelectorAll('[data-i18n]');

function applyLanguage(lang) {
  const langMap = translations[lang];
  if (!langMap) return;

  i18nNodes.forEach((node) => {
    const key = node.dataset.i18n;
    if (langMap[key]) {
      node.textContent = langMap[key];
    }
  });

  document.documentElement.lang = lang;

  langButtons.forEach((button) => {
    const isActive = button.dataset.lang === lang;
    button.classList.toggle('active', isActive);
  });
}

langButtons.forEach((button) => {
  button.addEventListener('click', () => applyLanguage(button.dataset.lang));
});

applyLanguage('fr');
