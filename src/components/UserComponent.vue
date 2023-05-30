<template>

  
  <div class="vue1">
    
    
    <h1>CRUD Usuarios</h1>
    <div class="d-flex justify-content-end button-container">
      <b-button v-b-modal.modal-1 variant="success" > <b-icon icon="plus-lg"></b-icon> Crear Usuario</b-button>
    </div>

    <b-modal id="modal-1" title="Crear Usuario">
      <form @submit.prevent="submitForm" enctype="multipart/form-data">
      
      <div class="form-group">
        <label for="nicknameInput">Nickname</label>
        <input
          type="text"
          class="form-control"
          id="nicknameInput"
          v-model="form.nickname"
          required
        >
      </div>
      <div class="form-group">
        <label for="passwordInput">Contraseña</label>
        <input
          type="password"
          class="form-control"
          id="passwordInput"
          v-model="form.password"
          required
        >
      </div>
      <div class="form-group">
        <label for="nombreInput">Nombre</label>
        <input
          type="text"
          class="form-control"
          id="nombreInput"
          v-model="form.nombre"
          required
        >
      </div>
      <div class="form-group">
        <label for="apellidoInput">Apellido</label>
        <input
          type="text"
          class="form-control"
          id="apellidoInput"
          v-model="form.apellido"
          required
        >
      </div>
      <div class="form-group">
        <label for="edadInput">Edad</label>
        <input
          type="number"
          class="form-control"
          id="edadInput"
          v-model="form.edad"
          required
        >
      </div>
      <div class="form-group">
        <label for="generoInput">Género</label>
        <select class="form-control" id="generoInput" v-model="form.genero" required>
          <option value="">Seleccionar</option>
          <option value="Masculino">Masculino</option>
          <option value="Femenino">Femenino</option>
          <option value="Otro">Otro</option>
        </select>
      </div>
      <div class="form-group">
        <label for="correoInput">Correo Electrónico</label>
        <input
          type="email"
          class="form-control"
          id="correoInput"
          v-model="form.correo_electronico"
          required
        >
      </div>
      <div class="form-group">
        <label for="telefonoInput">Teléfono</label>
        <input
          type="tel"
          class="form-control"
          id="telefonoInput"
          v-model="form.telefono"
          required
        >
      </div>
      <div class="form-group">
        <label for="direccionInput">Dirección</label>
        <input
          type="text"
          class="form-control"
          id="direccionInput"
          v-model="form.direccion"
          required
        >
      </div>
      
      <div class="form-group">
          <label for="dniInput">DNI</label>
          <input
            type="text"
            class="form-control"
            id="dniInput"
            v-model="form.dni"
            required
          >
      </div>

      <div class="form-group">
        <label for="fotoInput">Foto (PNG)</label>
        <input
          type="file"
          class="form-control-file"
          id="fotoInput"
          accept="image/png"
          @change="handleFileUpload"
          required
        >
      </div>
      <button type="submit" class="btn btn-primary">Enviar</button>
    </form>
    
    </b-modal>
    
    
    <b-modal id="modal-2" title="Editar Usuario">
      <form @submit.prevent="patchUserData" enctype="multipart/form-data">

      <div class="form-group">
        <label for="idInput">ID</label>
        <p>{{ form.id }}</p>
      </div>

      <div class="form-group">
        <label for="nicknameInput">Nickname</label>
        <input
          type="text"
          class="form-control"
          id="nicknameInput"
          v-model="form.nickname"
          required
        >
      </div>
      <div class="form-group">
        <label for="passwordInput">Contraseña</label>
        <input
          type="password"
          class="form-control"
          id="passwordInput"
          v-model="form.password"
          required
        >
      </div>
      <div class="form-group">
        <label for="nombreInput">Nombre</label>
        <input
          type="text"
          class="form-control"
          id="nombreInput"
          v-model="form.nombre"
          required
        >
      </div>
      <div class="form-group">
        <label for="apellidoInput">Apellido</label>
        <input
          type="text"
          class="form-control"
          id="apellidoInput"
          v-model="form.apellido"
          required
        >
      </div>
      <div class="form-group">
        <label for="edadInput">Edad</label>
        <input
          type="number"
          class="form-control"
          id="edadInput"
          v-model="form.edad"
          required
        >
      </div>
      <div class="form-group">
        <label for="generoInput">Género</label>
        <select class="form-control" id="generoInput" v-model="form.genero" required>
          <option value="">Seleccionar</option>
          <option value="Masculino">Masculino</option>
          <option value="Femenino">Femenino</option>
          <option value="Otro">Otro</option>
        </select>
      </div>
      <div class="form-group">
        <label for="correoInput">Correo Electrónico</label>
        <input
          type="email"
          class="form-control"
          id="correoInput"
          v-model="form.correo"
          required
        >
      </div>
      <div class="form-group">
        <label for="telefonoInput">Teléfono</label>
        <input
          type="tel"
          class="form-control"
          id="telefonoInput"
          v-model="form.telefono"
          required
        >
      </div>
      <div class="form-group">
        <label for="direccionInput">Dirección</label>
        <input
          type="text"
          class="form-control"
          id="direccionInput"
          v-model="form.direccion"
          required
        >
      </div>
      
      <div class="form-group">
          <label for="dniInput">DNI</label>
          <input
            type="text"
            class="form-control"
            id="dniInput"
            v-model="form.dni"
            required
          >
      </div>

      <div class="form-group">
        <label for="fotoInput">Foto (PNG)</label>
        <input
          type="file"
          class="form-control-file"
          id="fotoInput"
          accept="image/png"
          @change="handleFileUpload"
          
        >
      </div>
      <button type="submit" class="btn btn-primary">Enviar</button>
    </form>
    
    </b-modal>

    <template>
      <div class="overflow-auto">
        <b-pagination
          v-model="currentPage"
          :total-rows="rows"
          :per-page="perPage"
          aria-controls="my-table"
        ></b-pagination>

        <p class="mt-3">Current Page: {{ currentPage }}</p>

        <b-table responsive 
        class="myTable"
        label-sort-asc=""
        label-sort-desc=""
        label-sort-clear=""
        :sticky-header="stickyHeader" 
        :items="responseData" 
        :fields="fields"
        :per-page="perPage"
        :current-page="currentPage">
        
        
        <template #cell(acciones)="row">
            <b-button variant="danger" @click="deleteUser(row.item.id)"><b-icon icon="trash"></b-icon> Borrar</b-button>

            <b-button v-b-modal.modal-2 variant="primary" @click="openEditModal(row.item)"><b-icon icon="pencil"></b-icon> Editar</b-button>

            <!-- As `row.showDetails` is one-way, we call the toggleDetails function on @change -->
            
        </template>
        
        </b-table>
      </div>
    </template>
   

    
    
  </div>
