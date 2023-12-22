var apps = angular.module("myApp",["ngRoute"]);

apps.config(function($routeProvider){
	$routeProvider
	.when('/',{
		templateUrl:'pages/home.html',

	})

	.when('/entertainment',{
		templateUrl:'pages/entertainment.html',
		controller:'entertainmentCtrl',
	})
	.when('/movies',{
		templateUrl:'pages/movies.html',
		controller:'moviesCtrl',
	})
	.when('/songs',{
		templateUrl:'pages/songs.html',
		controller:'songsCtrl',
	})
	.when('/games',{
		templateUrl:'pages/games.html',
		controller:'gamesCtrl',
	})

	.when('/travel',{
		templateUrl:'pages/travel.html',
		controller:'travelCtrl',
	})

     .when('/adventureplaces',{
          templateUrl:'pages/adventureplaces.html',
          controller:'adventureplacesCtrl',
     })
     .when('/familyvisitplaces',{
          templateUrl:'pages/familyvisitplaces.html',
          controller:'familyvisitplacesCtrl',
     })
     .when('/religionplaces',{
          templateUrl:'pages/religionplaces.html',
          controller:'religionplacesCtrl',
     })
	.when('/trend',{
		templateUrl:'pages/trend.html',
		controller:'trendCtrl',
	})
     .when('/cloths',{
          templateUrl:'pages/cloths.html',
          controller:'clothsCtrl',
     })
     .when('/vehicles',{
          templateUrl:'pages/vehicles.html',
          controller:'vehiclesCtrl',
     })
     .when('/hotels',{
          templateUrl:'pages/hotels.html',
          controller:'hotelsCtrl',
     })
	.when('/electronics',{
		templateUrl:'pages/electronics.html',
		controller:'electronicsCtrl',
	})
     .when('/mobiles',{
          templateUrl:'pages/mobiles.html',
          controller:'mobilesCtrl',
     })
     .when('/computers',{
          templateUrl:'pages/computers.html',
          controller:'computersCtrl',
     })
     .when('/ac',{
          templateUrl:'pages/ac.html',
          controller:'acCtrl',
     })
	.when('/books',{
		templateUrl:'pages/books.html',
		controller:'booksCtrl',
	})
     .when('/novels',{
          templateUrl:'pages/novels.html',
          controller:'novelsCtrl',
     })
     .when('/hollybooks',{
          templateUrl:'pages/hollybooks.html',
          controller:'hollybooksCtrl',
     })
     .when('/fictionbooks',{
          templateUrl:'pages/fictionbooks.html',
          controller:'fictionbooksCtrl',
     })
});


apps.controller('indexCtrl',function($scope){
	

});
apps.controller('entertainmentCtrl',function($scope, entertainmentFactory){
	
	$scope.mainCategory = entertainmentFactory.getMainCategory();
});

apps.controller('moviesCtrl',function($scope, hollMoviesFactory, bollMoviesFactory){

	$scope.topHollMovies = hollMoviesFactory.getHollywoodMovies();
	$scope.topBollMovies = bollMoviesFactory.getBollywoodMovies();
});

apps.controller('songsCtrl',function($scope, hollSongsFactory, bollSongsFactory){
	
	$scope.topHollSongs = hollSongsFactory.getHollywoodSongs();
	$scope.topBollSongs = bollSongsFactory.getBollywoodSongs();
});

apps.controller('gamesCtrl',function($scope, mobGamesFactory, deskGamesFactory){
	
	$scope.topMobGames = mobGamesFactory.getMobileGames();
	$scope.topDeskGames = deskGamesFactory.getDesktopGames();
});
apps.controller('trendCtrl',function($scope,  trendFactory){
     
     $scope.mainCategory = trendFactory.getMainCategory();
     
    
});


apps.controller('clothsCtrl',function($scope, clothsFactory, footwearsFactory){
     
     $scope.topcloths = clothsFactory.getCloths();
     $scope.topfootwears = footwearsFactory.getFootwears();
});
apps.controller('vehiclesCtrl',function($scope, bikesFactory, carsFactory){
     
     $scope.topbikes = bikesFactory.getBikes();
     $scope.topcars = carsFactory.getCars();
});
apps.controller('hotelsCtrl',function($scope, hotelsFactory, hotels1Factory){
     
     $scope.top5hotels = hotelsFactory.getHotels();
     $scope.top3hotels = hotels1Factory.getHotels1();
});

apps.controller('travelCtrl',function($scope,  travelFactory){
     
     $scope.mainCategory = travelFactory.getMainCategory();
     
});

apps.controller('adventureplacesCtrl',function($scope,  adventureplacesFactory){
     
     $scope.topAdventure = adventureplacesFactory.getAdventureplaces();
     
});
apps.controller('familyvisitplacesCtrl',function($scope,  familyvisitplacesFactory){
     
     $scope.topFamily = familyvisitplacesFactory.getFamilyvisitplaces();
     
});
apps.controller('religionplacesCtrl',function($scope,  religionplacesFactory){
     
     $scope.topReligionplaces = religionplacesFactory.getReligionplaces();
     
});

apps.controller('booksCtrl',function($scope,  booksFactory){
     
     $scope.mainCategory = booksFactory.getMainCategory();
     
});

apps.controller('novelsCtrl',function($scope,  novelsFactory){
     
     $scope.topNovels = novelsFactory.getNovels();
     
});

apps.controller('hollybooksCtrl',function($scope,  hollybooksFactory){
     
     $scope.topHollybooks = hollybooksFactory.getHollybooks();
     
});
apps.controller('fictionbooksCtrl',function($scope,  fictionbooksFactory){
     
     $scope.topFictionbooks = fictionbooksFactory.getFictionbooks();
     
});

apps.controller('electronicsCtrl',function($scope,  electronicsFactory){
     
     $scope.mainCategory = electronicsFactory.getMainCategory();
     
});
apps.controller('mobilesCtrl',function($scope,  mobilesFactory){
     
     $scope.topMobiles = mobilesFactory.getMobiles();
     
});
apps.controller('computersCtrl',function($scope,  computersFactory){
     
     $scope.topComputers = computersFactory.getComputers();
     
});
apps.controller('acCtrl',function($scope,  acFactory){
     
     $scope.topAc = acFactory.getAc();
     
});

