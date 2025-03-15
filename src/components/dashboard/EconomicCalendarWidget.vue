<script setup>
import { ref, onMounted, watch } from 'vue';
import { useLayout } from '@/layout/composables/layout';

const { isDarkTheme } = useLayout();

const calendarContainer = ref(null);

onMounted(() => {
    // Limpar o conteúdo do div especificado
    if (calendarContainer.value) {
        calendarContainer.value.innerHTML = '';
    }

    // Carregar o widget do calendário econômico
    const script = document.createElement('script');
    script.async = true;
    script.type = 'text/javascript';
    script.src = 'https://www.tradays.com/c/js/widgets/calendar/widget.js?v=13';
    script.setAttribute('data-type', 'calendar-widget');
    script.textContent = JSON.stringify({
        width: '100%',
        height: '500px',
        mode: '1',
        lang: 'pt'
    });

    document.getElementById('economicCalendarWidget').appendChild(script);
});

</script>

<template>
    <div class="card">
        <div class="flex items-center justify-between mb-6">
            <div class="font-semibold text-xl">Calendário Econômico</div>
        </div>

        <div class="mt-2" id="economic-calendar" ref="calendarContainer"></div>

        <div id="economicCalendarWidget"></div>

    </div>
</template>
