<template>
  <div class="hello">
    
  </div>
</template>

<script lang="tsx">
import { Component, Vue } from 'vue-property-decorator';

@Component
export default class DataTable extends Vue {

  private renderdDashboardSheet() {
      return (
        <div class="dashboard-sheet">
          <div class="title">實驗</div>
        </div>
       
      )
  }

  render() {
    return (
      <div>{this.renderdDashboardSheet()}</div>
    );
  }
}
</script>

<style lang="less" scoped>
.dashboard-sheet {
  margin-bottom: 40px;
  .head {
    padding: 8px;
    display: flex;
    border: 1px solid #ebeef5;
    & > div + div {
      margin-left: 16px;
    }
  }
  .main {
    .section {
      .title {
        padding: 8px 0;
        font-weight: bold;
        border-left: 1px solid #ebeef5;
        border-right: 1px solid #ebeef5;
      }
    }
  }
  .table {
    .table-cell {
      padding: 16px 4px;
      font-size: 18px;
      flex: 1;
      border: 1px solid #ebeef5;
    }
    .table-header {
      display: flex;
    }
    .table-body {
    }
    .table-row-cell {
      display: flex;
    }
    .method {
      display: flex;
      align-items: stretch;
      .key {
        display: flex;
        align-items: center;
        justify-content: center;
        width: calc(100% / 6);
        border: 1px solid #ebeef5;
      }
      .table-body {
        flex: 1;
      }
    }

    .table-row {
      display: flex;
      flex-direction: row;
      .table-cell {
        margin-bottom: 0px; /* Adjust the margin as needed */
      }

      .table-cell span:first-child {
        font-weight: bold;
        margin-right: 4px;
      }
    }
  }
}
</style>