apps.factory('entertainmentFactory', function () {
  return {
       getMainCategory: function(){
          var array=[
          	{
          		"image" : "images/movie.jpg",
          		"name" : "Movies",
          		"link": "#!movies",
          	},
          	{
          		"image" : "images/songs.png",
          		"name" : "Songs",
          		"link": "#!songs",
          	},
          	{
          		"image" : "images/games.jpg",
          		"name" : "Games",
          		"link": "#!games",
          	},
               


          ]
          return array;
       }
   }
});
apps.factory('trendFactory', function () {
  return {
       getMainCategory: function(){
          var array=[
               {
                    "image" :"images/clothbrand.jpg",
                    "name"  :"Brands",
                    "link"  :"#!cloths",

               },
               {
                    "image" :"images/carbike.jpg",
                    "name"  :"Vehicles",
                    "link"  :"#!vehicles",
               },
               {

                    "image" :"images/hotel.jpg",
                    "name"  :"Hotels",
                    "link"  :"#!hotels",
               },
               

          ]
          return array;
       }
   }
});
apps.factory('travelFactory', function () {
  return {
       getMainCategory: function(){
          var array=[
              {
                    "image" :"images/adventure.jpg",
                    "name"  :"Adventure",
                    "link"  :"#!adventureplaces",

               },
               {
                    "image" :"images/family.jpg",
                    "name"  :"Tour",
                    "link"  :"#!familyvisitplaces",
               },
               {

                    "image" :"images/religious.jpg",
                    "name"  :"Religion",
                    "link"  :"#!religionplaces",
               },
               

          ]
          return array;
       }
   }
});

apps.factory('booksFactory', function () {
  return {
       getMainCategory: function(){
          var array=[
              {
                    "image" :"images/novels.jpg",
                    "name"  :"Novels",
                    "link"  :"#!novels",

               },
               {
                    "image" :"images/holybooks.jpg",
                    "name"  :"Holly",
                    "link"  :"#!hollybooks",
               },
               {

                    "image" :"images/fictionbooks.jpg",
                    "name"  :"Fiction",
                    "link"  :"#!fictionbooks",
               },
               

          ]
          return array;
       }
   }
});

apps.factory('electronicsFactory', function () {
  return {
       getMainCategory: function(){
          var array=[
              {
                    "image" :"images/mobile.jpg",
                    "name"  :"Mobile",
                    "link"  :"#!mobiles",

               },
               {
                    "image" :"images/computers.jpg",
                    "name"  :"Computer",
                    "link"  :"#!computers",
               },
               {

                    "image" :"images/acs.jpg",
                    "name"  :"Ac",
                    "link"  :"#!ac",
               },
               

          ]
          return array;
       }
   }
});


apps.factory('mobilesFactory', function () {

   return {

      getMobiles: function(){
          var array= [

               {
                    "rank":"1",
                    "image":"images/Samsung Galaxy S8.jpeg",
                    "imageName":"Samsung Galaxy S8",
                    "name" :"Samsung Galaxy S8",
               },
               {
                    "rank":"2",
                    "image":"images/Samsung Galaxy S8 Plus.jpeg",
                    "imageName":"Samsung Galaxy S8+",
                    "name" :"Samsung Galaxy S8+",
               },
               {
                    "rank":"3",
                    "image":"images/Google Pixel XL.jpeg",
                    "imageName":"Google Pixel XL",
                    "name" :"Google Pixel XL",
               },
               {
                    "rank":"4",
                    "image":"images/OnePlus 5.jpeg",
                    "imageName":"OnePlus 5",
                    "name" :"OnePlus 5",
               },
               {
                    "rank":"5",
                    "image":"images/LG G6.jpeg",
                    "imageName":"LG G6",
                    "name" :"LG G6",
               },
               {
                    "rank":"6",
                    "image":"images/Sony Xperia XZ Premium.jpeg",
                    "imageName":"Sony Xperia XZ Premium",
                    "name" :"Sony Xperia XZ Premium",
               },
               {
                    "rank":"7",
                    "image":"images/HTC U11.jpeg",
                    "imageName":"HTC U11",
                    "name" :"HTC U11",
               },
               { 
                    "rank":"8",
                    "image":"images/Samsung Galaxy S7 Edge.jpeg",
                    "imageName":"Samsung Galaxy S7 Edge",
                    "name" :"Samsung Galaxy S7 Edge",
               },
               {
                    "rank":"9",
                    "image":"images/OnePlus 3T.jpeg",
                    "imageName":"OnePlus 3T",
                    "name" :"OnePlus 3T",
               },
               {
                    "rank":"10",
                    "image":"images/Moto Z.jpeg",
                    "imageName":"Moto Z",
                    "name" :"Moto Z",
               },
          ]
          return array;
       }
          
     }
});

apps.factory('computersFactory', function () {

   return {

      getComputers: function(){
          var array= [

               {
                    "rank":"1",
                    "image":"images/Dell XPS Tower Special Edition.jpg",
                    "imageName":"Dell XPS Special Edition",
                    "name" :"Dell XPS Special Edition",
               },
               {
                    "rank":"2",
                    "image":"images/Surface Studio.jpg",
                    "imageName":"Surface Studio",
                    "name" :"Surface Studio",
               },
               {
                    "rank":"3",
                    "image":"images/Apple iMac with 5K Retina display (2015).jpg",
                    "imageName":"Apple iMac with 5K Retina display (2015)",
                    "name" :"Apple iMac with 5K Retina display (2015)",
               },
               {
                    "rank":"4",
                    "image":"images/Apple iMac with 4K Retina display (21.5-inch, Late 2015).jpg",
                    "imageName":"Apple iMac with 4K Retina display",
                    "name" :"Apple iMac with 4K Retina display",
               },
               {
                    "rank":"5",
                    "image":"images/Apple Mac mini.jpg",
                    "imageName":"Apple Mac mini",
                    "name" :"Apple Mac mini",
               },
               {
                    "rank":"6",
                    "image":"images/HP Pavilion Wave.jpg",
                    "imageName":"HP Pavilion Wave",
                    "name" :"HP Pavilion Wave",
               },
               {
                    "rank":"7",
                    "image":"images/Dell XPS 27 AIO.jpg",
                    "imageName":"Dell XPS 27 AIO",
                    "name" :"Dell XPS 27 AIO",
               },
               { 
                    "rank":"8",
                    "image":"images/2-in-1-precision-5720-mod-1.jpg",
                    "imageName":"Dell Precision 5720 All-in-One",
                    "name" :"Dell Precision 5720 All-in-One",
               },
               {
                    "rank":"9",
                    "image":"images/Asus VivoMini UN65U.jpg",
                    "imageName":"Asus VivoMini UN65U",
                    "name" :"Asus VivoMini UN65U",
               },
               {
                    "rank":"10",
                    "image":"images/hewlet.jpg",
                    "imageName":"Hewlett-Packard",
                    "name" :"Hewlett-Packard",
               },
          ]
          return array;
       }
          
     }
});


