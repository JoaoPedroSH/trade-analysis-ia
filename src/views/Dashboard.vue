<script setup>
import PerformanceByModelWidget from '@/components/dashboard/PerformanceByModelWidget.vue';
import SignalHistoryWidget from '@/components/dashboard/SignalHistoryWidget.vue';
import IaModelsWidget from '@/components/dashboard/IaModelsWidget.vue';
import EconomicCalendarWidget from '@/components/dashboard/EconomicCalendarWidget.vue';
</script>

<template>
    <div class="grid grid-cols-12 gap-8">
        <IaModelsWidget />

        <div class="col-span-12 xl:col-span-6">
            <SignalHistoryWidget />
            <!--<PerformanceByModelWidget />-->
        </div>
        <div class="col-span-12 xl:col-span-6">
            <EconomicCalendarWidget />
        </div>
    </div>
</template>
