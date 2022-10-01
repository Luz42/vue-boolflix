<template>
    <span :class="`fi fi-${fixFlag(isoFlag)}`"></span>
</template>

<script>
import "/node_modules/flag-icons/css/flag-icons.min.css";

    
export default {
    name: 'showFlagComponent',
    
    props:{
        isoFlag: String
    },
    methods: {
        fixFlag(isoFlag) {
             switch(isoFlag){
    
                case 'en':
                    return 'gb'

                case 'da':
                    return 'dk'
                
                case 'hi':
                    return 'in'

                case 'zh':
                    return 'cn'  
                
                case 'ja':
                    return 'jp'
                
                case 'ka':
                    return 'ge'

                case 'cs':
                    return 'cz'
    
                default:
                    return isoFlag;
             }
        }
        // case 'te':
        //     return 'Telugu' *in?*
        // case 'he':
        //     return 'Hebrew' *?*
    },
}
</script>

<style scoped lang="scss">

</style>