apps.factory('acFactory', function () {

   return {

      getAc: function(){
          var array= [

                {
                    "rank":"1",
                    "image":"images/kelvinator.jpg",
                    "imageName":"kelvinator",
                    "name" :"kelvinator",
               },
               {
                    "rank":"2",
                    "image":"images/whirlpool.jpg",
                    "imageName":"whirlpool",
                    "name" :"whirlpool",
               },
               {
                    "rank":"3",
                    "image":"images/blue-star.jpg",
                    "imageName":"blue-star",
                    "name" :"blue-star",
               },
               {
                    "rank":"4",
                    "image":"images/hyundai.jpg",
                    "imageName":"hyundai",
                    "name" :"hyundai",
               },
               {
                    "rank":"5",
                    "image":"images/LG.jpg",
                    "imageName":"LG",
                    "name" :"LG",
               },
               {
                    "rank":"6",
                    "image":"images/Voltas.jpg",
                    "imageName":"Voltas",
                    "name" :"Voltas",
               },
               {
                    "rank":"7",
                    "image":"images/videocon.jpg",
                    "imageName":"videocon",
                    "name" :"videocon",
               },
               { 
                    "rank":"8",
                    "image":"images/Samsung.jpg",
                    "imageName":"Samsung",
                    "name" :"Samsung",
               },
               {
                    "rank":"9",
                    "image":"images/Daikin.jpg",
                    "imageName":"Daikin",
                    "name" :"Daikin",
               },
               {
                    "rank":"10",
                    "image":"images/Mitashi.jpg",
                    "imageName":"Mitashi",
                    "name" :"Mitashi",
               },
          ]
          return array;
       }
          
     }
});
apps.factory('novelsFactory', function () {

   return {

      getNovels: function(){
          var array= [

               {
                    "rank":"1",
                    "image":"images/secretplace.jpg",
                    "imageName":"The Secret Place",
                    "name" :"The Secret Place",
               },
               {
                    "rank":"2",
                    "image":"images/boneclock.jpg",
                    "imageName":"The Bone Clocks",
                    "name" :"The Bone Clocks",
               },
               {
                    "rank":"3",
                    "image":"images/zoneinterest.jpg",
                    "imageName":"The Zone of Interest",
                    "name" :"The Zone of Interest",
               },
               {
                    "rank":"4",
                    "image":"images/redeploy.jpg",
                    "imageName":"Redeployment",
                    "name" :"Redeployment",
               },
               {
                    "rank":"5",
                    "image":"images/wonderland.jpg",
                    "imageName":"Wonderland",
                    "name" :"Wonderland",
               },
               {
                    "rank":"6",
                    "image":"images/whiskey.jpg",
                    "imageName":"Whiskey Tango Foxtrot",
                    "name" :"Whiskey Tango Foxtrot",
               },
               {
                    "rank":"7",
                    "image":"images/stationeleven.jpg",
                    "imageName":"Station Eleven",
                    "name" :"Station Eleven",
               },
               { 
                    "rank":"8",
                    "image":"images/euphoria.jpg",
                    "imageName":"Euphoria",
                    "name" :"Euphoria",
               },
               {
                    "rank":"9",
                    "image":"images/sevenkillings.jpg",
                    "imageName":"A Brief History of Seven Killings",
                    "name" :"A Brief History of Seven Killings",
               },
               {
                    "rank":"10",
                    "image":"images/laughingmonsters.jpg",
                    "imageName":"The Laughing Monsters",
                    "name" :"The Laughing Monsters",
               },
          ]
          return array;
       }
          
     }
});

apps.factory('hollybooksFactory', function () {

   return {

      getHollybooks: function(){
          var array= [

               {
                    "rank":"1",
                    "image":"images/christian.jpg",
                    "imageName":"Christianity,New Testament",
                    "name" :"Christianity,New Testament",
               },
               {
                    "rank":"2",
                    "image":"images/quran.jpg",
                    "imageName":"Islam,The HOly Quran",
                    "name" :"Islam,The HOly Quran",
               },
               {
                    "rank":"3",
                    "image":"images/geeta.jpg",
                    "imageName":"Hinduism,Shreemad Bhagavad Gita",
                    "name" :"Hinduism,Shreemad Bhagavad Gita",
               },
               {
                    "rank":"4",
                    "image":"images/buddhism.jpg",
                    "imageName":"Buddhism,Tripitakas",
                    "name" :"Buddhism,Tripitakas",
               },
               {
                    "rank":"5",
                    "image":"images/guru.jpg",
                    "imageName":"Sikhism,Guru Granth Sahib",
                    "name" :"Sikhism,Guru Granth Sahib",
               },
               {
                    "rank":"6",
                    "image":"images/torah.jpg",
                    "imageName":"Judaism,Torah",
                    "name" :"Judaism,Torah",
               },
               {
                    "rank":"7",
                    "image":"images/aqdas.jpg",
                    "imageName":"Baha'ism,Kitab-i-Aqdas",
                    "name" :"Baha'ism,Kitab-i-Aqdas",
               },
               { 
                    "rank":"8",
                    "image":"images/rites.jpg",
                    "imageName":"Confucianism,Book of Rites",
                    "name" :"Confucianism,Book of Rites",
               },
               {
                    "rank":"9",
                    "image":"images/agamas.jpg",
                    "imageName":"Jainism,The Agamas",
                    "name" :"Jainism,The Agamas",
               },
               {
                    "rank":"10",
                    "image":"images/kojiki.jpg",
                    "imageName":"Shintoism,kojiki",
                    "name" :"Shintoism,kojiki",
               },
          ]
          return array;
       }
          
       }
});