</template>

<script>
import axios from 'axios';

export default {
  computed: {
      rows() {
        return this.items.length
      }
  },

  data() {
    return {
      
      responseData: null,
      stickyHeader: true,
      showModal: false,
      perPage: 10,
      currentPage: 1,
      form: {
        nickname: '',
        password: '',
        nombre: '',
        apellido: '',
        edad: '',
        genero: '',
        correo_electronico: '',
        telefono: '',
        direccion: '',
        dni: '',
        foto: null
      },

      fields: [
          {
            key: 'id',
            sortable: true,
            
          },
          {
            key: 'nombre',
            sortable: true
          },
          {
            key: 'apellido'
          },
          {
            key: 'nickname',
            sortable: true
          },
          {
            key: 'edad',
            sortable: true
          },
          {
            key: 'genero',
            sortable: true
          },
          {
            key: 'correo',
            sortable: true
          },
          {
            key: 'telefono',
            sortable: true
          },
          {
            key: 'direccion',
            sortable: true
          },
          
          {
            key: 'dni',
            sortable: true
          },
          {
            key: 'foto',
            sortable: true
          },
          {
            key: 'acciones'
          }
      ],

      items: [
          { age: 40, first_name: 'Dickerson', last_name: 'Macdonald' },
          { age: 21, first_name: 'Larsen', last_name: 'Shaw' },
          { age: 89, first_name: 'Geneva', last_name: 'Wilson' },
          { age: 38, first_name: 'Jami', last_name: 'Carney' }
      ]
    };
  },

  created() {
    axios.post('http://127.0.0.1:5050/users')
      .then(response => {
        this.responseData = response.data.map(user => {
        return {
          id:user.id_usuario,
          nickname: user.nickname,
          password: user.password,
          apellido: user.apellido,
          nombre: user.nombre,
          edad: user.edad,
          genero: user.genero,
          correo : user.correo,
          telefono : user.telefono,
          direccion : user.direccion,
          foto : user.foto,
          dni : user.dni
        };
      });
      })
      .catch(error => {
        // Manejar el error
        console.error(error);
      });
  },

  methods: {
    // Resto de los métodos del componente
    openEditModal(item) {
      this.form = { ...item };
      this.showModal = true;
    },

    deleteUser(id) {
    axios.delete('http://127.0.0.1:5050/user', { data: { id_usuario: id } })
      .then(response => {
        // Realizar cualquier acción adicional después de borrar el usuario
        console.log(response.data);
        
      })
      .catch(error => {
        // Manejar el error
        console.error(error);
      });
    },

    patchUserData() {
      
      const formData = new FormData();
      formData.append('id_usuario', this.form.id);
      formData.append('nickname', this.form.nickname);
      formData.append('password', this.form.password);
      formData.append('nombre', this.form.nombre);
      formData.append('apellido', this.form.apellido);
      formData.append('edad', this.form.edad);
      formData.append('genero', this.form.genero);
      formData.append('correo_electronico', this.form.correo);
      formData.append('telefono', this.form.telefono);
      formData.append('direccion', this.form.direccion);
      formData.append('dni', this.form.dni);
      formData.append('foto', this.form.foto);
      
      axios.patch('http://127.0.0.1:5050/user', formData)
        .then(response => {
          console.log(response.data); // Maneja la respuesta de la API
          // Restablece los campos del formulario después de enviarlo
          this.form.id = '';
          this.form.nickname = '';
          this.form.password = '';
          this.form.nombre = '';
          this.form.apellido = '';
          this.form.edad = '';
          this.form.genero = '';
          this.form.correo_electronico = '';
          this.form.telefono = '';
          this.form.direccion = '';
          this.form.dni = '';
          this.form.foto = null;
        })
        .catch(error => {
          console.error(error); // Maneja los errores de la petición
        });
    },

    submitForm() {
      const formData = new FormData();
     
      formData.append('nickname', this.form.nickname);
      formData.append('password', this.form.password);
      formData.append('nombre', this.form.nombre);
      formData.append('apellido', this.form.apellido);
      formData.append('edad', this.form.edad);
      formData.append('genero', this.form.genero);
      formData.append('correo_electronico', this.form.correo_electronico);
      formData.append('telefono', this.form.telefono);
      formData.append('direccion', this.form.direccion);
      formData.append('dni', this.form.dni);
      formData.append('foto', this.form.foto);
      
      axios.put('http://127.0.0.1:5050/user', formData)
        .then(response => {
          console.log(response.data); // Maneja la respuesta de la API
          // Restablece los campos del formulario después de enviarlo
          this.form.id = '';
          this.form.nickname = '';
          this.form.password = '';
          this.form.nombre = '';
          this.form.apellido = '';
          this.form.edad = '';
          this.form.genero = '';
          this.form.correo_electronico = '';
          this.form.telefono = '';
          this.form.direccion = '';
          this.form.dni = '';
          this.form.foto = null;
        })
        .catch(error => {
          console.error(error); // Maneja los errores de la petición
        });
    },
    
    handleFileUpload(event) {
      const file = event.target.files[0];
      this.form.foto = file;
    },

    openEditModal(item) {
      this.form = { ...item };
      this.showModal = true;
    }
  }
} 
</script>

<style>
.sticky-header-table thead {
  position: sticky;
  top: 0;
  background-color: #f8f9fa;
  z-index: 1; /* Asegura que el encabezado esté por encima del contenido de la tabla */
}

.button-container {
  padding: 20px;
}

.myTable thead {
  background-color: black;
}

</style>