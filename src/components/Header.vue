<template>
    <div class="row">
        <div class="col-sm-12">
        <h3>Tasks progress bar</h3>
            <div class="progress">
                <div class="progress">
                    <div class="progress-bar" role="progressvar" aria-valuenow="60" aria-valuemin="100"
                    :style="{width:(taskCount / maxTasks) * 100 + '%'}">
                        {{ taskCount }} / {{ maxTasks }}
                    </div>
                </div>
            </div>
        </div>

    </div>
</template>
<script>
export default {
    props: ["taskCount", "maxTasks"]
}
</script>