apps.factory('fictionbooksFactory', function () {

   return {

      getFictionbooks: function(){
          var array= [

               {
                    "rank":"1",
                    "image":"images/11.jpg",
                    "imageName":"Underground Railroad",
                    "name" :"Underground Railroad",
               },
               {
                    "rank":"2",
                    "image":"images/12.jpg",
                    "imageName":"Another Brooklyn",
                    "name" :"Another Brooklyn",
               },
               {
                    "rank":"3",
                    "image":"images/13.jpg",
                    "imageName":"Commonwealth",
                    "name" :"Commonwealth",
               },
               {
                    "rank":"4",
                    "image":"images/14.jpg",
                    "imageName":"Homegoing",
                    "name" :"Homegoing",
               },
               {
                    "rank":"5",
                    "image":"images/15.jpg",
                    "imageName":"All the Birds In the Sky",
                    "name" :"All the Birds In the Sky",
               },
               {
                    "rank":"6",
                    "image":"images/16.jpg",
                    "imageName":"Imagine Me Gone",
                    "name" :"Imagine Me Gone",
               },
               {
                    "rank":"7",
                    "image":"images/17.jpg",
                    "imageName":"Swing Time",
                    "name" :"Swing Time",
               },
               { 
                    "rank":"8",
                    "image":"images/18.jpg",
                    "imageName":"The Trespasser",
                    "name" :"The Trespasser",
               },
               {
                    "rank":"9",
                    "image":"images/19.jpg",
                    "imageName":"My Name Is Lucy Barton",
                    "name" :"My Name Is Lucy Barton",
               },
               {
                    "rank":"10",
                    "image":"images/20.jpg",
                    "imageName":"Here I Am",
                    "name" :"Here I Am",
               },
          ]
          return array;
       }
          
       }
});



apps.factory('adventureplacesFactory', function () {

   return {

      getAdventureplaces: function(){
          var array= [

               {
                    "rank":"1",
                    "image":"images/manali.jpg",
                    "imageName":"Manali",
                    "name" :"Manali",
               },
               {
                    "rank":"2",
                    "image":"images/bandhavgarh.jpg",
                    "imageName":"Bandhavgarh",
                    "name" :"Bandhavgarh",
               },
               {
                    "rank":"3",
                    "image":"images/kaziranga.jpg",
                    "imageName":"kaziranga",
                    "name" :"Kaziranga",
               },
               {
                    "rank":"4",
                    "image":"images/nagarhole.jpg",
                    "imageName":"Nagarhole",
                    "name" :"Nagarhole",
               },
               {
                    "rank":"5",
                    "image":"images/lahaul-spiti.jpg",
                    "imageName":"Lahaul-Spiti",
                    "name" :"Lahaul-Spiti",
               },
               {
                    "rank":"6",
                    "image":"images/Punakha.jpg",
                    "imageName":"Punakha",
                    "name" :"Punakha",
               },
               {
                    "rank":"7",
                    "image":"images/auli.jpg",
                    "imageName":"Auli",
                    "name" :"Auli",
               },
               { 
                    "rank":"8",
                    "image":"images/rishikesh.jpg",
                    "imageName":"Rishikesh",
                    "name" :"Rishikesh",
               },
               {
                    "rank":"9",
                    "image":"images/zanskar.jpg",
                    "imageName":"Zanskar",
                    "name" :"Zanskar",
               },
               {
                    "rank":"10",
                    "image":"images/pokhara.jpg",
                    "imageName":"Pokhara",
                    "name" :"Pokhara",
               },
          ]
          return array;
       }
          
       }
});


apps.factory('familyvisitplacesFactory',function(){

     return {
          
            getFamilyvisitplaces: function(){
          var array= [
               {
                    "rank":"1",
                    "image":"images/taj mahel.jpg",
                    "imageName":"Taj Mahal",
                    "name" :"Taj Mahal",
               },
               {
                    "rank":"2",
                    "image":"images/gangas.jpg",
                    "imageName":"Ganges",
                    "name" :"Ganges",
               },
               {
                    "rank":"3",
                    "image":"images/amerfort.jpg",
                    "imageName":"Amer Fort",
                    "name" :"Amer Fort",
               },
               {
                    "rank":"4",
                    "image":"images/qutubminar.jpg",
                    "imageName":"Qutb minor",
                    "name" :"Qutb minor",
               },
               {
                    "rank":"5",
                    "image":"images/1g.jpg",
                    "imageName":"Golden temple",
                    "name" :"Golden temple",
               },
               {
                    "rank":"6",
                    "image":"images/humayuns-tomb.jpg",
                    "imageName":"Humayun's tomb",
                    "name" :"Humayun's tomb",
               },
               {
                    "rank":"7",
                    "image":"images/agrafort.jpg",
                    "imageName":"Agra fort",
                    "name" :"Agra fort",
               },
               { 
                    "rank":"8",
                    "image":"images/India-Gate.jpg",
                    "imageName":"India gate",
                    "name" :"India gate",
               },
               {
                    "rank":"9",
                    "image":"images/Hawa_Mahal.jpg",
                    "imageName":"Hawa mahal",
                    "name" :"Hawa mahal",
               },
               {
                    "rank":"10",
                    "image":"images/Charminar.jpg",
                    "imageName":"charminar",
                    "name" :"charminar",
               },
          ]
          return array;
       }
     }
});

