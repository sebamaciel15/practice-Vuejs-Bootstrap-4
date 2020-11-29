<template>
    <div>
        <h1>Formularios</h1>
        

        <form>
            <b-row>
                <b-col md="3">
                    <b-form-input type="text" v-model="texto" :state="comprobar"></b-form-input>
                    <small>Mínimo 3 carácteres</small>
                     <p>Texto: {{texto}}</p>
                </b-col>
                <b-col md="3">
                    <b-form-select v-model="select" :options="animales"></b-form-select>
                    <p>seleccion: {{select}}</p>
                </b-col>
                <b-col md="3">
                    <b-form-radio-group v-model="radio" :options="animalesRadio"></b-form-radio-group>
                    <p>Radio: {{radio}}</p>
                </b-col>
                <b-col md="3">
                    <b-form-checkbox-group v-model="check" :options="animalesCheckBox"></b-form-checkbox-group>
                    <p>check: {{check}}</p>
                </b-col>
            </b-row>
        </form>
       

    </div>
</template>


<script>
export default {
    name: 'Forms',
    data(){
        return{
            texto: '',
            check: [],
            radio: null,
            select: null,
            animales: [
                {value: null, text: 'seleccione un animal'},
                {value: 'perro', text: 'guau'},
                {value: 'gato', text: 'miau'},
                {value: 'pato', text: 'cuack'}
            ],
            animalesRadio: [                
                {value: 'perro', text: 'guau'},
                {value: 'gato', text: 'miau'},
                {value: 'pato', text: 'cuack'}
            ],
            animalesCheckBox: [
                {value: 'perro', text: 'guau'},
                {value: 'gato', text: 'miau'},
                {value: 'pato', text: 'cuack'}
            ]
        }
    },
    computed:{
        comprobar(){
            return this.texto.length > 2 ? true: false
        }
    }
}
</script>