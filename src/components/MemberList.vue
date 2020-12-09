<template>
    <div class="members">
        <div class="container">
            <ul>
                <li>
                    <button>
                        twentio
                    </button>
                </li>
            </ul>
        </div>
    </div>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";

interface Member {
    name: string;
    logo: string;
    summary: string;
    description: string;
    contactPlace: string;
    contactEmail: string;
    images: string[];
}



export default class MemberList extends Vue {
    members: Member[]=[{
        name:'',
        logo:'',
        summary:'',
        description:'',
        contactPlace:'',
        contactEmail:'',
        images:[],
    }]
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  
</style>