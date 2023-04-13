<template>
    <div class="modal" ref="modal">
    <div class="modal-dialog">
        <div class="modal-content">
        <!-- Encabezado del modal -->
        <div class="modal-header">
            <h5 class="modal-title">Diente seleccionado: {{ teeth.id }}</h5>
            <button type="button" class="close" data-dismiss="modal" aria-label="Close">
            <span aria-hidden="true">&times;</span>
            </button>
        </div>
        <!-- Cuerpo del modal -->
        <div class="modal-body">
            <div class="row">
                <div class="col-12 mb-2">
                    <p>Diagnostico actual:</p>
                </div>
                <div class="col-12 mb-2">
                    <img :src="teeth.img" class="img-fluid img" width="80" alt="">
                </div>

                <div class="col-12 mb-2">
                    <p>Nuevo diagnostico:</p>
                </div>
                <div v-for="(item) in diagnosesToChoose" @click="diagnosisSelected = item"
                    :class="[{'mouseoverSelecction':mouseoverSelecction===item.diagnosisKey, 
                        'divDiagnosisSelected':diagnosisSelected && diagnosisSelected.diagnosisKey === item.diagnosisKey}, 
                        'col-md-3 col-sm-6 mb-2 text-center']" 
                    @mouseover="mouseoverSelecction = item.diagnosisKey" 
                    :key="item.diagnosisKey">
                    <img :src="item.img" class="img-fluid img" alt="" width="68">
                    <label for="">{{ item.name  }}</label>
                </div>

                <div class="col-12 mt-3">
                    <label for="">Observaciones:</label>
                    <textarea class="form-control" name="" id="" cols="30" rows="4"></textarea>
                </div>
            </div>
        </div>
        <!-- Pie del modal -->
        <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-dismiss="modal" @click="closeModal()">Cerrar</button>
            <button type="button" class="btn btn-primary">Guardar cambios</button>
        </div>
        </div>
    </div>
    </div>
</template>

<script>
import { computed, onMounted, ref } from 'vue'
export default {
    name: 'modalOptionsTeeth',
    props: {
        teeth: {
            default: null,
            required: true,
            type: Object
        }
    },
    setup(props) {
        let modal = ref(null),
            modalInstance = ref(null),
            mouseoverSelecction = ref(null), // guarda el id del diagnosesToChoose cuando esta el cursor encima
            diagnosisSelected = ref(null)
        const diagnosesToChoose = computed(()=>{
            if(props.teeth){
                return [
                    {name: 'ausente', diagnosisKey: 'ausente', img: '/assets/img/teeth/'+props.teeth.id+'/ausente.png'},
                    {name: 'corona', diagnosisKey: 'corona', img: '/assets/img/teeth/'+props.teeth.id+'/corona.png'},
                    {name: 'extraccion', diagnosisKey: 'extraccion', img: '/assets/img/teeth/'+props.teeth.id+'/extraccion.png'},
                    {name: 'fractura', diagnosisKey: 'fractura', img: '/assets/img/teeth/'+props.teeth.id+'/fractura.png'},
                    {name: 'implante', diagnosisKey: 'implante', img: '/assets/img/teeth/'+props.teeth.id+'/implante.png'},
                    {name: 'pernomunon', diagnosisKey: 'pernomunon', img: '/assets/img/teeth/'+props.teeth.id+'/pernomunon.png'},
                    {name: 'restauracion', diagnosisKey: 'restauracion', img: '/assets/img/teeth/'+props.teeth.id+'/restauracion.png'},
                    {name: 'sano', diagnosisKey: 'sano', img: '/assets/img/teeth/'+props.teeth.id+'/sano.png'},
                ]
            }

            return []
        })

        function openModal() {
            modalInstance.value = new bootstrap.Modal(modal.value);
            modalInstance.value.show();
        }

        function closeModal() {
            modalInstance.value.hide();
        }

        return {
            modal,modalInstance,openModal,closeModal,diagnosesToChoose,
            mouseoverSelecction,diagnosisSelected
        }
    },
}
</script>

<style scoped>
    .mouseoverSelecction{
        border: 2px solid rgba(58, 177, 236, 0.679);
        cursor: pointer;
    }
    .divDiagnosisSelected{
        background-color:rgba(58, 177, 236, 0.679);
        cursor: pointer;
    }
</style>