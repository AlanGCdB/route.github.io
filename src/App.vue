<template>
  <div class="container" @click="fecharModal">
    <button @click="ativarModal = !ativarModal" class="buttonAtivar">
      Active
    </button>
    <transition name="modal">
      <div v-show="ativarModal">
        <div class="modal">
          <h3>Login</h3>
          <input
            type="email"
            name="email"
            id="email"
            placeholder="Seu E-mail"
          />
          <input
            type="password"
            name="password"
            id="password"
            placeholder="Seu Password"
          />
          <button>Login</button>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      ativarModal: true,
    };
  },
  methods: {
    fecharModal({ currentTarget, target }) {
      if (currentTarget === target) {
        this.ativarModal = false;
      }
    },
  },
};
</script>

<style>
.container {
  display: grid;
  justify-content: center;
  align-items: start;
  font-family: Arial, Helvetica, sans-serif;
  background: radial-gradient(
    circle,
    rgba(31, 66, 19, 0.8244803695150116) 33%,
    rgba(15, 15, 15, 0.8267898383371824) 81%
  );
  height: 100vh;
  grid-auto-rows: 150px 1fr;
}
.buttonAtivar {
  margin: 10px auto;
}

.buttonAtivar,
.modal button {
  height: 40px;
  width: 200px;
  color: white;
  font-weight: bold;
  background: rgb(31, 66, 19);
  border: 2px solid rgba(255, 255, 0, 0.114);
  box-shadow: 1px 1px 1px 1px rgba(255, 255, 0, 0.008);
}
.modal {
  width: 400px;
  height: 300px;
  justify-items: center;
  background: radial-gradient(
    circle,
    rgba(31, 66, 19, 0.8244803695150116) 33%,
    rgba(15, 15, 15, 0.628175519630485) 81%
  );
  display: grid;
  animation: slide 2s;
}
.modal h3 {
  color: rgba(68, 244, 9, 0.486);
}
.modal input {
  margin: 10px;
  width: 340px;
  height: 40px;
  border: none;
  border-radius: 4px;
}
.modal input[type="password"] {
  margin-bottom: 20px;
}
.modal button {
  margin-bottom: 150px;
}
@keyframes slide {
  from {
    transform: translate3d(0, 150px, 0);
  }
  to {
    transform: translate3d(0, 0px, 0);
  }
}
.modal-enter,
.modal-leave-to {
  opacity: 0;
}
.modal-enter-active,
.modal-leave-active {
  transition: opacity 1s;
}
</style>