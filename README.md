# SwiperAnimationJquery



// Import Swiper React components
import { Swiper, SwiperSlide } from 'swiper/react';
import $ from 'jquery';
// Import Swiper styles
import 'swiper/swiper.scss';

export default () => {
   
    const t = (index)=>{
       
$(`#${index}`).animate({
    width:'+=30px'
}).animate({
    width:'-=30px'
})
    }
   
  return (
    <Swiper
    pagination={{ clickable: true }}
      scrollbar={{ draggable: true }}
      spaceBetween={50}
      slidesPerView={3}
      onSlideChange={(e) => console.log(e)}
      onSwiper={(swiper) => console.log(swiper)}
      onTouchStart={()=>console.log('hi')}
      
    >
       {[1,2,3,4].map((e,index)=>

       
      <SwiperSlide >
           <img src='3.jpg' id={index} key={index} onMouseOver={()=>t(index)}
       />
       </SwiperSlide>
    ) }
     
      
    </Swiper>
  );
};
