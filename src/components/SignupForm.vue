<template>
    <form>
        <label>Email</label>
        <input type="email" required v-model="email">

        <label>Password</label>
        <input type="password" required v-model="password">

        <label>Role</label>
        <select v-model="role">
            <option value="developer">Web Developer</option>
            <option value="designer">Web Designer</option>
        </select>

        <label>Skills</label>
        <input type="text" v-model="tempSkill" @keyup="addSkill">
        <div v-for="skill in skills" :key="skill" class="pill">
            <span @click="eraseSkill(skill)">{{ skill }}</span>
        </div>

        <div class="terms">
            <input type="checkbox" required v-model="terms">
            <label>Accept terms and conditions</label>
        </div>

        <!-- <div>
            <input type="checkbox" value="mario" v-model="names">
            <label>Mario</label>
        </div>

        <div>
            <input type="checkbox" value="luigi" v-model="names">
            <label>Luigi</label>
        </div>

        <div>
            <input type="checkbox" value="todd" v-model="names">
            <label>Todd</label>
        </div> -->

        <div class="submit">
            <button>Create account</button>
        </div>
    </form>

    <!-- <p>Email: {{email}}</p>
    <p>Password: {{password}}</p>
    <p>Role: {{role}}</p>
    <p>Terms: {{terms}}</p> -->
    <!-- <p>Names: {{names}}</p> -->

</template>

<script>
export default {
    data() {
        return {
            email: '',
            password: '',
            role: '',
            terms: false,
            // names: []
            tempSkill: '',
            skills: []
        }
    },
    methods: {
        addSkill(e) {
            if (e.key === ',' && this.tempSkill) {
                let string = this.tempSkill.substring(0, this.tempSkill.length - 1)
                if (!this.skills.includes(string)) {
                    this.skills.push(string)
                }
                this.tempSkill = ''
            }
        },
        eraseSkill(skill) {
            this.skills = this.skills.filter((elm) => {
                return skill !== elm
            })
        }
    }
}
</script>

<style>
    form {
        width: 420px;
        background: white;
        text-align: left;
        padding: 40px;
    }

    label {
        color: #aaa;
        display: inline-block;
        margin: 25px 0 15px;
        font-size: 0.6em;
        text-transform: uppercase;
        letter-spacing: 1px;
        font-weight: bold;
    }

    input, select {
        display: block;
        padding: 10px 6px;
        width: 100%;
        box-sizing: border-box;
        border: none;
        border-bottom: 1px solid #ddd;
        color: #555;
        background-color: white;
    }

    input[type="checkbox"] {
        display: inline-block;
        width: 16px;
        margin: 0 10px 0 0;
        position: relative;
        top: 2px;
    }

    .pill {
        display: inline-block;
        margin: 20px 10px 0 0;
        padding: 6px 12px;
        background: #eee;
        border-radius: 20px;
        font-size: 12px;
        letter-spacing: 1px;
        font-weight: bold;
        color: #777;
        cursor: pointer;
    }

    button {
        background: #39317a;
        border: 0;
        padding: 10px 20px;
        margin-top: 20px;
        color: white;
        border-radius: 20px;
    }

    .submit {
        text-align: center;
    }
</style>