apps.factory('religionplacesFactory', function () {

   return {

      getReligionplaces: function(){
          var array= [

               {
                    "rank":"1",
                    "image":"images/472875-konark.jpg",
                    "imageName":"Sun Temple",
                    "name" :"Sun Temple",
               },
               {
                    "rank":"2",
                    "image":"images/Jagannath-Temple.jpg",
                    "imageName":"Jagannath Temple",
                    "name" :"Jagannath Temple",
               },
               {
                    "rank":"3",
                    "image":"images/Somnath-current_20170515143159.jpg",
                    "imageName":"Somnath Jyotirlinga",
                    "name" :"Somnath Jyotirlinga",
               },
               {
                    "rank":"4",
                    "image":"images/Tirumala Venkateswara Temple in Epics.png",
                    "imageName":"Tirumala Venkateswara",
                    "name" :"Tirumala Venkateswara",
               },
               {
                    "rank":"5",
                    "image":"images/HemkundSahib-536144_5.JPG",
                    "imageName":"Hemkund Sahib",
                    "name" :"Hemkund Sahib",
               },
               {
                    "rank":"6",
                    "image":"images/2016_12$largeimg03_Dec_2016_142725093.jpg",
                    "imageName":"Ajmer Sharif",
                    "name" :"Ajmer Sharif",
               },
               {
                    "rank":"7",
                    "image":"images/Velankanni-Church-HD-Wallpapers-8.jpg",
                    "imageName":"Velankanni Church",
                    "name" :"Velankanni Church",
               },
               { 
                    "rank":"8",
                    "image":"images/Amarnath-banner.jpg",
                    "imageName":"Amarnath Cave",
                    "name" :"Amarnath Cave",
               },
               {
                    "rank":"9",
                    "image":"images/2016_12$largeimg03_Dec_2016_142725093.jpg",
                    "imageName":"Mathura",
                    "name" :"Mathura",
               },
               {
                    "rank":"10",
                    "image":"images/zanskar.jpg",
                    "imageName":"Zanskar",
                    "name" :"Zanskar",
               },
          ]
          return array;
       }
          
     }
});

apps.factory('clothsFactory', function () {

   return {

      getCloths: function(){
          var array= [

               {
                    "rank":"1",
                    "image":"images/1.png",
                    "imageName":"Levi's",
                    "name" :"Levi's",
               },
               {
                    "rank":"2",
                    "image":"images/2.jpg",
                    "imageName":"Allen solly",
                    "name" :"Allen solly",
               },
               {
                    "rank":"3",
                    "image":"images/3.gif",
                    "imageName":"Pepe jeans",
                    "name" :"Pepe jeans",
               },
               {
                    "rank":"4",
                    "image":"images/4.jpg",
                    "imageName":"Provogue",
                    "name" :"Provogue",
               },
               {
                    "rank":"5",
                    "image":"images/5.jpg",
                    "imageName":"Park avenue",
                    "name" :"Park avenue",
               },
               {
                    "rank":"6",
                    "image":"images/6.jpg",
                    "imageName":"Van Heusen",
                    "name" :"Van Heusen",
               },
               {
                    "rank":"7",
                    "image":"images/7.jpg",
                    "imageName":"Numero uno",
                    "name" :"Numero uno",
               },
               { 
                    "rank":"8",
                    "image":"images/8.png",
                    "imageName":"Flying Machine",
                    "name" :"Flying Machine",
               },
               {
                    "rank":"9",
                    "image":"images/9.png",
                    "imageName":"Wrangler",
                    "name" :"Wrangler",
               },
               {
                    "rank":"10",
                    "image":"images/10.png",
                    "imageName":"Spykar",
                    "name" :"Spykar",
               },
          ]
          return array;
       }
          
     }
});

apps.factory('footwearsFactory',function(){

     return {
          
            getFootwears: function(){
          var array= [
          
               {
                    "rank":"1",
                    "image":"images/re.jpg",
                    "imageName":"Reebok",
                    "name" :"Reebok",
               },
              {
                    "rank":"2",
                    "image":"images/ba.jpg",
                    "imageName":"Bata",
                    "name" :"Bata",
               },
              {
                    "rank":"3",
                    "image":"images/nike.jpg",
                    "imageName":"Nike",
                    "name" :"Nike",
               },
              {
                    "rank":"4",
                    "image":"images/ad.jpg",
                    "imageName":"Adidas",
                    "name" :"Adidas",
               },
              {
                    "rank":"5",
                    "image":"images/li.jpg",
                    "imageName":"Liberty",
                    "name" :"Liberty",
               },
              {
                    "rank":"6",
                    "image":"images/wo.jpg",
                    "imageName":"Woodland",
                    "name" :"Woodland",
               },
               {
                    "rank":"7",
                    "image":"images/va.jpg",
                    "imageName":"Valentino",
                    "name" :"Valentino",
               },
               {
                    "rank":"8",
                    "image":"images/8d.jpg",
                    "imageName":"Converse",
                    "name" :"Converse",
               },
               {
                    "rank":"9",
                    "image":"images/la.jpg",
                    "imageName":"Lancer",
                    "name" :"Lancer",
               },
               {
                    "rank":"10",
                    "image":"images/10d.jpg",
                    "imageName":"Lotto",
                    "name" :"Lotto",
               },
               
          ]
          return array;
       }
     }
});

apps.factory('bikesFactory', function () {

   return {

      getBikes: function(){
          var array= [

               {
                    "rank":"1",
                    "image":"images/1B.jpg",
                    "imageName":"Honda Activa 4G",
                    "name" :"Honda Activa 4G",
               },
               {
                    "rank":"2",
                    "image":"images/2B.jpg",
                    "imageName":"Royal Enfield Classic 350",
                    "name" :"Royal Enfield Classic 350",
               },
               {
                    "rank":"3",
                    "image":"images/3B.jpg",
                    "imageName":"Bajaj Dominar 400",
                    "name" :"Bajaj Dominar 400",
               },
               {
                    "rank":"4",
                    "image":"images/4B.jpg",
                    "imageName":"Honda CB Shine",
                    "name" :"Honda CB Shine",
               },
               {  
                    "rank":"5",
                    "image":"images/5B.jpg",
                    "imageName":"TVS Apache RTR 160",
                    "name" :"TVS Apache RTR 160",
               },
               {
                    "rank":"6",
                    "image":"images/6B.jpg",
                    "imageName":"Bajaj Pulsar 150",
                    "name" :"Bajaj Pulsar 150",
               },
               {
                    "rank":"7",
                    "image":"images/7B.jpg",
                    "imageName":"Royal Enfield Bullet 350",
                    "name" :"Royal Enfield Bullet 350",
               },
               {
                    "rank":"8",
                    "image":"images/8B.jpg",
                    "imageName":"Honda CB Hornet 160R",
                    "name" :"Honda CB Hornet 160R",
               },
               {
                    "rank":"9",
                    "image":"images/9B.jpg",
                    "imageName":"Hero HF Deluxe",
                    "name" :"Hero HF Deluxe",
               },
               {
                    "rank":"10",
                    "image":"images/10B.jpg",
                    "imageName":"TVS Jupiter",
                    "name" :"TVS Jupiter",
               },
          ]
          return array;
       }
          
     }
});

