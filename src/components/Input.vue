<template>
  <div class="wrapper">
    <label for="input" :class="{ error: error }">
      {{ labelText }}
    </label>
    <div
      :class="[
        'input-container',
        size,
        { error: error, disabled: disabled, fullWidth: fullWidth },
      ]"
    >
      <span id="startIcon" class="material-icons" v-if="startIcon">
        {{ startIcon }}
      </span>
      <textarea
        :disabled="disabled"
        :placeholder="placeholder"
        :value="value"
        :rows="row"
        v-if="multiline"
      />
      <input
        type="text"
        :disabled="disabled"
        :placeholder="placeholder"
        :value="value"
        v-else
      />
      <span class="material-icons" v-if="endIcon">
        {{ endIcon }}
      </span>
    </div>
    <small :class="{ error: error }">{{ helperText }}</small>
  </div>
</template>

<script>
export default {
  name: "Input",
  props: {
    labelText: {
      type: String,
      default: "Label",
    },
    placeholder: {
      type: String,
      default: "Placeholder",
    },
    value: {
      type: String,
      default: "",
    },
    disabled: {
      type: Boolean,
      default: false,
    },
    error: {
      type: Boolean,
      default: false,
    },
    helperText: {
      type: String,
    },
    startIcon: {
      type: String,
    },
    endIcon: {
      type: String,
    },
    size: {
      type: String,
      default: "md",
      validator: (value) => {
        return ["sm", "md"].includes(value);
      },
    },
    fullWidth: {
      type: Boolean,
    },
    multiline: {
      type: Boolean,
    },
    row: {
      type: Number,
      default: 2,
    },
  },
};
</script>

<style scoped>
.wrapper {
  max-width: 100%;
  margin-top: 15px;
}

label {
  font-size: 14px;
  color: #333333;

  transition: all 0.3s ease-out;
}

label.error,
small.error {
  color: #d32f2f;
}

/*#region baseInputContainer */

.input-container {
  border: 1px solid #828282;
  border-radius: 8px;

  margin-top: 5px;

  width: max-content;
}

.input-container * {
  display: inline;
  vertical-align: middle;
}

input,
textarea {
  font-size: 16px;
  font-weight: 500;

  border: none;
  resize: none;

  transition: all 0.3s ease-out;
}

.input-container .material-icons {
  color: #828282;
}

#startIcon {
  margin-right: 10px;
}

.input-container:hover,
.input-container.error:hover {
  border: 1px solid #333333;
}

/*#endregion */

small {
  font-size: 12px;

  color: #828282;
}

/*#region Classes based styles */

.input-container.error {
  border-color: #d32f2f;
}

.input-container.disabled {
  background: #f2f2f2;
  border: 1px solid #e0e0e0;
}

.input-container.sm {
  padding: 8px 6px;
}

.input-container.md {
  padding: 14px 10px;
}

.input-container.fullWidth {
  width: 100%;
}

.wrapper:focus-within label {
  color: #2962ff;
}

.wrapper:focus-within .input-container {
  border-color: #2962ff;
}

.wrapper:focus-within label.error {
  color: #d32f2f;
}

.wrapper:focus-within .input-container.error {
  border-color: #d32f2f;
}

/*#endregion */
</style>