<template>
    <div id='first'>
        <Modal />
        <Footer />
    </div>
</template>

<script>
    import Modal from "@/components/Modal";
    import Footer from "@/components/Footer";
    export default {
        name: "Front",
        components: {
            Modal,
            Footer
        }
    };
</script>

<style>
    /* @keyframes backgroundAnimation {
        0% {
            background-image: url('https://s-media-cache-ak0.pinimg.com/originals/3d/4f/e6/3d4fe6bccddfd3b049ac90242bdce148.jpg');
        }
        8% {
            background-image: url('https://s-media-cache-ak0.pinimg.com/originals/3d/4f/e6/3d4fe6bccddfd3b049ac90242bdce148.jpg');
        }
        10% {
            background-image: url('https://gezgin-cift.webnode.com.tr/_files/200000706-c39fcc4992/12967484_1696177410671621_2910202682994657411_o.jpg');
        }
        18% {
            background-image: url('https://gezgin-cift.webnode.com.tr/_files/200000706-c39fcc4992/12967484_1696177410671621_2910202682994657411_o.jpg');
        }
        20% {
            background-image: url('https://i.pinimg.com/originals/23/e2/f8/23e2f8ecd201b4a6f772aa1e4f93a134.jpg');
        }
        28% {
            background-image: url('https://i.pinimg.com/originals/23/e2/f8/23e2f8ecd201b4a6f772aa1e4f93a134.jpg');
        }
        30% {
            background-image: url('https://i.ytimg.com/vi/Xw2KcAWkHDA/maxresdefault.jpg');
        }
        38% {
            background-image: url('https://i.ytimg.com/vi/Xw2KcAWkHDA/maxresdefault.jpg');
        }
        40% {
            background-image: url('https://onelifetimetrip.com/wp-content/uploads/2018/07/NewYork.jpg');
        }
        48% {
            background-image: url('https://onelifetimetrip.com/wp-content/uploads/2018/07/NewYork.jpg');
        }
        50% {
            background-image: url('https://throwbackpackerblog.files.wordpress.com/2017/09/pa233512.jpg?w=1280&h=768&crop=1');
        }
        58% {
            background-image: url('https://throwbackpackerblog.files.wordpress.com/2017/09/pa233512.jpg?w=1280&h=768&crop=1');
        }
        60% {
            background-image: url('https://traveloregon.com/wp-content/uploads/2018/04/2018Summer_family_tramway.jpg');
        }
        68% {
            background-image: url('https://traveloregon.com/wp-content/uploads/2018/04/2018Summer_family_tramway.jpg');
        }
        70% {
            background-image: url('https://summitvoice.files.wordpress.com/2014/04/breck.jpg');
        }
        78% {
            background-image: url('https://summitvoice.files.wordpress.com/2014/04/breck.jpg');
        }
        80% {
            background-image: url('https://s-ec.bstatic.com/images/hotel/max1280x900/333/33318644.jpg');
        }
        88% {
            background-image: url('https://s-ec.bstatic.com/images/hotel/max1280x900/333/33318644.jpg');
        }
        90% {
            background-image: url('https://cdn.allwallpaper.in/wallpapers/1280x768/15496/beautiful-switzerland-landscape-1280x768-wallpaper.jpg');
        }
        98% {
            background-image: url('https://cdn.allwallpaper.in/wallpapers/1280x768/15496/beautiful-switzerland-landscape-1280x768-wallpaper.jpg');
        }
        100% {
            background-image: url('https://s-media-cache-ak0.pinimg.com/originals/3d/4f/e6/3d4fe6bccddfd3b049ac90242bdce148.jpg');
        }
    } */
    
      body {
        background-image: url('https://i.gocollette.com/img/destination-page/europe/switzerland/switzerland-mustsee-v2.jpg?h=720&w=1280&la=en-NZ');
        height: 100vh;
        background-repeat: no-repeat;
        background-size: cover;
        background-attachment: fixed; 
    }
</style>