apps.factory('carsFactory', function () {

   return {

      getCars: function(){
          var array= [

               {
                    "rank":"1",
                    "image":"images/1C.jpg",
                    "imageName":"Ford Ecosport",
                    "name" :"Ford Ecosport",
               },
              {
                    "rank":"2",
                    "image":"images/2C.jpg",
                    "imageName":"New-Gen Hyundai Verna",
                    "name" :"New-Gen Hyundai Verna",
               },
               {
                    "rank":"3",
                    "image":"images/3C.jpg",
                    "imageName":"Nissan X-Trail hybrid",
                    "name" :"Nissan X-Trail hybrid",
               },
               {
                    "rank":"4",
                    "image":"images/4C.jpg",
                    "imageName":"New-Gen Toyota Camry",
                    "name" :"New-Gen Toyota Camry",
               },
               {
                    "rank":"5",
                    "image":"images/5C.jpg",
                    "imageName":"Maruti Suzuki Ciaz",
                    "name" :"Maruti Suzuki Ciaz",
               },
               {
                    "rank":"6",
                    "image":"images/6C.jpg",
                    "imageName":"Skoda kodiaq",
                    "name" :"Skoda kodiaq",
               },
               {
                    "rank":"7",
                    "image":"images/7C.jpg",
                    "imageName":"Renault Kaptur",
                    "name" :"Renault Kaptur",
               },
               {
                    "rank":"8",
                    "image":"images/8C.jpg",
                    "imageName":"Maruti Suzuki S-Cross",
                    "name" :"Maruti Suzuki S-Cross",
               },
               {
                    "rank":"9",
                    "image":"images/9C.jpg",
                    "imageName":"Ford Figo",
                    "name" :"Ford Figo",
               },
               {
                    "rank":"10",
                    "image":"images/10C.jpg",
                    "imageName":"Mahindra KUV100",
                    "name" :"Mahindra KUV100",
               },
          ]
          return array;
       }
          
       }
});

apps.factory('hotelsFactory', function () {

   return {

      getHotels: function(){
          var array= [

               {
                    "rank":"1",
                    "image":"images/hh1.jpg",
                    "imageName":"The oberoi Udaivilas,Udipur",
                    "name" :"The oberoi Udaivilas,Udipur",
               },
              {
                    "rank":"2",
                    "image":"images/hh2.jpg",
                    "imageName":"The Taj Mahal Palace,Mumbai",
                    "name" :"The Taj Mahal Palace,Mumbai",
               },
               {
                    "rank":"3",
                    "image":"images/hh3.jpg",
                    "imageName":"The oberoi Rajvilas,Jaipur",
                    "name" :"The oberoi Rajvilas,Jaipur",
               },
               {
                    "rank":"4",
                    "image":"images/hh4.jpg",
                    "imageName":"Taj Lake Palace,Udaipur",
                    "name" :"Taj Lake Palace,Udaipur",
               },
               {
                    "rank":"5",
                    "image":"images/hh5.jpg",
                    "imageName":"Maruti Suzuki Ciaz",
                    "name" :"Maruti Suzuki Ciaz",
               },
               {
                    "rank":"6",
                    "image":"images/hh6.jpg",
                    "imageName":"Taj Falaknuma Palace,Hyderabad",
                    "name" :"Taj Falaknuma Palace,Hyderabad",
               },
               {
                    "rank":"7",
                    "image":"images/hh7.jpg",
                    "imageName":"Wildflower Hall,Shimla",
                    "name" :"Wildflower Hall,Shimla",
               },
               {
                    "rank":"8",
                    "image":"images/hh8.jpg",
                    "imageName":"Leela Palace,Banglore",
                    "name" :"Leela Palace,Banglore",
               },
               {
                    "rank":"9",
                    "image":"images/hh9.jpg",
                    "imageName":"Leela Palace,New Delhi",
                    "name" :"Leela Palace,New Delhi",
               },
               {
                    "rank":"10",
                    "image":"images/hh10.jpg",
                    "imageName":"Vivanta Taj-Malabar,Kochi",
                    "name" :"Vivanta Taj-Malabar,Kochi",
               },
         
          ]
          return array;
       }
          
       }
});

apps.factory('hotels1Factory', function () {

   return {

      getHotels1: function(){
          var array= [

               {
                    "rank":"1",
                    "image":"images/h1.jpg",
                    "imageName":"Hotel Rajwada Resort,Jaipur",
                    "name" :"Hotel Rajwada Resort,Jaipur",
               },
              {
                    "rank":"2",
                    "image":"images/h2.jpg",
                    "imageName":"global Access Hotel,Kolkata",
                    "name" :"global Access Hotel,Kolkata",
               },
               {
                    "rank":"3",
                    "image":"images/h3.jpg",
                    "imageName":"Innate Hotel,Kolkata",
                    "name" :"Innate Hotel,Kolkata",
               },
               {
                    "rank":"4",
                    "image":"images/h4.jpg",
                    "imageName":"Hotel York,Delhi",
                    "name" :"Hotel York,Delhi",
               },
               {
                    "rank":"5",
                    "image":"images/h5.jpg",
                    "imageName":"DS Designers Hotel,Gaziabad",
                    "name" :"DS Designers Hotel,Gaziabad",
               },
               {
                    "rank":"6",
                    "image":"images/h6.jpg",
                    "imageName":"Amarpreet Hotel,Aurangabad",
                    "name" :"Amarpreet Hotel,Aurangabad",
               },
               {
                    "rank":"7",
                    "image":"images/h7.jpg",
                    "imageName":"Sky Blue Resort,Lonavala",
                    "name" :"Sky Blue Resort,Lonavala",
               },
               {
                    "rank":"8",
                    "image":"images/h8.jpg",
                    "imageName":"Hotel B.R. Inn,Panipat",
                    "name" :"Hotel B.R. Inn,Panipat",
               },
               {
                    "rank":"9",
                    "image":"images/h9.jpg",
                    "imageName":"Plan Trip Mumbai Hotel",
                    "name" :"Plan Trip Mumbai Hotel",
               },
               {
                    "rank":"10",
                    "image":"images/h10.jpg",
                    "imageName":"Hotel MKm rich",
                    "name" :"Hotel MKm rich",
               },
         
          ]
          return array;
       }
          
       }
});








