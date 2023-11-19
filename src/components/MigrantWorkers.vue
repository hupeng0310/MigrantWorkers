<template>
  <div class="main_container">
    <div class="title">摸鱼时间到</div>
    <el-divider class="divider" content-position="left">时间配置</el-divider>
    <div class="form_block">
      <span>工作时间</span>
      <el-time-select
        v-model="workTimeStart"
        :max-time="workTimeEnd"
        class="time-select"
        placeholder="开始时间"
        start="00:00"
        step="00:15"
        end="23:45"
        default-value="new Date()"
        is-range
      />
      <el-time-select
        v-model="workTimeEnd"
        :min-time="workTimeStart"
        class="time-select"
        placeholder="结束时间"
        start="00:00"
        step="00:15"
        end="23:45"
        is-range
      />
    </div>
    <div class="form_block">
      <span>午休时间</span>
      <el-time-select
        v-model="restTimeStart"
        :max-time="restTimeEnd"
        class="time-select"
        placeholder="开始时间"
        start="00:00"
        step="00:15"
        end="23:45"
        default-value="new Date()"
        is-range
      />
      <el-time-select
        v-model="restTimeEnd"
        :min-time="restTimeStart"
        class="time-select"
        placeholder="结束时间"
        start="00:00"
        step="00:15"
        end="23:45"
        is-range
      />
    </div>
  </div>
</template>
  
<script>
import { ref } from 'vue'
  export default {
    name: 'MigrantWorkers',
    setup() {
      const workTimeStart = ref('09:00');
      const workTimeEnd = ref('18:00');
      const restTimeStart = ref('12:00')
      const restTimeEnd = ref('13:00')

      return {
        workTimeStart,
        workTimeEnd,
        restTimeStart,
        restTimeEnd
      };
    }
  }
</script>
<style scoped>
.main_container {
  margin-top: 10px;
  margin-left: 10px;
  margin-right: 10px;
}
.title {
  font-size: 30px;
  font-weight: bold;
  text-align: center;
  color: rgb(0, 47, 167);
}

.divider {
  border-width: 2px;
  border-color: skyblue;
}

span {
  margin-right: 10px;
}

.time-select {
  margin-right: 10px;
}

.form_block{
  padding-left: 10px;
  margin-bottom: 10px;
}

</style>