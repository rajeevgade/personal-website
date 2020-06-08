<template>
    <div>
        <span id="txt-rotate"></span>
    </div>
</template>

<script>
export default {
    props: {
        rotateData: {
            type: Array,
            require: false,
            default: () => []
        },
        rotatePeriod: {
            type: Number,
            require: false,
            default: 2000
        }
    },
    data() {
        return {
            loopNum: 0,
            isDeleting: true,
            txt: '',
            el: '',
            period: 0,
            toRotate: []
        }
    },
    mounted(){
        this.initData()
    },
    methods: {
        initData(){
            var element = document.getElementById('txt-rotate');
            this.toRotate = this.rotateData
            this.period = parseInt(this.rotatePeriod, 10) || 2000;
            this.txt = '';
            this.el = element
            this.rotateText();
            this.isDeleting = false;

            var css = document.createElement("style");
            css.type = "text/css";
            css.innerHTML = ".wrap { border-right: 0.08em solid #666 }";
            document.body.appendChild(css);
        },

        rotateText() {
            var i = this.loopNum % this.toRotate.length;
            var fullTxt = this.toRotate[i];

            if (this.isDeleting) {
                this.txt = fullTxt.substring(0, this.txt.length - 1);
            } else {
                this.txt = fullTxt.substring(0, this.txt.length + 1);
            }

            this.el.innerHTML = '<span class="wrap">'+this.txt+'</span>';

            var delta = 100;

            if (this.isDeleting) { delta /= 2; }

            if (!this.isDeleting && this.txt === fullTxt) {
                delta = this.period;
                this.isDeleting = true;
            } else if (this.isDeleting && this.txt === '') {
                this.isDeleting = false;
                this.loopNum++;
                delta = 500;
            }

            setTimeout(() => { this.rotateText() }, delta);
        }
    }
}
</script>