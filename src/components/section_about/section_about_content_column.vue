<template>
    <div class="content-column">
        <div class="inner-column">
            <div class="sec-title">
                <h3 class="title-about">Sobre Nós</h3>
                <h3 class="title-about-description">Inovação<br>Transformação<br>Impacto</h3>
            </div>
            <div class="text-about">Somos uma agência criativa que trabalha com sua maior paixão: O desenvolvimento de
                soluções estratégicas para conectar sua marca com o consumidor de forma humanizada. <br> Somos uma
                equipe que traz o design e o marketing de um jeito unico para dar forma a um único objetivo: Tornar sua
                marca ainda mais relevante para as pessoas, ajudando a construir seu sonho.</div>
        </div>
    </div>

</template>

<script>
export default {
    name: 'SubSectionContentColumn',
    data() {
        return {
        };
    },
    methods: {
    },
};
</script>

<style scoped>

.content-column {
    position: relative;
    border-radius: 10px;
    margin-bottom: 40px;
    width: 40vw;
}

.inner-column {
    position: relative;
    align-items: flex-start;
}

.sec-title {
    margin-bottom: 20px;
    position: relative;
    padding: 40px;
}

.title-about {
    color: var(--primary_gold_color);
    text-shadow: var(--all_page_text_shadow);
    font-size: var(--all_text_size_h1);
    font-weight: 700;
    padding-left: 50px;
    margin-bottom: 15px;
    display: inline-block;
    text-transform: capitalize;
}

.title-about-description {
    color: var(--primary_gold_color);
    text-shadow: var(--all_page_text_shadow);
    font-size: var(--all_text_size_h3);;
    font-weight: 700;
    padding-right: 50px;
    margin-bottom: 15px;
    display: inline-block;
    text-transform: capitalize;

}

.text-about {
    position: relative;
    color: #777777;
    padding: 10px;
    font-size: 120%;
    line-height: 1.8em;
    background-color: rgba(41, 41, 41, 0.7);
    border-radius: 10px;
    margin-top: 20%;
    margin-bottom: 10%;
    width: 80vw;

    &::before {
        content: '\201C';
        font-size: 40px;
        color: #d7a449;
        position: absolute;
        left: -20px;
        top: -10px;
    }

    &::after {
        content: '\201D';
        font-size: 40px;
        color: #d7a449;
        position: absolute;
        right: -20px;
        bottom: -10px;
    }

    &:hover {
        color: #d7a449;
    }
}

@media (max-width: 767px) {
    .content-column {
        width: 50%;
        padding-right: 0;
    }

    .inner-column {
        padding-right: 0px;
    }

    .sec-title {
        width: 50%;
    }

    .text-about {
        width: 80vw;
        font-size: 100%;
        margin-bottom: 10%;
    }

    .title-about {
        font-size: calc(var(--all_text_size_h1) - 40%);
        white-space: nowrap;
    }

    .title-about-description {
        font-size: calc(var(--all_text_size_h3) - 40%);
    }
}

@media (max-width: 575px) {
    .content-column {
        padding-left: 5px;
        width: 50%;
        padding-right: 0;
    }

    .inner-column {
        padding-right: 0px;
    }

    .text-about {
        width: 80vw;
        margin-bottom: 10%;
        font-size: 90%;
    }

    .sec-title {
        padding: 10px;
    }

    .title-about {
        font-size: calc(var(--all_text_size_h3) - 60%);
        white-space: nowrap;
    }

    .title-about-description {
        font-size: calc(var(--all_text_size_h3) - 60%);
    }
}
</style>