apps.factory('hollMoviesFactory', function () {

   return {

      getHollywoodMovies: function(){
          var array= [

          	{	"rank" : "1",
          		"image" : "images/Avatar.png",
          		"imageName":"Avatar",
          		"name" : "Avatar",
          	},
          	{	"rank" : "2",
          		"image" : "images/deadpool.png",
          		"imageName":"Deadpool",
          		"name" : "Deadpool",
          	},
          	{	"rank" : "3",
          		"image" : "images/thejunglebook.png",
          		"imageName":"The Jungle Book",
          		"name" : "The Jungle Book",
          	},
          	{	"rank" : "4",
          		"image" : "images/transformers.png",
          		"imageName":"transformers:Dark Of The Moon",
          		"name" : "transformers:Dark Of The Moon",
          	},
          	{	"rank" : "5",
          		"image" : "images/fate.jpeg",
          		"imageName":"The Fate Of The Furious",
          		"name" : "The Fate Of The Furious",
          	},
          	{	"rank" : "6",
          		"image" : "images/ghost.png",
          		"imageName":"Ghost Riders",
          		"name" : "Ghost Riders",
          	},
          	{	"rank" : "7",
          		"image" : "images/logan.jpg",
          		"imageName":"Logan",
          		"name" : "Logan",
          	},
          	{	"rank" : "8",
          		"image" : "images/annabele.jpg",
          		"imageName":"Annabelle",
          		"name" : "Annabelle",
          	},
          	{	"rank" : "9",
          		"image" : "images/despicable.jpg",
          		"imageName":"Despicable Me 3",
          		"name" : "Despicable Me 3",
          	},
          	{	"rank" : "10",
          		"image" : "images/fun.jpg",
          		"imageName":"Fantastic 4",
          		"name" : "Fantastic 4",
          	},
          	
          ]
          return array;
       }
          
       }
});

apps.factory('bollMoviesFactory',function(){

	return {
     	
		  getBollywoodMovies: function(){
          var array= [
          
          	{	"rank" : "1",
          		"image" : "images/dangal.jpg",
          		"imageName":"Dangal",
          		"name" : "Dangal",
          	},
          	{	"rank" : "2",
          		"image" : "images/happy.jpg",
          		"imageName":"Happy New Year",
          		"name" : "Happy New Year",
          	},
          	{	"rank" : "3",
          		"image" : "images/kabil.jpg",
          		"imageName":"Kabil",
          		"name" : "Kabil",
          	},
          	{	"rank" : "4",
          		"image" : "images/bahubali.jpg",
          		"imageName":"Bahubali",
          		"name" : "Bahubali",
          	},
          	{	"rank" : "5",
          		"image" : "images/toilet.jpg",
          		"imageName":"Toilet - Ek Prem Katha",
          		"name" : "Toilet - Ek Prem Katha",
          	},
          	{	"rank" : "6",
          		"image" : "images/chennai.jpg",
          		"imageName":"Chennai Express",
          		"name" : "Chennai Express",
          	},
          	{	"rank" : "7",
          		"image" : "images/bajirao.jpg",
          		"imageName":"Bajirao Mastani",
          		"name" : "Bajirao Mastani",
          	},
          	{	"rank" : "8",
          		"image" : "images/jawani.jpg",
          		"imageName":"Yeh Jawaani Hai Deewani",
          		"name" : "Yeh Jawaani Hai Deewani",
          	},
          	{	"rank" : "9",
          		"image" : "images/dhoni.jpg",
          		"imageName":"M.S.Dhoni",
          		"name" : "M.S.Dhoni",
          	},
          	{	"rank" : "10",
          		"image" : "images/jindgai.jpg",
          		"imageName":"Zindagi Na Milegi Dobara",
          		"name" : "Zindagi Na Milegi Dobara",
          	},
          	
          ]
          return array;
       }
     }
});

apps.factory('hollSongsFactory',function(){

	return {
     	
		  getHollywoodSongs: function(){
          var array= [
          
          	{	"rank" : "1",
          		"image" : "images/images.jpg",
          		"imageName":"Somebody To Love",
          		"name" : "Somebody To Love",
          	},
          	{	"rank" : "2",
          		"image" : "images/never.jpg",
          		"imageName":"Never Let You Go",
          		"name" : "Never Let You Go",
          	},
          	{	"rank" : "3",
          		"image" : "images/heart.jpg",
          		"imageName":"HeartBreaker",
          		"name" : "HeartBreaker",
          	},
          	{	"rank" : "4",
          		"image" : "images/minute.jpg",
          		"imageName":"Wait For A Minute",
          		"name" : "Wait For A Minute",
          	},
          	{	"rank" : "5",
          		"image" : "images/all.jpg",
          		"imageName":"All Around The World",
          		"name" : "All Around The World",
          	},
          	{	"rank" : "6",
          		"image" : "images/life.jpg",
          		"imageName":"Life Is Worth Living",
          		"name" : "Life Is Worth Living",
          	},
          	{	"rank" : "7",
          		"image" : "images/matters.jpg",
          		"imageName":"All That Matters",
          		"name" : "All That Matters",
          	},
          	{	"rank" : "8",
          		"image" : "images/smile.jpg",
          		"imageName":"You Smile",
          		"name" : "You Smile",
          	},
          	{	"rank" : "9",
          		"image" : "images/confident.jpg",
          		"imageName":"Confident",
          		"name" : "Confident",
          	},
          	{	"rank" : "10",
          		"image" : "images/time.jpg",
          		"imageName":"One Time",
          		"name" : "One Time",
          	},
          	
          ]
          return array;
       }
     }
});

