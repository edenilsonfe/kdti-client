<template>
  <div class="content">
    <h2>Cadastrar vaga</h2>
    <form>
      <fieldset>
        <label for="title">Título</label>
        <input name="title" type="text" />
        <label>Descrição</label>
        <div>
          <div
            class="quill-editor"
            :content="description"
            @change="onEditorChange($event)"
            v-quill:myQuillEditor="editorOption"
          ></div>
        </div>
        <label>Tipo</label>
        <select>
          <option>PJ</option>
          <option>CLT</option>
          <option>Estágio</option>
        </select>
        <label>Faixa salarial</label>
        <label>Máximo</label>
        <select>
          <option>Não informar</option>
        </select>
        <label>Mínimo</label>
        <select>
          <option>Não informar</option>
        </select>
      </fieldset>
      <button @click.prevent="postLogin">Salvar</button>
    </form>
  </div>
</template>

<script>
export default {
  layout: 'admin',
  data() {
    return {
      description: '',
      editorOption: {
        // some quill options
        modules: {
          toolbar: [
            ['bold', 'italic', 'underline', 'strike'],
            ['blockquote'],
            [{ list: 'ordered' }, { list: 'bullet' }],
          ],
        },
      },
    }
  },
}
</script>
