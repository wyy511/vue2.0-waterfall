<template lang="pug">
#waterfall 
    .cell(
        v-for="(list, index) in lists"
    )
        a(:href="list.url")
            img(:src="list.img")
        p
            a(href="/") {{index + '.' + list.title}} 

</template>

<script>
import './js/waterfall.js'
// $.fn.extend({
//     waterfall: function(opt) {
//         opt = opt || {};
//         setting = $.extend(setting, opt);
//         this.$waterfall = this.waterfall.$waterfall = $(this);
//         this.waterfall.$columns = createColumn();
//     }
// })
export default {
    name: 'app',
    data() {
        return {
            lists: [
                {
                    url: '#',
                    img: 'http://cued.xunlei.com/demos/publ/img/P_000.jpg',
                    title: '瀑布流demo'
                },
                {
                    url: '#',
                    img: 'http://cued.xunlei.com/demos/publ/img/P_001.jpg',
                    title: '瀑布流demo'
                },
                {
                    url: '#',
                    img: 'http://cued.xunlei.com/demos/publ/img/P_002.jpg',
                    title: '瀑布流demo'
                },
                {
                    url: '#',
                    img: 'http://cued.xunlei.com/demos/publ/img/P_003.jpg',
                    title: '瀑布流demo'
                },
                {
                    url: '#',
                    img: 'http://cued.xunlei.com/demos/publ/img/P_004.jpg',
                    title: '瀑布流demo'
                },
                {
                    url: '#',
                    img: 'http://cued.xunlei.com/demos/publ/img/P_005.jpg',
                    title: '瀑布流demo'
                },
                {
                    url: '#',
                    img: 'http://cued.xunlei.com/demos/publ/img/P_006.jpg',
                    title: '瀑布流demo'
                },
                {
                    url: '#',
                    img: 'http://cued.xunlei.com/demos/publ/img/P_007.jpg',
                    title: '瀑布流demo'
                },

                {
                    url: '#',
                    img: 'http://cued.xunlei.com/demos/publ/img/P_008.jpg',
                    title: '瀑布流demo'
                },{
                    url: '#',
                    img: 'http://cued.xunlei.com/demos/publ/img/P_009.jpg',
                    title: '瀑布流demo'
                },
                {
                    url: '#',
                    img: 'http://cued.xunlei.com/demos/publ/img/P_010.jpg',
                    title: '瀑布流demo'
                },
                {
                    url: '#',
                    img: 'http://cued.xunlei.com/demos/publ/img/P_011.jpg',
                    title: '瀑布流demo'
                },
                {
                    url: '#',
                    img: 'http://cued.xunlei.com/demos/publ/img/P_012.jpg',
                    title: '瀑布流demo'
                },
                {
                    url: '#',
                    img: 'http://cued.xunlei.com/demos/publ/img/P_013.jpg',
                    title: '瀑布流demo'
                },
                {
                    url: '#',
                    img: 'http://cued.xunlei.com/demos/publ/img/P_014.jpg',
                    title: '瀑布流demo'
                },
                {
                    url: '#',
                    img: 'http://cued.xunlei.com/demos/publ/img/P_015.jpg',
                    title: '瀑布流demo'
                },
                {
                    url: '#',
                    img: 'http://cued.xunlei.com/demos/publ/img/P_016.jpg',
                    title: '瀑布流demo'
                },
                {
                    url: '#',
                    img: 'http://cued.xunlei.com/demos/publ/img/P_017.jpg',
                    title: '瀑布流demo'
                },
                {
                    url: '#',
                    img: 'http://cued.xunlei.com/demos/publ/img/P_018.jpg',
                    title: '瀑布流demo'
                },
                {
                    url: '#',
                    img: 'http://cued.xunlei.com/demos/publ/img/P_019.jpg',
                    title: '瀑布流demo'
                },

            ],
            // setting: {
            //     column_width: 240,//列宽
            //     column_className: 'waterfall_column', //列的类名
            //     column_space: 10, //列间距
            //     cell_selector: '.cell',//要排列的砖块选择器，context为整个外部容器
            //     auto_imgHeight: true, //是否要自动计算图片的高度
            //     fadein: true,//是否渐显载入
            //     fadein_speed: 600,//渐显速率，单位毫秒
            //     insert_type: 1, //单元格插入方式，1为插入最短的那列，2为按顺序流插入
            //     getResource: function(index) {}//获取动态资源函数，必须放回一个砖块元素集合，传入参数为加载的次数
            // },
            // waterfall: {
            //     load_index: 0,//加载次数
            // },//对外信息对象
            // $_waterfall: {},//对外信息对象
            // $waterfall: null,//容器
            
        }
    },
    mounted() {
        let opt = {
            getResource: function(index, render) {
                if(index >= 7) index = index % 7 + 1;
                let html = '';
                for(let i = 20 * (index - 1); i < 20 * (index - 1) + 20; i++) {
                    let k = '';
                    for(let j = 0; j < 3 - i.toString().length; j++) {
                        k += '0';
                    }
                    k += i;
                    let src="http://cued.xunlei.com/demos/publ/img/P_" + k + '.jpg';
                    html += '<div class="cell"><a href="#"><img src="'+src+'" /></a><p>'+k+'</p></div>';
                }
                return $(html);
            },
            auto_imgHeight: true,
            insert_type: 1
        };
        $('#waterfall').waterfall(opt);
    }
}
</script>

<style lang="sass">
#waterfall 
    text-align: center;
    width: 1306px;
    margin: 0 auto;
    .cell 
        padding: 10px 0 5px 0;
        width: 223px;
        border: 1px solid #e3e3e3;
        background: #fff;
        margin-top: 1.25rem;
        box-shadow: 0 2px 3px 1px #ccc;
        img
            width: 203px;
        &:hover 
            box-shadow: 0 2px 3px 1px #999;
        
    
    

</style>
