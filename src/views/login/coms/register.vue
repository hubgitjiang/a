<template>
    <el-dialog title="用户注册" :visible.sync="dialogFormVisible">
        <el-form :model="form">
            <el-form-item label="头像" :label-width="formLabelWidth">
                <el-input v-model="form.name" autocomplete="off"></el-input>
            </el-form-item>
            <el-form-item label="头像" :label-width="formLabelWidth">
                <el-input v-model="form.name" autocomplete="off"></el-input>
            </el-form-item>
            <el-form-item label="头像" :label-width="formLabelWidth">
                <el-input v-model="form.name" autocomplete="off"></el-input>
            </el-form-item>
            <el-form-item label="头像" :label-width="formLabelWidth">
                <el-row>
                    <el-col :span="17">
                        <el-input v-model="form.name" autocomplete="off"></el-input>
                    </el-col>
                    <el-col style="text-align: right;" :span="7">
                        <img class="codeimg" src="../../../assets/login_captcha.png" alt="">
                    </el-col>
                </el-row>
            </el-form-item>
            <el-form-item label="头像" :label-width="formLabelWidth">
                <el-row>
                    <el-col :span="17">
                        <el-input v-model="form.name" autocomplete="off"></el-input>
                    </el-col>
                    <el-col style="text-align: right;" :span="7">
                        <el-button>获取用户验证码</el-button>
                    </el-col>
                </el-row>
            </el-form-item>
        </el-form>
        <div slot="footer" class="dialog-footer">
            <el-button @click="dialogFormVisible = false">取 消</el-button>
            <el-button type="primary" @click="dialogFormVisible = false">确 定</el-button>
        </div>
    </el-dialog>
</template>

<script>
export default {
    data() {
        return {
            dialogFormVisible: true,
            form: {
                name: '',
                region: '',
                date1: '',
                date2: '',
                delivery: false,
                type: [],
                resource: '',
                desc: ''
            },
            formLabelWidth: '62px'
        }
    }
}
</script>

<style lang="less">
.el-dialog__header {
    padding: 0px !important;
    height: 53px;
    line-height: 53px;
    text-align: center;
    background: linear-gradient(to right, #03c4f9, #1495fd);
    .el-dialog__title {
        color: #fff;
    }
}

.codeimg {
    width: 143px;
    height: 40px;
}
.dialog-footer {
    text-align: center;
}
</style>
