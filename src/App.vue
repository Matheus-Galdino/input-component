<template>
  <h1>Inputs</h1>

  <section class="row">
    <article>
      <InputHeader content="Input" />
      <Input />
    </article>
  </section>

  <section class="row">
    <article>
      <InputHeader content="Input error" />
      <Input error />
    </article>
  </section>

  <section class="row">
    <article>
      <InputHeader content="Input disabled" />
      <Input disabled />
    </article>
  </section>

  <section class="row">
    <article>
      <InputHeader content='Input helperText="Some interesting text" ' />
      <Input helperText="Some interesting text" />
    </article>

    <article>
      <InputHeader content='Input helperText="Some interesting text" error ' />
      <Input helperText="Some interesting text" error />
    </article>
  </section>

  <section class="row">
    <article>
      <InputHeader content='Input startIcon="call" ' />
      <Input startIcon="call" />
    </article>

    <article>
      <InputHeader content='Input endIcon="lock"' />
      <Input endIcon="lock" />
    </article>
  </section>

  <section class="row">
    <article>
      <InputHeader content='Input value="text" ' />
      <Input value="text" />
    </article>
  </section>

  <section class="row">
    <article>
      <InputHeader content='Input size="sm"' />
      <Input size="sm" />
    </article>

    <article>
      <InputHeader content='Input size="md"' />
      <Input size="md" />
    </article>
  </section>

  <section class="row">
    <article>
      <InputHeader content="Input fullWidth" />
      <Input fullWidth />
    </article>
  </section>

  <section class="row">
    <article>
      <InputHeader content='Input multiline rows="4"' />
      <Input multiline :row="4" />
    </article>
  </section>

  <footer>Matheus Carvalho @devChallenges.io</footer>
</template>

<script>
import InputHeader from "./components/InputHeader";
import Input from "./components/Input";

export default {
  name: "App",
  components: {
    Input,
    InputHeader,
  },
};
</script>

<style>
#app {
  height: 100%;
  width: 100vw;

  padding: 30px 90px;
}

h1 {
  font-weight: 500;
  font-size: 24px;
  color: #4f4f4f;

  margin-bottom: 60px;
}

.row {
  display: flex;
  align-items: center;

  margin-bottom: 40px;
}

.row article {
  flex-grow: 1;
}

footer {
  font-weight: 600;
  font-size: 13px;

  color: #a9a9a9;
}
</style>