apps.factory('bollSongsFactory',function(){

	return {
     	
		  getBollywoodSongs: function(){
          var array= [
          
          	{	"rank" : "1",
          		"image" : "images/entry.jpg",
          		"imageName":"Tune Marri Entry Yaar",
          		"name" : "Tune Mari Entry Yaar",
          	},
          	{	"rank" : "2",
          		"image" : "images/baby.jpg",
          		"imageName":"Baby Ko Base Pasand Hai",
          		"name" : "Baby Ko Base Pasand Hai",
          	},
          	{	"rank" : "3",
          		"image" : "images/banjara.jpg",
          		"imageName":"Banjara",
          		"name" : "Banjara",
          	},
          	{	"rank" : "4",
          		"image" : "images/manwa.jpg",
          		"imageName":"Manwa",
          		"name" : "Manwa",
          	},
          	{	"rank" : "5",
          		"image" : "images/breakup.jpg",
          		"imageName":"BreakUp Song",
          		"name" : "BreakUp Song",
          	},
          	{	"rank" : "6",
          		"image" : "images/chiti.jpg",
          		"imageName":"Chittiyan Kallaiya",
          		"name" : "Chittiya Kallaiya",
          	},
          	{	"rank" : "7",
          		"image" : "images/enna.jpg",
          		"imageName":"Enna Sonna",
          		"name" : "Enna Sonna",
          	},
          	{	"rank" : "8",
          		"image" : "images/sooraj.jpg",
          		"imageName":"Suraj Dooba Hai",
          		"name" : "Suraj Dooba Hai",
          	},
          	{	"rank" : "9",
          		"image" : "images/humma.jpg",
          		"imageName":"Humma Song",
          		"name" : "Humma Song",
          	},
          	{	"rank" : "10",
          		"image" : "images/o.jpg",
          		"imageName":"O Re Piya",
          		"name" : "O Re Piya",
          	},
          	
          ]
          return array;
       }
     }
});

apps.factory('mobGamesFactory',function(){

	return {
     	
		  getMobileGames: function(){
          var array= [
          
          	{	"rank" : "1",
          		"image" : "images/pokemon.jpg",
          		"imageName":"Pokemon Go",
          		"name" : "Pokemon Go",
          	},
          	{	"rank" : "2",
          		"image" : "images/clash.jpg",
          		"imageName":"Clash Of Clans",
          		"name" : "Clash Of Clans",
          	},
          	{	"rank" : "3",
          		"image" : "images/subway.jpg",
          		"imageName":"Subway Surfers",
          		"name" : "Subway Surfers",
          	},
          	{	"rank" : "4",
          		"image" : "images/candy.jpg",
          		"imageName":"Candy Crush Saga",
          		"name" : "Candy Crush Saga",
          	},
          	{	"rank" : "5",
          		"image" : "images/crash.jpg",
          		"imageName":"Crash Land",
          		"name" : "Crash Land",
          	},
          	{	"rank" : "6",
          		"image" : "images/temple.jpg",
          		"imageName":"Temple Run",
          		"name" : "Temple Run",
          	},
          	{	"rank" : "7",
          		"image" : "images/fruit.jpg",
          		"imageName":"Fruit Ninja",
          		"name" : "Fruit Ninja",
          	},
          	{	"rank" : "8",
          		"image" : "images/adventure.jpg",
          		"imageName":"Alto's Adventure",
          		"name" : "Alto's Adventure",
          	},
          	{	"rank" : "9",
          		"image" : "images/racing.jpg",
          		"imageName":"Real Racing 3",
          		"name" : "Real Racing 3",
          	},
          	{	"rank" : "10",
          		"image" : "images/monument.jpg",
          		"imageName":"Monument Valley",
          		"name" : "Monument Valley",
          	},
          	
          ]
          return array;
       }
     }
});

apps.factory('deskGamesFactory',function(){

	return {
     	
		  getDesktopGames: function(){
          var array= [
          
          	{	"rank" : "1",
          		"image" : "images/battlefield1.jpg",
          		"imageName":"Battle Field",
          		"name" : "Battle Field 1",
          	},
          	{	"rank" : "2",
          		"image" : "images/DarkSouls3.jpg",
          		"imageName":"Dark Souls",
          		"name" : "Dark Souls 3",
          	},
          	{	"rank" : "3",
          		"image" : "images/Farcry.jpg",
          		"imageName":"Far Cry",
          		"name" : "Far Cry",
          	},
          	{	"rank" : "4",
          		"image" : "images/FInalfantasyXV.jpg",
          		"imageName":"Final Fantasy XV",
          		"name" : "Final Fantasy XV",
          	},
          	{	"rank" : "5",
          		"image" : "images/grandTheft.jpg",
          		"imageName":"Grand Theft",
          		"name" : "Grand Theft",
          	},
          	{	"rank" : "6",
          		"image" : "images/halflife.jpg",
          		"imageName":"Half Life",
          		"name" : "Half Life",
          	},
          	{	"rank" : "7",
          		"image" : "images/leagueOgLegends.jpg",
          		"imageName":"League Of Legends",
          		"name" : "League Of Legends",
          	},
          	{	"rank" : "8",
          		"image" : "images/minecraft.jpg",
          		"imageName":"MineCraft",
          		"name" : "MindCraft",
          	},
          	{	"rank" : "9",
          		"image" : "images/sunlessSea.jpg",
          		"imageName":"Sunless Sea",
          		"name" : "Sunless Sea",
          	},
          	{	"rank" : "10",
          		"image" : "images/undertale.jpg",
          		"imageName":"UnderTale",
          		"name" : "UnderTale",
          	},
          	
          ]
          return array;
       }
     }
});
