<template>
    <div @click="focus" class="normal" id="list">
        <div class="avatar">
            <i @click="onClick(this.contact.id)" class="fas fa-chevron-left fa-2x"></i>
            <i class="far fa-user-circle fa-4x"></i>
            <i class="fas fa-edit fa-2x"></i>
        </div>
        <div class="inner-contact">
            <h3>{{contact.name}}</h3>
            <h4>{{contact.phone}}</h4>
            <p>{{contact.email}}</p>
            <p>{{contact.company.name}}</p>
        </div>
        <i class="fas fa-phone-square-alt fa-2x contact-method"></i>
        <i class="fas fa-comment-dots fa-2x contact-method"></i>
    </div>
</template>

<script>

export default {
    name: 'Contact',
    props: {
        contact: Object
    },
    methods: {
        onClick(id) {
            let element = document.getElementById(id);
            element.classList.add("normal");
        },
        focus: function(event) {
            event.target.classList.remove('normal');
        }
    }
}
</script>

<style scoped>
    *{
        background: #fff;
        color: #000;
    }

    #list:hover {
        border: green solid 2px;
    }
    
    #list {
        max-width: 900px;
        margin: 0 auto;
        padding: 10px 0;
        border-bottom: 1px #000 solid;
        cursor: pointer;
    }

    .normal {
        max-width: 900px;
        max-height: 900px;
        display: flex;
        margin: 0 auto;
    }

    .normal div{
        display: flex;
        max-width: 900px;
        justify-content: space-between;
        margin: 0 auto;
    }

    .normal .avatar{
        margin: auto 10px;
        position: relative;
    }

    .normal h4, .normal p, .normal .fa-chevron-left, .normal .fa-edit{
        display: none;
    }

    .inner-contact {
        font-size:1.5em;
    }

    .contact-method{
        color: green;
        margin: 0 50px;
    }

    .normal .contact-method{
        margin: 10px;
        padding: 15px;
        width: 30px;
        height: 30px;
        color: green;
    }

    .contact-method:hover {
        background: green;
        color: #fff;
    }
    
    .avatar {
        display: flex;
        justify-content: space-between;
        margin: auto 20px;
        padding-top: 10px;
        color: #978F8C;
    }

    .fa-edit:hover, .fa-chevron-left:hover{
        color: green;
    }
</style>