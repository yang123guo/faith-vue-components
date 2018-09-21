<template>
	<input
        :tabindex="tabindex"
        v-if="type !== 'textarea'"
        class="el-input__inner"
        v-bind="$attrs"
        :type="type"
        :disabled="disabled"
        :readonly="readonly"
        :autocomplete="autoComplete || autocomplete"
        :value="currentValue"
        ref="input"
        @compositionstart="handleComposition"
        @compositionupdate="handleComposition"
        @compositionend="handleComposition"
        @input="handleInput"
        @focus="handleFocus"
        @blur="handleBlur"
        @change="handleChange"
        :aria-label="label"
    >
</template>

<script>
import isNull from '../../utils';
export default {
	name: 'FaithInput',
	componentName: 'FaithInput',
	inheritAttrs: false, // 不参与渲染的属性，不要在dom节点中渲染出来
	data() {
		return {

		}
	},
	props: {
		tabindex: String,
		type: {
			type: String,
			default: 'input'
		},
		readonly: {
			type: Boolean,
			default: false
		},
		disabled: {
			type: Boolean,
			default: false
		}
	},
	computed: {
		currentValue() {
			return isNull(this.value) ? '' : this.value
		}
	},
	methods: {
		handleInput() {

		},
	}
}
</script>

<style>

</style>
