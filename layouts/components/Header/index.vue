<template>
  <el-header style=" text-align: right; font-size: 10px">
    <!-- 下拉菜单 -->
    <div class="right-menu">
      <el-dropdown class="avatar-container right-menu-item hover-effect" trigger="click">
        <!-- 用户信息 -->
        <div class="avatar-wrapper">
          <img src="/images/avatar.jpg" class="user-avatar" />
          <i class="el-icon-caret-bottom"></i>
        </div>
        <el-dropdown-menu slot="dropdown">
          <router-link to="/profile/index">
            <el-dropdown-item>账号信息</el-dropdown-item>
          </router-link>
          <el-dropdown-item divided @click.native="logout">
            <span style="display:block;">退出登陆</span>
          </el-dropdown-item>
        </el-dropdown-menu>
      </el-dropdown>
    </div>
  </el-header>
</template>
<script>
export default {
  name: 'Header',

  props: {},
  data() {
    return {}
  },
  created() {},
  mounted() {},
  methods: {
    logout() {
      this.$message('你点击了退出')
    }
  }
}
</script>
<style lang="scss" scoped>
.el-header {
  background:#FFA500;
  color: #fff;
  line-height: 60px;
  .right-menu {
    float: right;
    height: 100%;
    line-height: 30px;
    .right-menu-item {
      display: inline-block;
      padding: 5px 8px;
      height: 100%;
      font-size: 18px;
      color: #5a5e66;
      vertical-align: text-bottom; //属性设置元素的垂直对齐方式
      &.hover-effect {
        cursor: pointer;
        &:hover {
          background: rgba(0, 0, 0, 0.025);
        }
      }
    }
    .avatar-container {
      margin-right: 30px;
      .avatar-wrapper {
        margin-top: 5px;
        position: relative;
        .user-avatar {
          cursor: pointer;
          width: 40px;
          height: 40px;
          border-radius: 10px;
        }
        .el-icon-caret-bottom {
          cursor: pointer;
          position: absolute;
          right: -20px;
          top: 15px;
          font-size: 12px;
        }
      }
    }
  }
}
</style>