<template>
    <div class="modal fade" tabindex="-1" role="dialog" id="modalOptionsTeeth" >
        <div class="modal-dialog" role="document">
            <div class="modal-content">
            <div class="modal-header">
                <h5 class="modal-title">Modal title</h5>
                <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                <span aria-hidden="true">&times;</span>
                </button>
            </div>
            <div class="modal-body">
                <p>Modal body text goes here.</p>
            </div>
            <div class="modal-footer">
                <button type="button" class="btn btn-primary">Save changes</button>
                <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
            </div>
            </div>
        </div>
    </div>
</template>

<script>
import { onMounted } from 'vue'
export default {
    name: 'modalOptionsTeeth',
    props: {
        teeth: {
            default: null,
            required: true,
            type: Object
        }
    },
    setup() {
        onMounted(()=>{
            document.querySelector('#modalOptionsTeeth').modal('show');
        })

        return {

        }
    },
}
</script>
